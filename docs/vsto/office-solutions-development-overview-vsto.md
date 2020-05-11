---
title: Übersicht über die Entwicklung von Office-Lösungen (VSTO)
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies, Office
- Office development in Visual Studio, about developing solutions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: abb58d30e33ab5cfe713175b40cd32f593921ae9
ms.sourcegitcommit: 054815dc9821c3ea219ae6f31ebd9cd2dc8f6af5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80543950"
---
# <a name="office-solutions-development-overview-vsto"></a>Übersicht über die Entwicklung von Office-Lösungen (VSTO)
  Wenn Sie Microsoft Office als Front-End für Projektmappen verwenden, können Sie die vertrauten Microsoft Office-Benutzeroberflächen und -Tools verwenden, z. B. die Textverarbeitungsfunktionen in Word, die Datenanalysefunktionen von Excel und die E-Mail-Verwaltungsfunktionen von Outlook. Sie können Projektmappen in Visual Studio entwickeln, um Office-Anwendungen anzupassen und die speziellen Funktionen hinzuzufügen, die Sie für Ihre Geschäftsprozesse benötigen. Beispielsweise können Sie Word in einen Vertragsgenerator verwandeln, mit dem Verträge aus bereits vorhandenen Teilen zusammengestellt werden können. Die Teile können dabei bearbeitbar oder nicht bearbeitbar sein. Mit Excel können Sie ein automatisiertes Budgetarbeitsblatt erstellen, das für unterschiedliche Projekte angepasst werden kann. Ihre Benutzer können Bürolösungen auch offline verwenden. Dies ist bei komplexen Lösungen praktikabler als die Verwendung einer webbasierten Architektur.

 Dieses Thema enthält eine Übersicht über die Arten von Office-Lösungen, die Sie mit den Vorlagen vom Typ "Visual Studio-Tools für Office" (VSTO) erstellen können. Sie sind in den Office Developer Tools von Visual Studio enthalten. Allgemeine Informationen zur Entwicklung mit Office finden Sie im [Office-Entwicklercenter](https://developer.microsoft.com/office).

## <a name="choose-an-office-project-type"></a>Auswählen eines Office-Projekttyps
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] stellt die folgenden Arten von Projektvorlagen für die VSTO-basierte Office-Entwicklung bereit:

- **Anpassungen auf Dokumentebene** sind mit einem bestimmten Dokument verknüpft.

- **VSTO Add-ins** sind mit der Anwendung selbst verknüpft.

  Für die Entscheidung, welche dieser Projekttypen für Ihre Lösung am besten geeignet ist, sollten Sie sich folgende Frage stellen: Möchten Sie, dass Ihr Code nur ausgeführt wird, wenn ein bestimmtes Dokument geöffnet ist, oder soll der Code immer verfügbar sein, wenn die Anwendung ausgeführt wird. Weitere Informationen zu den Projektvorlagen finden Sie unter Übersicht über [Office-Projektvorlagen](../vsto/office-project-templates-overview.md).

  Welche Typen von Projekten Sie erstellen können, hängt davon ab, welche Office-Anwendungen Sie auf dem Entwicklungscomputer installiert haben. Weitere Informationen finden Sie unter Features, die [von Office-Anwendung und Projekttyp verfügbar sind.](../vsto/features-available-by-office-application-and-project-type.md)

