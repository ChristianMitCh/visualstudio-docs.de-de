---
title: „Bearbeiten und fortfahren“ wird für F# nicht unterstützt | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [F#]
- Debugging [F#], Edit and Continue
ms.assetid: 40ec77bb-07e3-4b58-9254-ae015009441c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ceb0ca767b1ac6364e103925fb86ed639c3d321d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851163"
---
# <a name="edit-and-continue-not-supported-for-f"></a>Bearbeiten und Fortfahren wird für F# nicht unterstützt #
Beim Debuggen von F#-Code wird Bearbeiten und Fortfahren nicht unterstützt. Das Bearbeiten von F#-Code während einer Debugsitzung ist möglich, sollte aber vermieden werden. Codeänderungen werden während der Debugsitzung nicht übernommen. Daher führen alle während des Debuggens an F#-Code vorgenommenen Bearbeitungen dazu, dass der Quellcode nicht mit dem gerade gedebuggten Code übereinstimmt.
