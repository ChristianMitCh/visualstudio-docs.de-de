---
ms.openlocfilehash: 1e6c6714720d652fff266e3e852d01982c98e34a
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84173879"
---
Web Deploy 3.6 für Hostingserver umfasst zusätzliche Konfigurationsfeatures für die Erstellung der Datei mit Veröffentlichungseinstellungen über die Benutzeroberfläche.

1. Wenn Sie Web Deploy 3.6 bereits in Windows Server installiert haben, führen Sie über **Einstellungen** > **Programme** > **Uninstall a Program** (Programm deinstallieren) eine Deinstallation durch.

2. Installieren Sie anschließend Web Deploy 3.6 für Hostingserver in Windows Server.

    Verwenden Sie den Webplattform-Installer (Web PI) für die Installation von Web Deploy für Hostingserver. (Sie finden den Link zum Web PI über IIS, wenn Sie links im Server-Manager auf **IIS** klicken. Klicken sie zuerst im Serverbereich mit der rechten Maustaste auf den Server, und wählen Sie dann **Internet Information Services (IIS) Manager (Internetinformationsdienste-Manager)** aus. Verwenden Sie dann den Link **Neue Webplattformkomponenten abrufen** im Fenster **Aktionen**. Sie können den Webplattform-Installer (Web PI) auch über [Downloads](https://www.microsoft.com/web/downloads/platform.aspx) abrufen.

    Im Webplattform-Installer finden Sie **Web Deploy 3.6 für Hostingserver** auf der Registerkarte „Anwendungen“.

3. Installieren Sie, falls noch nicht geschehen, die **Verwaltungsskripts und -tools für IIS**.

    Navigieren Sie zu **Serverrollen auswählen** > **Web Server (IIS)**  > **Verwaltungstools**, wählen Sie die Rolle **IIS Management Scripts and Tools** (Verwaltungsskripts und -tools für IIS) aus, klicken Sie auf **Weiter**, und installieren Sie die Rolle.

    ![Installieren von Verwaltungsskripts und -tools für IIS](../../deployment/media/tutorial-iis-management-scripts-and-tools.png)

    Sie müssen die Skripts und Tools installieren, damit die Datei mit Veröffentlichungseinstellungen erstellt werden kann.

4. (Optional) Überprüfen Sie, ob Web Deploy korrekt ausgeführt wird, indem Sie **Einstellungen > System and Security (System und Sicherheit) > Verwaltung > Dienste** öffnen und sich vergewissern, dass der **Webbereitstellungs-Agent-Dienst**  ausgeführt wird (in älteren Versionen ist dieser Dienst anders benannt).

    Wenn der Agent-Dienst noch nicht ausgeführt wird, starten Sie ihn. Wenn er gar nicht vorhanden ist, navigieren Sie zu **Einstellungen > Programm > Uninstall a program** (Programm deinstallieren), und suchen Sie **Microsoft Web Deploy\<version>** . **Ändern** Sie die Installation, und vergewissern Sie sich, dass Sie für die Web Deploy-Komponenten **Will be installed to the local hard drive** (Wird auf der lokalen Festplatte installiert) auswählen. Führen Sie die Schritte zur Änderung der Installation durch.