### <a name="document-level-customizations"></a>Anpassungen auf Dokumentebene
 Anpassungen auf Dokumentebene bestehen aus einer Assembly, die einem einzelnen Dokument, einer Arbeitsmappe oder einer Vorlage in Microsoft Office Word oder Microsoft Office Excel zugeordnet ist. Dies Assembly wird geladen, wenn das zugeordnete Dokument geöffnet wird. Funktionen in von Ihnen erstellten Anpassungen sind nur verfügbar, wenn das zugeordnete Dokument geöffnet ist. Mit Anpassungen können keine anwendungsweiten Änderungen vorgenommen werden, z. B. das Anzeigen eines neuen Menüelements oder einer Menübandregisterkarte, wenn ein Dokument geöffnet ist.

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] enthält Tools, die für die Erstellung von Anpassungen auf Dokumentebene hilfreich sind. Das Dokument, das Sie anpassen, wird in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]als Entwurfsoberfläche gehostet. So können Sie das Dokument entwerfen, indem Sie Steuerelemente ziehen und darauf ablegen. Für Projekte auf Dokumentebene sind noch viele weitere [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] -Funktionen verfügbar, z. B. Windows Forms-Steuerelemente, Drag &amp; Drop-Datenbindung und ein integrierter Debugger.

 Weitere Informationen zu Anpassungen finden Sie in den folgenden Themen:

- [Erste Schritte beim Programmieren von Anpassungen auf Dokumentebene für Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md)

- [Erste Schritte beim Programmieren von Anpassungen auf Dokumentebene für Word](../vsto/getting-started-programming-document-level-customizations-for-word.md)

- [Architektur von Anpassungen auf Dokumentebene](../vsto/architecture-of-document-level-customizations.md)

### <a name="vsto-add-ins"></a>VSTO-Add-Ins
 VSTO-Add-Ins bestehen aus einer Assembly, die einer Microsoft Office-Anwendung zugeordnet ist. Normalerweise wird das VSTO-Add-In ausgeführt, wenn die zugeordnete Anwendung gestartet wird, Benutzer können VSTO-Add-Ins aber auch laden, nachdem die Anwendung bereits ausgeführt wird. Funktionen in VSTO-Add-Ins, die Sie erstellen, sind für die eigentliche Anwendung verfügbar. Dabei spielt es keine Rolle, welche Dokumente geöffnet sind.

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]enthält Tools, mit denen Sie VSTO-Add-Ins erstellen können. Add-In-Projekte enthalten eine automatisch generierte Klasse, die das VSTO-Add-In darstellt. Diese Klasse stellt Eigenschaften und Ereignisse bereit, mit denen Sie auf das Objektmodell der Hostanwendung zugreifen und Code ausführen können, wenn das VSTO-Add-In geladen und heruntergefahren wird. Es sind noch viele weitere [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] -Funktionen in VSTO-Add-In-Projekten verfügbar, z. B. Windows Forms und ein integrierter Debugger.

 Weitere Informationen zu VSTO-Add-Ins finden Sie unter den folgenden Themen:

- [Erste Schritte mit der Programmierung von VSTO-Add-Ins](../vsto/getting-started-programming-vsto-add-ins.md)

- [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)

## <a name="automate-office-applications-by-using-primary-interop-assemblies"></a>Automatisieren von Office-Anwendungen mithilfe primärer Interopassemblys
 Sie können die Funktionen einer Office-Anwendung programmgesteuert in Ihre Projektmappe einbinden, indem Sie Code schreiben, mit dem auf das Objektmodell der Anwendung zugegriffen wird. Bei Objektmodellen handelt es sich um eine Anordnung von Klassen, mit denen die Funktionalität unter Verwendung verschiedener Eigenschaften und Methoden verfügbar gemacht wird. Das Objektmodell ist für jede Office-Anwendung anders.

 Sie müssen die primäre Interopassembly (PIA) für die Anwendung verwenden, um das Objektmodell einer Office-Anwendung aus einer Projektmappe zu nutzen, die mit den Office-Entwicklungstools in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]erstellt wurde. Mit der PIA kann der verwaltete Code in Ihrer Projektmappe mit dem COM-basierten Objektmodell der Office-Anwendung interagieren.

 Die Office-PIAs müssen im globalen Assemblycache auf dem Entwicklungscomputer installiert und registriert sein, damit Sie die meisten Entwicklungsaufgaben ausführen können. Weitere Informationen finden Sie unter [Konfigurieren eines Computers zum Entwickeln von Office-Lösungen](../vsto/configuring-a-computer-to-develop-office-solutions.md). Zur Ausführung von VSTO-Office-Projektmappen sind die Office-PIAs auf Endbenutzercomputern nicht erforderlich. Weitere Informationen finden Sie unter [Entwerfen und Erstellen von Office-Lösungen](../vsto/designing-and-creating-office-solutions.md).

 Weitere Informationen zum Verwenden der PIAs in VSTO-Office-Projektmappen finden Sie unter den folgenden Themen:

