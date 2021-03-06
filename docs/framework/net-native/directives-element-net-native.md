---
title: Element &lt;Directives&gt; (architektura .NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ca27422889fd33071a02c3a4b6fea0a6ba7eb0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ltdirectivesgt-element-net-native"></a>Element &lt;Directives&gt; (architektura .NET Native)
W każdym pliku dyrektyw środowiska uruchomieniowego dla elementu głównego [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\<Dyrektywy xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`xmlns`|Przestrzeń nazw XML. Wartość jest zawsze **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.|  
  
## <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Aplikacji >](../../../docs/framework/net-native/application-element-net-native.md)|Służy jako kontener dla całej aplikacji typy i elementy członkowskie typu, w których metadane są dostępne w celu odbicia.|  
|[\<Biblioteka >](../../../docs/framework/net-native/library-element-net-native.md)|Definiuje zestaw, których typy podrzędne i elementy członkowskie typu wymagają metadanych w czasie wykonywania.|  
  
## <a name="remarks"></a>Uwagi  
 Każdy plik dyrektyw środowiska uruchomieniowego może zawierać tylko jeden `<Directives>` elementu.  
  
 `<Directives>` Element może zawierać zero lub jeden [ \<aplikacji >](../../../docs/framework/net-native/application-element-net-native.md) elementu, a wartość zero, co najmniej jeden [ \<biblioteki >](../../../docs/framework/net-native/library-element-net-native.md) elementów.  
  
## <a name="see-also"></a>Zobacz też  
 [Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Elementy dyrektyw środowiska uruchomieniowego](../../../docs/framework/net-native/runtime-directive-elements.md)
