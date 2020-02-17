---
title: Einführung in SAL
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
author: corob-msft
ms.author: corob
manager: markl
ms.workload:
- multiple
ms.openlocfilehash: e2cb2cb263344e45d83a2b143f6c56f138f77bf5
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "77271821"
---
# <a name="understanding-sal"></a>Einführung in SAL

Die Microsoft-Quell Code Anmerkung (Source-Code Anmerkung Language, SAL) stellt eine Reihe von Anmerkungen bereit, mit denen Sie beschreiben können, wie eine Funktion Ihre Parameter verwendet, die Annahmen, die Sie für Sie vornimmt, und die Garantien, die Sie nach dem Abschluss trifft. Die Anmerkungen werden in der Header Datei `<sal.h>`definiert. Die Visual Studio-Code C++ Analyse für verwendet SAL-Anmerkungen, um die Analyse von Funktionen zu ändern. Weitere Informationen zu SAL 2,0 für die Windows-Treiberentwicklung finden Sie unter [SAL 2,0-Anmerkungen für Windows-Treiber](/windows-hardware/drivers/devtest/sal-2-annotations-for-windows-drivers).

Nativ, C und C++ bieten nur eingeschränkte Möglichkeiten für Entwickler, Absicht und Invarianz konsistent auszudrücken. Mithilfe von Sal-Anmerkungen können Sie Ihre Funktionen ausführlicher beschreiben, damit Entwickler, die Sie nutzen, besser verstehen können, wie Sie verwendet werden.

## <a name="what-is-sal-and-why-should-you-use-it"></a>Was ist SAL und warum sollten Sie es verwenden?

Einfach ausgedrückt ist SAL eine kostengünstige Möglichkeit, um dem Compiler das Überprüfen des Codes für Sie zu ermöglichen.

### <a name="sal-makes-code-more-valuable"></a>SAL steigert den Wert des Codes

SAL kann Ihnen helfen, den Code Entwurf verständlicher zu machen, sowohl für Benutzer als auch für Code Analysetools. Sehen Sie sich dieses Beispiel an, das die C-Lauf Zeitfunktion `memcpy`zeigt

```cpp

void * memcpy(
   void *dest,
   const void *src,
   size_t count
);
```

Können Sie wissen, was diese Funktion macht? Wenn eine Funktion implementiert oder aufgerufen wird, müssen bestimmte Eigenschaften beibehalten werden, um die Richtigkeit des Programms sicherzustellen. Wenn Sie sich einfach eine Deklaration ansehen, z. b. die im Beispiel, wissen Sie nicht, was Sie sind. Ohne SAL-Anmerkungen müssten Sie sich auf Dokumentation oder Code Kommentare verlassen. In der MSDN-Dokumentation für `memcpy` wird Folgendes angegeben:

> "Kopiert Anzahl Bytes von src in dest. Wenn sich Quelle und Ziel überlappen, ist das Verhalten von memcpy nicht definiert. Verwenden Sie memmove zum Verarbeiten überlappenden Bereiche.
> **Sicherheitshinweis:** Stellen Sie sicher, dass der Ziel Puffer dieselbe Größe oder größer als der Quell Puffer ist. Weitere Informationen finden Sie unter Vermeiden von Pufferüberläufen.

Die Dokumentation enthält einige Informationen, die vorschlagen, dass Ihr Code bestimmte Eigenschaften beibehalten muss, um die Richtigkeit des Programms sicherzustellen:

- `memcpy` kopiert die `count` von Bytes aus dem Quell Puffer in den Ziel Puffer.

- Der Ziel Puffer muss mindestens so groß sein wie der Quell Puffer.

Der Compiler kann die Dokumentation oder informelle Kommentare jedoch nicht lesen. Es ist nicht bekannt, dass zwischen den beiden Puffern und `count`eine Beziehung besteht, und es ist auch nicht möglich, eine Beziehung zu erraten. SAL könnte mehr Klarheit über die Eigenschaften und die Implementierung der Funktion bieten, wie hier gezeigt:

```cpp

void * memcpy(
   _Out_writes_bytes_all_(count) void *dest,
   _In_reads_bytes_(count) const void *src,
   size_t count
);
```

