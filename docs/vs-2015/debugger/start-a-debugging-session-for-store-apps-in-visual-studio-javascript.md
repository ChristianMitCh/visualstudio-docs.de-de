---
title: Starten einer Debugsitzung für Store Apps (JavaScript) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: fb91203f-2cf4-44d3-8ed9-93bc5aaa50b8
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4b4e861c8985ee37a8c2d9b7f9286d6284bb4f91
ms.sourcegitcommit: 95f26af1da51d4c83ae78adcb7372b32364d8a2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "79301380"
---
# <a name="start-a-debugging-session-for-store-apps-in-visual-studio-javascript"></a>Starten einer Debugsitzung für Store-Apps in Visual Studio (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Gilt für Windows und Windows Phone](.. /Bild/windows_and_phone_content.png "windows_and_phone_content")

 In diesem Thema wird beschrieben, wie Sie eine Debugsitzung für in JavaScript und HTML5 geschriebene Windows Store-Apps starten können. Sie können das Debuggen mit einer einzigen Tastatureingabe starten, oder Sie können die Debugsitzung für bestimmte Szenarien konfigurieren und dann die Methode auswählen, mit der die App gestartet wird.

> [!NOTE]
> Informationen zu Apps, die in XAML und Visual C, Visual C++ oder Visual Basic geschrieben wurden, finden Sie unter [Starten einer Debugsitzung (VB, C, C++ und XAML).](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)

