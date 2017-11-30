---
title: Modyfikowanie drzew XML (LINQ do XML) (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de66788186f3ffd09560d8eacdebbbaa5edf067c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="99f2d-102">Modyfikowanie drzew XML (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="99f2d-103">jest magazynu w pamięci dla drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="99f2d-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="99f2d-104">Po załadować lub przeanalizować drzewo XML ze źródła, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] umożliwia modyfikowanie tego drzewa w miejscu, a następnie serializować drzewa, być może zapisać go do pliku lub wysłanie ich do serwera zdalnego.</span><span class="sxs-lookup"><span data-stu-id="99f2d-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="99f2d-105">Po zmodyfikowaniu drzewa w miejscu niektórych metod, takich jak używać <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="99f2d-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="99f2d-106">Istnieje jednak innym rozwiązaniem, który jest używany konstrukcji funkcjonalności do generowania nowego drzewa z innego kształtu.</span><span class="sxs-lookup"><span data-stu-id="99f2d-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="99f2d-107">W zależności od typów zmian, które należy wprowadzić swoje drzewo XML, a w zależności od wielkości drzewa ta metoda może być bardziej niezawodne i łatwiejsze do opracowywania.</span><span class="sxs-lookup"><span data-stu-id="99f2d-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="99f2d-108">Pierwszym temacie w tej sekcji porównanie tych dwóch metod.</span><span class="sxs-lookup"><span data-stu-id="99f2d-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99f2d-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="99f2d-109">In This Section</span></span>  
  
|<span data-ttu-id="99f2d-110">Temat</span><span class="sxs-lookup"><span data-stu-id="99f2d-110">Topic</span></span>|<span data-ttu-id="99f2d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="99f2d-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="99f2d-112">Vs modyfikacji drzewa XML w pamięci. Konstrukcja funkcjonalności (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="99f2d-113">Porównuje modyfikowanie drzewo XML w pamięci do budowy funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="99f2d-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="99f2d-114">Dodawanie elementy, atrybuty i węzłów do drzewa XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="99f2d-115">Zawiera informacje o dodawaniu elementy, atrybuty lub węzłów do drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="99f2d-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="99f2d-116">Modyfikowanie elementy, atrybuty i węzłów w drzewie XML</span><span class="sxs-lookup"><span data-stu-id="99f2d-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="99f2d-117">Zawiera informacje dotyczące modyfikowania istniejące elementy, atrybuty lub węzłów.</span><span class="sxs-lookup"><span data-stu-id="99f2d-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="99f2d-118">Usuwanie elementy, atrybuty i węzły z drzewa XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="99f2d-119">Zawiera informacje o usuwaniu elementy, atrybuty lub węzłów w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="99f2d-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="99f2d-120">Obsługa pary nazwa/wartość (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="99f2d-121">Zawiera opis sposobu obsługi informacji o aplikacji, która najlepiej jest przechowywane jako pary nazwa/wartość, takie jak informacje o konfiguracji lub ustawień globalnych.</span><span class="sxs-lookup"><span data-stu-id="99f2d-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="99f2d-122">Porady: Zmienianie Namespace drzewo całego XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="99f2d-123">Przedstawia sposób przenoszenia drzewa XML z jednej przestrzeni nazw do innego.</span><span class="sxs-lookup"><span data-stu-id="99f2d-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99f2d-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="99f2d-124">See Also</span></span>  
 [<span data-ttu-id="99f2d-125">Przewodnik programowania w języku (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f2d-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)