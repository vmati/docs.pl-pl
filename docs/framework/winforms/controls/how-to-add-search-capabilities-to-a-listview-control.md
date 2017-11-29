---
title: 'Porady: dodawanie funkcji wyszukiwania do formantu ListView'
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
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd6c3011b234f9d281a68a51fa8d9ef9d610816c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="a0b96-102">Porady: dodawanie funkcji wyszukiwania do formantu ListView</span><span class="sxs-lookup"><span data-stu-id="a0b96-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="a0b96-103">Często podczas pracy z dużą listę elementów w <xref:System.Windows.Forms.ListView> kontroli, które chcesz zaoferować możliwości wyszukiwania dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a0b96-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="a0b96-104"><xref:System.Windows.Forms.ListView> Formant oferuje tę możliwość na dwa sposoby: dopasowywania tekstu i lokalizację wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="a0b96-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="a0b96-105"><xref:System.Windows.Forms.ListView.FindItemWithText%2A> Metoda służy do wyszukiwania tekstu w <xref:System.Windows.Forms.ListView> w widoku listy lub szczegółów podany ciąg wyszukiwania i opcjonalnie początkową i końcową indeksu.</span><span class="sxs-lookup"><span data-stu-id="a0b96-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="a0b96-106">Z kolei <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metoda pozwala znaleźć element <xref:System.Windows.Forms.ListView> w widoku ikon lub kafelka, mając do dyspozycji zestaw współrzędne x i y i kierunek do wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="a0b96-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="a0b96-107">Aby znaleźć element przy użyciu tekstu</span><span class="sxs-lookup"><span data-stu-id="a0b96-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="a0b96-108">Utwórz <xref:System.Windows.Forms.ListView> z <xref:System.Windows.Forms.ListView.View%2A> ustawioną właściwość <xref:System.Windows.Forms.View.Details> lub <xref:System.Windows.Forms.View.List>, a następnie wypełnij <xref:System.Windows.Forms.ListView> z elementami.</span><span class="sxs-lookup"><span data-stu-id="a0b96-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="a0b96-109">Wywołanie <xref:System.Windows.Forms.ListView.FindItemWithText%2A> jest metoda tekst elementu, który chcesz odnaleźć.</span><span class="sxs-lookup"><span data-stu-id="a0b96-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="a0b96-110">Poniższy przykładowy kod przedstawia sposób tworzenia prostej <xref:System.Windows.Forms.ListView>umieścić w nim elementów i użyj wprowadzanie tekstu od użytkownika, aby znaleźć element na liście.</span><span class="sxs-lookup"><span data-stu-id="a0b96-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="a0b96-111">Aby znaleźć element za pomocą współrzędnych x i y</span><span class="sxs-lookup"><span data-stu-id="a0b96-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="a0b96-112">Utwórz <xref:System.Windows.Forms.ListView> z <xref:System.Windows.Forms.View> ustawioną właściwość <xref:System.Windows.Forms.View.SmallIcon> lub <xref:System.Windows.Forms.View.LargeIcon>, a następnie wypełnij <xref:System.Windows.Forms.ListView> z elementami.</span><span class="sxs-lookup"><span data-stu-id="a0b96-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="a0b96-113">Wywołanie <xref:System.Windows.Forms.ListView.FindNearestItem%2A> jest metoda żądaną współrzędne x i y- a kierunek chcesz wyszukać.</span><span class="sxs-lookup"><span data-stu-id="a0b96-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="a0b96-114">Poniższy przykładowy kod przedstawia sposób tworzenia podstawowych ikona <xref:System.Windows.Forms.ListView>, umieścić w nim elementów i przechwytywania <xref:System.Windows.Forms.Control.MouseDown> zdarzenia do znalezienia najbliższej element w górę kierunku.</span><span class="sxs-lookup"><span data-stu-id="a0b96-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b96-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a0b96-115">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [<span data-ttu-id="a0b96-116">ListView — formant</span><span class="sxs-lookup"><span data-stu-id="a0b96-116">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="a0b96-117">Informacje o formancie ListView</span><span class="sxs-lookup"><span data-stu-id="a0b96-117">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="a0b96-118">Porady: Dodawanie i usuwanie elementów za pomocą systemu Windows formantu ListView formularzy</span><span class="sxs-lookup"><span data-stu-id="a0b96-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)