## <a name="in-this-topic"></a><a name="BKMK_In_this_topic"></a>In diesem Thema
 [In diesem Thema](#BKMK_In_this_topic)

 [Die einfache Methode zum Starten des Debuggings](#BKMK_The_easy_way_to_start_debugging)

 [Konfigurieren der Debugsitzung](#BKMK_Configure_the_debugging_session)

- [Öffnen Sie die Debugeigenschaftenseite für das Projekt](#BKMK_Open_the_debugging_property_page_for_the_project)

- [Wählen Sie die Buildkonfigurationsoptionen aus.](#BKMK_Choose_the_build_configuration_options)

- [Wählen Sie das Bereitstellungsziel](#BKMK_Choose_the_deployment_target)

- [Wählen Sie den zu verwendenden Debugger aus.](#BKMK_Choose_the_debugger_to_use)

- [(Optional) Verzögertes Starten der App in der Debugsitzung](#BKMK__Optional__Delay_starting_app_in_the_debug_session)

- [(Optional) Deaktivieren von Netzwerk-Loopbacks](#BKMK__Optional__Disable_network_loopbacks)

  [Starten der Debugsitzung](#BKMK_Start_the_debugging_session)

- [Debuggen starten (F5)](#BKMK_Start_debugging__F5_)

- [Starten des Debuggens (F5) jedoch verzögerter Anwendungsstart](#BKMK_Start_debugging__F5__but_delay_the_app_start)

  [Starten einer installierten App im Debugger](#BKMK_Start_an_installed_app_in_the_debugger)

  [Anfügen des Debuggers an eine ausgeführte App](#BKMK_Attach_the_debugger_to_a_running_app_)

- [Festlegen der App für die Ausführung im Debugmodus](#BKMK_Set_the_app_to_run_in_debug_mode)

- [Fügen Sie den Debugger an.](#BKMK_Attach_the_debugger)

## <a name="the-easy-way-to-start-debugging"></a><a name="BKMK_The_easy_way_to_start_debugging"></a>Die einfache Möglichkeit, mit dem Debuggen zu beginnen
 ![Gilt nur für Windows](../debugger/media/windows-only-content.png "windows_only_content")

1. Öffnen Sie in Visual Studio die Anwendungsprojektmappe.

2. Wenn die Projektmappe Projekte für Windows Store- und Windows Phone Store-Apps enthält, muss das zu debuggende Projekt das Startprojekt sein. Wählen Sie unter Projektlösungsumgebung das Projekt aus, und wählen Sie dann im Kontextmenü **Als Startupprojekt festlegen** aus.

3. Drücken Sie F5.

   ![Gilt nur für Windows Phone](../debugger/media/phone-only-content.png "phone_only_content")

   In Visual Studio wird die Anwendung mit dem angefügten Debugger erstellt und gestartet. Die Ausführung wird fortgeführt, bis ein Haltepunkt erreicht wird, bis Sie diese manuell anhalten, bis eine unbehandelte Ausnahme auftritt, oder bis die Anwendung beendet ist. Weitere Informationen finden Sie unter [Schnellstart: Debug-HTML und CSS](../debugger/quickstart-debug-html-and-css.md).

## <a name="configure-the-debugging-session"></a><a name="BKMK_Configure_the_debugging_session"></a> Konfigurieren der Debugsitzung
 Da das Skript nicht kompiliert wird, sind die Einstellungen der Buildkonfiguration und -plattform nicht anwendbar. Wenn Sie eine C++- oder verwaltete Komponente debuggen, legen Sie die **Konfiguration** auf **Debuggen** fest, und wählen Sie Ihre Zielplattform im **Dialogfeld Konfiguration** aus.

### <a name="open-the-debugging-property-page-for-the-project"></a><a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Öffnen der Debugging-Eigenschaftsseite für das Projekt

1. Wählen Sie im Projektmappen-Explorer das Projekt aus. Wählen Sie im Kontextmenü **Eigenschaften**aus.

2. Erweitern Sie den Knoten **Konfigurationseigenschaften,** und wählen Sie dann **Debugging** aus.

### <a name="choose-the-build-configuration-options"></a><a name="BKMK_Choose_the_build_configuration_options"></a>Wählen Sie die Buildkonfigurationsoptionen

1. Wählen Sie in der Liste **Konfiguration** den Eintrag **Debuggen** oder **Aktive Konfiguration**aus.

2. Wählen Sie in der Liste **Plattform** die Zielplattform aus, in der der Build erfolgen soll. In den meisten Fällen ist **jede CPU** die beste Wahl.

### <a name="choose-the-deployment-target"></a><a name="BKMK_Choose_the_deployment_target"></a> Auswählen des Bereitstellungsziels
 Sie können eine App auf dem Visual Studio-Computer, im Visual Studio-Simulator auf dem lokalen Computer oder auf einem Remotecomputer bereitstellen und debuggen. Sie wählen das Ziel aus dem **Debugger aus, um** die Liste auf der **Eigenschaftenseite Debugging** für das Projekt zu starten.

 ![Gilt nur für Windows](../debugger/media/windows-only-content.png "windows_only_content")

 Wählen Sie für eine Windows Store-App eine der folgenden Optionen aus der Liste **Zielgeräte** aus:

|||
|-|-|
|**Lokale Maschine**|Debuggen Sie die Anwendung in der aktuellen Sitzung auf dem lokalen Computer. Weitere Informationen finden Sie unter [Ausführen von Windows Store-Apps auf dem lokalen Computer](../debugger/run-windows-store-apps-on-the-local-machine.md).|
|**Simulator**|Debuggen Sie die Anwendung im Visual Studio-Simulator für [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] -Apps. Der Simulator ist ein Desktopfenster mit dem Sie Gerätefunktionen wie z. B. die Fingereingabe und Gerätedrehung debuggen können, die nicht auf dem lokalen Computer verfügbar sind. Weitere Informationen finden Sie unter Ausführen von [Windows Store-Apps im Simulator](../debugger/run-windows-store-apps-in-the-simulator.md).|
|**Remote-Maschine**|Debuggen Sie die Anwendung auf einem Gerät, das mit dem lokalen Computer über ein Intranet oder direkt über ein Ethernetkabel verbunden ist. Zum Remotedebuggen müssen die Visual Studio-Remotetools installiert sein und auf dem Remotegerät ausgeführt werden. Weitere Informationen finden Sie unter [Ausführen von Windows Store-Apps auf einem Remotecomputer](../debugger/run-windows-store-apps-on-a-remote-machine.md).|

 Wenn Sie **Remotecomputer**auswählen, geben Sie den Namen oder die IP-Adresse des Remotecomputers auf eine der folgenden Weisen an:

- Geben Sie den Namen oder die IP-Adresse des Remotecomputers in das Feld **Computername** ein.

- Wählen Sie den Abwärtspfeil im Feld **Maschinenname** aus und wählen Sie ** \<Suchen...>**. Wählen Sie dann den Remotecomputer aus dem Dialogfeld **Remote-Debuggerverbindung auswählen** aus.

   ![Remotedebuggerverbindung auswählen](../debugger/media/vsrun-pro-selectremotedebuggerdlg.png "VSRUN_PRO_SelectRemoteDebuggerDlg")

  > [!NOTE]
  > Im Dialogfeld "Remotedebuggerverbindung auswählen" werden Computer im lokalen Subnetz sowie solche Computer angezeigt, die mit dem Visual Studio-Computer durch ein Ethernetkabel direkt verbunden sind. Um einen anderen Computer anzugeben, geben Sie den Namen im Feld **Computername** ein.

  ![Gilt nur für Windows Phone](../debugger/media/phone-only-content.png "phone_only_content")

  Wählen Sie für eine Windows Store Phone-App **Gerät** oder einen der Emulatoren aus der Liste **Zielgeräte** aus.

### <a name="choose-the-debugger-to-use"></a><a name="BKMK_Choose_the_debugger_to_use"></a> Auswahl des zu verwendenden Debuggers
 Standardmäßig wird der Debugger an den JavaScript-Code in der App angefügt. Sie können auswählen, ob Sie den systemeigenen C++-Code und den verwalteten Code von Komponenten der App anstelle des JavaScript-Codes debuggen möchten. Sie geben den zu debuggenden Code in der Liste **Debuggertyp** auf der Eigenschaftenseite **Debuggen** des App-Projekts an.

 Wählen Sie einen der folgenden Debugger aus der **Debuggertypliste** aus:

|||
|-|-|
|**Nur Skript**|Für das Debuggen des JavaScript-Codes der Anwendung. Verwalteter und systemeigener Code werden ignoriert.|
|**Nur Native**|Für das Debuggen des systemeigenen C/C++-Codes der Anwendung. Verwalteter und JavaScript-Code werden ignoriert.|
|**Nativ mit Skript**|Für das Debuggen des systemeigenen C++-Codes und des JavaScript-Codes der Anwendung.|
|**Nur verwaltet**|Für das Debuggen des verwalteten Codes der Anwendung. JavaScript- und systemeigener C/C++-Code werden ignoriert.|
|**Gemischt (verwaltet und systemeigen)**|Für das Debuggen des systemeigenen C/C++- und des verwalteten Codes der Anwendung. JavaScript-Code wird ignoriert.|

### <a name="optional-delay-starting-the-app-in-the-debug-session"></a><a name="BKMK__Optional__Delay_starting_app_in_the_debug_session"></a>(Optional) Verzögern des Startens der App in der Debugsitzung
 In der Standardeinstellung wird die Anwendung in Visual Studio sofort gestartet, wenn Sie das Debuggen starten. Sie können zudem eine Debugsitzung starten, den Start der App jedoch verzögern. Die App wird im Debugger gestartet, wenn sie über das Startmenü oder durch einen Aktivierungsvertrag bzw. durch einen anderen Prozess oder eine andere Methode gestartet wird. Mit einem verzögerten Start können Sie auch Hintergrundereignisse in der App debuggen, die auftreten sollen, wenn die App nicht ausgeführt wird.

 Sie geben an, ob der Start Ihrer App in der Liste **"Anwendung starten"** auf der **Eigenschaftenseite Debugging** des App-Projekts verzögert werden soll. Wählen Sie eine der Optionen aus:

- Wählen Sie **Nein,** um den Start Ihrer App zu verzögern.

- Wählen Sie **Ja,** um die App sofort zu starten.

### <a name="optional-disable-network-loopbacks"></a><a name="BKMK__Optional__Disable_network_loopbacks"></a> (Optional) Netzwerkloopbacks deaktivieren
 ![Gilt nur für Windows](../debugger/media/windows-only-content.png "windows_only_content")

 Aus Sicherheitsgründen wird einer im Standardverfahren installierten Windows Store-App nicht erlaubt, Netzwerkaufrufe an das Gerät auszuführen, auf dem sie installiert wurde. Standardmäßig wird durch die Visual Studio-Bereitstellung eine Ausnahme von dieser Regel für die bereitgestellte App erstellt. Diese Ausnahme ermöglicht das Testen von Kommunikationsverfahren auf einem einzelnen Computer. Bevor Sie die App an Windows Store senden, sollten Sie die App ohne die Ausnahme testen.

 Um die Netzwerk-Loopback-Ausnahme zu entfernen, wählen Sie **Nein** aus der Liste **Netzwerkschleifenback zulassen** auf der **Eigenschaftenseite Debugging** aus.

## <a name="start-the-debugging-session"></a><a name="BKMK_Start_the_debugging_session"></a>Starten der Debugsitzung

### <a name="start-debugging-f5"></a><a name="BKMK_Start_debugging__F5_"></a> Debuggen starten (F5)
 Wenn Sie im **Debugmenü** **Debuggen** starten (Tastatur: F5) auswählen, startet Visual Studio die App mit dem angefügten Debugger. Die Ausführung wird fortgeführt, bis ein Haltepunkt erreicht wird, bis Sie diese manuell anhalten, bis eine unbehandelte Ausnahme auftritt, oder bis die Anwendung beendet ist.

### <a name="start-debugging-f5-but-delay-the-app-start"></a><a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>Starten Sie das Debuggen (F5), verzögern Sie jedoch den App-Start
 Sie können die App so einrichten, dass sie im Debugmodus ausgeführt wird, aber mit einer anderen Methode als dem Debugger gestartet werden kann. Beispielsweise, um den über das Startmenü ausgeführten Start der App zu debuggen, oder um einen Hintergrundprozess aus der App zu debuggen, ohne sie zu starten. Um den App-Start zu verzögern, gehen Sie folgendermaßen vor:

1. **Wählen** Sie auf der **Seite Debug** der App-Projekteigenschaften aus der Liste **Anwendung starten** aus.

2. Wählen Sie **Debugging starten** im **Menü Debuggen** (Tastatur: F5).

3. Starten Sie die Anwendung vom Startmenü aus, über einen Ausführungsvertrag oder von einer anderen Prozedur.

   Die Anwendung wird im Debugmodus gestartet. Die Ausführung wird fortgeführt, bis ein Haltepunkt erreicht wird, bis Sie diese manuell anhalten, bis eine unbehandelte Ausnahme auftritt, oder bis die Anwendung beendet ist.

   . Weitere Informationen zum Debuggen von Hintergrundaufgaben finden Sie unter [Anhalten, Fortsetzen und Hintergrundereignisse für Windows Store auslösen)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).

## <a name="start-an-installed-app-in-the-debugger"></a><a name="BKMK_Start_an_installed_app_in_the_debugger"></a> Starten einer installierten App im Debugger
 Wenn Sie das Debugging mit F5 beginnen, erstellt Visual Studio die App, stellt sie bereit, aktiviert den Debugmodus für die App und startet sie. Um eine App zu starten, die bereits auf dem Gerät installiert ist, verwenden Sie das Dialogfeld "Installiertes App-Paket debuggen". Diese Prozedur ist nützlich, wenn Sie eine App debuggen müssen, die aus dem Windows Store installiert wurde, oder wenn Sie zwar über die Quelldateien der App, nicht jedoch über ein Visual Studio-Projekt für die App verfügen. So kann beispielsweise ein benutzerdefiniertes Buildsystem vorhanden sein, das keine Visual Studio-Projekte oder -Projektmappen verwendet.

 Die App kann auf dem lokalen Gerät oder einem Remotegerät installiert sein.  Sie können die App sofort starten oder festlegen, dass sie im Debugger ausgeführt wird, wenn ein anderer Prozess oder eine andere Methode sie startet, z. B. das Startmenü oder ein Aktivierungskontrakt. Auch um einen Hintergrundprozess zu debuggen, können Sie festlegen, dass die App im Debugmodus ausgeführt wird. Weitere Informationen finden Sie unter [Anhalten, Fortsetzen und Hintergrundereignisse für Windows Store auslösen)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).

 Um festzulegen, dass die App im Debugmodus ausgeführt wird, gehen sie folgendermaßen vor:

> [!NOTE]
> Die App darf nicht ausgeführt werden, wenn Sie mit dieser Prozedur beginnen.

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen Installed App Package**.

2. Wählen Sie eine der folgenden Optionen aus der Liste:

   |                    |                                                                                                                                                                                                                                                                                                                                                                                                           |
   |--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Lokale Maschine**  |                                                                                                                Debuggen Sie die Anwendung in der aktuellen Sitzung auf dem lokalen Computer. Weitere Informationen finden Sie unter [Ausführen von Windows Store-Apps auf dem lokalen Computer](../debugger/run-windows-store-apps-on-the-local-machine.md).                                                                                                                 |
   |   **Simulator**    | Debuggen Sie die Anwendung im Visual Studio-Simulator für [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] -Apps. Der Simulator ist ein Desktopfenster mit dem Sie Gerätefunktionen wie z. B. die Fingereingabe und Gerätedrehung debuggen können, die nicht auf dem lokalen Computer verfügbar sind. Weitere Informationen finden Sie unter Ausführen von [Windows Store-Apps im Simulator](../debugger/run-windows-store-apps-in-the-simulator.md). |
   | **Remote-Maschine** |                          Debuggen Sie die Anwendung auf einem Gerät, das mit dem lokalen Computer über ein Intranet oder direkt über ein Ethernetkabel verbunden ist. Zum Remotedebuggen müssen die Visual Studio-Remotetools installiert sein und auf dem Remotegerät ausgeführt werden. Weitere Informationen finden Sie unter [Ausführen von Windows Store-Apps auf einem Remotecomputer](../debugger/run-windows-store-apps-on-a-remote-machine.md).                           |

3. Wählen Sie die App aus der Liste **Installierte App-Pakete** .

4. Wählen Sie die Debug-Engine aus der Liste **Diesen Codetyp debuggen** .

5. (Optional). Wählen Sie **Eigenen Code zunächst nicht starten sondern debuggen** , um die App zu debuggen, wenn Sie von einer anderen Methode gestartet wird, oder um einen Hintergrundprozess zu debuggen.

   Wenn Sie auf **Starten**&gt; klicken, wird die App gestartet oder festgelegt, dass sie im Debugmodus ausgeführt werden soll.

## <a name="attach-the-debugger-to-a-running-app"></a><a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Anfügen des Debuggers an eine ausgeführte Anwendung
 Um den Debugger an eine [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] -App anzufügen, müssen Sie im Manager für debugfähige Pakete festlegen, dass die App im Debugmodus ausgeführt wird. Der Manager für debugfähige Pakete wird mit den Visual Studio-Remotetools installiert.

 Das Anfügen des Debuggers an eine App ist nützlich zum Debuggen einer bereits installierten App, beispielsweise einer App, die aus dem Windows Store installiert wurde. Das Anfügen ist erforderlich, wenn Sie über die Quelldateien für die Anwendung, nicht jedoch über ein Visual Studio-Projekt für die Anwendung verfügen. So kann beispielsweise ein benutzerdefiniertes Buildsystem vorhanden sein, das keine Visual Studio-Projekte oder -Projektmappen verwendet.

 So fügen Sie den Debugger an eine App an

1. Legen Sie die Ausführung der Anwendung im Debugmodus fest. Dies muss erfolgen, wenn die Anwendung nicht ausgeführt wird.

2. Starten Sie die App. Sie können die App über das Startmenü, einen Ausführungsvertrag oder eine andere Methode starten.

3. Fügen Sie den Debugger an die ausgeführte Anwendung an.

### <a name="set-the-app-to-run-in-debug-mode"></a><a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> Festlegen der Ausführung der Anwendung im Debugmodus

1. Installieren Sie die Visual Studio-Remotetools auf dem Gerät, auf dem die Anwendung installiert wurde. Weitere Informationen finden [Sie unter Installieren der Remotetools](https://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools).

2. Suchen Sie im Startmenü nach `Debuggable Package Manager`, und starten Sie diesen.

     Es wird ein ordnungsgemäß für das AppxDebug-Cmdlet konfiguriertes PowerShell-Fenster angezeigt.

3. Um das Debuggen einer Anwendung zu aktivieren, müssen Sie den PackageFullName-Bezeichner der App angeben. Um eine Liste aller Apps anzuzeigen, die PackageFullName enthält, geben Sie an der PowerShell-Eingabeaufforderung `Get-AppxPackage` ein.

4. Geben Sie an der PowerShell-Eingabeaufforderung `Enable-AppxDebug` *PackageFullName* ein, wobei *PackageFullName* der PackageFullName-Bezeichner der App ist.

### <a name="attach-the-debugger"></a><a name="BKMK_Attach_the_debugger"></a>Anfügen des Debuggers

> [!TIP]
> JavaScript-Apps werden in einer Instanz des wwahost.exe-Prozesses ausgeführt. Wenn andere JavaScript-Apps ausgeführt werden, während Sie an die App anfügen, müssen Sie die numerische Prozess-ID (PID) des wwahost.exe-Prozesses kennen, in dem die App ausgeführt wird. 
>
> Die einfachste Möglichkeit in dieser Situation besteht darin, alle anderen JavaScript-Apps zu schließen. Andernfalls können Sie vor dem Starten der App den Windows Task-Manager öffnen und sich die IDs der wwahost.exe-Prozesse notieren. Wenn Sie den Prozess angeben, an den im Dialogfeld **Verfügbare Prozesse** angefügt werden soll, hat wwahost.exe der App eine id, die sich von der von Ihnen notierten id unterscheidet.

 So fügen Sie den Debugger an

1. Klicken Sie im Menü **Debuggen** auf **An den Prozess anhängen**.

    Das Dialogfeld **An den Prozess anhängen** wird angezeigt.

2. Um an eine Anwendung auf einem Remotegerät anzufügen, geben Sie das Remotegerät im Feld **Qualifizierer** an. Ihre Möglichkeiten:

   - Geben Sie im Feld **Qualifizierer** den gewünschten Anzeigenamen ein.

   - Wählen Sie den Abwärtspfeil im Feld **Qualifizierer** aus, und wählen Sie das Gerät aus einer Liste der Geräte aus, an die Sie zuvor angeschlossen haben.

   - Wählen Sie **Suchen** aus, um das Gerät aus einer Liste von Geräten in Ihrem lokalen Subnetz auszuwählen.

3. Geben Sie den Typ des Codes an, den Sie im Feld **Anfügen an** debuggen möchten.

    Wählen Sie **Auswählen** aus, und gehen Sie folgendermaßen vor:

   - Wählen Sie **Zu debuggenden Codetyp automatisch bestimmen**aus.

   - Wählen Sie **Diese Codetypen debuggen** und anschließend mindestens einen Typ aus der Liste aus.

4. Wählen Sie in der Liste **Verfügbare Prozesse** den entsprechenden **wwahost.exe-Prozess** aus. Verwenden Sie die Spalte **Titel,** um Ihre App zu identifizieren.

5. Wählen Sie **Anfügen**aus.

   Der Debugger wird in Visual Studio an den Prozess angefügt. Die Ausführung wird fortgeführt, bis ein Haltepunkt erreicht wird, bis Sie diese manuell anhalten, bis eine unbehandelte Ausnahme auftritt, oder bis die Anwendung beendet ist.

## <a name="see-also"></a>Weitere Informationen
 [Steuern der Ausführung in einer Debugsitzung (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md) [Quickstart: Debug HTML und CSS](../debugger/quickstart-debug-html-and-css.md) [Trigger suspend, resume, and background events for Windows Store)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md) [Debug-Apps in Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