Beachten Sie, dass diese Anmerkungen den Informationen in der MSDN-Dokumentation ähneln, aber präziser sind und einem semantischen Muster folgen. Wenn Sie diesen Code lesen, können Sie sich schnell mit den Eigenschaften dieser Funktion vertraut machen und verhindern, dass Sicherheitsprobleme mit Pufferüberlauf vermieden werden. Noch besser ist, dass die von Sal bereitgestellten Semantik Muster die Effizienz und Effektivität automatisierter Code Analysetools bei der frühen Ermittlung potenzieller Fehler verbessern können. Stellen Sie sich vor, dass jemand diese fehlerhafte Implementierung von `wmemcpy`schreibt:

```cpp

wchar_t * wmemcpy(
   _Out_writes_all_(count) wchar_t *dest,
   _In_reads_(count) const wchar_t *src,
   size_t count)
{
   size_t i;
   for (i = 0; i <= count; i++) { // BUG: off-by-one error
      dest[i] = src[i];
   }
   return dest;
}
```

Diese Implementierung enthält einen allgemeinen Fehler, der von einem Fehler auftritt. Glücklicherweise enthielt der Code Autor die Anmerkung der SAL-Puffergröße – ein Code Analysetool könnte den Fehler durch die Analyse dieser Funktion erfassen.

### <a name="sal-basics"></a>Grundlagen von SAL
SAL definiert vier grundlegende Arten von Parametern, die nach Verwendungs Mustern kategorisiert werden.

|Kategorie|Parameter Anmerkung|Beschreibung|
|--------------|--------------------------|-----------------|
|**Eingabe in aufgerufene Funktion**|`_In_`|Daten werden an die aufgerufene Funktion weitergegeben und als schreibgeschützt behandelt.|
|**Eingabe in aufgerufene Funktion und Ausgabe an Aufrufer**|`_Inout_`|Verwendbare Daten werden an die Funktion geleitet und potenziell geändert.|
|**Ausgabe an Aufrufer**|`_Out_`|Der Aufrufer stellt nur Platz für die aufgerufene Funktion bereit, in die geschrieben wird. Die aufgerufene Funktion schreibt Daten in diesen Bereich.|
|**Ausgabe von Zeiger auf Aufrufer**|`_Outptr_`|Like **Ausgabe an**Aufrufer. Der von der aufgerufenen Funktion zurückgegebene Wert ist ein-Zeiger.|

Diese vier grundlegenden Anmerkungen können auf verschiedene Weise deutlicher gemacht werden. Standardmäßig wird davon ausgegangen, dass mit Anmerkungen versehene Zeiger Parameter erforderlich sind – Sie dürfen nicht NULL sein, damit die Funktion erfolgreich ausgeführt werden kann. Die am häufigsten verwendete Variation der grundlegenden Anmerkungen gibt an, dass ein Zeiger Parameter optional ist – wenn er NULL ist, kann die Funktion weiterhin erfolgreich ausgeführt werden.

In der folgenden Tabelle wird gezeigt, wie zwischen erforderlichen und optionalen Parametern unterschieden wird:

||Parameter sind erforderlich.|Parameter sind optional.|
|-|-----------------------------|-----------------------------|
|**Eingabe in aufgerufene Funktion**|`_In_`|`_In_opt_`|
|**Eingabe in aufgerufene Funktion und Ausgabe an Aufrufer**|`_Inout_`|`_Inout_opt_`|
|**Ausgabe an Aufrufer**|`_Out_`|`_Out_opt_`|
|**Ausgabe von Zeiger auf Aufrufer**|`_Outptr_`|`_Outptr_opt_`|

Diese Anmerkungen helfen dabei, mögliche nicht initialisierte Werte zu identifizieren, und ungültige NULL-Zeiger werden auf formale und exakte Weise verwendet. Das übergeben von NULL an einen erforderlichen Parameter kann zu einem Absturz führen, oder es kann dazu führen, dass der Fehlercode "failed" zurückgegeben wird. In jedem Fall kann die Funktion nicht erfolgreich ausgeführt werden.

## <a name="sal-examples"></a>Beispiele zu SAL
Dieser Abschnitt enthält Codebeispiele für die grundlegenden SAL-Anmerkungen.

### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Suchen von Fehlern mit den Visual Studio-Codeanalysetools
In den Beispielen wird das Visual Studio Code Analysetool in Verbindung mit SAL-Anmerkungen verwendet, um Code Fehler zu finden. Gehen Sie dazu wie folgt vor.

#### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>So verwenden Sie Visual Studio-Codeanalysetools und SAL

1. Öffnen Sie in Visual Studio ein C++ Projekt, das SAL-Anmerkungen enthält.

