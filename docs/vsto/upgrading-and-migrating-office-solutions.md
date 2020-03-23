---
title: Aktualisieren und Migrieren von Office-Lösungen
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], upgrading
- Office projects [Office development in Visual Studio], upgrading
- upgrading applications [Office development in Visual Studio]
- upgrading Office solutions in Visual Studio
- migrating Office solutions in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5e421d6e4ee94d9974c0a0583db1fb495c72593e
ms.sourcegitcommit: b32fbbcbc43910b0ed7ce79aa9a22f2ed36ab57e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416535"
---
# <a name="upgrade-and-migrate-office-solutions"></a>Aktualisieren und Migrieren von Office-Lösungen
  Wenn Sie über ein Microsoft Office-Projekt verfügen, das in einer früheren Version von Visual Studio erstellt wurde, müssen Sie das Projekt aktualisieren, um es in der aktuellen Version von Visual Studio verwenden zu können. Um ein Microsoft Office-Projekt zu aktualisieren, öffnen Sie es in einer Version von Visual Studio, die die Microsoft Office-Entwicklertools umfasst. Weitere Informationen zu den Versionen von Visual Studio, zu denen die Microsoft Office-Entwicklertools gehören, finden Sie unter [Konfigurieren eines Computers zum Entwickeln von Office-Lösungen](../vsto/configuring-a-computer-to-develop-office-solutions.md).

[!include[Add-ins note](includes/addinsnote.md)]

> [!NOTE]
> Von Visual Studio können keine InfoPath-Formularvorlagenprojekte aktualisiert werden, die mit früheren Versionen von Visual Studio erstellt wurden. Diese Projekttypen werden in der aktuellen Version von Visual Studio nicht unterstützt.

## <a name="changes-to-upgraded-projects"></a>Änderungen an aktualisierten Projekten
 Wenn Sie ein Microsoft Office-Projekt aktualisieren, ändert Visual Studio das Projekt so, dass die folgenden Elemente als Ziel verwendet werden:

- Die Visual Studio 2010-Tools für Office-Laufzeit. Weitere Informationen finden Sie unter [Visual Studio Tools for Office-Laufzeitübersicht](../vsto/visual-studio-tools-for-office-runtime-overview.md).

- Die aktuellen Assemblyverweise.

- Eine Version von .NET Framework, die vom Projekttyp unterstützt wird (nur bei einem Upgrade auf Visual Studio 2013).

- Eine Version von Microsoft Office, die vom Projekttyp unterstützt wird (nur bei einem Upgrade auf Visual Studio 2013).

## <a name="assembly-references"></a>Assemblyverweise
 Die folgenden Assemblyverweise im Projekt werden aktualisiert:

- Primäre Interop-Assemblys für Microsoft Office (PIAS).

