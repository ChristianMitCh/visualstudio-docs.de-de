---
title: 'Vorgehensweise: Debuggen eines selbstgehosteten WCF-Diensts | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12654a6aa1abb34c9813e8d29c7608814021a3f0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72733981"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Vorgehensweise: Debuggen eines lokal gehosteten WCF-Diensts
Ein *lokal gehosteter Dienst* ist ein WCF-Dienst, der nicht innerhalb von IIS, WCF-Diensthost oder [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server ausgeführt wird. Der einfachste Weg zum Debuggen eines lokal gehosteten WCFs besteht darin, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für das Starten sowohl von Client als auch Server zu konfigurieren, wenn Sie im Menü **Debuggen** den Befehl **Debuggen starten** auswählen.

 Wenn der WCF-Dienst in einem Prozess lokal gehostet wird, der nicht auf diese Weise gestartet werden kann, z. B. ein NT-Dienst, kann diese Methode nicht verwendet werden. Verwenden Sie stattdessen eine der folgenden Methoden:

- Fügen Sie den Debugger manuell an den Hostprozess an. Weitere Informationen finden Sie unter [Anfügen an laufende Prozesse](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

     \- oder -

- Starten Sie das Debuggen des Clients, und führen Sie einen Einzelschritt in einen Aufruf des Diensts aus. Dazu muss das Debuggen in der Datei app.config aktiviert werden. Weitere Informationen finden Sie unter [Einschränkungen beim WCF-Debuggen](../debugger/limitations-on-wcf-debugging.md).

### <a name="to-start-both-client-and-host-from-visual-studio"></a>So starten Sie sowohl Client als auch Host in Visual Studio

1. Erstellen Sie eine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Projektmappe, in der sowohl das Client- als auch das Serverprojekt enthalten ist.

2. Konfigurieren Sie die Projektmappe zum Starten sowohl des Client- als auch des Serverprozesses, wenn Sie im Menü **Debuggen** den Befehl **Starten** auswählen.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Namen der Projektmappe.

   2. Klicken Sie auf **Startprojekte festlegen**.

   3. Wählen Sie im Dialogfeld **Eigenschaften der Projektmappe \<Name>** die Option **Mehrere Startprojekte** aus.

   4. Wechseln Sie im Raster **Mehrere Startprojekte** zu der Zeile, die dem Serverprojekt entspricht, klicken Sie auf **Aktion**, und wählen Sie **Starten** aus.

   5. Klicken Sie in der Zeile, die dem Clientprojekt entspricht, auf **Aktion**, und wählen Sie **Starten** aus.

   6. Klicken Sie auf **OK**.

## <a name="see-also"></a>Siehe auch
- [Debuggen von WCF-Diensten](../debugger/debugging-wcf-services.md)
- [Einschränkungen beim WCF-Debugging](../debugger/limitations-on-wcf-debugging.md)
- [How to: Ausführen eines Einzelschritts in WCF-Diensten](../debugger/how-to-step-into-wcf-services.md)