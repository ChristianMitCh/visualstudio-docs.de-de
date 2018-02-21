---
title: Konvertieren einer Get-Methode in eine Eigenschaft und Konvertieren einer Eigenschaft in eine Get-Methode in Visual Studio | Microsoft-Dokumentation
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: 3d0a532e2e3e5bb8afa4a3c3dc9720134a1b7e8b
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method-refactorings"></a>Konvertieren einer Get-Methode in eine Eigenschaft und Konvertieren einer Eigenschaft in ein Refactoring einer Get-Methode

Diese Refactorings gelten für:

- C#

## <a name="convert-get-method-to-property"></a>Konvertieren einer Get-Methode in eine Eigenschaft

**Beschreibung**: Hiermit können Sie eine Get-Methode in eine Eigenschaft (und optional die Set-Methode) konvertieren und umgekehrt.

**Hintergrund**: Sie verwenden eine Get-Methode, die keinerlei Logik aufweist.

### <a name="how-to"></a>Vorgehensweise

1. Platzieren Sie den Cursor in den Namen der Get-Methode.

1. Führen Sie dann eine der folgenden Aktionen aus:

   - **Tastatur**
     - Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und wählen Sie im Popupvorschaufenster **Replace method with property** (Methode durch Eigenschaft ersetzen) aus.
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
     - Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und wählen Sie im Popupvorschaufenster **Eigenschaft durch Methoden ersetzen** aus.
   - **Maus**
     - Klicken Sie mit der rechten Maustaste auf den Code, und wählen Sie das Menü **Schnellaktionen und Refactorings** sowie im Popupvorschaufenster **Eigenschaft durch Methoden ersetzen** aus.

1. Wenn Sie mit der Änderung in der Codevorschau zufrieden sind, drücken Sie die **EINGABETASTE**. Die Änderungen werden angewendet. Klicken Sie alternativ im Menü auf die Schaltfläche zum Korrigieren.

## <a name="see-also"></a>Siehe auch

[Refactoring](../refactoring-in-visual-studio.md)  
[Vorschau der Änderungen](../../ide/preview-changes.md)