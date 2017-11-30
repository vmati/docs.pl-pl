---
title: "Porady: dostosowywanie wyglądu komórek w formancie DataGridView formularzy systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545a3bff5e810f9c0a995366e7f6460930f9e936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Porady: dostosowywanie wyglądu komórek w formancie DataGridView formularzy systemu Windows
Obsługa można dostosować wygląd dowolną komórkę <xref:System.Windows.Forms.DataGridView> formantu <xref:System.Windows.Forms.DataGridView.CellPainting> zdarzeń. Można wyodrębnić <xref:System.Windows.Forms.DataGridView> formantu <xref:System.Drawing.Graphics> z <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> właściwość <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Z tym <xref:System.Drawing.Graphics>, mogą wpływać na wygląd całą <xref:System.Windows.Forms.DataGridView> sterowania, ale zazwyczaj można wpływają na wygląd komórek, który jest obecnie rysowane. <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Właściwość <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> pozwala ograniczyć do komórek, która jest obecnie rysowane operacje rysowania.  
  
 W poniższym przykładzie kodu namaluje wszystkie komórki w `ContactName` przy użyciu kolumny <xref:System.Windows.Forms.DataGridView> schemat kolorów formantu. Zawartość tekstu każdej komórki jest rysowane w <xref:System.Drawing.Color.Crimson%2A>, i krawędzi prostokąta jest rysowana w taki sam jak kolor <xref:System.Windows.Forms.DataGridView> formantu <xref:System.Windows.Forms.DataGridView.GridColor%2A> właściwości.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   A <xref:System.Windows.Forms.DataGridView> formantu o nazwie `dataGridView1` z `ContactName` kolumny znajdującego się w tabeli Klienci w bazie danych Northwind.  
  
-   Odwołania do zestawów systemu, System.Windows.Forms i System.Drawing.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Dostosowywanie formantu DataGridView formularzy systemu Windows](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)