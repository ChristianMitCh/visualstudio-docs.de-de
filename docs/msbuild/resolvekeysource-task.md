---
title: ResolveKeySource-Aufgabe | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3aa4e2454a0216e697ed12404091eb0ef16416cb
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "77632705"
---
# <a name="resolvekeysource-task"></a>ResolveKeySource-Aufgabe

Bestimmt die Schlüsselquelle mit starkem Namen

## <a name="task-parameters"></a>Aufgabenparameter

 In der folgenden Tabelle werden die Parameter der `ResolveKeySource`-Aufgabe beschrieben.

|Parameter|Beschreibung|
|---------------|-----------------|
|`AutoClosePasswordPromptShow`|Optionaler `Int32`-Parameter.<br /><br /> Ruft die Zeitspanne (in Sekunden) für die Anzeige der Countdownmeldung ab oder legt sie fest.|
|`AutoClosePasswordPromptTimeout`|Optionaler `Int32`-Parameter.<br /><br /> Ruft die Zeitspanne in Sekunden ab, die gewartet werden soll, bevor das Dialogfeld mit der Kennworteingabeaufforderung geschlossen wird, oder legt diese fest.|
|`CertificateFile`|Optionaler `String`-Parameter.<br /><br /> Ruft den Pfad der Zertifikatsdatei. ab oder legt ihn fest.|
|`CertificateThumbprint`|Optionaler `String`-Parameter.<br /><br /> Ruft den Zertifikatfingerabdruck ab oder legt diesen fest.|
|`KeyFile`|Optionaler `String`-Parameter.<br /><br /> Ruft den Pfad der Schlüsseldatei ab oder legt ihn fest.|
|`ResolvedKeyContainer`|Optionaler `String`-Ausgabeparameter.<br /><br /> Ruft den aufgelösten Schlüsselcontainer ab oder legt ihn fest.|
|`ResolvedKeyFile`|Optionaler `String`-Ausgabeparameter.<br /><br /> Ruft die aufgelöste Schlüsseldatei ab oder legt sie fest.|
|`ResolvedThumbprint`|Optionaler `String`-Ausgabeparameter.<br /><br /> Ruft den aufgelösten Fingerabdruck des Zertifikats ab oder legt diesen fest.|
|`ShowImportDialogDespitePreviousFailures`|Optionaler `Boolean`-Parameter.<br /><br /> Wenn `true`, wird das Importdialogfeld auch bei vorherigen Ausfällen angezeigt|
|`SuppressAutoClosePasswordPrompt`|Optionaler `Boolean`-Parameter.<br /><br /> Dient zum Abrufen oder Festlegen eines booleschen Werts, der angibt, ob das Dialogfeld mit der Eingabeaufforderung für das Kennwort nicht automatisch geschlossen werden soll.|

## <a name="remarks"></a>Bemerkungen

 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension-Basisklasse](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Weitere Informationen

- [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)
- [Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)