2. Wählen Sie in der Menüleiste die Option **Erstellen**und dann **Code Analyse für Projekt Mappe ausführen aus**.

     Beachten Sie die \_in\_ Beispiel in diesem Abschnitt. Wenn Sie eine Code Analyse ausführen, wird diese Warnung angezeigt:

    > **C6387 Ungültiger Parameter Wert** "Pint" kann "0" sein: Dies entspricht nicht der Spezifikation für die Funktion "incallee".

### <a name="example-the-_in_-annotation"></a>Beispiel: der \_in\_ Anmerkung

Die `_In_` Anmerkung zeigt Folgendes an:

- Der-Parameter muss gültig sein und wird nicht geändert.

- Die Funktion liest nur aus dem Puffer mit einem einzelnen Element.

- Der Aufrufer muss den Puffer bereitstellen und ihn initialisieren.

- `_In_` gibt "schreibgeschützt" an. Ein häufiger Fehler ist das Anwenden von `_In_` auf einen Parameter, der stattdessen die `_Inout_` Anmerkung enthalten soll.

- `_In_` ist zulässig, wird aber vom Analyzer für nicht-Zeiger-skalare ignoriert.

```cpp
void InCallee(_In_ int *pInt)
{
   int i = *pInt;
}

void GoodInCaller()
{
   int *pInt = new int;
   *pInt = 5;

   InCallee(pInt);
   delete pInt;
}

void BadInCaller()
{
   int *pInt = NULL;
   InCallee(pInt); // pInt should not be NULL
}
```

Wenn Sie in diesem Beispiel Visual Studio Code Analyse verwenden, wird überprüft, ob die Aufrufer einen nicht-NULL-Zeiger auf einen initialisierten Puffer für `pInt`übergeben. In diesem Fall kann `pInt` Zeiger nicht NULL sein.

### <a name="example-the-_in_opt_-annotation"></a>Beispiel: der \_in\_opt\_-Anmerkung

`_In_opt_` ist identisch mit `_In_`, mit dem Unterschied, dass der Eingabeparameter NULL sein darf und die Funktion daher diese überprüfen sollte.

```cpp

void GoodInOptCallee(_In_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
   }
}

void BadInOptCallee(_In_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
}

void InOptCaller()
{
   int *pInt = NULL;
   GoodInOptCallee(pInt);
   BadInOptCallee(pInt);
}
```

Visual Studio Code Analyse überprüft, ob die Funktion auf NULL überprüft, bevor Sie auf den Puffer zugreift.

### <a name="example-the-_out_-annotation"></a>Beispiel: die \_out-\_ Anmerkung

`_Out_` unterstützt ein häufiges Szenario, in dem ein nicht-NULL-Zeiger, der auf einen Element Puffer zeigt, übermittelt wird und die Funktion das Element initialisiert. Der Aufrufer muss den Puffer vor dem Aufruf nicht initialisieren. die aufgerufene Funktion verspricht, Sie zu initialisieren, bevor Sie zurückkehrt.

```cpp
void GoodOutCallee(_Out_ int *pInt)
{
   *pInt = 5;
}

void BadOutCallee(_Out_ int *pInt)
{
   // Did not initialize pInt buffer before returning!
}

void OutCaller()
{
   int *pInt = new int;
   GoodOutCallee(pInt);
   BadOutCallee(pInt);
   delete pInt;
}
```

Visual Studio Code Analyse Tool überprüft, ob der Aufrufer einen nicht-NULL-Zeiger an einen Puffer für `pInt` übergibt und dass der Puffer von der Funktion initialisiert wird, bevor er zurückgegeben wird.

### <a name="example-the-_out_opt_-annotation"></a>Beispiel: das \_out\_opt\_ Anmerkung

`_Out_opt_` ist mit `_Out_`identisch, mit dem Unterschied, dass der-Parameter NULL sein darf und daher die-Funktion diese überprüfen sollte.

```cpp
void GoodOutOptCallee(_Out_opt_ int *pInt)
{
   if (pInt != NULL) {
      *pInt = 5;
   }
}

void BadOutOptCallee(_Out_opt_ int *pInt)
{
   *pInt = 5; // Dereferencing NULL pointer 'pInt'
}

void OutOptCaller()
{
   int *pInt = NULL;
   GoodOutOptCallee(pInt);
   BadOutOptCallee(pInt);
}
```

Visual Studio Code Analyse überprüft, ob diese Funktion nach NULL sucht, bevor `pInt` dereferenziert wird, und wenn `pInt` nicht NULL ist, wird der Puffer von der Funktion initialisiert, bevor er zurückgegeben wird.

