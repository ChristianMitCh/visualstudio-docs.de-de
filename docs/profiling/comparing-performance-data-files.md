---
title: Vergleichen von Leistungsdatendateien | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 64842c5b4f622a1f76aa528360f79403ec92cb42
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74777854"
---
# <a name="compare-performance-data-files"></a>Vergleichen von Leistungsdatendateien

Mit der Datendateivergleichsfunktion der Profilerstellungstools können Sie zwei Berichtsdateien (*VSP* bzw. *VSPS*) auswählen und einen Bericht generieren, der die Unterschiede, Leistungsregressionen und Verbesserungen zeigt, die zwischen den beiden Profilerstellungssitzungen aufgetreten sind.

Ein Vergleichsbericht von Datendateien aus [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools vergleicht die Ergebnisse einer Analyse in einer Profilerstellungs-Datendatei mit den Ergebnissen einer Baseline-Analyse in einer anderen Datendatei. Beide Datendateien müssen mit derselben Profilerstellungsmethode erstellt worden sein. Der Bericht der analysierten Vergleiche wird als *VSPS-Datei* gespeichert.

Die Vergleichsberichtsansicht enthält eine Tabellenansicht der geänderten Daten. In der Tabelle wird das Delta bzw. die Abweichung von der Baseline dargestellt. Zur Berechnung des Deltas wird der Unterschied zwischen dem alten Wert, dem Baselinewert und dem Ergebniswert aus der neuen Analyse ermittelt.

Vergleiche der Profilerdaten können auf den Funktionen im Code, den Modulen in der Anwendung, Zeilen, Anweisungszeigern (IPs) und Typen basieren.

Profilerstellungsdaten, die für den Vergleich verfügbar sind, umfassen die Informationen, die in den Spalten angezeigt werden. Definitionen dieser Spaltennamen finden Sie unter [Berichtsansichten für Profilerstellungstools](../profiling/performance-report-views.md).

Es kann ein Schwellenwert festgelegt werden, um Störungen zu reduzieren und alle Daten in der Vergleichstabellenansicht der Zeilen herauszufiltern, bei denen keine Änderung um einen bestimmten Wert feststellbar ist.

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Vergleichen von Leistungsdatendateien](../profiling/how-to-compare-performance-data-files.md)
