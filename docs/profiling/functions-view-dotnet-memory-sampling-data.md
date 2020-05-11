---
title: 'Funktionsansicht: .NET-Speichersamplingdaten | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- dotnet
ms.openlocfilehash: cce13da0c2dfee61d70da8bc288d1f0ff4690deb
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74780038"
---
# <a name="functions-view---net-memory-sampling-data"></a>Funktionsansicht: .NET-Speichersamplingdaten
In der Funktionsansicht der Profilerstellungsdaten für die .NET-Speicherbelegung, die mithilfe der Samplingmethode erfasst wurden, werden sowohl die Funktionen angezeigt, die während der Profilerstellungsausführung Arbeitsspeicher belegt haben, als auch die Größe und die Anzahl der Speicherbelegungen.

|Spalte|Beschreibung|
|------------|-----------------|
|**Prozess-ID**|Die Prozess-ID (PID) der Profilerstellung.|
|**Prozessname**|Der Name des Prozesses.|
|**Modulname**|Der Name des Moduls, das die Funktion enthält.|
|**Modulpfad**|Der Pfad des Moduls, das die Funktion enthält.|
|**Quelldatei**|Die Quelldatei, die die Definition der Funktion enthält.|
|**Funktionsname**|Der vollqualifizierte Name der Funktion.|
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|
|**Funktionsadresse**|Die Adresse der Funktion.|
|**Inklusive Speicherbelegungen**|Die Gesamtanzahl der Objekte, die in dieser Funktion und ihren untergeordneten Funktionen Speicher belegt haben.|
|**Inklusive Zuordnungen in %**|Der Prozentsatz aller Objekte, die während der Profilerstellung Speicher belegt haben und inklusive Belegungen dieser Funktion waren.|
|**Exklusive Speicherbelegungen**|Die Anzahl der Objekte, die während der Ausführung der Funktion am Anfang der Aufrufliste erstellt wurden. Diese Zahl schließt nicht die Objekte mit ein, die in untergeordneten Funktionen erstellt wurden.|
|**Exklusive Zuordnungen %**|Der Prozentsatz aller Objekte, die während der Profilerstellung Speicher belegt haben und exklusive Belegungen dieser Funktion waren.|
|**Inklusive Bytes in %**|Die Anzahl der Bytes im Arbeitsspeicher, die von dieser Funktion und ihren untergeordneten Funktionen belegt wurden.|
|**Inklusive Bytes in %**|Der Prozentsatz aller Bytes im Arbeitsspeicher, die während der Profilerstellung belegt wurden und inklusive Bytes dieser Funktion waren.|
|**Exklusive Bytes**|Die Anzahl der Bytes im Arbeitsspeicher, die von dieser Funktion, nicht jedoch von ihren untergeordneten Funktionen belegt wurden.|
|**Exklusive Bytes %**|Der Prozentsatz aller Bytes im Arbeitsspeicher, die während der Profilerstellung belegt wurden und exklusive Belegungen dieser Funktion waren.|

## <a name="see-also"></a>Weitere Informationen
- [Funktionsansicht: Instrumentierung](../profiling/functions-view-dotnet-memory-instrumentation-data.md)
- [Funktionsansicht](../profiling/functions-view-sampling-data.md)
- [Funktionsansicht](../profiling/functions-view-instrumentation-data.md)
