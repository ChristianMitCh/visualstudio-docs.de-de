---
title: 'Vorgehensweise: Programmgesteuertes durchlaufen Sie gefundener Elemente in Dokumenten'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 22f8035cc7c1b09e7fd54f3c10842237ee6273b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812409"
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Vorgehensweise: Programmgesteuertes durchlaufen Sie gefundener Elemente in Dokumenten
  Die <xref:Microsoft.Office.Interop.Word.Find> -Klasse hat eine <xref:Microsoft.Office.Interop.Word.Find.Found%2A> -Eigenschaft, die jedes Mal **true** zurückgibt, wenn ein gesuchtes Element gefunden wurde. Sie können alle in einem <xref:Microsoft.Office.Interop.Word.Range> -Objekt gefundenen Instanzen mit der <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> -Methode durchlaufen.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-loop-through-found-items"></a>So durchlaufen Sie gefundene Elemente

1. Deklarieren Sie ein <xref:Microsoft.Office.Interop.Word.Range> -Objekt.

    Das folgende Codebeispiel kann in einer Anpassung auf Dokumentebene verwendet werden.

    [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
    [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]

    Das folgende Codebeispiel kann in einem VSTO-Add-In verwendet werden. In diesem Beispiel wird das aktive Dokument verwendet.

    [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]

2. Verwenden Sie die <xref:Microsoft.Office.Interop.Word.Find.Found%2A> -Eigenschaft in einer Schleife, um nach allen Vorkommen der Zeichenfolge im Dokument zu suchen, und erhöhen Sie eine ganzzahlige Variable jedes Mal um 1, wenn die Zeichenfolge gefunden wurde.

    [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
    [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]

3. Zeigen Sie in einem Meldungsfeld an, wie oft die Zeichenfolge gefunden wurde.

    [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
    [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]

   Die folgenden Beispiele zeigen die vollständige Methode.

## <a name="document-level-customization-example"></a>Beispiel für die Anpassung auf Dokumentebene

### <a name="to-loop-through-items-in-a-document-level-customization"></a>So durchlaufen Sie Elemente in einer Anpassung auf Dokumentebene

1. Das folgende Beispiel zeigt den vollständigen Code für eine Anpassung auf Dokumentebene. Wenn Sie diesen Code verwenden möchten, führen Sie ihn von der `ThisDocument` -Klasse im Projekt aus.

     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]

## <a name="vsto-add-in-example"></a>Beispiel für VSTO-Add-in

### <a name="to-loop-through-items-in-a-vsto-add-in"></a>So durchlaufen Sie Elemente in einem VSTO-Add-in

1. Das folgende Beispiel zeigt den vollständigen Code für ein VSTO-Add-In. Wenn Sie diesen Code verwenden möchten, führen Sie ihn von der `ThisAddIn` -Klasse im Projekt aus.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]

## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Programmgesteuertes suchen Sie und Ersetzen Sie Rext in Dokumenten](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Vorgehensweise: Programmgesteuertes Festlegen von Suchoptionen in Word](../vsto/how-to-programmatically-set-search-options-in-word.md)
- [Vorgehensweise: Programmgesteuertes definieren und Markieren von Bereichen in Dokumenten](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Vorgehensweise: Programmgesteuertes Wiederherstellen der Auswahl nach Suchvorgängen](../vsto/how-to-programmatically-restore-selections-after-searches.md)
- [Optionaler Parameter in Office-Projektmappen](../vsto/optional-parameters-in-office-solutions.md)
