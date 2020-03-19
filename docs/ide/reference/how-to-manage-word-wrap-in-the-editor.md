---
title: Zeilenumbruch
ms.date: 11/07/2018
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- editors, text viewing
- Code Editor, word wrap
ms.assetid: 442f33ef-9f52-4515-b55f-fb816d664645
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f456a35f4a65438df5229492beb1f3e142e38f05
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79508939"
---
# <a name="how-to-manage-word-wrap-in-the-editor"></a>Vorgehensweise: Verwalten von Zeilenumbrüchen im Editor

Sie können die Option **Zeilenumbruch** aktivieren und deaktivieren. Wenn diese Option aktiviert ist, wird der Teil einer langen Zeile, der über die aktuelle Breite des Code-Editor-Fensters hinausgeht, auf der nächsten Zeile angezeigt. Wenn diese Option deaktiviert ist, können Sie nach rechts scrollen, um ans Ende von langen Zeilen zu gelangen, z.B. um die Verwendung der Zeilennummerierung zu erleichtern.

> [!NOTE]
> Dieses Thema gilt nur für Visual Studio unter Windows. Visual Studio für Mac unterstützt derzeit keine Zeilenumbrüche.

## <a name="to-set-word-wrap-preferences"></a>So legen Sie Einstellungen für den Zeilenumbruch fest

1. Klicken Sie im Menü **Extras** auf **Optionen**.

2. Wählen Sie im Ordner **Text-Editor** im Unterordner **Alle Sprachen** die Option **Allgemein** aus, um diese Option global festzulegen.

     \- oder -

     Wählen Sie die Optionen **Allgemein** im Unterordner für die Sprache aus, in der Sie programmieren.

3. Aktivieren oder Deaktivieren Sie in **Einstellungen** die Option **Zeilenumbruch**.

     Wenn die Option **Zeilenumbruch** aktiviert ist, wird die Option **Visuelle Symbole für Zeilenumbruch anzeigen** aktiviert.

4. Wählen Sie die Option **Visuelle Symbole für Zeilenumbruch anzeigen** aus, wenn Sie beim Umbruch einer langen Zeile auf eine zweite Zeile lieber einen Indikator in Form eines Rückwärtspfeils anzeigen lassen möchten. Deaktivieren Sie diese Option, wenn Sie diese Indikatoren nicht anzeigen möchten.

    > [!NOTE]
    > Diese Markierungspfeile werden nicht in Ihren Code eingefügt, sie dienen lediglich der Anzeige.

## <a name="known-issues"></a>Bekannte Probleme

Wenn Sie mit Zeilenumbrüchen in Notepad++, Sublime Text oder Visual Studio Code vertraut sind, beachten Sie folgende Probleme, bei denen Visual Studio sich anders als andere Editoren verhält:

* [Triple click doesn't select whole line (Durch dreifaches Klicken wird nicht die gesamte Zeile ausgewählt)](https://developercommunity.visualstudio.com/content/problem/268989/triple-click-doesnt-select-whole-line-when-word-wr.html)
* [Pressing End key twice does not move cursor to end of line (Durch doppeltes Drücken der Taste „Ende“ wird der Zeiger nicht zum Zeilenende bewegt)](https://developercommunity.visualstudio.com/content/problem/138274/pressing-end-key-twice-should-move-cursor-to-end-o.html)

## <a name="see-also"></a>Weitere Informationen

- [Funktionen des Code-Editors](../../ide/writing-code-in-the-code-and-text-editor.md)