### <a name="example-the-_inout_-annotation"></a>Beispiel: die \_INOUT-\_ Anmerkung

`_Inout_` wird verwendet, um einen Zeiger Parameter zu kommentieren, der von der Funktion geändert werden kann. Der Zeiger muss vor dem-Befehl auf gültige initialisierte Daten verweisen, und auch wenn er sich ändert, muss er bei der Rückgabe weiterhin über einen gültigen Wert verfügen. Die-Anmerkung gibt an, dass die Funktion aus dem Puffer mit einem einzelnen Element frei lesen und in diesen schreiben kann. Der Aufrufer muss den Puffer bereitstellen und ihn initialisieren.

> [!NOTE]
> Wie `_Out_`müssen `_Inout_` auf einen änderbaren Wert angewendet werden.

```cpp
void InOutCallee(_Inout_ int *pInt)
{
   int i = *pInt;
   *pInt = 6;
}

void InOutCaller()
{
   int *pInt = new int;
   *pInt = 5;
   InOutCallee(pInt);
   delete pInt;
}

void BadInOutCaller()
{
   int *pInt = NULL;
   InOutCallee(pInt); // 'pInt' should not be NULL
}
```

Visual Studio Code Analyse überprüft, ob Aufrufer einen nicht-NULL-Zeiger an einen initialisierten Puffer für `pInt`übergeben, und dass `pInt` vor der Rückgabe noch nicht NULL ist und der Puffer initialisiert wird.

### <a name="example-the-_inout_opt_-annotation"></a>Beispiel: der \_INOUT-\_opt\_ Anmerkung

`_Inout_opt_` ist identisch mit `_Inout_`, mit dem Unterschied, dass der Eingabeparameter NULL sein darf und die Funktion daher diese überprüfen sollte.

```cpp
void GoodInOutOptCallee(_Inout_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
      *pInt = 6;
   }
}

void BadInOutOptCallee(_Inout_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
   *pInt = 6;
}

void InOutOptCaller()
{
   int *pInt = NULL;
   GoodInOutOptCallee(pInt);
   BadInOutOptCallee(pInt);
}
```

Visual Studio Code Analyse überprüft, ob diese Funktion auf NULL überprüft, bevor Sie auf den Puffer zugreift, und wenn `pInt` nicht NULL ist, wird der Puffer von der Funktion initialisiert, bevor er zurückgegeben wird.

### <a name="example-the-_outptr_-annotation"></a>Beispiel: die \_outptr-\_ Anmerkung

`_Outptr_` wird verwendet, um einen Parameter zu kommentieren, der einen Zeiger zurückgeben soll.  Der Parameter selbst darf nicht NULL sein, und die aufgerufene Funktion gibt einen nicht-NULL-Zeiger darin zurück, und der Zeiger verweist auf initialisierte Daten.

```cpp
void GoodOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 5;

   *pInt = pInt2;
}

void BadOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   // Did not initialize pInt buffer before returning!
   *pInt = pInt2;
}

void OutPtrCaller()
{
   int *pInt = NULL;
   GoodOutPtrCallee(&pInt);
   BadOutPtrCallee(&pInt);
}
```

Visual Studio Code Analyse überprüft, ob der Aufrufer einen nicht-NULL-Zeiger für `*pInt`übergibt, und dass der Puffer von der Funktion initialisiert wird, bevor er zurückgegeben wird.

### <a name="example-the-_outptr_opt_-annotation"></a>Beispiel: der \_outptr\_opt\_ Anmerkung

`_Outptr_opt_` ist identisch mit `_Outptr_`, mit dem Unterschied, dass der Parameter optional ist – der Aufrufer kann einen NULL-Zeiger für den-Parameter übergeben.

```cpp
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;

   if(pInt != NULL) {
      *pInt = pInt2;
   }
}

void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'
}

void OutPtrOptCaller()
{
   int **ppInt = NULL;
   GoodOutPtrOptCallee(ppInt);
   BadOutPtrOptCallee(ppInt);
}
```

Visual Studio Code Analyse überprüft, ob diese Funktion nach NULL sucht, bevor `*pInt` dereferenziert wird, und dass der Puffer von der Funktion initialisiert wird, bevor er zurückgegeben wird.

### <a name="example-the-_success_-annotation-in-combination-with-_out_"></a>Beispiel: der \_Erfolg\_ Anmerkung in Kombination mit \_out\_

