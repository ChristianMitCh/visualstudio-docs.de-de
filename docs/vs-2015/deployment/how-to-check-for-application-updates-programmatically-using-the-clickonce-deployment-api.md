---
title: 'Gewusst wie: Überprüfen Sie programmgesteuert mithilfe der ClickOnce-Bereitstellungs-API | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5250e719cce945bdcce90a9d49d2ed8c27555612
ms.sourcegitcommit: 7b60e81414a82c6d34f6de1a1f56115c9cd26943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81444963"
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Gewusst wie: Programmgesteuertes Suchen nach Anwendungsupdates mit der API für die ClickOnce-Bereitstellung
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ClickOnce bietet zwei Möglichkeiten, eine Anwendung nach der Bereitstellung zu aktualisieren. In der ersten Methode können Sie die ClickOnce-Bereitstellung so konfigurieren, dass in bestimmten Intervallen automatisch nach Aktualisierungen gesucht wird. In der zweiten Methode können Sie <xref:System.Deployment.Application.ApplicationDeployment> Code schreiben, der die Klasse verwendet, um basierend auf einem Ereignis nach Aktualisierungen zu suchen, z. B. eine Benutzeranforderung.  
  
 Die folgenden Verfahren zeigen Code zum Durchführen einer programmgesteuerten Aktualisierung und beschreiben auch, wie Sie Ihre ClickOnce-Bereitstellung konfigurieren, um programmgesteuerte Aktualisierungsprüfungen zu aktivieren.  
  
 Um eine ClickOnce-Anwendung programmgesteuert zu aktualisieren, müssen Sie einen Speicherort für Aktualisierungen angeben. Dies wird manchmal als Bereitstellungsanbieter bezeichnet. Weitere Informationen zum Festlegen dieser Eigenschaft finden Sie [unter Auswählen einer ClickOnce-Aktualisierungsstrategie](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
> Sie können die unten beschriebene Technik auch verwenden, um Ihre Anwendung von einem Speicherort aus bereitzustellen, sie jedoch von einem anderen standortaktualisieren. Weitere Informationen finden Sie unter [Gewusst wie: Angeben eines alternativen Speicherorts für Bereitstellungsupdates](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>So suchen Sie programmgesteuert nach Updates  
  
1. Erstellen Sie eine neue Windows Forms-Anwendung mit Ihren bevorzugten Befehlszeilen oder visuellen Tools.  
  
2. Erstellen Sie eine Schaltfläche, ein Menüelement oder ein anderes Benutzeroberflächenelement, das die Benutzer auswählen sollen, um nach Updates zu suchen. Rufen Sie im Ereignishandler dieses Elements die folgende Methode auf, um nach Updates zu suchen und sie zu installieren.  
  
     [!code-cpp[ClickOnceAPI#6](../snippets/cpp/VS_Snippets_Winforms/ClickOnceAPI/cpp/form1.cpp#6)]
     [!code-csharp[ClickOnceAPI#6](../snippets/csharp/VS_Snippets_Winforms/ClickOnceAPI/CS/Form1.cs#6)]
     [!code-vb[ClickOnceAPI#6](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnceAPI/VB/Form1.vb#6)]  
  
3. Kompilieren Sie Ihre Anwendung.  
  
### <a name="using-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Verwenden von Mage.exe zum Bereitstellen einer Anwendung, die programmgesteuert nach Updates sucht  
  
- Befolgen Sie die Anweisungen zum Bereitstellen Ihrer Anwendung mit Mage.exe, wie in [der exemplarischen Vorgehensweise erläutert: Manuelle Bereitstellung einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Wenn Sie Mage.exe aufrufen, um das Bereitstellungsmanifest zu `providerUrl`generieren, stellen Sie sicher, dass Sie den Befehlszeilenschalter verwenden und die URL angeben, unter der ClickOnce nach Updates suchen soll. Wenn Ihre Anwendung `http://www.adatum.com/MyApp`z. B. von aktualisiert wird, sieht Ihr Aufruf zum Generieren des Bereitstellungsmanifests wie folgt aus:  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Verwenden von MageUI.exe zum Bereitstellen einer Anwendung, die programmgesteuert nach Updates sucht  
  
- Befolgen Sie die Anweisungen zum Bereitstellen Ihrer Anwendung mit Mage.exe, wie in [der exemplarischen Vorgehensweise erläutert: Manuelle Bereitstellung einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Legen Sie auf der Registerkarte **Bereitstellungsoptionen** das Feld **Startspeicherort** auf das Anwendungsmanifest fest, das Klicken Sie nach Updates suchen soll. Deaktivieren Sie auf der Registerkarte **Aktualisierungsoptionen** das Kontrollkästchen Diese Anwendung sollte auf **Updates überprüfen.**  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Ihre Anwendung muss über voll vertrauenswürdige Berechtigungen verfügen, um die programmgesteuerte Aktualisierung verwenden zu können.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Gewusst wie: Angeben eines alternativen Speicherorts für Bereitstellungsupdates](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [Auswählen einer ClickOnce-Update-Strategie](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Veröffentlichen von ClickOnce-Anwendungen](../deployment/publishing-clickonce-applications.md)
