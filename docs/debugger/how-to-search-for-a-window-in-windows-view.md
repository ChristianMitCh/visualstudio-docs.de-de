---
title: 'Vorgehensweise: Suchen nach einem Fenster in der Fensteransicht | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5ba5c8469885fd62c99a672e894cde82700c980d
ms.sourcegitcommit: 3fe6bed9ef8fb1478106645f655c7472009ae43a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64831026"
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>Vorgehensweise: Suchen nach einem Fenster in der Fensteransicht
Sie können in der Fensteransicht anhand des Handles, der Beschriftung, der Klasse oder einer Kombination aus Beschriftung und Klasse als Suchkriterium nach einem Fenster suchen. Sie können auch die anfängliche Richtung der Suche angeben. In den Feldern im Dialogfeld werden die Attribute des ausgewählten Fensters in der Fensterstruktur angezeigt.

 Erweitern Sie die Struktur zunächst auf die zweite Ebene (alle Fenster, die dem Desktop untergeordnet sind), damit Sie die Fenster der Desktopebene anhand ihrer Klassennamen und Titel identifizieren können. Sobald Sie ein Fenster der Desktopebene ausgewählt haben, können Sie diese Ebene erweitern, um ein spezifisches untergeordnetes Fenster zu suchen.

### <a name="to-search-for-a-window-in-windows-view"></a>So suchen Sie in der Fensteransicht nach einem Fenster

1. Ordnen Sie Ihre Fenster so an, dass Spy++, das Fenster [Fensteransicht](../debugger/windows-view.md) und das Zielfenster sichtbar sind.

2. Klicken Sie im Menü **Suche** auf **Fenster suchen**.

    Daraufhin wird das [Dialogfeld „Fenstersuche“](../debugger/window-search-dialog-box.md) geöffnet.

   > [!TIP]
   > Damit der Bildschirm übersichtlich bleibt, wählen Sie die Option **Spy++ ausblenden** aus. Mit dieser Option wird das Spy++-Hauptfenster ausgeblendet, sodass nur das Dialogfeld **Fenster suchen** über Ihren anderen Anwendungen angezeigt wird. Das Spy++-Hauptfenster wird wiederhergestellt, wenn Sie auf **OK** oder **Abbrechen** klicken oder die Option **Spy++ ausblenden** deaktivieren.

3. Ziehen Sie das **Suchtool** über das Zielfenster. Während Sie das Tool ziehen, werden im Dialogfeld **Fenster suchen** Details zum ausgewählten Fenster angezeigt.

   - ODER

     Wenn Sie den Handle des gesuchten Fensters kennen (z. B. vom Debugger), können diesen in das Feld **Handle** eingeben.

   - ODER

     Wenn Sie die Beschriftung und/oder die Klasse des gesuchten Fensters kennen, können Sie diese in die Textfelder **Beschriftung** und **Klasse** eingeben und den Inhalt des Textfelds **Handle** löschen.

4. Sie können auch **Nach oben** oder **Nach unten** als anfängliche Suchrichtung angeben.

5. Klicken Sie auf **OK**.

    Wenn ein übereinstimmendes Fenster gefunden wird, wird es im Fenster [Fensteransicht](../debugger/windows-view.md) hervorgehoben.