- Assemblys in [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Weitere Informationen zu diesen Assemblys finden Sie unter [Visual Studio Tools for Office-Laufzeitübersicht](../vsto/visual-studio-tools-for-office-runtime-overview.md).

- Neue oder aktualisierte Versionen abhängiger Assemblys.

## <a name="targeted-net-framework"></a>Als Ziel festgelegte .NET Framework-Version
 Wenn Sie ein Upgrade eines Projekts auf Visual Studio 2013 ausführen, ändert Visual Studio das Projekt für die Verwendung von [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] oder [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]als Zielversion. Die vom Projekt als Ziel verwendete Version von .NET Framework hängt davon ab, welche Version von Office auf dem Computer installiert ist. Wenn nur [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] installiert ist, ändert Visual Studio das Projekt für die Verwendung von [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]als Ziel. Andernfalls ändert Visual Studio das Projekt für die Verwendung von [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]als Ziel.

> [!NOTE]
> Unter Umständen sind einige zusätzliche Schritte erforderlich, um eine neu zugewiesene Lösung auf Entwicklungs- und Endbenutzercomputern auszuführen. Das Projekt wird nicht mehr kompiliert, wenn darin bestimmte Funktionen verwendet werden. Weitere Informationen finden Sie unter [Migrieren von Office-Lösungen zu .NET Framework 4 oder höher](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).

 Wenn Sie in einem Office-Projekt [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher als Zielversion festlegen, können Sie einige Features verwenden, die nicht verfügbar sind, wenn .NET Framework 3.5 als Zielversion festgelegt wird. Weitere Informationen finden Sie unter [Entwerfen und Erstellen von Office-Lösungen](../vsto/designing-and-creating-office-solutions.md).

## <a name="targeted-office-application"></a>Gezielte Office-Anwendung
 Wenn Sie ein Upgrade eines Office-Projekts auf Visual Studio 2013 ausführen, ändert Visual Studio das Projekt so, dass eine Version von Microsoft Office als Zielversion verwendet wird, die durch den Projekttyp unterstützt wird, z. B. ein Anpassungsprojekt auf Dokumentebene oder ein VSTO-Add-In-Projekt.

 Office-Projekte in Visual Studio 2015 können nur [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] und [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] als Zielanwendung verwenden. Visual Studio ändert das Projekt so, dass die aktuellste Version von Office als Zielversion verwendet wird, die Sie installiert haben. Wenn keine dieser Versionen von Office installiert ist, aktualisiert Visual Studio das Projekt nicht.

> [!NOTE]
> Wenn Sie ein VSTO-Add-In-Projekt auf Das [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] `ThisAddIn_Startup` Ziel oder höher aktualisieren, stellen Sie sicher, dass der Ereignishandler des VSTO-Add-Ins keinen Code enthält, der auf ein Dokument in der Anwendung zugreift. Weitere Informationen finden Sie [unter Zugriff auf ein Dokument beim Starten der Office-Anwendung](../vsto/programming-vsto-add-ins.md#AccessingDocuments).

 Konvertiert für Anpassungen [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] auf Dokumentebene Dokumente in einem Projekt mit einem binären Format, z. B. Dokumente mit *.xls* oder *.doc-Erweiterung,* in das Office Open XML-Format. Weitere Informationen zu Open XML finden Sie unter [Einführung in neue Dateinamenerweiterungen und Open XML-Formate](https://support.office.com/en-nz/article/Introduction-to-new-file-name-extensions-eca81dcb-5626-4e5b-8362-524d13ae4ec1).

> [!NOTE]
> Smarttags sind in Excel 2010 und Word 2010 veraltet. Wenn Ihre Projektmappe Smarttags verwendet, müssen Sie diese entfernen, bevor Sie sie in Visual Studio 2013 oder Visual Studio 2015 testen und debuggen können.

## <a name="upgrade-microsoft-office-2003-projects"></a>Aktualisieren von Microsoft Office 2003-Projekten
 Für die Aktualisierung von Anpassungen auf Dokumentebene und VSTO-Add-Ins für Microsoft Office 2003 gelten einige weitere Überlegungen.

### <a name="document-level-projects"></a>Projekte auf Dokumentebene
 Falls das Dokument im Projekt Windows Forms-Steuerelemente enthält, müssen Sie die Visual Studio 2005-Tools für Office Second Edition-Laufzeit installieren, bevor Sie das Projekt aktualisieren. Wenn diese Version der Laufzeit vor dem Aktualisieren des Projekts nicht auf dem Entwicklungscomputer installiert wird, können im aktualisierten Projekt Kompilier- oder Laufzeitfehler auftreten. Nachdem Sie das Projekt aktualisiert haben, können Sie die Visual Studio 2005-Tools für Office Second Edition-Laufzeit vom Entwicklungscomputer deinstallieren, wenn sie nicht von anderen Office-Projektmappen verwendet wird. Diese Version der Laufzeit steht im Microsoft Download Center unter [Microsoft Visual Studio 2005-Tools für Office Second Edition-Laufzeit (VSTO 2005 SE) (x86)](https://www.microsoft.com/download/details.aspx?id=2392)als verteilbares Paket zur Verfügung.

### <a name="vsto-add-in-projects"></a>VSTO-Add-In-Projekte
 Wenn die Projektmappendatei für das ursprüngliche Projekt ein Setup- oder InstallShield Limited Edition-Projekt enthielt, das dafür konfiguriert war, das VSTO-Add-In zu installieren, aktualisiert Visual Studio das Projekt, nimmt jedoch keine weiteren Änderungen am Projekt vor. Wenn Sie das VSTO-Add-In weiterhin mit einer Windows Installer-Datei bereitstellen möchten, muss das Setup- oder InstallShield Limited Edition-Projekt so geändert werden, dass neue erforderliche Komponenten wie [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], Visual Studio 2010 Tools für Office-Laufzeit und optional die primären Interopassemblys, auf die durch das VSTO-Add-In verwiesen wird, installiert werden. Weitere Informationen finden Sie unter [Bereitstellen einer Office-Lösung mithilfe von Windows Installer](../vsto/deploying-a-vsto-solution-by-using-windows-installer.md).

 Wenn Sie das VSTO-Add-In mit ClickOnce bereitstellen möchten, können Sie das Setup- oder das InstallShield Limited- Edition-Projekt vollständig löschen. Weitere Informationen zum Bereitstellen von VSTO-Add-Ins mithilfe von ClickOnce finden Sie unter [Bereitstellen einer Office-Lösung](../vsto/deploying-an-office-solution.md).

## <a name="see-also"></a>Weitere Informationen
- [Gewusst wie: Aktualisieren von Office-Lösungen](https://msdn.microsoft.com/a269e539-b717-4680-a568-2152b070347e)
- [Migrieren von Office-Lösungen zu .NET Framework 4 oder höher](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)
- [Dialogfeld "Projektaktualisierung", "Optionen"](../vsto/project-upgrade-options-dialog-box.md)
