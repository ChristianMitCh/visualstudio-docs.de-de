---
title: 'Vorgehensweise: Veröffentlichen Sie ein Projekt, das einem bestimmten Gebietsschema | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 42fc6e45e0e32e9b165251c7ec61d3d67b924e1c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697606"
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>Vorgehensweise: Veröffentlichen eines Projekts mit einem bestimmten Gebietsschema
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Es ist nicht ungewöhnlich, dass eine Anwendung Komponenten mit unterschiedlichen Gebietsschemas enthält. In diesem Szenario würden Sie eine Projektmappe aus mehreren Projekten erstellen und dann gesonderte Projekte für jedes Gebietsschema veröffentlichen. Dieses Verfahren zeigt, wie Sie das erste Projekt in einer Projektmappe mit dem Gebietsschema "en" mit einem Makro veröffentlichen können. Wenn Sie das Verfahren mit einem anderen Gebietsschema als "en" verwenden möchten, müssen Sie `localeString` im Makro auf das verwendete Gebietsschema festlegen (beispielsweise auf "de" oder "de-DE").  
  
> [!NOTE]
> Wenn Sie dieses Makro verwenden, sollte der Ort der Veröffentlichung eine gültige URL oder UNC-Freigabe (Universal Naming Convention) sein. Darüberhinaus müssen Internetinformationsdienste (Internet Information Services, IIS) auf Ihrem Computer installiert sein. Klicken Sie zur Installation von IIS im Menü **Start** auf **Systemsteuerung**. Doppelklicken Sie auf **Software**. Klicken Sie unter **Software** auf **Windows-Komponenten hinzufügen/entfernen**. Aktivieren Sie unter **Assistent für Windows-Komponenten** in der Liste **Komponenten** das Kontrollkästchen **Internetinformationsdienste (IIS)**. Klicken Sie dann auf **Fertig stellen**, um den Assistenten zu schließen.  
  
### <a name="to-create-the-publishing-macro"></a>So erstellen Sie das Makro zum Veröffentlichen  
  
1. Zeigen Sie zum Öffnen des Makro-Explorers im Menü **Extras** auf **Makros**, und klicken Sie dann auf **Makro-Explorer**.  
  
2. Erstellen Sie ein neues Makromodul. Wählen Sie im Makro-Explorer **MyMacros** aus. Zeigen Sie im Menü **Extras** auf **Makros**, und klicken Sie dann auf **Neues Makromodul**. Geben Sie dem Modul den Namen **PublishSpecificCulture**.  
  
3. Erweitern Sie im Makro-Explorer den Knoten **MyMacros**, und öffnen Sie dann das Modul **PublishAllProjects**, indem Sie darauf doppelklicken (oder zeigen Sie im Menü **Extras** auf **Makros**, und klicken Sie dann auf **Makro-IDE**).  
  
4. Fügen Sie in der Makro-IDE dem Modul nach den `Import`-Anweisungen den folgenden Code hinzu:  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certificate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5. Schließen Sie die Makro-IDE. Der Fokus wechselt wieder zu Visual Studio.  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>So veröffentlichen Sie ein Projekt für ein bestimmtes Gebietsschema  
  
1. Um ein Visual Basic-Projekt für eine Windows-Anwendung zu erstellen, zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2. Wählen Sie im Dialogfeld **Neues Projekt** im Knoten **Visual Basic** die Option **Windows-Anwendung** aus. Geben Sie dem Projekt den Namen **PublishLocales**.  
  
3. Klicken Sie auf "Form1". Ändern Sie im Fenster **Eigenschaften** unter **Entwurf** die Einstellung **Sprache** von **(Standard)** in **Englisch**. Ändern Sie die Eigenschaft **Text** des Formulars in **MyForm**.  
  
     Beachten Sie, dass die lokalisierten Ressourcen-DLLs erst erstellt werden, wenn sie benötigt werden. Sie werden beispielsweise erstellt, wenn Sie den Text des Formulars oder eines der Steuerelemente ändern, nachdem Sie das neue Gebietsschema angegeben haben.  
  
4. Veröffentlichen Sie "PublishLocales" mit der Visual Studio-IDE.  
  
     In **Projektmappen-Explorer**, wählen Sie "PublishLocales". Wählen Sie im Menü **Projekt** die Option **Eigenschaften** aus. Im Projekt-Designer auf die **veröffentlichen** Seite, geben Sie als Veröffentlichungsort **http://localhost/PublishLocales**, und klicken Sie dann auf **jetzt veröffentlichen**.  
  
     Wenn die veröffentlichte Webseite angezeigt wird, schließen Sie sie. (Für diesen Schritt müssen Sie das Projekt nur veröffentlichen, Sie müssen es nicht installieren.)  
  
5. Veröffentlichen Sie "PublishLocales" erneut, indem Sie das Makro über die Visual Studio-Eingabeaufforderung aufrufen. Anzeigen im Eingabeaufforderungsfenster auf den **anzeigen** , zeigen Sie auf **andere Windows** , und klicken Sie dann auf **Befehlsfenster**, oder drücken Sie STRG + ALT + A. Geben Sie im Eingabeaufforderungsfenster Befehl `macros`, automatische Vervollständigung wird eine Liste der verfügbaren Makros bieten. Wählen Sie das folgende Makro aus, und drücken Sie die EINGABETASTE:  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6. Bei einer erfolgreichen Veröffentlichung wird in einer Meldung angegeben, dass die Veröffentlichung von "PublishLocales\PublishLocales.vbproj" erfolgreich war Die Sprache für die Veröffentlichung war „en“. Klicken Sie im Meldungsfeld auf **OK**. Wenn die veröffentlichte Webseite angezeigt wird, klicken Sie auf **Installieren**.  
  
7. Sehen Sie unter "C:\Inetpub\wwwroot\PublishLocales\en" nach. Sie sollten die installierten Dateien wie Manifeste, "setup.exe" und die veröffentlichte Webseitendatei sowie die lokalisierte Ressourcen-DLL finden. (Standardmäßig fügt ClickOnce eine DEPLOY-Erweiterung an EXEs und DLLs an. Sie können diese Erweiterung nach der Bereitstellung entfernen.)  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von ClickOnce-Anwendungen](../deployment/publishing-clickonce-applications.md)   
 [Makros-Entwicklungsumgebung](https://msdn.microsoft.com/d23105d8-34fe-4ad9-8278-fae2c660aeac)   
 [Makro-Explorer-Fenster](https://msdn.microsoft.com/762169e6-f83f-44b4-bffa-d0f107cae9a3)   
 [Vorgehensweise: Bearbeiten und Programmgesteuertes Erstellen von Makros](https://msdn.microsoft.com/6716f820-1feb-48ad-a718-27eb6b473c5a)
