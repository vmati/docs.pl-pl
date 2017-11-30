---
title: "Jak zdefiniować tabelę przy użyciu XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 350dff0b6ea9d92e919e45e4f46cf888f44f6212
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="8eb4f-102">Jak zdefiniować tabelę przy użyciu XAML</span><span class="sxs-lookup"><span data-stu-id="8eb4f-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="8eb4f-103">W poniższym przykładzie pokazano sposób definiowania <xref:System.Windows.Documents.Table> przy użyciu [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8eb4f-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="8eb4f-104">Przykładowa tabela ma cztery kolumny (reprezentowany przez <xref:System.Windows.Documents.TableColumn> elementy) i kilka wierszy (reprezentowane przez <xref:System.Windows.Documents.TableRow> elementy) zawierające dane, a także jako tytuł, nagłówek i informacje stopki.</span><span class="sxs-lookup"><span data-stu-id="8eb4f-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="8eb4f-105">Wierszy musi być zawarty w <xref:System.Windows.Documents.TableRowGroup> elementu.</span><span class="sxs-lookup"><span data-stu-id="8eb4f-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="8eb4f-106">Każdy wiersz w tabeli składa się z co najmniej jedna komórka (reprezentowane przez <xref:System.Windows.Documents.TableCell> elementów).</span><span class="sxs-lookup"><span data-stu-id="8eb4f-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="8eb4f-107">Zawartość w komórce tabeli muszą być zawarte w <xref:System.Windows.Documents.Block> elementu; w takim przypadku <xref:System.Windows.Documents.Paragraph> elementy są używane.</span><span class="sxs-lookup"><span data-stu-id="8eb4f-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="8eb4f-108">Tabela hostuje również hiperłącza (reprezentowane przez <xref:System.Windows.Documents.Hyperlink> element) w wierszu stopki.</span><span class="sxs-lookup"><span data-stu-id="8eb4f-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb4f-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="8eb4f-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="8eb4f-110">Na poniższej ilustracji przedstawiono, jak renderuje tabeli zdefiniowane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8eb4f-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="8eb4f-111">![Tabela renderowany. ] (../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="8eb4f-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>