---
title: "&lt;states&gt; w WCF — &lt;workflowInstanceQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5995ebfc2cee0f636d2acd8b1cadead0bc7b67e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a>&lt;states&gt; w WCF — &lt;workflowInstanceQuery&gt;
Reprezentuje kolekcję subskrybowanego stanów z wystąpienia śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.  
  
 Aby uzyskać więcej informacji na zapytania dotyczące profilu śledzenia, zobacz [profile śledzenia](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
 \<system.serviceModel >  
\<Śledzenie >  
\<trackingProfile >  
\<przepływ pracy >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<Stany >  
  
## <a name="syntax"></a>Składnia  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Stany >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Stan subskrybowanego z wystąpienia elementu śledzonych przepływu pracy podczas rekordem śledzenia.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<workflowInstanceQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Kwerenda, która śledzi zmiany cyklu życia wystąpienia przepływu pracy, takich jak zdarzenia rozpoczęte lub zostało zakończone.|  
  
## <a name="remarks"></a>Uwagi  
 Zwracane rekordy są filtrowane według stanów w tej kolekcji.  
  
 Stan możliwe wartości są opisane w poniższej tabeli.  
  
|Stan|Opis|  
|-----------|-----------------|  
|Zostało przerwane|Wystąpienie przepływu pracy zostało przerwane.|  
|Zakończone|Wystąpienie przepływu pracy jest zakończone.|  
|Usunięte|Wystąpienie przepływu pracy, został usunięty.|  
|Bezczynności (%)|Wystąpienie przepływu pracy jest bezczynny.|  
|Trwały|Wystąpienie przepływu pracy jest trwały.|  
|Wznowione|Wystąpienie przepływu pracy zostanie wznowione.|  
|Rozpoczęto|Wystąpienie przepływu pracy zostało rozpoczęte.|  
|UnhandledException|Wystąpienie przepływu pracy napotkał nieobsługiwany wyjątek.|  
|Zwolniono|Wystąpienie przepływu pracy nie jest załadowany.|  
|Anulowane|Wystąpienie przepływu pracy zostało anulowane.|  
|Wstrzymane|Wystąpienie przepływu pracy jest zawieszone.|  
|Zakończone|Wystąpienie przepływu pracy jest zakończone.|  
|Anulowano|Anulowano to wystąpienie przepływu pracy.|  
  
## <a name="example"></a>Przykład  
 Następująca konfiguracja subskrybuje przepływu rekordów dla śledzenia na poziomie wystąpienia `Started` stan wystąpienia przy użyciu tego zapytania.  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [Kontrola i śledzenie przepływu pracy](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Profile śledzenia](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
