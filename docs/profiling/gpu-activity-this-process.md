---
title: GPU-Aktivität (dieser Prozess) | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68e85fc44977a3d9756965de12e25d13d62dbb89
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "62969537"
---
# <a name="gpu-activity-this-process"></a>GPU-Aktivität (dieser Prozess)
Die Segmente der **GPU-Aktivität (dieser Prozesse)** in der Threads-Ansicht des Concurrency Visualizer stellen Zeiten dar, in denen die GPU Anforderungen im Auftrag des aktuellen Prozesses verarbeitet hat. Diese Anforderungen werden an die GPU als DMA-Pakete (direkter Speicherzugriff) gesendet. Die Segmentlänge entspricht der Zeit, in der die GPU ein DMA-Paket im Namen des aktuellen Prozesses bearbeitet hat.

 Wenn Sie das Segment der GPU-Aktivität auswählen, zeigt der Bericht in der Registerkarte **Aktuelle** Informationen über das verarbeitete DMA-Paket an. Diese Information umfasst die Zeitspanne, in der das Paket in der Hardware-Warteschlange gewartet hat, die mit der DirectX-Engine – der Prozess, der das Paket gesendet hat – und der Zeit, die zum Verarbeiten des Pakets benötigt wurde, verbunden wird. Ein anderen Prozess als der Aktuelle hat vielleicht das DMA-Paket physisch an die GPU gesendet. Der Concurrency Visualizer kann erkennen, wenn ein anderer Prozess Arbeit im Namen des aktuellen Prozesses an die GPU übermittelt.