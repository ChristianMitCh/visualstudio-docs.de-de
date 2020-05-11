---
title: Befehl "Befehlsfensterausgaben protokollieren"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6ba8fb419726018bd089e217386ab5dbd6a9c33
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "75568658"
---
# <a name="log-command-window-output-command"></a>Befehl „Befehlsfensterausgaben protokollieren“

Kopiert die gesamte Ein- und Ausgabe aus dem **Befehlsfenster** in eine Datei.

## <a name="syntax"></a>Syntax

```cmd
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]
```

## <a name="arguments"></a>Argumente

`filename`\
Dies ist optional. Der Name der Protokolldatei. Standardmäßig wird die Datei im Profilordner des Benutzers erstellt. Wenn der Dateiname bereits vorhanden ist, wird „log“ dem Ende der vorhandenen Datei angefügt. Wenn keine Datei angegeben ist, wird die zuletzt angegebene Datei verwendet. Wenn noch keine Datei angegeben wurde, wird eine Standardprotokolldatei mit dem Namen „cmdline.log“ erstellt.

> [!TIP]
> Geben Sie den vollständigen Dateipfad in Anführungszeichen an, wenn der Pfad Leerzeichen enthält, um den Speicherort der Protokolldatei zu ändern.

## <a name="switches"></a>Schalter

/on\
Dies ist optional. Startet das Protokoll für das **Befehlsfenster** in der angegebenen Datei und hängt die Datei mit den neuen Informationen an.

/off\
Dies ist optional. Stoppt das Protokoll für das **Befehlsfenster**.

/overwrite\
Dies ist optional. Wenn die angegebene Datei im `filename`-Argument mit einer vorhandenen Datei übereinstimmt, wird die Datei überschrieben.

## <a name="remarks"></a>Bemerkungen

Wenn noch keine Datei angegeben ist, wird standardmäßig die Datei „cmdline.log“ erstellt. Der Alias dieses Befehls lautet standardmäßig „Log“.

## <a name="examples"></a>Beispiele

In diesem Beispiel wird eine neue Protokolldatei („cmdlog“) erstellt, und das Befehlsprotokoll wird gestartet.

```cmd
>Tools.LogCommandWindowOutput cmdlog
```

In diesem Beispiel werden Protokollierungsbefehle angehalten.

```cmd
>Tools.LogCommandWindowOutput /off
```

In diesem Beispiel wird das Protokollieren von Befehlen in der vormals verwendeten Protokolldatei wieder aufgenommen.

```cmd
>Tools.LogCommandWindowOutput /on
```

## <a name="see-also"></a>Weitere Informationen

- [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)
- [Befehlsfenster](../../ide/reference/command-window.md)
- [Feld „Suchen/Befehl“](../../ide/find-command-box.md)
- [Visual Studio-Befehlsaliase](../../ide/reference/visual-studio-command-aliases.md)
