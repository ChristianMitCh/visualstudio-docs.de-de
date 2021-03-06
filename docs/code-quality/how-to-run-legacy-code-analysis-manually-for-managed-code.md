---
title: Manuelles Ausführen der Legacy Code Analyse für verwalteten Code
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- code analysis, running
ms.assetid: 5086d228-f92e-4515-9708-c5b89b9e9a03
author: Mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 44190f8e828f9a971f15b57266978603dcac8139
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "85462061"
---
# <a name="how-to-run-legacy-code-analysis-manually-for-managed-code"></a>Gewusst wie: Manuelles Ausführen der Legacy Code Analyse für verwalteten Code
Das Code Analysetool enthält Informationen zu möglichen Fehlern im Quellcode. Sie können die Code Analyse automatisch mit jedem Build eines Code Projekts ausführen, und Sie können die Code Analyse auch manuell ausführen. Die Regeln, die beim Ausführen der Code Analyse geprüft werden, werden auf der Seite Code Analyse der Eigenschaften Seiten des Projekts angegeben. Weitere Informationen finden Sie unter Gewusst [wie: Konfigurieren der Code Analyse für ein Projekt mit verwaltetem Code](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).

## <a name="to-run-code-analysis-manually"></a>So führen Sie die Code Analyse manuell aus

1. Wenn Sie Visual Studio 2019 Version 16,5 oder höher ausführen, führen Sie vor dem Starten von Visual Studio den folgenden Befehl an der Eingabeaufforderung aus:

```
set EnableLegacyCodeAnalysis = true
```

2. Klicken Sie in **Projektmappen-Explorer**auf das Projekt.

3. Klicken Sie im Menü **analysieren** auf **Code Analyse für** *Projekt Name*ausführen.

