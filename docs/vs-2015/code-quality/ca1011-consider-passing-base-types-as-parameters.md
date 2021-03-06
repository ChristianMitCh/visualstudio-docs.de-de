---
title: 'CA1011: übergeben von Basis Typen als Parameter | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3968d81e8ee18b4b0a56bed50f7aa1f121e1c074
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663240"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Basistypen als Parameter übergeben
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Kategorie|Microsoft. Design|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Eine Methoden Deklaration enthält einen formalen Parameter, der ein abgeleiteter Typ ist, und die Methode ruft nur Member des Basistyps des Parameters auf.

## <a name="rule-description"></a>Regelbeschreibung
 Wenn in einer Methodendeklaration ein Basistyp als Parameter angegeben wird, kann jeder Typ, der von diesem Basistyp abgeleitet ist, als entsprechendes Argument an die Methode übergeben werden. Wenn das-Argument innerhalb des Methoden Texts verwendet wird, hängt die spezifische Methode, die ausgeführt wird, vom Typ des Arguments ab. Wenn die zusätzliche Funktionalität, die vom abgeleiteten Typ bereitgestellt wird, nicht erforderlich ist, ermöglicht die Verwendung des Basistyps eine breitere Verwendung der-Methode.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, ändern Sie den Typ des Parameters in seinen Basistyp.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Es ist sicher, eine Warnung aus dieser Regel zu unterdrücken.

- Wenn die Methode die spezifische Funktionalität erfordert, die vom abgeleiteten Typ bereitgestellt wird

   \- oder -

- , um zu erzwingen, dass nur der abgeleitete Typ oder ein stärker abgeleiteter Typ an die-Methode weitergegeben wird.

  In diesen Fällen ist der Code aufgrund der starken Typüberprüfung, die vom Compiler und der Laufzeit bereitgestellt wird, robuster.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt eine Methode, `ManipulateFileStream`, die nur mit einem <xref:System.IO.FileStream>-Objekt verwendet werden kann, das gegen diese Regel verstößt. Eine zweite Methode, `ManipulateAnyStream`, erfüllt die Regel, indem der <xref:System.IO.FileStream> Parameter durch eine <xref:System.IO.Stream> ersetzt wird.

 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cpp/FxCop.Design.ConsiderPassingBaseTypes.cpp#1)]
 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cs/FxCop.Design.ConsiderPassingBaseTypes.cs#1)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/vb/FxCop.Design.ConsiderPassingBaseTypes.vb#1)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA1059: Member sollten bestimmte konkrete Typen nicht verfügbar machen](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)
