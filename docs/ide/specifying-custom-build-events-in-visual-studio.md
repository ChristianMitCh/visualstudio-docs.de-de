---
title: Angeben benutzerdefinierter Buildereignisse
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fda60ffb97ecb44bd4a881cb42e4d9199cc958b8
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "76115339"
---
# <a name="specify-custom-build-events-in-visual-studio"></a>Festlegen von benutzerdefinierten Buildereignissen in Visual Studio

Durch Angeben eines benutzerdefinierten Buildereignisses können Sie vor dem Starten oder nach dem Beenden eines Builds Befehle automatisch ausführen. Sie können beispielsweise eine *BAT-Datei* ausführen, bevor ein Build gestartet wird, oder neue Dateien in einen Ordner kopieren, nachdem der Build abgeschlossen wurde. Buildereignisse werden nur ausgeführt, wenn der Build die betreffenden Punkte im Buildprozess erfolgreich erreicht.

Spezifische Informationen zu den verwendeten Programmiersprachen finden Sie in den folgenden Themen:

- Visual Basic: [Vorgehensweise: Festlegen von Buildereignissen (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).

- C# und F#: [Vorgehensweise: Festlegen von Buildereignissen (C#)](../ide/how-to-specify-build-events-csharp.md).

- Visual C++: [Festlegen von Buildereignissen](/cpp/build/specifying-build-events).

## <a name="syntax"></a>Syntax

Buildereignisse folgen derselben Syntax wie DOS-Befehle, Sie können aber außerdem Makros verwenden, um die Erstellung zu erleichtern. Eine Liste der verfügbaren Makros finden Sie unter [Pre-build Event/Post-build Event command line dialog box (Dialogfelder „Befehlszeile für Präbuildereignis“ und „Befehlszeile für Postbuildereignis“)](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

Um optimale Ergebnisse zu erhalten, befolgen Sie diese Tipps zur Formatierung:

- Fügen Sie allen Buildereignissen, die `call`BAT-Dateien*ausführen, eine*-Anweisung hinzu.

   Ein Beispiel: `call C:\MyFile.bat`

   Ein Beispiel: `call C:\MyFile.bat call C:\MyFile2.bat`

- Schließen Sie Dateipfade in Anführungszeichen ein.

   Beispiel (für [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "%ProgramFiles(x86)%\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe" -if "$(TargetPath)"

- Trennen Sie mehrere Befehle durch Zeilenumbrüche.

- Verwenden Sie Platzhalterzeichen nach Bedarf.

   Beispiel: `for %I in (*.txt *.doc *.html) do copy %I c:\`*meinverzeichnis*`\`

  > [!NOTE]
  > `%I` im oben abgebildeten Code sollte in Batchskripts zu `%%I` werden.

## <a name="see-also"></a>Weitere Informationen

- [Kompilieren und Erstellen](../ide/compiling-and-building-in-visual-studio.md)
- [Pre-build Event/Post-build Event command line dialog box (Dialogfelder „Befehlszeile für Präbuildereignis“ und „Befehlszeile für Postbuildereignis“)](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)
- [MSBuild-Sonderzeichen](../msbuild/msbuild-special-characters.md)
- [Exemplarische Vorgehensweise: Erstellen einer Anwendung](../ide/walkthrough-building-an-application.md)
