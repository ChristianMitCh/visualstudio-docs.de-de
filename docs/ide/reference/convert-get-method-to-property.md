---
title: Konvertieren einer Get-Methode in eine Eigenschaft und Konvertieren einer Eigenschaft in eine Get-Methode
ms.date: 03/10/2020
ms.topic: reference
ms.devlang: csharp
author: mikadumont
ms.author: midumont
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: af507a8b437a20e3d4f4807d582abab6f9a12e27
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79094205"
---
# <a name="convert-get-method-to-property--convert-property-to-get-method-refactorings"></a>Konvertieren einer Get-Methode in eine Eigenschaft und Konvertieren einer Eigenschaft in ein Refactoring einer Get-Methode

Diese Refactorings gelten für:

- C#

- Visual Basic

## <a name="convert-get-method-to-property"></a>Konvertieren einer Get-Methode in eine Eigenschaft

**Beschreibung**: Hiermit können Sie eine Get-Methode in eine Eigenschaft (und optional die Set-Methode) konvertieren.

**Hintergrund**: Sie verwenden eine Get-Methode, die keinerlei Logik aufweist.

### <a name="how-to"></a>Vorgehensweise

1. Platzieren Sie den Cursor in den Namen der Get-Methode.

1. Führen Sie dann eine der folgenden Aktionen aus:

   - **Tastatur**
      - Drücken Sie an einer beliebigen Stelle in einer Zeile **STRG**+ **.** , um das Menü **Schnellaktionen und Refactorings** aufzurufen, und wählen Sie im Popupvorschaufenster **Replace method with property** (Methode durch Eigenschaft ersetzen) aus.
   - **Maus**
      - Klicken Sie mit der rechten Maustaste auf den Code, und klicken Sie auf das Menü **Schnellaktionen und Refactorings** sowie im Popupvorschaufenster **Replace method with property** (Methode durch Eigenschaft ersetzen) aus.

1. (Optional) Wenn Sie eine Set-Methode verwenden, können Sie diese auch konvertieren, indem sie die **Get-Methode und die Set-Methode durch die Eigenschaft ersetzen**.

1. Wenn Sie mit der Änderung in der Codevorschau zufrieden sind, drücken Sie die **EINGABETASTE**. Die Änderungen werden angewendet. Klicken Sie alternativ im Menü auf die Schaltfläche zum Korrigieren.

Beispiel:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>Konvertieren einer Eigenschaft in eine Get-Methode

**Beschreibung**: Hiermit können Sie eine Eigenschaft in eine Get-Methode konvertieren.

**Hintergrund**: Sie verwenden eine Eigenschaft, die mehr als das sofortige Festlegen und Abrufen eines Werts erfordert.

### <a name="how-to"></a>Vorgehensweise

1. Platzieren Sie den Cursor in den Namen der Get-Methode.

1. Führen Sie dann eine der folgenden Aktionen aus:

   - **Tastatur**
      - Drücken Sie an einer beliebigen Stelle in einer Zeile **STRG**+ **.** , um das Menü **Schnellaktionen und Refactorings** aufzurufen, und wählen Sie im Popupvorschaufenster **Eigenschaft durch Methoden ersetzen** aus.
   - **Maus**
      - Klicken Sie mit der rechten Maustaste auf den Code, und wählen Sie das Menü **Schnellaktionen und Refactorings** sowie im Popupvorschaufenster **Eigenschaft durch Methoden ersetzen** aus.

1. Wenn Sie mit der Änderung in der Codevorschau zufrieden sind, drücken Sie die **EINGABETASTE**. Die Änderungen werden angewendet. Klicken Sie alternativ im Menü auf die Schaltfläche zum Korrigieren.

## <a name="see-also"></a>Weitere Informationen

- [Refactoring](../refactoring-in-visual-studio.md)
- [Vorschau der Änderungen](../../ide/preview-changes.md)
