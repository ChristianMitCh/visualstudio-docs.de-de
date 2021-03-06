---
title: Vereinfachen der Zeichenfolgeninterpolation
ms.date: 03/10/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a8b0fd53164cb98921b111d49fa04a76c9d0d8a8
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79094303"
---
# <a name="simplify-string-interpolation-refactoring"></a>Refactoring zur Vereinfachung von Zeichenfolgeninterpolationen

Dieses Refactoring gilt für:

- C#

- Visual Basic

**Beschreibung:** Ermöglicht Ihnen das Vereinfachen einer [Zeichenfolgeninterpolation](https://docs.microsoft.com/dotnet/csharp/tutorials/string-interpolation)

**Hintergrund:** Sie verfügen über eine Zeichenfolgeninterpolation, die vereinfacht werden kann.

**Vorteile**: Das Vereinfachen einer Zeichenfolgeninterpolation kann zu einer übersichtlicheren und präziseren Syntax führen. Dieses Refactoringtool führt die Aufgaben automatisch aus, anstatt dass Sie sie manuell ausführen müssen.

## <a name="how-to"></a>Vorgehensweise

1. Zeigen Sie mit dem Cursor auf die Zeichenfolgeninterpolation:

2. Drücken Sie an einer beliebigen Stelle in einer Zeile **STRG**+ **.** , um das Menü **Schnellaktionen und Refactorings** aufzurufen.

3. Klicken Sie auf **Interpolation vereinfachen**.

    ![Vereinfachen der Zeichenfolgeninterpolation](media/simplify-string-interpolation.png)

## <a name="see-also"></a>Siehe auch

- [Refactoring](../refactoring-in-visual-studio.md)