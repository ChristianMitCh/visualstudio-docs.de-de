---
title: 'Exemplarische Vorgehensweise: LinqToXmlDataBinding-Beispiel | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0e97d612e19f64110f3090029dcff82acbad8e87
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663969"
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>Exemplarische Vorgehensweise: LinqToXmlDataBinding-Beispiel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird das &lt;legacyBold&gt;LinqToXmlDataBinding&lt;/legacyBold&gt;-Beispiel beschrieben, und es werden einige wichtige Aspekte seiner beiden primären Quelldateien &lt;legacyBold&gt;L2DBForm.xaml&lt;/legacyBold&gt; und &lt;legacyBold&gt;L2DBForm.xaml.cs&lt;/legacyBold&gt; erläutert.

## <a name="prerequisites"></a>Erforderliche Voraussetzungen
 Bevor Sie sich diese exemplarische Vorgehensweise durchlesen, wird dringend empfohlen, das LinqToXmlDataBinding-Programm, wie in [Vorgehensweise: Erstellen und Ausführen des LinqToXmlDataBinding-Beispiels](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md) beschrieben, zu erstellen und auszuführen.

## <a name="remarks"></a>Hinweise
 Das LinqToXmlDataBinding-Programm ist eine WPF-Anwendung (Windows Presentation Foundation), die aus C#- und XAML-Quelldateien besteht. Es enthält ein eingebettetes XML-Dokument, das eine Liste von Büchern definiert. Das Programm versetzt den Benutzer in die Lage, diese Einträge anzuzeigen, hinzuzufügen, zu löschen und zu bearbeiten. Das Programm setzt sich aus den folgenden beiden primären Quelldateien zusammen:

- &lt;legacyBold&gt;L2DBForm.xaml&lt;/legacyBold&gt; enthält den XAML-Deklarationscode für die Benutzeroberfläche des Hauptfensters. Außerdem enthält die Datei den Abschnitt Window.Resources, in dem ein Datenanbieter und ein eingebettetes XML-Dokument für die Bücherlisten definiert sind.

- L2DBForm.xaml.cs enthält die Initialisierungs- und Ereignishandlingmethoden, die der Benutzeroberfläche zugeordnet sind.

  Das Hauptfenster ist in die folgenden vier vertikalen Benutzeroberflächenabschnitte unterteilt:

- **XML**: Zeigt die unformatierte XML-Quelle der eingebetteten Bücherliste an.

- **Book List** (Bücherliste): Zeigt die Bucheinträge als Standardtext an, und versetzt den Benutzer in die Lage, einzelne Einträge auszuwählen und zu löschen.

- **Edit Selected Book** (Ausgewähltes Buch bearbeiten): Ermöglicht es dem Benutzer, die dem aktuell ausgewählten Bucheintrag zugeordneten Werte zu bearbeiten.

- **Add New Book** (Neues Buch hinzufügen): Ermöglicht das Erstellen eines neuen Bucheintrags anhand der vom Benutzer eingegebenen Werte.

## <a name="in-this-section"></a>In diesem Abschnitt

|Topic|Beschreibung|
|-----------|-----------------|
|[L2DBForm.xaml-Quellcode](../designers/l2dbform-xaml-source-code.md)|Enthält den Inhalt und die Beschreibung des XAML-Codes in der Datei L2DBForm.xaml.|
|[L2DBForm.xaml.cs Source Code](../designers/l2dbform-xaml-cs-source-code.md)|Enthält den Inhalt und die Beschreibung des C#-Quellcodes in der Datei L2DBForm.xaml.cs.|

## <a name="see-also"></a>Siehe auch
 [WPF-Datenbindung unter Verwendung LINQ to XML Beispiels](../designers/wpf-data-binding-using-linq-to-xml-example.md) Gewusst [wie: Erstellen und Ausführen des LinqToXmlDataBinding-Beispiels](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)
