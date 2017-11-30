---
title: "Języku zintegrowanym osi w języku Visual Basic (LINQ do XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d648ba7c8710f73c4aeb8dad3983f219c5fe1815
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="39155-102">Języku zintegrowanym osi w języku Visual Basic (LINQ do XML)</span><span class="sxs-lookup"><span data-stu-id="39155-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="39155-103">Ta sekcja zawiera opis funkcji wbudowanych bezpośrednio w [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] języka aby ułatwić dostęp XML.</span><span class="sxs-lookup"><span data-stu-id="39155-103">This section describes features built directly into the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="39155-104">Większość przykładów w LINQ do dokumentacji XML ich używać zintegrowanych [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] osi.</span><span class="sxs-lookup"><span data-stu-id="39155-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39155-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="39155-105">In This Section</span></span>  
  
|<span data-ttu-id="39155-106">Temat</span><span class="sxs-lookup"><span data-stu-id="39155-106">Topic</span></span>|<span data-ttu-id="39155-107">Opis</span><span class="sxs-lookup"><span data-stu-id="39155-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="39155-108">Właściwość osi elementu podrzędnego XML</span><span class="sxs-lookup"><span data-stu-id="39155-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="39155-109">Zapewnia dostęp do jednego z następujących elementów podrzędnych: <xref:System.Xml.Linq.XElement> obiektu <xref:System.Xml.Linq.XDocument> obiektu, to zbiór <xref:System.Xml.Linq.XElement> obiektów lub kolekcji <xref:System.Xml.Linq.XDocument> obiektów.</span><span class="sxs-lookup"><span data-stu-id="39155-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="39155-110">Ta oś jest odpowiednikiem <xref:System.Xml.Linq.XContainer.Elements%2A> osi.</span><span class="sxs-lookup"><span data-stu-id="39155-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="39155-111">Właściwości osi elementu podrzędnego XML</span><span class="sxs-lookup"><span data-stu-id="39155-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="39155-112">Zapewnia dostęp do następujących elementów podrzędnych: <xref:System.Xml.Linq.XElement> obiektu <xref:System.Xml.Linq.XDocument> obiekcie lub kolekcji <xref:System.Xml.Linq.XElement> obiektów.</span><span class="sxs-lookup"><span data-stu-id="39155-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="39155-113">Ta oś jest odpowiednikiem <xref:System.Xml.Linq.XContainer.Descendants%2A> osi.</span><span class="sxs-lookup"><span data-stu-id="39155-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="39155-114">Właściwości osi atrybutu XML</span><span class="sxs-lookup"><span data-stu-id="39155-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="39155-115">Zapewnia dostęp do atrybutu <xref:System.Xml.Linq.XElement> obiektu.</span><span class="sxs-lookup"><span data-stu-id="39155-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="39155-116">Ta oś jest w przybliżeniu równy <xref:System.Xml.Linq.XElement.Attribute%2A> osi.</span><span class="sxs-lookup"><span data-stu-id="39155-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="39155-117">Tej osi różni się od <xref:System.Xml.Linq.XElement.Attribute%2A> osi, który zwraca wartość atrybutu, nie <xref:System.Xml.Linq.XAttribute> obiektu.</span><span class="sxs-lookup"><span data-stu-id="39155-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="39155-118">Właściwość indeksatora rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="39155-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="39155-119">Zapewnia dostęp do poszczególnych elementów w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="39155-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39155-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39155-120">See Also</span></span>  
 [<span data-ttu-id="39155-121">LINQ do osi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39155-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)