- [Schreiben von Code in Office-Lösungen](../vsto/writing-code-in-office-solutions.md)

- [Primäre Interopassemblys von Office](../vsto/office-primary-interop-assemblies.md)

## <a name="run-microsoft-vsto-office-solutions-on-end-user-computers"></a>Ausführen von Microsoft VSTO Office-Lösungen auf Endbenutzercomputern
 Berücksichtigen Sie beim Erstellen einer VSTO-Office-Projektmappe, wie sich die Bereitstellungsanforderungen auf Ihre Entwicklungsentscheidungen auswirken.

### <a name="deployment-options"></a>Bereitstellungsoptionen
 Verwenden Sie ClickOnce oder Windows Installer zum Bereitstellen von Projektmappen, die Sie mit den Office-Entwicklungstools in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]erstellen. Mit der ClickOnce-Bereitstellung können Sie sich selbst aktualisierende Projektmappen erstellen, die mit minimaler Benutzerinteraktion installiert und ausgeführt werden können. Windows Installer -*.msi*) Dateien können einfach an Endbenutzercomputer verteilt werden, oder mit Systems Management Server (SMS). Weitere Informationen zum Bereitstellen von VSTO Office-Lösungen finden Sie unter [Bereitstellen einer Office-Lösung](../vsto/deploying-an-office-solution.md).

### <a name="install-prerequisites"></a>Installieren der erforderlichen Komponenten
 Bevor Endbenutzer eine Projektmappe ausführen können, die Sie mit den Office-Entwicklungstools in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]erstellen, müssen auf deren Computern bestimmte erforderliche Komponenten installiert werden. Wenn Sie Ihre Projektmappe per ClickOnce oder per Erstellung einer Windows Installer-Datei bereitstellen, können diese erforderlichen Komponenten mit Ihrer Projektmappe installiert werden. Weitere Informationen finden Sie unter [Office-Lösungsvoraussetzungen für](https://msdn.microsoft.com/9f672809-43a3-40a1-9057-397ce3b5126e) die Bereitstellung und [Gewusst wie: Installieren von Voraussetzungen auf Endbenutzercomputern zum Ausführen von Office-Lösungen](https://msdn.microsoft.com/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).

### <a name="security"></a>Sicherheit
 Die Sicherheit für VSTO-Office-Projektmappen wird mit einer Reihe von Prüfungen durchgesetzt, die von [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] durchgeführt werden, wenn die Projektmappe installiert und geladen wird. Bei diesen Prüfungen wird unter anderem überprüft, ob der Speicherort des Bereitstellungsmanifests vertrauenswürdig ist oder ob das Zertifikat, mit dem das Bereitstellungsmanifest signiert wurde, vertrauenswürdig ist. Weitere Informationen finden Sie unter [Secure Office-Lösungen](../vsto/securing-office-solutions.md).

## <a name="see-also"></a>Siehe auch
- [Erste Schritte &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Architektur von Anpassungen auf Dokumentebene](../vsto/architecture-of-document-level-customizations.md)
- [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)
- [Erste Schritte beim Programmieren von Anpassungen auf Dokumentebene für Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md)
- [Erste Schritte beim Programmieren von Anpassungen auf Dokumentebene für Word](../vsto/getting-started-programming-document-level-customizations-for-word.md)
- [Erste Schritte mit der Programmierung von VSTO-Add-Ins](../vsto/getting-started-programming-vsto-add-ins.md)
