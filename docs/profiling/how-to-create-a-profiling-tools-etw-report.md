---
title: 'Vorgehensweise: Erstellen eines ETW-Berichts mit Profilerstellungstools | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: ce7b02be682d825205fc5fa50d07c1ca817a24d7
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74776400"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Vorgehensweise: Erstellen eines ETW-Berichts für Profilerstellungstools
In einem ETW-Bericht werden die ETW-Ereignisse aufgeführt, die während einer Leistungssitzung der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools aufgezeichnet wurden. ETW-Daten werden in einer Binärdatei (*ETL*) erfasst. Weitere Informationen zu diesem Bericht finden Sie unter [Bericht der Ereignisablaufverfolgung für Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).

> [!NOTE]
> ETW-Berichte können in der Schnittstelle für [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nicht angezeigt werden.

- Weitere Informationen zum Erfassen der ETW-Daten über die Schnittstelle für [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] finden Sie unter [Vorgehensweise: Sammeln von Daten der Ereignisablaufverfolgung für Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).

- Informationen zum Erfassen von ETW-Daten über eine Eingabeaufforderung finden Sie unter [VSPerfCmd](../profiling/vsperfcmd.md) und [Events (Ereignisse)](../profiling/events-vsperfcmd.md).

  Der ETW-Bericht wird über den Befehl **VSReport/summary:etw** erstellt. Die *ETL*-Datei, die die ETW-Daten enthält, muss sich in demselben Verzeichnis befinden wie die Profilerstellungsdatendatei (.*vsp* oder .*vsps*). Standardmäßig wird der Bericht als eine durch Trennzeichen getrennte Datei (.*csv*) generiert. Weitere Informationen finden Sie unter [VSPerfReport](../profiling/vsperfreport.md).

### <a name="to-generate-an-etw-report"></a>So erstellen Sie einen ETW-Bericht

- Geben Sie im Fenster **Eingabeaufforderung** die folgende Befehlszeile ein:

     *ToolsPath* **VSPerfReport** *VSPFile* **/Summary:ETW [/Xml]**

    |||
    |-|-|
    |*ToolsPath*|Der Pfad zum Hilfsprogramm für die Profilerstellungstools. Weitere Informationen finden Sie unter [Angeben des Pfads für Befehlszeilentools](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|
    |*VSPFile*|Die Datendatei für die Profilerstellung (.*vsp* oder .*vsps*). Es werden vollständige und partielle Pfade angenommen.|
    |Xml|Generiert einen in XML formatierten Bericht.|
