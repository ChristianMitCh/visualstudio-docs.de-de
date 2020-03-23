---
title: Events (VSPerfCmd) | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 46b47f9b615c824d25e931cd3d05f5d2a04257ba
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74777320"
---
# <a name="events-vsperfcmd"></a>Events (VSPerfCmd)
Die *VSPerfCmd.exe*-Option **Events** steuert die Protokollierung der Ereignisablaufverfolgung für Windows (ETW). ETW-Daten werden in einer ETL-Datei gespeichert, die von der Profiler-Datendatei getrennt ist. Die Daten können in einem Bericht mithilfe des Befehls „[VSPerfReport ](../profiling/vsperfreport.md) /summary: etw“ angezeigt werden.

 Die Option **Events** kann jederzeit aufgerufen werden, bevor der VSPerfCmd-Befehl **Shutdown** zum Beenden der Profilerstellung aufgerufen wird.

## <a name="syntax"></a>Syntax

```cmd
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]
```

#### <a name="parameters"></a>Parameter
 **On**&#124;**Off**: startet oder beendet die Sammlung von Ereignisdaten.

 `Guid`: die GUID des Anbietersteuerelements.

 `ProviderName`: der Name des Anbieters, der bei der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) registriert ist.

 `Flags`: ein mit „0x“ präfigierter Wert eines hexadezimal Flags, der vom Ereignisanbieter definiert wird.

 `Level`: gibt die Menge der gesammelten Daten an. `Level` wird vom Ereignisanbieter definiert.

 Die Option **Events** versteht die folgenden Kernelschlüsselwörter als Anbieternamen:

 **Process:** Prozessereignisse

 **Thread:** Threadereignisse

 **Image:** Lade- und Entladeereignisse für Images

 **Disk:** E/A-Datenträgerereignisse

 **File:** E/A-Dateiereignisse

 **Hardfault:** Harte Seitenfehler

 **Pagefault:** Weiche Seitenfehler

 **Network:** Netzwerkereignisse

 **Registry:** Ereignisse beim Zugriff auf die Registrierung

 Beachten Sie, dass der Kernelanbieter nur aktiviert werden kann. Er kann weder deaktiviert werden, noch können Flags geändert werden, bis der Monitor heruntergefahren wurde.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Wenn CLR-ETW-Ereignisse aktiviert sind, werden im Bericht in der Ablaufverfolgungsansicht auch zusätzliche Startdaten gesammelt. Mit dem folgenden Befehl vermeiden Sie, dass Startereignisse im Bericht angezeigt werden:

```cmd
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5
```

> [!IMPORTANT]
> Wenn Sie Startereignisse nicht ausschließen, werden sie als GUIDs im Bericht angezeigt, weil sie nicht in der MOF-Datei (Managed Object Format) aufgeführt werden. Weitere Informationen finden Sie auf der folgenden Microsoft-Website: [Sample Managed Object Format (MOF) file (MOF-Beispieldatei (Managed Object Format))](https://msdn.microsoft.com/library/default.aspx).

## <a name="see-also"></a>Siehe auch
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profilerstellung für Dienste](../profiling/command-line-profiling-of-services.md)
