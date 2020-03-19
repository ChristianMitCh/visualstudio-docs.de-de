---
title: Unzip-Aufgabe | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Unzip
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Unzip task [MSBuild]
- MSBuild, Unzip task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d331fda05e8655be0536a1e83d8309ae8c060b1f
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631509"
---
# <a name="unzip-task"></a>Unzip-Aufgabe

Entzippt ein *ZIP*-Archiv am angegebenen Speicherort.

>[!NOTE]
>Die `Unzip`-Aufgabe ist nur in MSBuild 15.8 und höher verfügbar.

## <a name="parameters"></a>Parameter

 In der folgenden Tabelle werden die Parameter der `Unzip`-Aufgabe beschrieben.

|Parameter|Beschreibung|
|---------------|-----------------|
|`DestinationFolder`|Erforderlicher <xref:Microsoft.Build.Framework.ITaskItem>-Parameter<br /><br /> Gibt den Zielordner an, in dem die Datei entzippt werden soll.|
|`OverwriteReadOnlyFiles`|Optionaler `Boolean`-Parameter.<br /><br /> Wenn dieser auf `true` festgelegt ist, werden schreibgeschützte Dateien überschrieben. Wird standardmäßig auf `false` festgelegt.|
|`SkipUnchangedFiles`|Optionaler `Boolean`-Parameter.<br /><br /> Wenn `true` festgelegt ist, wird das Entzippen von Dateien übersprungen, die nicht geändert werden. Wird standardmäßig auf `true` festgelegt. In der `Unzip`-Aufgabe werden Dateien als identisch betrachtet, wenn diese dieselbe Größe aufweisen und zur selben Zeit zuletzt geändert wurden.|
|`SourceFiles`|Erforderlicher <xref:Microsoft.Build.Framework.ITaskItem>`[]`-Parameter.<br /><br /> Gibt eine oder mehrere zu entzippende Dateien an. Wenn mehrere Dateien angegeben werden, werden diese der Reihenfolge nach im selben Ordner entzippt.|

## <a name="remarks"></a>Bemerkungen

 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension-Basisklasse](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird ein Archiv entzippt, und alle schreibgeschützten Dateien werden überschrieben.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="UnzipArchive" BeforeTargets="Build">
        <Unzip
            SourceFiles="MyArchive.zip"
            DestinationFolder="$(OutputPath)\unzipped"
            OverwriteReadOnlyFiles="true"
        />
    </Target>

</Project>
```

## <a name="see-also"></a>Weitere Informationen

- [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)
- [Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)
