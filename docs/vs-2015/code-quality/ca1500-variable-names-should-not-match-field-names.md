---
title: 'CA1500: Variablennamen sollten nicht mit Feldnamen in Einklang stehen | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9565bc1ae3166c0475e8af7f0fde381497309b01
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547913"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Variablennamen sollten nicht mit Feldnamen übereinstimmen.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Dokumentation zu Visual Studio finden Sie unter [CA1500: Variablennamen sollten nicht mit Feldnamen](/visualstudio/code-quality/ca1500-variable-names-should-not-match-field-names)verglichen werden.

|Element|Wert|
|-|-|
|TypName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|Category|Microsoft. Wartbarkeit|
|Unterbrechende Änderung|Wenn für einen Parameter ausgelöst wird, der denselben Namen wie ein Feld hat:<br /><br /> -Nicht unterbrechend: Wenn sowohl das Feld als auch die Methode, die den Parameter deklariert, nicht außerhalb der Assembly angezeigt werden können, unabhängig von der Änderung, die Sie vornehmen.<br />-Unterbrechung: Wenn Sie den Namen des Felds ändern und außerhalb der Assembly angezeigt werden können.<br />-Unterbrechung: Wenn Sie den Namen des Parameters und die Methode ändern, die ihn deklariert, kann diese außerhalb der Assembly angezeigt werden.<br /><br /> Wenn eine lokale Variable mit demselben Namen wie ein Feld ausgelöst wird, wird Sie ausgelöst:<br /><br /> -Nicht unterbrechend: Wenn das Feld außerhalb der Assembly nicht sichtbar ist, unabhängig von der Änderung, die Sie vornehmen.<br />-Nicht unterbrechend: Wenn Sie den Namen der lokalen Variablen ändern und den Namen des Felds nicht ändern.<br />-Unterbrechung: Wenn Sie den Namen des Felds ändern, kann es außerhalb der Assembly angezeigt werden.|

## <a name="cause"></a>Ursache
 Eine Instanzmethode deklariert einen Parameter oder eine lokale Variable, deren Name mit einem Instanzfeld des deklarierenden Typs übereinstimmt. Um lokale Variablen abzufangen, die gegen die Regel verstoßen, muss die getestete Assembly mithilfe von Debuginformationen erstellt werden, und die zugehörige Programm Datenbankdatei (. pdb) muss verfügbar sein.

## <a name="rule-description"></a>Beschreibung der Regel
 Wenn der Name eines Instanzfelds mit einem Parameter oder einem lokalen Variablennamen übereinstimmt, erfolgt der Zugriff auf das Instanzfeld mithilfe des `this` `Me` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Schlüssel Worts (in) im Methoden Text. Wenn Sie Code verwalten, ist es einfach, diesen Unterschied zu vergessen und davon auszugehen, dass der Parameter/die lokale Variable auf das Instanzfeld verweist, was zu Fehlern führt. Dies gilt insbesondere für lange Methoden Texte.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, benennen Sie entweder den Parameter/die Variable oder das Feld um.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt zwei Verstöße gegen die Regel.

 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/cs/FxCop.Maintainability.VarMatchesField.cs#1)]
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/vb/FxCop.Maintainability.VarMatchesField.vb#1)]
