---
title: "Porady: Pisanie zapytań na kod XML w przestrzeni nazw (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5708a2a162132262722f390842f59c9c6a6838e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="86925-102">Porady: Pisanie zapytań na kod XML w przestrzeni nazw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86925-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="86925-103">Aby napisać zapytanie na języku XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają poprawną przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="86925-104">W języku Visual Basic najbardziej typowym podejściem jest zdefiniowanie globalnej przestrzeni nazw, a następnie użyj literały XML i właściwości XML, które używają globalnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="86925-105">Można określić domyślnej globalnej przestrzeni nazw, w którym to przypadku elementy w literałach XML będzie się w przestrzeni nazw domyślnie.</span><span class="sxs-lookup"><span data-stu-id="86925-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="86925-106">Alternatywnie można zdefiniować globalnej przestrzeni nazw z prefiksem, a następnie użyć prefiksu zgodnie z wymaganiami w literałach XML i właściwości XML.</span><span class="sxs-lookup"><span data-stu-id="86925-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="86925-107">Podobnie jak w przypadku innych rodzajów XML atrybuty są zawsze podkatalogi domyślnie obszaru nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="86925-108">Pierwszy zestaw przykłady w tym temacie przedstawiono sposób tworzenia drzewo XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="86925-109">Drugi zestaw pokazano, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="86925-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86925-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="86925-110">Example</span></span>  
 <span data-ttu-id="86925-111">Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="86925-112">Następnie pobierania kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="86925-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="86925-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86925-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="86925-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="86925-114">Example</span></span>  
 <span data-ttu-id="86925-115">W języku Visual Basic, jednak Pisanie zapytań w drzewie XML, który używa przestrzeni nazw z prefiksem bardzo różni się od badania drzewo XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86925-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="86925-116">Zazwyczaj używają `Imports` instrukcji, aby zaimportować przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="86925-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="86925-117">Następnie należy użyć prefiksu w nazwach elementów i atrybutów podczas skonstruuj drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="86925-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="86925-118">Prefiks można także użyć podczas wykonywania zapytania drzewa XML za pomocą właściwości XML.</span><span class="sxs-lookup"><span data-stu-id="86925-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="86925-119">Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="86925-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="86925-120">Następnie pobierania kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="86925-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="86925-121">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86925-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="86925-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="86925-122">See Also</span></span>  
 [<span data-ttu-id="86925-123">Praca z przestrzeni nazw XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86925-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)