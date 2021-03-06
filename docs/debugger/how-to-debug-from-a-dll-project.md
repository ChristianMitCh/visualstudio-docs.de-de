---
title: 'Vorgehensweise: Debuggen über ein DLL-Projekt | Microsoft-Dokumentation'
ms.date: 10/10/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2e4df2028a14281ee2343ad48b4b71812d29fca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62847983"
---
# <a name="how-to-debug-from-a-dll-project-in-visual-studio-c-c-visual-basic-f"></a>Vorgehensweise: Debuggen über ein DLL-Projekt in Visual Studio (C#, C++, Visual Basic, F#)

Eine Möglichkeit zum Debuggen eines DLL-Projekts besteht darin, die aufrufende App in den Eigenschaften des DLL-Projekts anzugeben. Dann können Sie mit dem Debuggen über das DLL-Projekt beginnen. Damit diese Methode funktioniert, muss die App dieselbe DLL an demselben Speicherort aufrufen, die mit Ihrer Konfiguration identisch ist. Wenn die App eine andere Version der DLL findet und lädt, enthält diese Version Ihre Haltepunkte nicht. Weitere Methoden zum Debuggen von DLLs sind unter [Debuggen von DLL-Projekten](../debugger/debugging-dll-projects.md) beschrieben.

Wenn Ihre verwaltete App eine native DLL oder die native App eine verwaltete DLL aufruft, können Sie sowohl die DLL als auch die aufrufende App debuggen. Weitere Informationen finden Sie unter [Vorgehensweise: Debuggen im gemischten Modus](../debugger/how-to-debug-in-mixed-mode.md).

Native und verwaltete DLL-Projekte verfügen über unterschiedliche Einstellungen, um aufrufende Apps anzugeben.

## <a name="specify-a-calling-app-in-a-native-dll-project"></a>Angeben einer aufrufenden App in einem nativen DLL-Projekt

1. Wählen Sie im **Projektmappen-Explorer** das C++-DLL-Projekt aus. Wählen Sie das Symbol **Eigenschaften** aus, und drücken Sie **ALT**+**EINGABETASTE**, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften** aus.

1. Stellen Sie im Dialogfeld **\<Projekt > Eigenschaftenseiten** sicher, dass das Feld **Konfiguration** am oberen Rand des Fensters auf **Debuggen** eingestellt ist.

1. Wählen Sie **Konfigurationseigenschaften** > **Debuggen** aus.

1. Wählen Sie in der Liste **Zu startender Debugger** entweder **Lokaler Windows-Debugger** oder **Remote-Windows-Debugger** aus.

1. Fügen Sie im Feld **Befehl** oder **Remotebefehl** den vollqualifizierten Pfad und den Dateinamen der aufrufenden App hinzu, z. B. eine *EXE*-Datei.

   ![Debugeigenschaftenfenster](../debugger/media/dbg-debugging-properties-dll.png "Debugeigenschaftenfenster")

1. Fügen Sie die notwendigen Programmargumente in das Feld **Befehlsargumente** ein.

1. Klicken Sie auf **OK**.

## <a name="specify-a-calling-app-in-a-managed-dll-project"></a>Angeben einer aufrufenden App in einem verwalteten DLL-Projekt

1. Wählen Sie im **Projektmappen-Explorer** das C#- oder Visual Basic-DLL-Projekt aus. Wählen Sie das Symbol **Eigenschaften** aus, und drücken Sie **ALT**+**EINGABETASTE**, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften** aus.

1. Stellen Sie sicher, dass das Feld **Konfiguration** am oberen Rand des Fensters auf **Debuggen** festgelegt ist.

1. Legen Sie unter **Startaktion** Folgendes fest:

   - Wählen Sie für .NET Framework-DLLs die Option **Externes Programm starten** aus, und fügen Sie den vollqualifizierten Pfad und den Namen der aufrufenden App hinzu.

   - Oder wählen Sie **Browser mit URL starten** aus, und geben Sie die URL einer lokalen ASP.NET-App ein.

   - Bei .NET Core-DLLs ist Eigenschaftenseite **Debuggen** anders. Wählen Sie im Dropdownmenü **Start** die Option **Ausführbare Datei** aus, und fügen Sie dann im Feld **Ausführbare Datei** den vollqualifizierten Pfad und den Namen der aufrufenden App hinzu.

1. Fügen Sie im Feld **Befehlszeilenargumente** oder **Anwendungsargumente** alle erforderlichen Befehlszeilenargumente hinzu.

   ![C#-Debugeigenschaftenfenster](../debugger/media/dbg-debugging-properties-dll-csharp.png "C#-Debugeigenschaftenfenster")

1. Verwenden Sie **Datei** > **Ausgewählte Elemente speichern** oder **STRG**+**S**, um die Änderungen zu speichern.

## <a name="debug-from-the-dll-project"></a>Debuggen über das DLL-Projekt

1. Legen Sie Haltepunkte im DLL-Projekt fest.

1. Klicken Sie mit der rechten Maustaste auf das DLL-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

1. Stellen Sie sicher, dass das Feld **Projektmappenkonfiguration** auf **Debuggen** eingestellt ist. Drücken Sie **F5**, und klicken Sie auf den grünen **Startpfeil**, oder wählen Sie **Debuggen** > **Debuggen starten** aus.

Wenn beim Debuggen die Haltepunkte nicht getroffen werden, stellen Sie sicher, dass die DLL-Ausgabe (standardmäßig der Ordner *\<project>\Debug*) in den Speicherort erfolgt, den die aufrufende App aufruft.

## <a name="see-also"></a>Siehe auch
- [Debugging DLL projects (Debuggen von DLL-Projekten)](../debugger/debugging-dll-projects.md)
- [Projekteinstellungen für C#-Debugkonfigurationen](../debugger/project-settings-for-csharp-debug-configurations.md)
- [Projekteinstellungen für eine Visual Basic-Debugkonfiguration](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Projekteinstellungen für eine C++-Debugkonfiguration](../debugger/project-settings-for-a-cpp-debug-configuration.md)