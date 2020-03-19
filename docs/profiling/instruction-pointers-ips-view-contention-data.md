---
title: Anweisungszeigeransicht – Konfliktdaten | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: f5e49c24-d4cf-4f87-977d-37e3223d1196
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: f37fb451238ec7ce6f48d8a4d3b91efa9ce04db7
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74774311"
---
# <a name="instruction-pointers-ips-view---contention-data"></a>Anweisungszeigeransicht: Konfliktdaten
Die Anweisungszeigeransicht (IPs-Ansicht) der Konfliktdaten führt Daten für die Assemblyanweisungen auf, die nicht während der Profilerstellung ausgeführt werden durften.

 In der nachstehenden Tabelle werden die Werte der Spalten in der Anweisungszeigeransicht erklärt.

|Spalte|Beschreibung|
|------------|-----------------|
|**Exklusive blockierte Zeit %**|Die blockierte Zeit in dieser Funktion|
|**Exklusive blockierte Zeit %**|Der Prozentsatz der blockierten Zeit, während die Anweisung ausgeführt wurde|
|**Exklusive Konflikte**|Die Anzahl der Konflikte, die aufgetreten sind, während die Anweisung ausgeführt wurde|
|**Exklusive Konflikte %**|Der Prozentsatz aller Konflikte bei der Profilerstellung, die aufgetreten sind, während die Anweisung ausgeführt wurde|
|**Funktionsadresse**|Die Startspeicheradresse der Funktion in der geladenen Binärdatei|
|**Funktionsname**|Der Name der Funktion, die die Anweisung enthält|
|**Anweisungsadresse**|Die Speicheradresse der Anweisung in der geladenen Binärdatei|
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|
|**Modulname**|Der Name des Moduls, das die Anweisung enthält|
|**Modulpfad**|Der Pfad des Moduls, das die Anweisung enthält|
|**Prozess-ID**|Die Prozess-ID (PID) des Profilerstellungsprozesses.|
|**Prozessname**|Der Prozessname.|
|**Quellanfangszeichen**|Der Offset des Zeichens der Quelldateizeile, an dem diese Anweisung beginnt|
|**Quellendzeichen**|Der Offset des Zeichens der Quelldateizeile, an dem diese Anweisung endet|
|**Quelldatei**|Die Quelldatei, die die Anweisung enthält|
|**Quellanfangszeile**|Die Zeilennummer in der Quelldatei, bei der diese Anweisung beginnt|
|**Quellendzeile**|Die Zeilennummer in der Quelldatei, bei der diese Anweisung endet|

## <a name="see-also"></a>Siehe auch
- [How to: Anpassen von Spalten in Berichtsansichten](../profiling/how-to-customize-report-view-columns.md)
- [Anweisungszeigeransicht](../profiling/instruction-pointers-ips-view.md)
- [Anweisungszeigeransicht: .NET-Speichersamplingdaten im Profiler](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)
- [Anweisungszeigeransicht](../profiling/instruction-pointers-ips-view-sampling-data.md)
