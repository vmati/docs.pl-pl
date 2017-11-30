---
title: Style i szablony wbudowane
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2acb455db8f8bdc5a95bfd2462b651cebbb692c3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="5e98b-102">Style i szablony wbudowane</span><span class="sxs-lookup"><span data-stu-id="5e98b-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="5e98b-103">udostępnia <xref:System.Windows.Style> obiekty i szablonu (<xref:System.Windows.FrameworkTemplate> podklasy) jako sposób definiowania wygląd elementu w zasobach, dzięki czemu mogą być używane wiele razy.</span><span class="sxs-lookup"><span data-stu-id="5e98b-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="5e98b-104">Z tego powodu atrybutów w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] typy, które wymagają <xref:System.Windows.Style> i <xref:System.Windows.FrameworkTemplate> prawie zawsze zasobów odwołuje się do istniejącego style i szablony, zamiast definiować nowych wbudowanego.</span><span class="sxs-lookup"><span data-stu-id="5e98b-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="5e98b-105">Ograniczenia style wbudowane i szablony</span><span class="sxs-lookup"><span data-stu-id="5e98b-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="5e98b-106">W [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], technicznie można ustawić właściwości stylu i szablonu w jeden z dwóch sposobów.</span><span class="sxs-lookup"><span data-stu-id="5e98b-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="5e98b-107">Za pomocą składni atrybutów ma dotyczyć odwołanie styl, który został zdefiniowany w ramach zasobu, na przykład `<` *obiektu*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="5e98b-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="5e98b-108">Lub składni elementu właściwości umożliwia definiowanie w tekście stylu, na przykład:</span><span class="sxs-lookup"><span data-stu-id="5e98b-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="5e98b-109">`<`*obiektu*`>`</span><span class="sxs-lookup"><span data-stu-id="5e98b-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="5e98b-110">`<`*obiektu*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="5e98b-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="5e98b-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="5e98b-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="5e98b-112">`</`*obiektu*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="5e98b-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="5e98b-113">`</`*obiektu*`>`</span><span class="sxs-lookup"><span data-stu-id="5e98b-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="5e98b-114">Użycie atrybutu jest znacznie bardziej powszechne.</span><span class="sxs-lookup"><span data-stu-id="5e98b-114">The attribute usage is much more common.</span></span> <span data-ttu-id="5e98b-115">Styl, który zdefiniowano w tekście i zasoby nie są zdefiniowane w niekoniecznie obejmuje tylko zawierającego element i nie można ponownie użyć równie łatwo, ponieważ nie ma on zasobów klucza.</span><span class="sxs-lookup"><span data-stu-id="5e98b-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="5e98b-116">Ogólnie rzecz biorąc jest bardziej elastyczne i przydatne zasób zdefiniowany styl i jest bardziej zgodne ogólne [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programowania modelu Zasada oddzielenia logice programu w kodzie z projektu w znaczniku.</span><span class="sxs-lookup"><span data-stu-id="5e98b-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="5e98b-117">Zwykle to nie nie powodu można ustawić stylu lub szablonie wbudowany, nawet jeśli zamierzasz używać tego stylu lub szablonie w tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="5e98b-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="5e98b-118">Większość elementów, które można wykonać w stylu lub szablonie obsługują także właściwością zawartości i modelu zawartości.</span><span class="sxs-lookup"><span data-stu-id="5e98b-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="5e98b-119">Jeśli używane są tylko niezależnie od drzewa logicznego można tworzyć za pomocą stylów lub tworzenia szablonów raz, będzie jeszcze lepiej tylko elementy podrzędne odpowiednik w znaczniku bezpośredniego wypełnienie tej właściwości zawartości.</span><span class="sxs-lookup"><span data-stu-id="5e98b-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="5e98b-120">Czy to całkowicie pominąć szablon i stylu mechanizmów.</span><span class="sxs-lookup"><span data-stu-id="5e98b-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="5e98b-121">Możliwe, style i szablony są również innych składni, aby włączyć rozszerzenia znaczników, które zwracają obiekt.</span><span class="sxs-lookup"><span data-stu-id="5e98b-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="5e98b-122">Dwa rozszerzenia, które mają możliwe scenariusze obejmują [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) i <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="5e98b-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e98b-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5e98b-123">See Also</span></span>  
 [<span data-ttu-id="5e98b-124">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="5e98b-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)