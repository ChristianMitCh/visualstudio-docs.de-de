---
title: Bei einem Prozess ist ein nicht behebbarer Fehler aufgetreten
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c30ac5950ca9bf775b05e9f77867c119b7c7565d
ms.sourcegitcommit: eef26de3d7a5c971baedbecf3b4941fb683ddb2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81544340"
---
# <a name="visual-studio-unrecoverable-process-error"></a>Nicht behebbare Prozessfehler in Visual Studio

Visual Studio verwendet mehrere Out-of-Proc-Prozesse, um die erforderlichen Hintergrundaufgaben, wie z.B. Live-Komponententests, Code-Analysetools und mehr auszuführen. Diese Prozesse werden Out-of-Proc ausgeführt, um Leistungsvorteile von Visual Studio zu nutzen, z.B. dass Visual Studio schneller reagieren kann, wenn ressourcenintensive, langfristige Aufträge ausgeführt werden. Da Visual Studio ein 32-Bit-Prozess ist, bietet die Out-of-Proc-Ausführung von Prozessen anspruchsvollen speicherintensiven Arbeiten einen größeren Speicherplatz, in dem ausgeführt werden soll.

Wenn der Prozess *ServiceHub.RoslynCodeAnalysisService.exe* oder *ServiceHub.RoslynCodeAnalysisService32.exe* aus irgendeinem Grund beendet wird, wird eine Popup-Informationsleiste mit folgender Meldung angezeigt:

**„Unfortunately, a process used by Visual Studio has encountered an unrecoverable error. We recommend saving your work, and then closing and restarting Visual Studio.“ (Leider ist bei einem von Visual Studio verwendeten Prozess ein nicht behebbarer Fehler aufgetreten. Es wird empfohlen, die Arbeit abzuspeichern und Visual Studio anschließend neu zu starten.)**

Wenn diese Meldung angezeigt wird, müssen Sie Ihre Arbeit speichern und Visual Studio anschließend schließen und neu starten.

## <a name="list-of-processes"></a>Liste der Prozesse

Im Folgenden finden Sie eine Liste der Out-of-Proc-Prozesse, die von Visual Studio verwendet werden. Diese Liste enthält Prozesse, die in bestimmten Workflows oder Szenarios gestartet werden. In den meisten Fällen werden diese also nicht alle gleichzeitig ausgeführt.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- MSBuild.exe
- PerfWatson2.exe
- ScriptedSandbox64.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- „ServiceHub.RoslynCodeAnalysisService.exe“
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.VSDetouredHost.exe
- VBCSCompiler.exe
- VsHub.exe
- vstest.discoveryengine.x86.exe
- WaAppAgent.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe

Wenn einer dieser Prozesse unerwartet beendet wird, funktionieren einige Funktionalitäten in Visual Studio nicht mehr. Bei einigen Prozesse kann der Ausfall dieser Funktionalitäten unbedeutend sein. Bei anderen wird die Stabilität von Visual Studio beeinträchtigt, und eine Fehlermeldung wird angezeigt.
