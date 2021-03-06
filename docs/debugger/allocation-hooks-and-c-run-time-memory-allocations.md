---
title: Belegungshooks und Speicherbelegungen von C-Laufzeitbibliotheken | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 79e55ec521de098a7ae0339c4460502dde3d482d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745795"
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>Reservierungshooks und Speicherreservierungen von C-Laufzeitbibliotheken
Eine wichtige Einschränkung bei Hookfunktionen für Belegungen ist die, dass sie `_CRT_BLOCK`-Blöcke explizit ignorieren müssen. Bei diesen Blöcken handelt es sich um die Speicherbelegungen, die von C-Laufzeitbibliotheksfunktionen intern vorgenommen werden, wenn Aufrufe an C-Laufzeitbibliotheksfunktionen gesendet werden, durch die interner Speicher belegt wird. Die `_CRT_BLOCK`-Blöcke können ignoriert werden, wenn Sie am Anfang der Belegungshookfunktion folgenden Code einfügen:

```cpp
if ( nBlockUse == _CRT_BLOCK )
    return( TRUE );
```

Werden `_CRT_BLOCK`-Blöcke nicht vom Belegungshook ignoriert, kann es vorkommen, dass eine im Hook aufgerufene C-Laufzeitbibliotheksfunktion das Programm in eine Endlosschleife führt. Beispielsweise nimmt `printf` eine interne Reservierung vor. Wenn durch den Hookcode `printf` aufgerufen wird, bewirkt die daraus resultierende Zuweisung, dass der Hook erneut aufgerufen wird, wodurch wiederum **printf** aufgerufen wird usw., bis ein Stapelüberlauf auftritt. Wenn Sie `_CRT_BLOCK`-Reservierungsoperationen in einem Bericht ausgeben möchten, können Sie diese Beschränkung umgehen, indem Sie für die Formatierung und die Ausgabe anstelle der C-Laufzeitfunktionen Windows-API-Funktionen verwenden. Da der Heap der C-Laufzeitbibliothek nicht von Windows-APIs verwendet wird, führen sie den Belegungshook nicht in eine Endlosschleife.

Wenn Sie die Quelldateien der Laufzeitbibliothek untersuchen, werden Sie feststellen, dass sich die standardmäßige Zuweisungshookfunktion **CrtDefaultAllocHook** (die einfach **TRUE** zurückgibt) in einer separaten Datei namens „DBGHOOK.C“ befindet. Wenn der Zuweisungshook auch für die Zuweisungen aufgerufen werden soll, die vom Laufzeitstartcode vorgenommen wurden, der vor der **main**-Funktion der Anwendung ausgeführt wird, können Sie diese Standardfunktion durch eine eigene Funktion ersetzen, anstatt [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook) zu verwenden.

## <a name="see-also"></a>Siehe auch
- [Schreiben von Hookfunktionen zum Debuggen](../debugger/debug-hook-function-writing.md)
