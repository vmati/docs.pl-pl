---
title: "mc:ProcessContent — Atrybut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent — Atrybut
Określa, która [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementy nadal powinien mieć zawartość przetworzone przez elementy nadrzędne istotne, nawet wtedy, gdy element nadrzędny natychmiastowego może być ignorowane przez [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora z powodu określania [mc: atrybut Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . `mc:ProcessContent` Atrybut obsługuje zgodności znaczników, zarówno w przypadku mapowania niestandardowej przestrzeni nazw, jak i dla [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] przechowywania wersji.  
  
## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Dowolny ciąg prawidłowy prefiks, na Specyfikacja XML 1.0.|  
|*ignorableUri*|Wszelkie prawidłowy identyfikator URI przestrzeni nazw na Specyfikacja XML 1.0 wyznaczania.|  
|*ThisElementCanBeIgnored*|Element, który może być ignorowane przez [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementacji procesora, jeśli nie można rozpoznać typu podstawowego.|  
|*[zawartość]*|*ThisElementCanBeIgnored* jest oznaczony do pominięcia. Jeśli procesor ignoruje tego elementu *[zawartości]* jest przetwarzany przez *obiektu*.|  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora zignoruje zawartość elementu została zignorowana. Można określić elementu określonych przez `mc:ProcessContent`, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora będą w dalszym ciągu przetwarzania zawartości w elemencie została zignorowana. To zazwyczaj będzie można użyć, jeśli zawartość jest zagnieżdżony w kilku tagów, co najmniej jeden z nich do pominięcia i co najmniej jeden z nich nie jest do pominięcia.  
  
 Można określić wiele prefiksów w atrybucie, używając separatora miejsca, na przykład: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Definiuje przestrzeń nazw innych elementów i atrybutów, które nie są opisane w tym obszarze [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Aby uzyskać więcej informacji, zobacz [specyfikacji zgodności znaczników XML](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Zobacz też  
 [mc:Ignorable, atrybut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [Przegląd XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