Anmerkungen können auf die meisten-Objekte angewendet werden.  Vor allem können Sie eine ganze Funktion mit Anmerkungen versehen.  Eine der offensichtlichsten Merkmale einer Funktion besteht darin, dass Sie erfolgreich ausgeführt werden kann oder fehlschlägt. Aber wie bei der Zuordnung zwischen einem Puffer und seiner Größe kann CC++ /die Funktion Erfolg oder Fehler nicht ausdrücken. Mit der `_Success_`-Anmerkung können Sie angeben, wie erfolgreich eine Funktion aussieht.  Der Parameter für die `_Success_` Anmerkung ist nur ein Ausdruck, der angibt, dass die Funktion erfolgreich war, wenn Sie true ist. Der Ausdruck kann alles sein, was der Anmerkung-Parser behandeln kann. Die Auswirkungen der Anmerkungen, die nach der Rückgabe der Funktion auftreten, sind nur anwendbar, wenn die Funktion erfolgreich ausgeführt wird. Dieses Beispiel zeigt, wie `_Success_` mit `_Out_` interagiert, um das richtige zu tun. Sie können das Schlüsselwort `return` verwenden, um den Rückgabewert darzustellen.

```cpp
_Success_(return != false) // Can also be stated as _Success_(return)
bool GetValue(_Out_ int *pInt, bool flag)
{
   if(flag) {
      *pInt = 5;
      return true;
   } else {
      return false;
   }
}
```

Die `_Out_`-Anmerkung bewirkt, dass Visual Studio Code Analyse überprüft, ob der Aufrufer einen nicht-NULL-Zeiger an einen Puffer für `pInt`übergibt, und dass der Puffer von der Funktion initialisiert wird, bevor er zurückgegeben wird.

## <a name="sal-best-practice"></a>Bewährte Methoden für SAL

### <a name="adding-annotations-to-existing-code"></a>Hinzufügen von Anmerkungen zu vorhandenem Code

SAL ist eine leistungsstarke Technologie, mit der Sie die Sicherheit und Zuverlässigkeit Ihres Codes verbessern können. Nachdem Sie SAL gelernt haben, können Sie die neue Qualifikation auf Ihre tägliche Arbeit anwenden. In neuem Code können Sie SAL-basierte Spezifikationen für den gesamten Entwurf verwenden; in älteren Code können Sie Anmerkungen inkrementell hinzufügen und so die Vorteile jedes Mal erhöhen, wenn Sie ein Update durchsetzen.

Öffentliche Microsoft-Header wurden bereits mit Anmerkungen versehen. Daher wird empfohlen, dass Sie in Ihren Projekten zuerst Endknoten Funktionen und-Funktionen kommentieren, die Win32-APIs aufzurufen, um die meisten Vorteile zu erzielen.

### <a name="when-do-i-annotate"></a>Wann sollte ich Anmerkungen einfügen?

Im folgenden finden Sie einige Richtlinien:

- Kommentieren Sie alle Zeiger Parameter.

- Kommentieren Sie Wertebereichs Anmerkungen, damit die Code Analyse die Puffer-und Zeiger Sicherheit sicherstellen kann.

- Kommentieren von Sperr Regeln und Sperren von Nebeneffekten. Weitere Informationen finden Sie unter [kommentieren von Sperr Verhalten](../code-quality/annotating-locking-behavior.md).

- Kommentieren Sie Treiber Eigenschaften und andere domänenspezifische Eigenschaften.

Oder Sie können alle Parameter mit Anmerkungen versehen, um die Absicht zu vereinfachen und zu überprüfen, ob Anmerkungen durchgeführt wurden.

## <a name="related-resources"></a>Zugehörige Ressourcen

[Blog des Code Analyseteams](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>Siehe auch

- [Verwenden von SAL-Anmerkungen zum Reduzieren von C/C++-Codefehlern](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Hinzufügen einer Anmerkung zu Funktionsparametern und Rückgabewerten](../code-quality/annotating-function-parameters-and-return-values.md)
- [Hinzufügen einer Anmerkung zum Funktionsverhalten](../code-quality/annotating-function-behavior.md)
- [Hinzufügen einer Anmerkung zu Strukturen und Klassen](../code-quality/annotating-structs-and-classes.md)
- [Hinzufügen einer Anmerkung zum Sperrverhalten](../code-quality/annotating-locking-behavior.md)
- [Angeben, wann und wo eine Anmerkung gültig ist](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Empfohlene Vorgehensweisen und Beispiele](../code-quality/best-practices-and-examples-sal.md)
