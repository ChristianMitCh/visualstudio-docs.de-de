---
title: Ausführungsprofilbericht | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25886ad4f7c31ea02c8dab2d45d8709a362a5a69
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "62969991"
---
# <a name="execution-profile-report"></a>Ausführungsprofilbericht
Der Ausführungsprofilbericht ist ein herkömmliches Samplingprofil. Samplings werden etwa jede Millisekunde während der Zeiträume genommen, in denen ein Thread auf einem logischen Kern ausgeführt wird. Die Parallelitätsschnellansicht erstellt durch Sortieren des akkumulierten Satzes von Samplingstapeln eine typische Aufrufstruktur. Die Daten in dieser Tabelle sind vom aktuellem Zeitraum und ausgeblendeten Threads, sowie von den möglicherweise angewendeten Filtern abhängig:

- Wenn „Nur eigenen Code“ ausgewählt ist, werden nur Stapelrahmen mit Benutzercode, sowie die Ebene direkt unter dem Benutzercode angezeigt.

- Wenn der Wert „Rauschunterdrückung“ festgelegt ist, werden sortierte Stapel mit einer geringeren als der angegebenen Frequenz aus dem Bericht gefiltert.

  Die folgende Tabelle zeigt die Spalten im Bericht.

|Spalte|Beschreibung|
|------------|-----------------|
|Name|Der Name der Funktion für die einzelnen Ebenen der Aufrufliste.|
|Inklusive Samplings|Die Gesamtzahl von Samplings, die für alle Stapel erfasst werden, die diese Ebene der Aufruflistenstruktur bilden. Die inklusive Anzahl ist die Summe der exklusiven Samplings für diese Funktion und der inklusiven Anzahl für alle untergeordneten Knoten.|
|Exklusive Stichproben|Die Gesamtzahl erfasster Samplings, für die diese Funktion die niedrigste Ebene der Aufrufliste bildet.|
|% inklusive|Der Prozentsatz der gesamten Samplings, die in der Spalte für inklusive Samplings angezeigt werden. Prozentsätze werden auf zwei Dezimalstellen gerundet.|
|% exklusive|Der Prozentsatz der gesamten Samplings, die in der Spalte für exklusive Samplings angezeigt werden. Prozentsätze werden auf zwei Dezimalstellen gerundet.|
|Details|Der vollqualifizierte Name der Funktion. Darin eingeschlossen ist die Zeilenanzahl, sofern verfügbar.|

 Diese Berichtstabelle kann in der Ansicht [Ausführungszeit (Threadansicht)](../profiling/execution-time-threads-view.md) angezeigt werden.

## <a name="see-also"></a>Weitere Informationen
- [Threads View (Threadansicht)](../profiling/threads-view-parallel-performance.md)