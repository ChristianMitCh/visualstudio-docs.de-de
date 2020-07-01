---
title: VSPerf | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: c58033e89742650dc097a7469cbf62d7b6168509
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "85520366"
---
# <a name="vsperf"></a>VSPerf
Verwenden Sie das Befehlszeilentool **VsPerf** für Folgendes:

1. Erstellen Sie von der Befehlszeile aus Profile für UWP-Apps, wenn Visual Studio nicht auf dem Gerät installiert ist.

2. Erstellen Sie Profile für Windows 8-Desktopanwendungen und Windows Server 2012-Anwendungen mithilfe der Sampling-Profilerstellungsmethode.

   Weitere Informationen zu Ihren Profilerstellungsoptionen finden Sie unter [Profilerstellung für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="uwp-apps-only"></a>Nur UWP-Apps
 Diese Optionen gelten nur für UWP-Apps.

|Option|Beschreibung|
|-|-|
|**/app:{AppName}**|Startet den Profiler und wartet darauf, dass die angegebene App vom Startmenü aus gestartet wird.<br /><br /> Führen Sie `vsperf /listapps` aus, um den App-Namen und PackageFullName der installierten Apps anzuzeigen.|
|**/package:{PackageFullName}**|Startet den Profiler und wartet darauf, dass die angegebene App vom Startmenü aus gestartet wird.<br /><br /> Führen Sie `vsperf /listapps` aus, um den App-Namen und PackageFullName der installierten Apps anzuzeigen.|
|**/js**|Erforderlich für die Profilerstellung von JavaScript-Apps.<br /><br /> Es werden Leistungsdaten von JavaScript-Apps gesammelt.<br /><br /> Nur mit „/package“ oder „/attach“ verwenden.|
|**/noclr**|Dies ist optional. Es werden keine CLR-Daten gesammelt.<br /><br /> Nur mit „/package“ oder „/attach“ verwenden.<br /><br /> Optimierung, es werden keine verwalteten Symbole aufgelöst.|
|**/listapps**|Listet Namen installierter Apps und PackageFullNames auf.|

## <a name="windows-8-desktop-applications-and-windows-server-2012-applications-only"></a>Nur Windows 8-Desktopanwendungen und Windows Server 2012-Anwendungen
 Diese Optionen funktionieren nicht mit UWP-Apps.

|Option|Beschreibung|
|-|-|
|**/launch:{Executable}**|Startet und beginnt die Profilerstellung für die angegebene ausführbare Datei.|
|**/args:{ExecutableArguments}**|Gibt Befehlszeilenargumente an, um das **/launch**-Ziel zu erreichen.|
|**/console**|Führt das **/launch**-Ziel in einem neuen Befehlsfenster aus.|

## <a name="all-applications"></a>Alle Anwendungen
 Diese Option gilt für jede Windows 8- oder Windows Server 2012-Anwendung.

|Option|Beschreibung|
|-|-|
|**/attach:{PID&#124;ProcessName}[,PID&#124;ProcessName]...**|Sammelt Daten aus den angegebenen Prozessen.<br /><br /> Verwenden Sie Task-Manager, um die Prozess-ID (PID) anzuzeigen und Namen von ausgeführten Apps zu verarbeiten.|
|**/file:{ReportName}**|Dies ist optional. Gibt die Ausgabedatei an (überschreibt die vorhandene Datei).<br /><br /> Nur mit „/package“ oder „/attach“ verwenden.|
|**/pause**|Hält die Datensammlung an.|
|**/resume**|Führt die Datensammlung fort.|
|**/stop**|Beendet die Datensammlung und die Zielprozesse.|
|**/detach**|Beendet die Datensammlung, erlaubt jedoch die weitere Ausführung von Zielprozessen.|
|**/status**|Zeit den Profiler-Status an.|

## <a name="see-also"></a>Siehe auch
- [Leistungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)
- [Profilerstellung über die Befehlszeile](../profiling/using-the-profiling-tools-from-the-command-line.md)
