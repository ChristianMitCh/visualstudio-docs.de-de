---
title: 'Vorgehensweise: Dateinamenoptionen für Profilerstellungsdaten | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: cc42b63524a867c0893aa255180c740d03d4b5fe
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778764"
---
# <a name="how-to-set-performance-data-file-name-options"></a>Vorgehensweise: Dateinamensoptionen für Profilerstellungsdaten

Standardmäßig speichern Sie eine Profilerstellungs-Datendatei (.*vsp*) mithilfe der folgenden Syntax:

*Path\VSP-File\YYMMDD(N)* **.vsp**

Sie können auf der Seite **Allgemein** im Dialogfeld „Eigenschaften“ für die Leistungssitzung jeden beliebigen Namensparameter ändern.

|||
|-|-|
|*Pfad*|Das Verzeichnis mit dem Bericht. Der Standardspeicherort ist der Projektmappenordner oder der Standardspeicherort für Projekte und Projektmappen des Benutzers.|
|*VSP-Datei*|Der Name der Profilerstellungs-Datendatei. Der Standardname ist der Name der Projektmappe oder der ausführbaren Datei, für die ein Profil erstellt wird.|
|*JJMMTT*|Ein Datumsstempel, der Jahr, Monat und Tag anzeigt, an dem die Profilerstellungsdaten gesammelt wurden.|
|*(N)*|Wenn mehr als eine Profilerstellungsdatendatei vorhanden ist, wird dem Dateinamen eine inkrementierte Zahl in Klammern hinzugefügt.|

## <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>So ändern Sie die Benennungssyntax der Profilerstellungs-Datendateien einer Leistungssitzung

1. Klicken Sie im **Leistungs-Explorer** mit der rechten Maustaste auf den Namen der Leistungssitzung und anschließend auf **Eigenschaften**.

2. Klicken Sie auf **Allgemein**.

3. Ändern Sie unter **Bericht** eine der folgenden Einstellungen:

    |||
    |-|-|
    |**Berichtsspeicherort**|Geben Sie ein Verzeichnis zum Speichern der Profilerstellungs-Datendateien an.|
    |**Berichtsname**|Geben Sie einen Basisnamen für die Dateien an.|
    |**Neue Berichte automatisch zur Sitzung hinzufügen**|Wählen Sie das Kontrollkästchen aus, um die Datendatei der Leistungssitzung automatisch hinzuzufügen.|
    |**Generierte Berichte mit inkrementeller Nummer versehen**|Wählen Sie das Kontrollkästchen aus, um eine inkrementelle Nummer an den Dateinamen hinzuzufügen, wenn mehr als eine Datei mit demselben Namen vorhanden ist. Deaktivieren Sie das Kontrollkästchen, um eine vorhandene Datei zu überschreiben.|
    |**Zeitstempel für die Nummer verwenden**|Wählen Sie das Kontrollkästchen aus, um dem Dateinamen einen Datumsstempel hinzuzufügen.|
