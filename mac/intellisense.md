---
title: IntelliSense
description: Informationen zur Verwendung von IntelliSense in Visual Studio für Mac
author: cobey
ms.author: cobey
ms.date: 08/16/2019
ms.openlocfilehash: 07ef1d6292e4ac88ca616d0f35e3fd831cacc649
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2020
ms.locfileid: "75405809"
---
# <a name="intellisense"></a>IntelliSense

IntelliSense bietet verschiedene Funktionen, die das Schreiben und Bearbeiten von Code verbessern. Die IntelliSense-Engine stellt beispielsweise zusätzlich zur Codevervollständigung auch Memberlisten, Parameterinformationen und QuickInfos bereit.

In Visual Studio für Mac wird IntelliSense vom Kern-Editor-Dienst bereitgestellt und in vielen Sprachen unterstützt (z. B. C#, XAML, F#, JavaScript usw.). Visual Studio für Mac bietet auch erweiterte IntelliSense-Funktionen wie die das Anzeigen von Vervollständigungen aus Bibliotheken, die noch nicht in das Projekt importiert wurden.

## <a name="code-completion"></a>Codevervollständigung

Beim Eingeben von Code in einer unterstützten Datei (z. B. C#-Codedatei) werden in einer Vervollständigungsliste gültige Vervollständigungen für die gerade eingegebene Zeichenfolge angezeigt und beim Eingeben aktualisiert. Wenn Sie den Text löschen, wird die Liste außerdem noch mal automatisch aktualisiert, um eine größere Anzahl von Möglichkeiten zum Vervollständigen der angegebenen Zeichenfolge einzuschließen. 

Das Vervollständigungsfenster bietet auch Unterstützung für das Filtern der enthaltenen Vervollständigungen nach Typ. Es ist beispielsweise möglich, die Member der Liste einzuschränken, sodass sie nur Typen wie Klassen oder Delegate repräsentieren. Dieser Filtervorgang kann entweder durch das Klicken auf ein bestimmtes Symbol, das den zu filternden Typ darstellt, oder mithilfe von Tastenkombinationen aktiviert werden, die einem bestimmten Typ entsprechen. Die Symbole, die sich unten im Vervollständigungsfenster befinden, lauten wie folgt:

| Symbol                         | Name          | Schlüsselwort    | Hotkey |
| -----------------------------|---------------| -----------|--------|
| ![Symbol „Klassen“](media/classes-icon.png)  | class         | `class`    |  ⌥C
| ![Symbol "Konstante"](media/constant-icon.png) | Konstante      | `const`    |  ⌥O
| ![Symbol „Delegieren“](media/delegate-icon.png) | -Delegat      | `delegate` |  ⌥D
| ![Symbol „Enumeration“](media/enums-icon.png)    | enum          | `enum`     |  ⌥E
| ![Symbol „Ereignis“](media/event-icon.png)    | Ereignis         |            |  ⌥V
| ![Symbol "Feld"](media/fields-icon.png)   | Feld         |            |  ⌥F
| ![Symbol „Schnittstelle“](media/interface-icon.png)| Schnittstelle     | `interface`|  ⌥I
| ![Symbol „Schlüsselwort“](media/keyword-icon.png)  | Schlüsselwort (keyword)       |            |  ⌥K
| ![Symbol „Methode“](media/method-icon.png)   | method        |            |  ⌥M
| ![Symbol „Namespace“](media/namespace-icon.png)| Namespace     | `namespace`|  ⌥N
| ![Symbol „Eigenschaften“](media/props-icon.png)    | property      |            |  ⌥P
| ![Symbol „Ausschnitt“](media/snippet-icon.png)  | Codeausschnitt       | `class`    |  ⌥S
| ![Symbol „Struktur“](media/struct-icon.png)   | structure     | `struct`   |  ⌥S

Wenn Sie auf eines der Symbole klicken oder die entsprechenden Hotkeys drücken, wird die Vervollständigungsliste auf die vom Filtersatz definierten Typen beschränkt.  

![Filtern nach Typen mit IntelliSense](media/intellisense-typefiltering.gif)

## <a name="parameter-window"></a>Parameterfenster

Ein weiteres Feature von IntelliSense ermöglicht es, bei Bedarf eine Parameterliste bereitzustellen. Die Parameterliste enthält Details zu den Methodensignaturen für den aufgerufenen Code. Durch Klicken auf die NACH-OBEN- und NACH-UNTEN-TASTEN innerhalb der Signatur können Sie jede der verfügbaren Parametersignaturen durchlaufen, um die am besten für Ihre Anforderungen geeignete Parametersignatur zu ermitteln. Zusätzlich zu den Details bezüglich der zulässigen Datentypen kann wie in der Zielmethode über XML-Kommentare definiert auch eine Beschreibung enthalten sein.

![Parameterliste](media/intellisense-parameter.png)

Wenn Sie die Parameter ausfüllen, wird der gerade bearbeitete Parameter fett formatiert, während die inaktiven Parameter die Standardgewichtung aufweisen. 


## <a name="triggering-completion-window-and-parameter-window"></a>Auslösen des Vervollständigungsfensters und des Parameterfensters

Das Vervollständigungsfenster wird bei Eingaben in der Quelldatei automatisch ausgelöst. Sie können das Vervollständigungsfenster jedoch auch mithilfe der Verknüpfung `control-space` auslösen. Diese Tastenkombination bewirkt, dass die Vervollständigungsliste an der aktuellen Position des Caretzeichens angezeigt wird. 

Sie können die Darstellung des Parameterfensters auch manuell auslösen, indem Sie `control-shift-space` eingeben. Wenn Sich das Caretzeichen an einer für die Parameterliste gültigen Position befindet, wird die Parameterliste in der Nähe der Position des Caretzeichens angezeigt.

## <a name="see-also"></a>Weitere Informationen

- [Schnellaktionen (Visual Studio unter Windows)](/visualstudio/ide/quick-actions)
- [Umgestalten von Code (Visual Studio unter Windows)](/visualstudio/ide/refactoring-in-visual-studio)
