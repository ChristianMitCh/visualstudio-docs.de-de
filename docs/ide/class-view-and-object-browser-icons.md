---
title: Symbole in der Klassenansicht und im Objektbrowser
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- icons, in Object Browser
- signal icons
- Class View tool, symbols
- graphic symbols
- IntelliSense, icons
- icons, IntelliSense
- symbols, Object Browser icons
- Object Browser, icons in Class View
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6589d40d8f897eb8df7f108f53973af268d1edc9
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "75588394"
---
# <a name="class-view-and-object-browser-icons"></a>Symbole in der Klassenansicht und im Objektkatalog

Die **Klassenansicht** und der **Objektkatalog** zeigen Symbole an, die Codeentitäten darstellen, z.B. Namespaces, Klassen, Funktionen und Variablen. In der folgenden Tabelle werden die Symbole dargestellt und beschrieben.

|Symbol|Beschreibung|Symbol|Beschreibung|
|----------|-----------------|----------|-----------------|
|![Symbol "Namespace"](../ide/media/vxnamespace_icon.gif)|Namespace|![Symbol "Deklaration"](../ide/media/vxmethod_icon.gif)|Methode oder Funktion|
|![Symbol "Klasse"](../ide/media/vxclass_icon.gif)|Klasse|![Symbol "Operator"](../ide/media/vxoperator_icon.gif)|Operator|
|![Schnittstellensymbol "Lollipop"](../ide/media/vxinterface_icon.gif)|Schnittstelle|![Symbol "Eigenschaften"](../ide/media/vxproperty_icon.gif)|Eigenschaft|
|![Symbol "Struktur"](../ide/media/vxstruct_icon.gif)|Struktur|![Symbol "Feld"](../ide/media/vxfield_icon.gif)|Feld oder Variable|
|![Symbol "Union"](../ide/media/vxunion_icon.gif)|Union|![Symbol "Ereignis"](../ide/media/vxevent_icon.gif)|event|
|![Symbol "Enumeration"](../ide/media/vxenum_icon.gif)|Enum|![Symbol "Konstante"](../ide/media/vxconstant_icon.gif)|Konstante|
|![Symbol "Typdefinition"](../ide/media/vxtypedef_icon.gif)|TypeDef|![Symbol "Element enumerieren"](../ide/media/vxenumitem_icon.gif)|Enum-Element|
|![Symbol "Visual Studio-Modul"](../ide/media/vxmodule_icon.gif)|Modul|![Symbol "Zuordnungselement"](../ide/media/vxmapitem_icon.gif)|Zuordnungselement|
|![Symbol "Erweiterungsmethode"](../ide/media/extensionmethod.gif)|Erweiterungsmethode|![Symbol "Deklaration"](../ide/media/vxmethod_icon.gif)|Externe Deklaration|
|![Symbol "Delegat"](../ide/media/vxdelegate_icon.gif)|Delegate|![Fehlersymbol für Klassenansicht und Objektkatalog](../ide/media/erroricon.gif)|Fehler|
|![Symbol "Ausnahme"](../ide/media/vxexception_icon.gif)|-Ausnahme|![Symbol "Vorlage"](../ide/media/vxtemplate_icon.gif)|Vorlage|
|![Symbol "Zuordnung"](../ide/media/vxmap_icon.gif)|Karte|![Symbol "Fehler - Ausrufezeichen"](../ide/media/vxerror_icon.gif)|Unknown|
|![Symbol "Typweiterleitung"](../ide/media/ob_type_forward.gif)|Typweiterleitung|||

## <a name="signal-icons"></a>Signalsymbole

Die folgenden Signalsymbole gelten für alle zuvor erwähnten Symbole und geben deren Barrierefreiheit an.

|Symbol|Beschreibung|
|----------|-----------------|
|\<Kein Signalsymbol>|Öffentlich. Der komponenteninterne Zugriff ist möglich. Außerdem können andere Komponenten, die auf die Komponente verweisen, auf diese zugreifen.|
|![Symbol "Signal geschützt"](../ide/media/vxsignal_icon_key.gif)|Geschützt. Der Zugriff ist innerhalb der enthaltenen Klasse oder dem enthaltenen Typ möglich. Außerdem haben Klassen oder Typen Zugriff, die von der enthaltenen Klasse oder dem enthaltenen Typ abgeleitet sind.|
|![Symbol "Signal privat"](../ide/media/vxsignal_icon_lock.gif)|Privat. Der Zugriff ist nur in der enthaltenden Klasse oder dem Typ möglich.|
|![Symbol "Signal versiegelt"](../ide/media/vxsignal_icon_envelope.gif)|Versiegelt.|
|![Signalsymbol „Friend&#47;Internal“ (Freund/Intern)](../ide/media/vxsignal_icon_diamond.gif)|Friend/Intern. Der Zugriff ist nur über das Projekt möglich.|
|![Signalsymbol "Pfeil"](../ide/media/vxsignal_icon_arrow.gif)|Verknüpfung. Eine Verknüpfung mit dem Objekt.|

> [!NOTE]
> Wenn Ihr Projekt in einer Quellcodeverwaltungs-Datenbank enthalten ist, werden möglicherweise zusätzliche Signalsymbole angezeigt, um den Quellcodestatus anzugeben, z.B. eingecheckt oder ausgecheckt.

## <a name="see-also"></a>Weitere Informationen

- [Anzeigen der Codestruktur](../ide/viewing-the-structure-of-code.md)
