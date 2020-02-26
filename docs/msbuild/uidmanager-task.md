---
title: UidManager-Aufgabe| Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 312e174b1bbe0a21d155e4e6b5050e6f41dd8352
ms.sourcegitcommit: 2ae2436dc3484b9dfa10e0483afba1e5a02a52eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "77579547"
---
# <a name="uidmanager-task"></a>UidManager-Aufgabe
Der <xref:Microsoft.Build.Tasks.Windows.UidManager>-Task überprüft, aktualisiert oder entfernt eindeutige Bezeichner (UIDs), um alle [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)]-Elemente zu lokalisieren, die in den [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Quelldateien enthalten sind.

## <a name="task-parameters"></a>Aufgabenparameter

| Parameter | Beschreibung |
|-------------------------| - |
| `IntermediateDirectory` | Optionaler **String**-Parameter.<br /><br /> Gibt das Verzeichnis an, das zur Sicherung der Quell-[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Dateien verwendet wird, die vom **MarkupFiles**-Parameter angegeben werden. |
| `MarkupFiles` | Erforderlicher **ITaskItem[]** -Parameter.<br /><br /> Gibt die Quell-[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Dateien an, die für UID-Überprüfung, -Aktualisierung oder -Entfernung einbezogen werden. |
| `Task` | Erforderlicher **String**-Parameter.<br /><br /> Gibt die UID-Verwaltungsaufgabe an, die Sie ausführen möchten. Gültige Optionen sind **Check**, **Update** oder **Remove**. |

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird mit dem <xref:Microsoft.Build.Tasks.Windows.UidManager>-Task überprüft, ob die angegebenen [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Quelldateien [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Elemente enthalten, die über geeignete UIDs verfügen.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="UidManagerTask">
    <UidManager
      Task="Check"
      MarkupFiles="Page1.xaml;Page2.xaml"
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />
  </Target>
</Project>
```

## <a name="see-also"></a>Siehe auch
- [WPF-MSBuild-Referenz](../msbuild/wpf-msbuild-reference.md)
- [Referenz zu MSBuild-Tasks](../msbuild/wpf-msbuild-task-reference.md)
- [MSBuild-Referenz](../msbuild/msbuild-reference.md)
- [Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)
- [Erstellen einer WPF-Anwendung (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
- [How to: Lokalisieren einer Anwendung](/dotnet/framework/wpf/advanced/how-to-localize-an-application)