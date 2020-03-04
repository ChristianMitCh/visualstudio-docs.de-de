---
title: Dateinachverfolgung | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9335ca6608d36edbd17e47a441e13aecaa41c890
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634200"
---
# <a name="file-tracking"></a>Dateinachverfolgung

Die Dateinachverfolgung protokolliert Aufrufe an das Windows-Dateisystem für einen Prozess und dessen untergeordnete Prozesse. Durch das Aufrufen der unten aufgeführten Funktionen wird gesteuert, wann diese Protokollierung aktiviert oder deaktiviert wird, und die zu verwendende Protokolldatei angegeben.

- [EndTrackingContext:](../msbuild/endtrackingcontext.md) Beendet der Nachverfolgung des aktuellen Kontexts.

- [ResumeTracking:](../msbuild/resumetracking.md) Setzt die Nachverfolgung nach einem Aufruf von [SuspendTracking](../msbuild/suspendtracking.md) fort.

- [SetThreadCount:](../msbuild/setthreadcount.md) Legt die Anzahl der Threads fest, die zur Nachverfolgung verwendet werden sollen.

- [StartTrackingContext:](../msbuild/starttrackingcontext.md) Startet einen neuen Nachverfolgungskontext.

- [StartTrackingContextWithRoot:](../msbuild/starttrackingcontextwithroot.md) Startet einen neuen Nachverfolgungskontext mit einem angegebenen Stamm.

- [StopTrackingAndCleanup:](../msbuild/stoptrackingandcleanup.md) Beendet die Nachverfolgung und gibt die verwendeten Ressourcen frei.

- [SuspendTracking:](../msbuild/suspendtracking.md) Hält die Nachverfolgung vorübergehend an.

- [WriteAllTLogs:](../msbuild/writealltlogs.md) Erstellt Nachverfolgungsprotokolle für alle Kontexte.

- [WriteContextTLogs:](../msbuild/writecontexttlogs.md) Erstellt ein Nachverfolgungsprotokoll für den aktuellen Kontext.
