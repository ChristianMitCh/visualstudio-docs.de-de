---
title: Durchsuchen des Speichers zum Hochladen von Daten
author: jillre
ms.author: jillfra
manager: jillfra
monikerRange: vs-2017
ms.date: 11/13/2017
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: ece3ffa3a273e903f403fd7df7005bfb54172f62
ms.sourcegitcommit: 9c1cecaff4d9955276eee7865b78d47679dd1e2a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80638443"
---
# <a name="browse-storage-to-upload-data-or-download-models-and-logs"></a>Durchsuchen des Speichers, um Daten hochzuladen oder Modelle und Protokolle herunterzuladen

Sie können den gesamten Speicher auf dem Remotecomputer oder der Azure-Dateifreigabe durchsuchen, um das Hochladen von Daten oder das Herunterladen von Modellen und Protokollen zu ermöglichen. Wenn Sie alternativ auf Protokolle und Auftragsausgaben für einen bestimmten Auftrag zugreifen möchten, können Sie dies auch im Auftragsbrowser tun.

## <a name="to-access-all-data-on-the-remote-machine-or-file-share"></a>So greifen Sie auf alle Daten auf dem Remotecomputer oder der Dateifreigabe zu

1. Öffnen Sie den **Server-Explorer**.
2. Erweitern Sie den Remotecomputer oder den Computekontext „Batch AI“.
3. Klicken Sie mit der rechten Maustaste auf **Speicher** und dann auf **Durchsuchen**.

    ![storage](media/manage-storage/browse-storage.png)

## <a name="to-access-job-specific-data-on-the-remote-machine-or-file-share"></a>So greifen Sie auf auftragsspezifische Daten auf dem Remotecomputer oder der Dateifreigabe zu

1. Öffnen Sie den [Auftragsverlauf](job-details.md).
2. Wählen Sie den Auftrag aus.
3. Klicken Sie auf **Arbeitsordner** oder auf **StdOut/Stderr**, um schnell auf diese wichtigen Protokolldateien zuzugreifen.

    ![storage](media/manage-storage/job-workingfolder.png)
