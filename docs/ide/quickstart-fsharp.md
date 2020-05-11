---
title: 'Schnellstart: Erstellen eines ASP.NET Core-Webdiensts in F#'
description: Dieser Artikel enthält eine ausführliche Anleitung zum Erstellen eines ASP.NET Core-Webdiensts mit F# in Visual Studio.
ms.date: 08/24/2018
ms.topic: quickstart
author: cartermp
ms.author: phcart
manager: andrehal
dev_langs:
- FSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 990106f7f3ca97ae38a20170ca6ed2e1d699d4e4
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2020
ms.locfileid: "70180322"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-service-in-f"></a>Schnellstart: Verwenden von Visual Studio zum Erstellen Ihres ersten ASP.NET Core-Webdiensts in F\#

In dieser 5- bis 10-minütigen Einführung in F# in Visual Studio erstellen Sie eine ASP.NET Core-Webanwendung in F#.

::: moniker range="vs-2017"

Wenn Sie Visual Studio noch nicht installiert haben, können Sie es auf der Seite [Visual Studio-Downloads](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) kostenlos herunterladen.

::: moniker-end

::: moniker range="vs-2019"

Wenn Sie Visual Studio noch nicht installiert haben, können Sie es auf der Seite [Visual Studio-Downloads](https://visualstudio.microsoft.com/downloads) kostenlos herunterladen.

::: moniker-end

## <a name="create-a-project"></a>Erstellen eines Projekts

Zunächst müssen Sie ein Projekt für die ASP.NET Core-Web-API erstellen. Der Projekttyp enthält Vorlagendateien, die schon bevor Sie daran gearbeitet haben, einen funktionsfähigen Webdienst darstellen.

::: moniker range="vs-2017"

1. Öffnen Sie Visual Studio.

2. Klicken Sie oben in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

3. Erweitern Sie im Dialogfeld **Neues Projekt** links den Eintrag **Visual F#** , und klicken Sie auf **Web**. Klicken Sie im mittleren Bereich auf **ASP.NET Core-Webanwendung** und anschließend auf **OK**.

     Falls Sie die Projektvorlagenkategorie **.NET Core** nicht finden, klicken Sie im linken Bereich auf den Link **Visual Studio-Installer öffnen**. Der Visual Studio-Installer wird gestartet. Klicken Sie auf die Workload **ASP.NET und Webentwicklung**, und klicken Sie anschließend auf **Ändern**.

     ![ASP.NET-Workload in VS-Installer](../ide/media/quickstart-aspnet-workload.png)

4. Wählen Sie im oberen Dropdownmenü des Dialogfelds **Neue ASP.NET Core-Webanwendung** die Option **ASP.NET Core 2.1**. (Wenn **ASP.NET Core 2.1** nicht in der Liste angezeigt wird, installieren Sie es über den **Download**-Link, der in einer gelben Leiste im oberen Bereich des Dialogfelds angezeigt werden sollte.) Klicken Sie auf **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Öffnen Sie Visual Studio.

2. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

3. Geben Sie auf der Seite **Neues Projekt erstellen** im Suchfeld **f# web**ein, und wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus. Wählen Sie **Weiter** aus.

4. Geben Sie auf der Seite **Neues Projekt konfigurieren** einen Namen ein, und wählen Sie dann **Erstellen** aus.

5. Wählen Sie auf der Seite **Neue ASP.NET Core-Webanwendung erstellen** im oberen Dropdownmenü **ASP.NET Core 2.1** und dann **Erstellen** aus.

::: moniker-end

## <a name="explore-the-ide"></a>Durchsuchen der IDE

1. Erweitern Sie in der Symbolleiste des **Projektmappen-Explorers** den Ordner **Controllers** (Controller), und klicken Sie anschließend auf die Datei **ValuesController.fs**, um sie im Editor zu öffnen.

   ![Projektmappen-Explorer mit dem erweiterten Ordner „Controllers“ im F#-Web-API-Projekt](../ide/media/hello-world-fs-sln-explorer.png)

2. Als Nächstes ändern Sie das `Get()`-Element wie folgt:

   ```fsharp
   [<HttpGet>]
   member this.Get() =
       let values = [|"Hello"; "World"; "First F#/ASP.NET Core web API!"|]
       ActionResult<string[]>(values)
   ```

Der Code ist einfach. Ein F#-Array von Werten wird an den Namen `values` gebunden und dann als `ActionResult` an das ASP.NET Core-MVC-Framework übergeben. ASP.NET Core übernimmt den Rest für Sie.

Im Editor sollte es wie folgt aussehen:

![Geändertes Get-Element](../ide/media/hello-world-fs-get-member.png)

## <a name="run-the-application"></a>Ausführen der Anwendung

1. Drücken Sie **STRG**+**F5**, um die Anwendung auszuführen und sie im Webbrowser zu öffnen.

2. Die Seite sollte zur Route `/api/values` navigieren, wenn dies jedoch nicht der Fall ist, geben Sie `https://localhost:44396/api/values` in Ihren Browser ein.

Der Webbrowser zeigt nun JSON an, das mit dem übereinstimmt, was Sie zuvor eingegeben haben.

## <a name="next-steps"></a>Nächste Schritte

Damit haben Sie den Schnellstart erfolgreich abgeschlossen. Wir hoffen, dass Sie etwas über F#, ASP.NET Core und die Visual Studio-IDE gelernt haben. Klicken Sie auf die folgende Schaltfläche, um die App anzuzeigen, die auf einem öffentlichen Server ausgeführt wird.

> [!div class="nextstepaction"]
> [Deploy the app to Azure App Service (Bereitstellen der App in Azure App Service)](../deployment/quickstart-deploy-to-azure.md)

Weitere Informationen zu F# finden Sie im offiziellen [Leitfaden für F#](/dotnet/fsharp/index).