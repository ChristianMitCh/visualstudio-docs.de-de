---
title: Registerkarte „Aktuell“ | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.reportnav.current
helpviewer_keywords:
- Concurrency Visualizer, Callstack at Selection Point
ms.assetid: 2c7b1ae5-3756-4795-bc59-f6bb113f2ba5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f48ba44d41286f1cf5eda6ececb68d21d39abd14
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "62552787"
---
# <a name="current-tab"></a>Registerkarte „Aktuell“
Bei der Auswahl eines CPU-Threadsegments wird durch Klicken auf die Registerkarte **Aktuell** eine Aufrufliste (sofern vorhanden) angezeigt, die dem aktuellen Auswahlpunkt auf der Zeitachse am ehesten entspricht.  In diesem Fall wird der Auswahlpunkt durch einen schwarzen Pfeil oder ein Caretzeichen oberhalb der Zeitachse dargestellt. Wenn ein Blockierungssegment ausgewählt wird, wird das Caretzeichen nicht angezeigt, weil keine Ausführung stattgefunden hat. Das Segment wird aber dennoch hervorgehoben, und eine Aufrufliste wird angezeigt.

 Auf der Registerkarte **Aktuell** werden zudem Informationen zu DirectX-Aktivitätssegmenten, Marker und E/A-Zugriff angezeigt.  Für DirectX-Aktivitätssegmente werden Informationen zur Verarbeitung von DMA-Paketen durch die Hardwarewarteschlange angezeigt.  Für Marker werden Informationen zur Beschreibung sowie zum Markertyp angezeigt.  Für den E/A-Zugriff werden Informationen zu Datei und Anzahl der gelesenen oder geschriebenen Bytes angezeigt.

## <a name="see-also"></a>Weitere Informationen
- [Threads View (Threadansicht)](../profiling/threads-view-parallel-performance.md)