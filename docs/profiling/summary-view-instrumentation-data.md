---
title: Zusammenfassungsansicht – Instrumentationsdaten | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 2f52f80cad4ce7678a832a7b76a75d8f2fd4460e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778218"
---
# <a name="summary-view---instrumentation-data"></a>Zusammenfassungsansicht – Instrumentationsdaten
Die Zusammenfassungsansicht zeigt Informationen über die leistungsintensivsten Funktionen in einem Profilerstellungslauf. Weitere Informationen, einschließlich einer Beschreibung der Benachrichtigungslinks und Berichtslisten, finden Sie unter [Zusammenfassungsansicht](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Zeitachsendiagramm
 Die Zeitachse in der Zusammenfassungsansicht zeigt die Auslastung des Prozessors (CPU) durch die profilierte Anwendung während des Zeitraums an, in dem die Profilerstellung stattgefunden sind. Sie können das Zeitachsendiagramm zum Filtern der Ansicht in einem ausgewählten Zeitraum verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Filtern von Berichtsansichten aus der Zeitachsenübersicht.](../profiling/how-to-filter-report-views-from-the-summary-timeline.md)

## <a name="hot-path"></a>Langsamster Pfad
 Die Option **Langsamster Pfad** zeigt den Ausführungspfad an, der die meiste Zeit beansprucht hat. Sie können auf eine Funktion klicken, um die Ansicht „Funktionsdetails“ für die Funktion anzuzeigen. Zum Anzeigen anderer Ansichten für die Funktion klicken Sie mit rechten Maustaste auf die Funktion, und klicken Sie dann auf eine Ansicht in der Liste.

 **Langsamster Pfad** umfasst die folgenden Daten für jede Funktion:

|Spalte|Beschreibung|
|------------|-----------------|
|**Name**|Der Name der Funktion.|
|**Verstrichene inklusive Zeit %**|Der Prozentsatz der gesamten Zeit in den Profilerstellungsdaten, die die Funktion für die Ausführung von Code im Funktionsrumpf und in den von ihr aufgerufenen Funktionen aufgewendet hat.|
|**Verstrichene exklusive Zeit %**|Der Prozentsatz der gesamten Zeit in den Profilerstellungsdaten, die die Funktion für die Ausführung von Code im Funktionsrumpf verwendet hat. In Funktionen, die von der Funktion aufgerufen wurden, aufgewendete Zeit wurde nicht berücksichtigt.|

## <a name="functions-with-most-individual-work"></a>Funktionen mit den meisten einzelnen Aufgaben
 Eine Liste der Funktionen, die die meiste Zeit für die Ausführung von Code im Rumpf der Funktion und nicht in von ihr aufgerufenen Funktionen aufgewendet hat.

 **Funktionen mit den meisten einzelnen Aufgaben** umfasst die folgenden Daten für jede Funktion:

|Spalte|Beschreibung|
|------------|-----------------|
|**Name**|Der Name der Funktion.|
|**Exklusive Zeit %**|Der Prozentsatz der gesamten Zeit in den Profilerstellungsdaten, die die Funktion für die Ausführung von Code im Funktionsrumpf verwendet hat. In Funktionen, die von der Funktion aufgerufen wurden, aufgewendete Zeit wurde nicht berücksichtigt.|

## <a name="see-also"></a>Weitere Informationen
- [Zusammenfassungsansicht: Samplingdaten](../profiling/summary-view-sampling-data.md)
- [Summary view - .NET memory data (Zusammenfassungsansicht – .NET-Arbeitsspeicherdaten)](../profiling/summary-view-dotnet-memory-data.md)
