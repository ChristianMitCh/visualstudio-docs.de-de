---
title: Beschreibung Element (Visual Studio Vorlagen) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Description element [Visual Studio project templates]
ms.assetid: 6e12be73-081f-4c7d-898f-027c307a9fe1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ea10b43662d2818792dbc57aeac09a056cb63ce
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80712258"
---
# <a name="description-element-visual-studio-templates"></a>Beschreibungselement (Visual Studio-Vorlagen)
Gibt die Beschreibung der Vorlage an, wie sie im Dialogfeld **Neues Projekt** oder Neues **Element hinzufügen** angezeigt wird.

 \<VSTemplate \<> TemplateData> \<Beschreibung>

## <a name="syntax"></a>Syntax

```
<Description>
    Template Description
</Description>
```

```
<Description Package="{PackageID}" ID="ResourceID" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`Package`|Optionales Attribut für erweiterte Benutzerszenarien.<br /><br /> Eine GUID, die die Visual Studio-Paket-ID angibt.|
|`ID`|Optionales Attribut für erweiterte Benutzerszenarien.<br /><br /> Gibt die Visual Studio-Ressourcen-ID an.|

### <a name="child-elements"></a>Untergeordnete Elemente
 Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Erforderliches Element<br /><br /> Kategorisiert die Vorlage und definiert, wie diese in den Dialogfeldern **Neues Projekt** oder **Neues Element hinzufügen** angezeigt wird.|

## <a name="text-value"></a>Textwert
 Ein Textwert ist erforderlich, es sei denn, die Attribute `Package` und `ID` werden verwendet.

 Der Text enthält eine Beschreibung der Vorlage.

## <a name="remarks"></a>Bemerkungen
 `Description`ist ein erforderliches `TemplateData` untergeordnetes Element des Elements.

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
