---
title: "Porady: uzyskiwanie dostępu do obiektów powiązanych z wierszami formantu DataGridView formularzy systemu Windows"
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
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66db5f6ff7b964162f77317f17a9e3a8d3ed22b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>Porady: uzyskiwanie dostępu do obiektów powiązanych z wierszami formantu DataGridView formularzy systemu Windows
Czasami jest przydatne wyświetlić tabelę informacji przechowywanych w kolekcji obiektów biznesowych. Po powiązaniu <xref:System.Windows.Forms.DataGridView> formant do tych kolekcji, każda właściwość publiczna jest wyświetlany w kolumnie, chyba że właściwość jest oznaczona nie można przeglądać z <xref:System.ComponentModel.BrowsableAttribute>. Na przykład kolekcja `Customer` obiekty takie jak miałoby kolumn **nazwa** i **adres**.  
  
 Jeśli te obiekty zawierają dodatkowe informacje i kod, który chcesz uzyskać dostęp, możesz uzyskać do niej dostęp za pośrednictwem obiektów wiersza. W poniższym przykładzie kodu użytkownicy mogą wybrać wiele wierszy i kliknij przycisk, aby wysłać faktury do każdego z odpowiednich klientów.  
  
### <a name="to-access-row-bound-objects"></a>Dostęp do obiektów powiązanych z wiersza  
  
-   Użyj <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> właściwości.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>Przykład  
 Pełny przykład kodu obejmuje prostą `Customer` implementacji i wiązania <xref:System.Windows.Forms.DataGridView> do <xref:System.Collections.ArrayList> zawierającego kilka `Customer` obiektów. <xref:System.Windows.Forms.Control.Click> Obsługi zdarzeń <xref:System.Windows.Forms.Button?displayProperty=nameWithType> muszą uzyskać dostęp do `Customer` obiektów za pomocą wierszy, ponieważ kolekcja klienta nie jest dostępny na zewnątrz <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> obsługi zdarzeń.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów systemu i System.Windows.Forms.  
  
 Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.  Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [Wyświetlanie danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Instrukcje: wiązanie obiektów z kontrolkami DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
