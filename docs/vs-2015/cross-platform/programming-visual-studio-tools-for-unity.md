---
title: Programmieren mit Visual Studio-Tools für Unity | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: a5758cb0-e73b-45f5-8cae-c0eb40491026
caps.latest.revision: 5
author: conceptdev
ms.author: crdun
manager: jillfra
ms.openlocfilehash: 469478f05546a32bb890f759d3d00cb447b54d2b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "68145892"
---
# <a name="programming-visual-studio-tools-for-unity"></a>Programmieren mit Visual Studio-Tools für Unity
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

In diesem Abschnitt finden Sie Beispiele für die Verwendung der Visual Studio-Tools für Unity-API.  
  
## <a name="examples"></a>Beispiele  
 Hier sind einige Beispiele, die zeigen, wie Sie Visual Studio-Tools für Unity-APIs verwenden können.  
  
### <a name="customize-project-files-created-by-vstu"></a>Anpassen von mit VSTU erstellten Projektdateien  
 Visual Studio-Tools für Unity bieten während der Generierung der Projektdatei einen Rückruf im Unity-Stil. Informationen dazu, wie Sie die Projektdatei ändern können, wenn diese erneut generiert wird, finden Sie unter [Anpassen von Projekt generieren](../cross-platform/customize-project-files-created-by-vstu.md).  
  
### <a name="share-the-unity-log-callback-with-vstu"></a>Freigeben des Unity-Protokollrückrufs für VSTU  
 Visual Studio-Tools für Unity registrieren einen Protokollrückruf bei Unity, damit dessen Konsole in Visual Studio gestreamt werden kann. Wenn Ihre Editorskripts auch einen Protokollrückruf bei Unity registrieren, kann der VSTU-Rückruf Ihren Rückruf stören. Informationen dazu, wie Sie den Unity-Protokollrückruf mit VSTU freigeben können, finden Sie unter [Freigeben des Melden Sie sich Rückruf](../cross-platform/share-the-unity-log-callback-with-vstu.md).
