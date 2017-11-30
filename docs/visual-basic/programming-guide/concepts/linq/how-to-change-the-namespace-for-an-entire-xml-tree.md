---
title: "Porady: Zmienianie Namespace drzewo całego XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1837324b-5cb5-4fa8-95b9-3071efa0f913
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c5ee83840f9d8b4105e7af53008a329dfde37d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-visual-basic"></a><span data-ttu-id="0d4dd-102">Porady: Zmienianie Namespace drzewo całego XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d4dd-102">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>
<span data-ttu-id="0d4dd-103">Czasami trzeba programowo zmienić przestrzeni nazw dla elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="0d4dd-104">LINQ do XML ułatwia to.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="0d4dd-105"><xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> Można ustawić właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="0d4dd-106"><xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> Nie można ustawić właściwości, ale można go łatwo skopiować atrybuty do <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, Usuń istniejące atrybuty, a następnie dodaj nowe atrybuty, które znajdują się w nowej przestrzeni nazw żądany.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="0d4dd-107">Aby uzyskać więcej informacji, zobacz [Praca z przestrzeni nazw XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="0d4dd-107">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d4dd-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d4dd-108">Example</span></span>  
 <span data-ttu-id="0d4dd-109">Poniższy kod tworzy dwa drzewa XML w bez przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="0d4dd-110">Następnie zmiany nazw poszczególnych drzewa i łączy je w jednym drzewie.</span><span class="sxs-lookup"><span data-stu-id="0d4dd-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```vb  
Dim tree1 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim tree2 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim ad As XNamespace = "http://www.adatum.com"  
' change the namespace of every element and attribute in the first tree  
For Each el As XElement In tree1.DescendantsAndSelf  
    el.Name = aw.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' change the namespace of every element and attribute in the second tree  
For Each el As XElement In tree2.DescendantsAndSelf()  
    el.Name = ad.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' add attribute namespaces so that the tree will be serialized with  
' the aw and ad namespace prefixes  
tree1.Add( _  
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _  
)  
tree2.Add( _  
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _  
)  
' create a new composite tree  
Dim root As XElement = _  
    <Root>  
        <%= tree1 %>  
        <%= tree2 %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="0d4dd-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0d4dd-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d4dd-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d4dd-112">See Also</span></span>  
 [<span data-ttu-id="0d4dd-113">Modyfikowanie drzew XML (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d4dd-113">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)