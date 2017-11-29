---
title: "Jak nadać styl wierszowi w ListView, który implementuje GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c51f6cc5c35200267aa84960655fd734a937a7c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="32efa-102">Jak nadać styl wierszowi w ListView, który implementuje GridView</span><span class="sxs-lookup"><span data-stu-id="32efa-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="32efa-103">W tym przykładzie pokazano, jak do nadawania stylu wiersza w <xref:System.Windows.Controls.ListView> formant, który implementuje <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> tryb.</span><span class="sxs-lookup"><span data-stu-id="32efa-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32efa-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="32efa-104">Example</span></span>  
 <span data-ttu-id="32efa-105">Styl możesz wiersza w <xref:System.Windows.Controls.ListView> kontroli przez ustawienie <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> na <xref:System.Windows.Controls.ListView> formantu.</span><span class="sxs-lookup"><span data-stu-id="32efa-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="32efa-106">Ustawienie stylu dla jego elementów, które są reprezentowane jako <xref:System.Windows.Controls.ListViewItem> obiektów.</span><span class="sxs-lookup"><span data-stu-id="32efa-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="32efa-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Odwołania <xref:System.Windows.Controls.ControlTemplate> obiektów, które są używane do wyświetlania zawartości wiersza.</span><span class="sxs-lookup"><span data-stu-id="32efa-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="32efa-108">Wyświetla całą próbkę następujące przykłady są wyodrębniane z, kolekcję utworu informacji przechowywanych w [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] bazy danych.</span><span class="sxs-lookup"><span data-stu-id="32efa-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="32efa-109">Każdy utworu w bazie danych znajduje się pole klasyfikacji i wartość tego pola określa sposób wyświetlania wiersza utworu informacji.</span><span class="sxs-lookup"><span data-stu-id="32efa-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="32efa-110">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> dla <xref:System.Windows.Controls.ListViewItem> obiekty reprezentujące utworów muzycznych w kolekcji utworów.</span><span class="sxs-lookup"><span data-stu-id="32efa-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="32efa-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Odwołania <xref:System.Windows.Controls.ControlTemplate> obiektów, które określają sposób wyświetlania wiersza utworu informacji.</span><span class="sxs-lookup"><span data-stu-id="32efa-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="32efa-112">W poniższym przykładzie przedstawiono <xref:System.Windows.Controls.ControlTemplate> dodaje ciąg tekstowy `"Strongly Recommended"` do wiersza.</span><span class="sxs-lookup"><span data-stu-id="32efa-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="32efa-113">Ten szablon jest przywoływany w <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> i wyświetlany, gdy klasyfikacja utworu ma wartość 5 (pięć).</span><span class="sxs-lookup"><span data-stu-id="32efa-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="32efa-114"><xref:System.Windows.Controls.ControlTemplate> Obejmuje <xref:System.Windows.Controls.GridViewRowPresenter> obiekt, który wychodzi poza zawartości wiersza w kolumnach, zgodnie z definicją <xref:System.Windows.Controls.GridView> trybu wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="32efa-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="32efa-115">W poniższym przykładzie zdefiniowano <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="32efa-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="32efa-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32efa-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="32efa-117">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="32efa-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="32efa-118">ListView — omówienie</span><span class="sxs-lookup"><span data-stu-id="32efa-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="32efa-119">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="32efa-119">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)