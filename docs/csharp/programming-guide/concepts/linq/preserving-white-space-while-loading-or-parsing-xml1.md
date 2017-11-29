---
title: "Zachowanie podczas ładowania lub analizowania XML1 biały znak"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bc4923ef5ea526de3c988636cd766c3b012c902e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="7fa24-102">Zachowywanie biały znak podczas ładowania lub analiza kodu XML</span><span class="sxs-lookup"><span data-stu-id="7fa24-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="7fa24-103">W tym temacie opisano sposób kontrolowania zachowania biały znak [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fa24-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="7fa24-104">Typowy scenariusz jest Odczytaj dane XML z wcięciami, utwórz drzewo XML w pamięci bez żadnych białe węzły tekstowe (to znaczy nie zachowania biały znak), operacji na pliku XML, a następnie zapisz plik XML z wcięcia.</span><span class="sxs-lookup"><span data-stu-id="7fa24-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="7fa24-105">Podczas formatowania kodu XML, tylko znaczący biały znak w drzewie XML są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="7fa24-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="7fa24-106">Jest to domyślne zachowanie dla [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fa24-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="7fa24-107">Inny typowy scenariusz polega może odczytywać i modyfikować XML, który już został celowo wcięcia.</span><span class="sxs-lookup"><span data-stu-id="7fa24-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="7fa24-108">Nie można zmienić tej wcięcia w dowolny sposób.</span><span class="sxs-lookup"><span data-stu-id="7fa24-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="7fa24-109">Aby to zrobić w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], można zachować biały znak w przypadku obciążenia lub analizy kodu XML i wyłączyć formatowania podczas serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="7fa24-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="7fa24-110">W tym temacie opisano zachowanie biały znak metod, które wypełnić drzew XML.</span><span class="sxs-lookup"><span data-stu-id="7fa24-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="7fa24-111">Informacje dotyczące sterowania biały znak, podczas serializacji XML drzewa, zobacz [zachowania biały znak podczas serializowania](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="7fa24-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="7fa24-112">Zachowanie metody, które wypełnić drzew XML</span><span class="sxs-lookup"><span data-stu-id="7fa24-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="7fa24-113">Następujące metody w <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> klasy wypełnić drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="7fa24-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="7fa24-114">Drzewo składni XML z pliku, można go wypełnić <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, lub ciągiem:</span><span class="sxs-lookup"><span data-stu-id="7fa24-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="7fa24-115">Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.LoadOptions> jako argument metody nie zachowa nieważny biały znak.</span><span class="sxs-lookup"><span data-stu-id="7fa24-115">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="7fa24-116">W większości przypadków, gdy metoda korzysta z <xref:System.Xml.Linq.LoadOptions> jako argument, można opcjonalnie Zachowaj nieważny biały znak jako tekst węzłów w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="7fa24-116">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="7fa24-117">Jednak jeśli metoda Trwa ładowanie XML z <xref:System.Xml.XmlReader>, a następnie <xref:System.Xml.XmlReader> Określa, czy biały znak, zostaną zachowane, czy nie.</span><span class="sxs-lookup"><span data-stu-id="7fa24-117">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="7fa24-118">Ustawienie <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> nie odniesie żadnego skutku.</span><span class="sxs-lookup"><span data-stu-id="7fa24-118">Setting <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> will have no effect.</span></span>  
  
 <span data-ttu-id="7fa24-119">Z tych metod, jeśli biały znak jest zachowywany, nieważny biały znak jest wstawiany drzewa XML jako <xref:System.Xml.Linq.XText> węzłów.</span><span class="sxs-lookup"><span data-stu-id="7fa24-119">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="7fa24-120">Jeśli nie są zachowywane biały znak, nie są wstawiane węzły tekstowe.</span><span class="sxs-lookup"><span data-stu-id="7fa24-120">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="7fa24-121">Drzewo XML można tworzyć przy użyciu <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="7fa24-121">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7fa24-122">Węzły, które są zapisywane na <xref:System.Xml.XmlWriter> są wypełnione w drzewie.</span><span class="sxs-lookup"><span data-stu-id="7fa24-122">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="7fa24-123">Jednak podczas kompilowania drzewo XML za pomocą tej metody, wszystkie węzły są konserwowane, niezależnie od tego, czy węzeł jest białe, czy nie, lub czy biały znak jest istotny, czy nie.</span><span class="sxs-lookup"><span data-stu-id="7fa24-123">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa24-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7fa24-124">See Also</span></span>  
 [<span data-ttu-id="7fa24-125">Analiza kodu XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7fa24-125">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)