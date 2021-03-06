---
title: Private Galerien | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: afd1d79d7f1846e60386d2a9478466bf7eae72e4
ms.sourcegitcommit: 7b60e81414a82c6d34f6de1a1f56115c9cd26943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81444647"
---
# <a name="private-galleries"></a>Private Galerien
Sie können die Steuerelemente, Vorlagen und Tools, die Sie entwickeln, wie folgt in einem *privaten Katalog* im Intranet für Ihre Organisation freigeben:

- Erstellen Sie einen Atom -Feed (RSS) an einen entsprechend konfigurierten zentralen Speicherort (Repository) in Ihrem Intranet. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines Atom-Feeds für eine private Galerie](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md).

- Verteilen Sie eine *.pkgdef-Datei,* die die private Galerie beschreibt. Wir empfehlen diese Konfiguration für Administratoren, die gleichzeitig eine private Galerie mit vielen Computern verbinden möchten.

## <a name="add-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>Hinzufügen einer privaten Galerie zu Erweiterungen und Updates in Visual Studio
 Wenn eine private Galerie verfügbar ist, können Sie sie **Erweiterungen und Updates** in Visual Studio hinzufügen.

 ![Erweiterungs-Manager – Dialogfeld „Hinzufügen“](../extensibility/media/em_adddialog.png "EM_AddDialog")

### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>So fügen Sie Erweiterungen und Updates eine private Galerie hinzu

1. Klicken Sie in der Menüleiste auf **Extras** > **Optionen**.

2. Wählen Sie im **Knoten Umgebung** **Erweiterungen und Updates**aus.

3. Klicken Sie auf die Schaltfläche **Hinzufügen**.

4. Geben Sie im Feld **Name** einen Namen für `My Gallery`die private Galerie ein, z. B. .

5. Geben Sie im Feld **URL** die URL des Atom-Feeds oder der SharePoint-Website ein, auf der die private Galerie gehostet wird.

    1. Wenn es sich bei dem Host um einen Atom-Feed handelt, der eine Verbindung mit der privaten Galerie herstellt, würde die URL diesem ähneln: `http://www.mywebsite/mygallery/atom.xml`.  Diese URL kann auf eine Datei oder einen Netzwerkpfad verweisen.

    2. Wenn es sich bei dem Host um eine `http://mysharepoint/sites/mygallery/forms/AllItems.aspx`SharePoint-Website handelt, würde die URL dieser folgenden ähneln: .

### <a name="manage-private-galleries"></a>Verwalten privater Galerien
 Ein Administrator kann einen privaten Katalog mehreren Computern gleichzeitig zur Verfügung stellen, indem er die Systemregistrierung auf jedem Computer ändert. Um dies zu erreichen, erstellen Sie eine *.pkgdef-Datei,* die die neuen Registrierungsschlüssel und ihre Werte beschreibt.  Das Format dieser Datei ist wie folgt.

```
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]
@={URI}  (REG_SZ)
Disabled=0 | 1 (DWORD)
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)
Protocol=Atom|Sharepoint (REG_SZ)
DisplayName={DisplayName} (REG_SZ)
DisplayNameResourceID={ID} (REG_SZ)
DisplayNamePackageGuid={GUID} (REG_SZ)

```

 Weitere Informationen finden Sie unter [Gewusst wie: Verwalten einer privaten Galerie mithilfe](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md)von Registrierungseinstellungen .

## <a name="install-extensions-from-a-private-gallery"></a>Installieren von Erweiterungen aus einer privaten Galerie
 Sie können Visual Studio-Erweiterungen in einer privaten Galerie in **Erweiterungen und Updates**suchen und installieren. In den folgenden Schritten `My Gallery`wird eine private Galerie mit dem Namen verwendet.

 ![Erweiterungs-Manager – Installieren der privaten Galerie](../extensibility/media/em_.png "EM_")

### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>So suchen und installieren Sie Erweiterungen aus einer privaten Galerie

1. Wählen Sie in der Menüleiste **Tools** > **Extensions und Updates**aus.

2. Wählen Sie im linken Bereich **Onlineerweiterungen**aus, und wählen Sie dann **Meine Galerie**aus.

3. Wählen Sie im rechten Bereich eine Erweiterung aus, und wählen Sie dann die Schaltfläche **Herunterladen** aus.

## <a name="update-extensions-from-a-private-gallery"></a>Aktualisieren von Erweiterungen aus einer privaten Galerie
 Wenn neue Versionen von Visual Studio-Erweiterungen im privaten Katalog veröffentlicht werden, können Sie die installierten Erweiterungen aktualisieren. In den folgenden Schritten `My Repository`wird eine private Galerie mit dem Namen verwendet.

 ![Erweiterungs-Manager – Aktualisierung der privaten Galerie](../extensibility/media/em_update.png "EM_Update")

### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>So aktualisieren Sie eine installierte Erweiterung aus einer privaten Galerie

1. Wählen Sie in der Menüleiste **Tools** > **Extensions und Updates**aus.

2. Wählen Sie im linken Bereich **Updates**aus, und wählen Sie dann **Mein Repository**aus.

3. Wählen Sie im rechten Bereich eine Erweiterung aus, und wählen Sie dann die Schaltfläche **Aktualisieren** aus.

## <a name="see-also"></a>Weitere Informationen
- [Suchen und Verwenden von Visual Studio-Erweiterungen](../ide/finding-and-using-visual-studio-extensions.md)
- [Visual Studio-Erweiterungen versenden](../extensibility/shipping-visual-studio-extensions.md)
