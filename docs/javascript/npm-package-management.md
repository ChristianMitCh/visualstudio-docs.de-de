---
title: Verwalten von npm-Paketen
description: Dank Visual Studio können Sie Pakete mit dem Node.js-Paket-Manager (NPM) verwalten.
ms.custom: seodec18
ms.date: 06/06/2018
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: de92c3f1f0d0e29d1ba2dfaf5d536a42e636be2c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79307220"
---
# <a name="manage-npm-packages-in-visual-studio"></a>Verwalten von NPM-Paketen in Visual Studio

Mit NPM können Sie Pakete zur Verwendung in Ihren Node.js-Anwendungen installieren und verwalten. Wenn Sie mit NPM nicht vertraut sind und weitere Informationen benötigen, wechseln Sie zur [NPM-Dokumentation](https://docs.npmjs.com/).

Visual Studio erleichtert die Interaktion mit NPM sowie die Ausführung von NPM-Befehlen über die Benutzeroberfläche oder direkt. Sie können die folgenden Methoden verwenden:
* [Installieren von Paketen über den Projektmappen-Explorer](#npmInstallWindow)
* [Verwalten von installierten Paketen über den Projektmappen-Explorer](#solutionExplorer)
* [Verwenden des Befehls `.npm` im interaktiven Node.js-Fenster](#interactive)

Diese Features arbeiten zusammen und werden mit dem Projektsystem und der Datei *package.json* im Projekt synchronisiert.

> [!Important]
> NPM erwartet, dass der Ordner *node_modules* und *package.json* im Projektstamm vorhanden sind. Wenn sich die Ordnerstruktur Ihrer App unterscheidet, sollten Sie Ihre Ordnerstruktur aktualisieren, wenn Sie npm-Pakete mit Visual Studio verwalten.

> [!NOTE]
> Verwenden Sie für vorhandene npm-Projekte die Projektmappenvorlage **Aus vorhandenem Node.js-Code**.

## <a name="npmInstallWindow"></a>Installieren von Paketen über den Projektmappen-Explorer

NPM-Pakete lassen sich am einfachsten über das NPM-Paketinstallationsfenster installieren. Um dieses Fenster aufzurufen, klicken Sie im Projekt mit der rechten Maustaste auf den Knoten **NPM**. Wählen Sie anschließend die Option **Neue NPM-Pakete installieren** aus.

![Installieren eines neuen NPM-Pakets über den Projektmappen-Explorer](../javascript/media/solution-explorer-install-package.png)

In diesem Fenster können Sie nach einem Paket suchen sowie Optionen angeben und installieren.

![Suchen nach einem NPM-Paket](../javascript/media/search-package.png)

* **Abhängigkeitstyp**: Wählen Sie zwischen den Paketen **Standard**, **Entwicklung** und **Optional**. „Standard“ gibt an, dass es sich bei dem Pakte um eine Laufzeitabhängigkeit handelt, während „Entwicklung“ angibt, dass das Paket nur während der Entwicklung benötigt wird.
* **Zu „package.json“ hinzufügen**: Diese Option ist veraltet.
* **Ausgewählte Version**: Wählen Sie die Version des Pakets aus, die Sie installieren möchten.
* **Weitere NPM-Argumente**: Geben Sie weitere NPM-Standardargumente an. Sie können beispielsweise einen Versionswert wie `@~0.8` eingeben, um eine bestimmte Version zu installieren, die in der Versionsliste nicht verfügbar ist.

Der Fortschritt der Installation wird im Fenster „Ausgabe“ auf der Registerkarte „NPM“ angezeigt. Dieser Vorgang kann einige Zeit dauern.

> [!TIP]
> Sie können nach bereichsbezogenen Paketen suchen, indem Sie die Suchabfrage mit dem für Sie interessanten Bereich voranstellen. Geben Sie beispielsweise `@types/mocha` ein, um nach TypeScript-Definitionsdateien für Mocha zu suchen. Wenn Sie Typdefinitionen für TypeScript installieren, können Sie die TypeScript-Version angeben, die Sie als Ziel verwenden. Fügen Sie hierzu `@ts2.6` im NPM-Argumentfeld hinzu.

## <a name="solutionExplorer"></a>Verwalten von installierten Paketen über den Projektmappen-Explorer

NPM-Pakete werden im Projektmappen-Explorer angezeigt. Die Einträge unter dem Knoten **NPM** stellt die Abhängigkeiten in der Datei *package.json* dar.

![Suchen nach einem NPM-Paket](../javascript/media/solution-explorer-status.png)

### <a name="package-status"></a>Paketstatus
* ![Installiertes Paket](../javascript/media/installed-npm.png) - In „package.json“ installiert und aufgeführt
* ![Nicht relevantes Paket](../javascript/media/extraneous-npm.png): Installiert, aber in „package.json“ nicht explizit aufgeführt
* ![Fehlendes Paket](../javascript/media/missing-npm.png) - Nicht installiert, aber in „package.json“ aufgeführt

Klicken Sie mit der rechten Maustaste auf einen Paketknoten oder auf den Konten **NPM**, um eine der folgenden Aktionen durchzuführen:
* **Fehlende Pakete installieren**, die in *package.json* aufgeführt sind
* **Pakete aktualisieren** auf die neueste Version
* **Paket deinstallieren** und in *package.json* entfernen

## <a name="interactive"></a>Verwenden des Befehls „.npm“ im interaktiven Node.js-Fenster

Zum Ausführen von NPM-Befehlen können Sie auch den Befehl `.npm` im interaktiven Node.js-Fenster verwenden. Klicken Sie zum Öffnen des Fensters mit der rechten Maustaste im Projektmappen-Explorer auf das Projekt, und wählen Sie **Interaktives Node.js-Fenster** aus.

In diesem Fenster können Sie Befehle wie die folgenden zum Installieren eines Pakets verwenden:

`.npm install azure@4.2.3`

 > [!Tip]
 > NPM wird standardmäßig im Basisverzeichnis Ihres Projekts ausgeführt. Wenn sich in Ihrer Projektmappe mehrere Projekte befinden, geben Sie den Namen oder den Pfad des Projekts in Klammern an.
 > `.npm [MyProjectNameOrPath] install azure@4.2.3`

 > [!Tip]
 > Wenn in Ihrem Projekt die Datei „package.json“ nicht enthalten ist, verwenden Sie `.npm init -y`, um eine neue „package.json“-Datei mit Standardeinträgen zu erstellen.
