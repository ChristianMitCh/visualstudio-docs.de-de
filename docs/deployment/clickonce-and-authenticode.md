---
title: ClickOnce und Authenticode | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- .pfx files
- ClickOnce deployment, Authenticode
- Authenticode, ClickOnce
- ClickOnce deployment, certificates
- ClickOnce deployment, security
ms.assetid: ab5b6712-f32a-4e33-842f-e88ab4818ccf
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9b0e22f56ab68be521eda7a765a2be7e23bbf92
ms.sourcegitcommit: 6c3aa85ff17916936018d121e7a0d1b486f6c7eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "79093959"
---
# <a name="clickonce-and-authenticode"></a>ClickOnce und Authenticode
*Authenticode* ist eine Microsoft-Technologie, die mithilfe von Industriestandard-Kryptografie Anwendungscode mit digitalen Zertifikaten signiert, die die Echtheit des Herausgebers der Anwendung bestätigen. Durch die Verwendung von Authenticode bei der Bereitstellung einer Anwendung reduziert [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] das Risiko eines trojanischen Pferdes. Ein trojanisches Pferd ist ein Virus oder ein schädliches Programm, das ein böswilliger Drittanbieter als sicheres Programm aus einer bekannten und vertrauenswürdigen Quelle darstellt. Signieren von [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Bereitstellungen mit einem digitalen Zertifikat ist ein optionaler Schritt, um sicherzustellen, dass die Assemblys und Dateien nicht manipuliert wurden.

 In den folgenden Abschnitten sind die verschiedenen Typen von digitalen Zertifikaten beschrieben, die in Authenticode verwendet werden, wie Zertifikate durch Zertifizierungsstellen (CAs) überprüft werden, die Rolle des Zeitstempels in Zertifikaten und die Methoden des verfügbaren Speichers für Zertifikate.

## <a name="authenticode-and-code-signing"></a>Authenticode und Codesignatur
 Ein *digitales Zertifikat* ist eine Datei, die ein öffentliches/privates kryptografisches Schlüsselpaar enthält sowie Metadaten über den Herausgeber, für den das Zertifikat ausgestellt wurde, und die Agentur, die das Zertifikat ausgestellt hat.

 Es gibt viele verschiedene Arten von Authenticode-Zertifikaten. Jedes ist für unterschiedliche Arten von Signaturen konfiguriert. Für [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Anwendungen benötigen Sie ein Authenticode-Zertifikat, das zum Signieren von Code gültig ist. Wenn Sie versuchen, eine [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Anwendung mit einem anderen Typ von Zertifikat zu signieren, z.B. einem digitalen Zertifikat für E-Mail, funktioniert dies nicht. Weitere Informationen finden Sie unter [Einführung in die Codesignatur](/windows/desktop/seccrypto/cryptography-tools).

 Sie können ein Zertifikat für Codesignaturen auf eine von drei Arten abrufen:

- Sie erwerben es von einem Zertifikatsanbieter.

- Sie erhalten es von einer Abteilung in Ihrem Unternehmen, die für das Erstellen von digitalen Zertifikaten verantwortlich ist.

- Generieren Sie Ihr eigenes Zertifikat mithilfe des New-SelfSignedCertificate PowerShell-Cmdlets oder mit *MakeCert.exe*, das im [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]enthalten ist.

### <a name="how-using-certificate-authorities-helps-users"></a>Wie die Verwendung von Zertifizierungsstellen Benutzern hilft
 Ein Zertifikat, das mit New-SelfSignedCertificate oder dem *Dienstprogramm MakeCert.exe* generiert wird, wird gemeinhin als *Selbstzertifizierung* oder *Testzertifizierungsdatei*bezeichnet. Diese Art von Zertifikat funktioniert ähnlich wie eine *.snk-Datei* in .NET Framework. Es besteht ausschließlich aus einem kryptografischen öffentlichen/privaten Schlüsselpaar und enthält keine überprüfbaren Informationen zum Herausgeber. Sie können selbst signierte Zertifikate zum Bereitstellen von [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Anwendungen mit hoher Vertrauenswürdigkeit in einem Intranet verwenden. Beim Ausführen dieser Anwendungen auf einem Clientcomputer wird [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] sie jedoch als von einem unbekannten Herausgeber stammend identifizieren. In der Standardeinstellung können [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Applikationen, die mit selbst signierten Zertifikaten signiert und über das Internet bereitgestellt sind, keine vertrauenswürdige Anwendungsbereitstellung nutzen.

 Wenn Sie dagegen ein Zertifikat von einer Zertifizierungsstelle erhalten, zum Beispiel von einem Zertifikatsanbieter oder einer Abteilung in Ihrem Unternehmen, bietet dieses Zertifikat mehr Sicherheit für Ihre Benutzer. Es identifiziert nicht nur den Herausgeber der signierten Software, sondern überprüft dessen Identität durch Abgleich mit den Daten der Zertifizierungsstelle, die es signiert hat. Wenn die Zertifizierungsstelle nicht die Stammzertifizierungsstelle ist, wird Authenticode auch zurück zur Stammzertifizierungsstelle „verketten“, um zu überprüfen, ob die Zertifizierungsstelle zum Ausstellen von Zertifikaten autorisiert ist. Aus Sicherheitsgründen sollten Sie möglichst ein Zertifikat von einer Zertifizierungsstelle verwenden.

 Weitere Informationen zum Generieren von Selbstzertifizierungen finden Sie unter [New-SelfSignedCertificate](https://technet.microsoft.com/itpro/powershell/windows/pkiclient/new-selfsignedcertificate) oder [MakeCert](/windows/desktop/SecCrypto/makecert).

### <a name="timestamps"></a>Zeitstempel
 Die Zertifikate zum Signieren von [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Applikationen laufen nach einem bestimmten Zeitraum ab, in der Regel zwölf Monate. Um nicht ständig mit neuen Zertifikaten neu signieren zu müssen, unterstützt [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Timestamps (Zeitstempel). Wenn eine Anwendung mit einem Zeitstempel versehen ist, wird ihr Zertifikat auch nach Ablauf der Gültigkeit des Zertifikats akzeptiert, vorausgesetzt, dass der Zeitstempel gültig ist. Dadurch können [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Anwendungen mit abgelaufenen Zertifikaten, aber gültigen Zeitstempeln, heruntergeladen und ausgeführt werden. Außerdem können installierte Programme mit abgelaufenen Zertifikaten weiterhin Updates herunterladen und installieren.

 Um einen Zeitstempel in einen Anwendungsserver einzuschließen, muss ein Timestampserver verfügbar sein. Weitere Informationen zum Auswählen eines Timestampservers finden Sie unter [How to: Sign Application and Deployment Manifests](../ide/how-to-sign-application-and-deployment-manifests.md).

### <a name="update-expired-certificates"></a>Aktualisieren abgelaufener Zertifikate
 In früheren Versionen von .NET Framework verursachte das Aktualisieren einer Anwendung, deren Zertifikat abgelaufen war, den Absturz dieser Anwendung. Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen:

- Aktualisieren Sie .NET Framework auf Version 2.0 SP1 oder höher auf Windows XP oder Version 3.5 oder höher auf Windows Vista.

- Deinstallieren Sie die Anwendung, und installieren Sie eine neue Version mit einem gültigen Zertifikat.

### <a name="store-certificates"></a>Speichern von Zertifikaten

- Sie können Zertifikate als *PFX*-Datei im Dateisystem speichern oder in einem Schlüsselcontainer speichern. Ein Benutzer auf einer Windows-Domäne kann über mehrere Schlüsselcontainer verfügen. Standardmäßig speichert *MakeCert.exe* Zertifikate in Ihrem persönlichen Schlüsselcontainer, es sei denn, Sie geben an, dass es stattdessen in einer *.pfx* gespeichert werden soll. *Mage.exe* und *MageUI.exe*, die [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]-Tools zum Erstellen von [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]-Bereitstellungen, ermöglichen es Ihnen, auf beide Arten gespeicherte Zertifikate zu verwenden.

## <a name="see-also"></a>Weitere Informationen
- [ClickOnce-Sicherheit und -Bereitstellung](../deployment/clickonce-security-and-deployment.md)
- [Sichere ClickOnce-Anwendungen](../deployment/securing-clickonce-applications.md)
- [Übersicht über die Bereitstellung vertrauenswürdiger Anwendungen](../deployment/trusted-application-deployment-overview.md)
- [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)
