---
title: Projektelement (Visual Studio-Vorlagen) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Project
helpviewer_keywords:
- Project element [Visual Studio Templates]
- <Project> element [Visual Studio Templates]
ms.assetid: 1da15ea6-26e2-462b-a03e-584ef4996579
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 335a1e4efa62f07e10bb24b9971627d24bb13273
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80702001"
---
# <a name="project-element-visual-studio-templates"></a>Projektelement (Visual Studio-Vorlagen)
Gibt die Dateien oder Verzeichnisse an, die dem Projekt hinzugefügt werden sollen.

 \<VSTemplate \<> TemplateContent> \<Project>

## <a name="syntax"></a>Syntax

```
<Project
    File="MyProject.proj"
    TargetFileName="MyTargetProject.proj"
    ReplaceParameters="true/false">
    IgnoreProjectParameter="$myCustomParameter$"
        ...
</Project>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden attribute-Elemente sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`File`|Erforderliches Attribut.<br /><br /> Gibt den Namen der Projektdatei in der *.zip-Datei* der Vorlage an.|
|`ReplaceParameters`|Optionales Attribut.<br /><br /> Ein boolescher Wert, der angibt, ob die Projektdatei Parameterwerte enthält, die ersetzt werden müssen, wenn ein Projekt aus der Vorlage erstellt wird. Der Standardwert ist `false`.|
|`TargetFileName`|Optionales Attribut.<br /><br /> Gibt den Namen der Projektdatei an, wenn ein Projekt aus der Vorlage erstellt wird.|
|`IgnoreProjectParameter`|Optionales Attribut.<br /><br /> Gibt an, ob das Projekt der aktuellen Projektmappe hinzugefügt werden soll. Wenn in der Parameterersatzdatei der Wert des benutzerdefinierten Parameters "-*myCustomParameter"* vorhanden ist, wird das Projekt erstellt, aber nicht als Teil der aktuell geöffneten Projektmappe hinzugefügt.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Ordner](../extensibility/folder-element-visual-studio-project-templates.md)|Optionales Element.<br /><br /> Gibt einen Ordner an, der dem Projekt hinzugefügt werden soll.|
|[ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md)|Optionales Element.<br /><br /> Gibt eine Datei an, die einem Projekt hinzugefügt werden soll.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Erforderliches Element|

## <a name="remarks"></a>Bemerkungen
 `Project` ist ein optionales untergeordnetes Element von `TemplateContent`.

 Das `Project` Element wird zum Spezifizieren eines Projekts verwendet und ist daher nur in Projektvorlagen gültig.

 `Project`Elemente können [untergeordnete Ordnerelemente](../extensibility/folder-element-visual-studio-project-templates.md) oder [ProjectItem-Elemente](../extensibility/projectitem-element-visual-studio-project-templates.md) enthalten, `Folder` `ProjectItem` jedoch keine Mischung aus beiden und untergeordneten Elementen.

 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Benennt den Projektdateinamen automatisch basierend auf dem Namen, den der Benutzer im Dialogfeld **Neues Projekt** eingegeben hat. Verwenden `TargetFileName` Sie das Attribut, wenn Sie einen alternativen Dateinamen für Projektdateien angeben möchten, die mit der Vorlage erstellt wurden.

## <a name="example"></a>Beispiel
 Im folgenden Beispiel werden die Metadaten für eine Projektvorlage einer [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-Anwendung veranschaulicht.

```
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic starter kit</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyStarterKit.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Weitere Informationen
- [Visual Studio-Vorlagenschemareferenz](../extensibility/visual-studio-template-schema-reference.md)
- [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)
- [ProjectItem-Element (Visual Studio-Projektvorlagen)](../extensibility/projectitem-element-visual-studio-project-templates.md)
- [Ordnerelement (Visual Studio-Projektvorlagen)](../extensibility/folder-element-visual-studio-project-templates.md)
