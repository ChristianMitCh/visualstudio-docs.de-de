---
title: Übersicht über die Benutzeroberfläche von DSL-Tools | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: overview
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: 27
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3bffb1f7fe6449f078c21c14b0a070cbd23db539
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2020
ms.locfileid: "72652125"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Übersicht über die Benutzeroberfläche für domänenspezifische Sprachtools
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Wenn Sie zum ersten Mal eine Projektmappe für DSL-Tools (Domain-Specific Language Tools) in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] öffnen, sieht die Benutzeroberfläche in etwa wie folgt aus:

 ![DSL-Designer](../modeling/media/dsl-designer.png "dsl_designer")

 In der folgenden Tabelle wird erläutert, wie die einzelnen Bestandteile der Benutzeroberfläche verwendet werden.

|**Element**|**Definition**|
|-----------------|--------------------|
|Diagramm|Das Diagramm zeigt das Domänenmodell an.<br /><br /> Es hat zwei Seiten: Die eine Seite definiert die Elementtypen in Ihren Modellen. Die andere Seite definiert, wie Ihre Modelle auf dem Bildschirm angezeigt werden.|
|Werkzeugkasten|Ziehen Sie Tools aus der Toolbox, um Domänenklassen hinzuzufügen und um Typen für das Diagramm zu formen. Wenn Sie Beziehungen, Connectors und Formzuordnungen hinzufügen möchten, klicken Sie erst auf das Tool, dann auf den Quellknoten im Diagramm und anschließend auf den Zielknoten.|
|DSL-Explorer|Der **DSL-Explorer** wird angezeigt, wenn die DSL-Definition in einem aktiven Fenster angezeigt wird. Er stellt die DSL als Struktur dar. Sie können mithilfe des DSL-Explorers Features des Modells bearbeiten, die nicht in dem Diagramm angezeigt werden. Beispielsweise können Sie Toolboxelemente hinzufügen und den Validierungsprozess mithilfe des **DSL-Explorers** starten.|
|Das Fenster „DSL-Details“|Im Fenster **DSL-Details** werden Eigenschaften der Elemente des Domänenmodells angezeigt, mit denen Sie die Anzeige, das Löschen und das Kopieren von Elementen steuern können.<br /><br /> Standardmäßig wird das Fenster **DSL-Details** neben den Fenstern **Fehlerliste** und **Ausgabe** angezeigt.|

## <a name="the-domain-model-diagram"></a>Das Domänenmodelldiagramm
 Das Domänenmodelldiagramm ist in zwei Teile unterteilt. Auf der einen Seite des Diagramms werden die Elemente und Beziehungen in dem Modell angezeigt. Auf der anderen Seite wird angezeigt, wie das Modell dargestellt werden soll und welche Formen zu verwenden sind, um die Elemente und Eigenschaften des Modelldiagramms anzuzeigen. Die folgende Abbildung veranschaulicht die Elemente des Diagramms.

 ![DSL-Designer mit Swimlane](../modeling/media/dsl-desinger.png "dsl_desinger")

 In der folgenden Tabelle werden einige Elemente des Domänenmodelldiagramms erläutert.

|**Begriff**|**Definition**|
|--------------|--------------------|
|Domänenklasse|Die Domänenklassen sind die Elementtypen in Ihren Modellen.<br /><br /> Eine Domänenklasse kann mehrmals in einem Diagramm angezeigt werden, wenn sie Ziel von mehreren Beziehungen ist.<br /><br /> Wenn Sie eine Domänenklasse hinzufügen möchten, ziehen Sie das Domänenklassentool aus der **Toolbox** auf die Diagrammseite **Klassen und Beziehungen**.|
|Domänenbeziehung|Domänenbeziehungen stellen die Verbindungen zwischen einzelnen Elementen in Ihren Modellen dar.<br /><br /> Eine *Embedding Relationship* deutet darauf hin, dass das Quellelement Besitzer des Zielelements ist oder dieses enthält. Für diese Art von Beziehung wir eine durchgezogene Linie verwendet. Jedes Element in einem Modell sollte das Ziel einer Embedding Relationship sein, damit eine Modellstruktur entsteht. Eine *Verweisbeziehung* deutet auf eine allgemeine Verbindung zwischen Modellelementen hin, die durch gestrichelte Linien kenntlich gemacht werden. Für jedes Element können beliebig viele Verweisbeziehungen bestehen.<br /><br /> Sie können eine Beziehung erstellen, indem Sie in der **Toolbox** erst auf das Tool, dann auf die Quelldomänenklasse und dann auf die Zielklasse klicken.|
|Formen und Konnektoren|Formen geben an, wie Modellelemente in einem DSL-Diagramm angezeigt werden sollen, und Connectors geben Zeilen auf einem DSL-Diagramm an, die zum Anzeigen von Beziehungen verwendet werden können.<br /><br /> Wenn Sie eine Form oder einen Connector erstellen möchten, ziehen Sie das Tool zur Seite **Diagram Elements** (Diagrammelemente) des Diagramms.|
|Formzuordnungen|Eine Formzuordnung wird im Domänenmodelldiagramm in Form einer Linie dargestellt, die eine Form mit der angezeigten Domänenklasse oder einen Connector mit der angezeigten Domänenbeziehung verbindet.|

## <a name="see-also"></a>Siehe auch
 [Übersicht über domänenspezifische Sprachtools](../modeling/overview-of-domain-specific-language-tools.md) [Glossar für DSL-Tools](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa) [Anpassen und Erweitern einer domänenspezifischen Sprache](../modeling/customizing-and-extending-a-domain-specific-language.md)
