---
title: "x:XData — Typ funkcji XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 3e448c28be6515748254e267b70f3c898b9226a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="e3381-102">x:XData — Typ funkcji XAML</span><span class="sxs-lookup"><span data-stu-id="e3381-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="e3381-103">Umożliwia umieszczanie Wysp danych XML w produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="e3381-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="e3381-104">Elementy XML w `x:XData` nie powinny być traktowane przez procesory XAML, jak, jeśli są one częścią działania domyślnej przestrzeni nazw XAML lub innych nazw XAML.</span><span class="sxs-lookup"><span data-stu-id="e3381-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="e3381-105">`x:XData`może zawierać dowolne poprawnie sformułowany plik XML.</span><span class="sxs-lookup"><span data-stu-id="e3381-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="e3381-106">Użycie elementu obiektu języka XAML</span><span class="sxs-lookup"><span data-stu-id="e3381-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e3381-107">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="e3381-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="e3381-108">Element z jednym elementem głównym Wyspy danych zamknięte.</span><span class="sxs-lookup"><span data-stu-id="e3381-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="e3381-109">Dla większości ostatecznego konsumentów XML, który nie ma jednym elementem głównym jest uznawane za nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e3381-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="e3381-110">W szczególności jednym elementem głównym jest wymagany, jeśli `x:XData` ma pełnić rolę źródła danych XML dla WPF i wiele innych technologii używające źródła XML dla powiązania danych.</span><span class="sxs-lookup"><span data-stu-id="e3381-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="e3381-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="e3381-111">Optional.</span></span> <span data-ttu-id="e3381-112">Kod XML, który reprezentuje dane XML.</span><span class="sxs-lookup"><span data-stu-id="e3381-112">XML that represents the XML data.</span></span> <span data-ttu-id="e3381-113">Dowolna liczba elementów może być używany jako element danych i elementów zagnieżdżonych mogą być zawarte w innych elementach; Ogólne zasady XML się.</span><span class="sxs-lookup"><span data-stu-id="e3381-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3381-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e3381-114">Remarks</span></span>  
 <span data-ttu-id="e3381-115">Elementy XML w `x:XData` obiekt można ponownie zadeklarować wszystkie możliwe obszary nazw i prefiksy zawierającego XMLDOM w danych.</span><span class="sxs-lookup"><span data-stu-id="e3381-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="e3381-116">Programowy dostęp do danych XML i `x:XData` wewnętrznego typu XAML jest możliwe w .NET Framework XAML Services za pośrednictwem <xref:System.Windows.Markup.XData> klasy.</span><span class="sxs-lookup"><span data-stu-id="e3381-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="e3381-117">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="e3381-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="e3381-118">`x:XData` Obiekt przede wszystkim jest używany jako obiekt podrzędny <xref:System.Windows.Data.XmlDataProvider>, lub też obiektu podrzędnego <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> właściwości (w języku XAML, to jest zwykle wyrażony w składni elementu właściwości).</span><span class="sxs-lookup"><span data-stu-id="e3381-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="e3381-119">Dane zwykle powinny przedefiniować podstawowej przestrzeni nazw XML w Wyspy danych jako nowy domyślnej przestrzeni nazw XML (Ustaw ciąg pusty).</span><span class="sxs-lookup"><span data-stu-id="e3381-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="e3381-120">Jest to najprostszy Wyspy proste danych, ponieważ <xref:System.Windows.Data.Binding.XPath%2A> wyrażeń, które są używane do odwołania i ich powiązania z danymi można uniknąć włączenia prefiksów.</span><span class="sxs-lookup"><span data-stu-id="e3381-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="e3381-121">Bardziej złożone Wyspy danych może zdefiniować wiele prefiksów dla danych i używać określonego prefiksu dla przestrzeni nazw XML w katalogu głównym.</span><span class="sxs-lookup"><span data-stu-id="e3381-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="e3381-122">W takim przypadku wszystkie <xref:System.Windows.Data.Binding.XPath%2A> odwołania do wyrażenia powinna zawierać prefiksu mapowane w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e3381-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="e3381-123">Aby uzyskać więcej informacji, zobacz [omówienie powiązania danych](../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3381-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="e3381-124">Z technicznego punktu widzenia `x:XData` mogą być używane jako zawartość żadnej właściwości typu <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="e3381-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="e3381-125">Jednak <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> tylko poświęcone implementacji.</span><span class="sxs-lookup"><span data-stu-id="e3381-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3381-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3381-126">See Also</span></span>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [<span data-ttu-id="e3381-127">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="e3381-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e3381-128">Powiązanie — rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="e3381-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)