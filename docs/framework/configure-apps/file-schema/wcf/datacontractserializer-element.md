---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a>&lt;dataContractSerializer&gt;
Zawiera dane konfiguracyjne <xref:System.Runtime.Serialization.DataContractSerializer>. Ten element występuje w dwóch różnych hierarchii. Co znajduje się w poniższej sekcji hierarchii schematu, a druga jest wymieniony w sekcji uwag.  
  
 \<System. ServiceModel >  
\<zachowania >  
\<serviceBehaviors >  
\<zachowanie >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Element|Opis|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Wartość logiczna określająca, czy można zignorować dane dostarczone przez punkt końcowy, gdy jest on serializowany lub deserializowany. Ten atrybut nie można ustawić tylko na `<dataContractSerializer>` w obszarze `<behavior>` elementu.|  
|MaxItemsInObjectGraph|Liczba całkowita określająca maksymalną liczbę elementów do serializacji lub deserializacji. Ten atrybut jest 65536.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<zachowanie >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Kolekcję ustawień zachowania dla usługi.|  
|[\<System.Runtime.serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Reprezentuje element główny <xref:System.Runtime.Serialization> sekcji przestrzeni nazw i zawiera elementy dla opcji ustawienia obiektu <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Uwagi  
 Jak już wspomniano w wprowadzenie tego tematu, to drugiej hierarchii, w którym \<X509Extension > element występuje.  
  
 [\<System.Runtime.serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Aby uzyskać więcej informacji na temat znanych typów, zobacz <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [Znane typy kontraktów danych](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Transfer i serializacja danych](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
