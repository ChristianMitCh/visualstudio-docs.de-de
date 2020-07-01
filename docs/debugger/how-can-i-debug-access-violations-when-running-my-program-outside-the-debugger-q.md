---
title: Debuggen von Zugriffsverletzungen beim Ausführen der App außerhalb des Debuggers
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 88dde869e6e9e1551459ce1171364709baf6403e
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2020
ms.locfileid: "85350432"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Wie können Zugriffsverletzungen, die beim Ausführen des Programms außerhalb des Debuggers auftreten, gedebuggt werden?

## <a name="problem-description"></a>Problembeschreibung
 Das Programm läuft in der Visual Studio-Umgebung einwandfrei. Wird es jedoch eigenständig unter dem Windows-Betriebssystem ausgeführt, generiert es eine Zugriffsverletzung. Wie kann dieses Problem behoben werden?

## <a name="solution"></a>Lösung
 Legen Sie die Option für das [Just-In-Time-Debuggen](../debugger/just-in-time-debugging-in-visual-studio.md) fest, und führen Sie das Programm im eigenständigen Modus aus, bis eine Zugriffsverletzung auftritt. Dann können Sie im Dialogfeld **Zugriffsverletzung** auf **Abbrechen** klicken, um den Debugger zu starten.

## <a name="see-also"></a>Siehe auch
- [FAQs zum Debuggen von nativem Code](../debugger/debugging-native-code-faqs.md)
- [Debuggen von nativem Code](../debugger/debugging-native-code.md)