---
title: Festlegen allgemeiner Leistungsoptionen für Sitzungen | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.general
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 023681b263e6e70048ec7d82d2cee741672989ff
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74773941"
---
# <a name="set-general-performance-session-options"></a>Festlegen allgemeiner Leistungsoptionen für Sitzungen

Sie können die Auflistungsmethode und Benennungskonventionen für Profilerstellungsdaten für eine Leistungssitzung der Visual Studio-Profilerstellungstools auf der Seite **Allgemein** des Dialogfelds „Eigenschaften“ für die Leistungssitzung festlegen. Zum Öffnen dieses Dialogfelds klicken Sie im **Leistungs-Explorer** mit der rechten Maustaste auf die Leistungssitzung, und klicken Sie dann auf **Eigenschaften**.

## <a name="choosing-data-collection-methods"></a>Auswählen von Datensammlungsmethoden

Die Basisauflistungsmethode kann durch Auswählen einer der Optionen unter **Profilauflistung** festgelegt werden. Die Optionen sind in der folgenden Tabelle beschrieben:

|||
|-|-|
|**Stichprobennahme**. Die Samplingmethode sammelt in regelmäßigen Abständen Profilerstellungsinformationen. Diese Methode ist nützlich für das Auffinden von Prozessornutzungsproblemen und ist die vorgeschlagene Methode zum Starten der meisten Leistungsuntersuchungen.|- [Collecting Performance Statistics by Using Sampling (Sammeln von Leistungsstatistiken durch Sampling)](../profiling/collecting-performance-statistics-by-using-sampling.md)|
|**Instrumentierung**. Die Instrumentationsmethode springt in eine Kopie eines Modulprofilerstellungscodes, durch den jeder Eintritt, jeder Austritt und jeder Funktionsaufruf der Funktionen in dem Modul während der Profilerstellungsausführung aufgezeichnet wird. Mithilfe dieser Methode können ausführliche Zeitsteuerungsdaten zu einem Abschnitt des Codes erfasst werden. Zudem werden mit dieser Methode die Auswirkungen von Eingabe- und Ausgabeoperationen auf die Leistung der Anwendung besser verständlich.|- [Collecting Detailed Timing Data by Using Instrumentation (Sammeln ausführlicher Zeitsteuerungsdaten mithilfe der Instrumentierung) ](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|
|**Parallelität**: Die Parallelitätsmethode erfasst Daten für jedes Ereignis, das die Ausführung des Codes blockiert, wie z. B. ein Thread, der darauf wartet, dass der gesperrte Zugriff auf eine Anwendungsressource freigegeben wird. Diese Methode ist hilfreich für das Analysieren von Multithreadanwendungen.|- [Collecting Thread and Process Concurrency Data (Sammeln von Nebenläufigkeitsdaten zu Threads und Prozessen) ](../profiling/collecting-thread-and-process-concurrency-data.md)|

 .NET-Arbeitsspeicherdaten können mit der Sampling- oder Instrumentationsmethode erfasst werden. Sie wählen den Typ der Daten unter **Profilerstellung für .NET-Arbeitsspeicher** aus.

|||
|-|-|
|**.NET-Objektzuordnungsinformationen auflisten**. Standardmäßig enthalten Daten die Anzahl und die Größe von zugeordneten Objekten. Aktivieren oder deaktivieren Sie dieses Kontrollkästchen, um die .NET-Arbeitsspeicherdatensammlung zu aktivieren oder zu deaktivieren. |- [Sammeln von Daten zur .NET-Speicherbelegung und Lebensdauer](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|
|**Lebensdauerinformationen für .NET-Objekt auflisten**. Aktivieren Sie dieses Kontrollkästchen, um Daten zu den Garbage Collection-Generierungen einzuschließen, die verwendet wurden, um die Speicherobjekte freizugeben.|- [Sammeln von Daten zur .NET-Speicherbelegung und Lebensdauer](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md) |

 Eine Profilerstellungs-Sitzungsseite wird angezeigt, wenn Sie beginnen, ein Profil für eine Anwendung zu erstellen, bei dem Sie die Profilerstellung anhalten, fortsetzen und beenden können.

 ![Profilerstellungs-Sitzungsseite](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")

## <a name="set-profiling-data-file-options"></a>Festlegen von Optionen für die Profilerstellungs-Datendatei

|||
|-|-|
|**Bericht**. Standardmäßig erhält die Profilerstellungs-Datendatei (.vsp) den Namen der profilierten Anwendung, und sie befindet sich im Projektmappen- oder Projektordner. Es wird auch eine Datumszeichenfolge an den Namen angefügt, und Datendateien, die andernfalls doppelte Namen hätten, wird eine inkrementierte Zahl hinzugefügt. Sie können diese Optionen ändern.|- [How to: Set Performance Data File Name Option (Vorgehensweise: Festlegen von Dateinamenoptionen für Profilerstellungsdaten)](../profiling/how-to-set-performance-data-file-name-options.md)|
