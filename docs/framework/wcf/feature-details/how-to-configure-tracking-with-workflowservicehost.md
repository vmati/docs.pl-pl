---
title: "Porady: Konfigurowanie śledzenia przy użyciu klasy WorkflowServiceHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b9bba3c589ca0232171bab58c26b19c7312a313
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Porady: Konfigurowanie śledzenia przy użyciu klasy WorkflowServiceHost
W tym temacie opisano sposób konfigurowania śledzenia dla [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] przepływu pracy hostowanych w <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Jest on skonfigurowany za pomocą pliku Web.config, określając zachowanie usługi.  
  
### <a name="configure-tracking-in-configuration"></a>Konfigurowanie śledzenia w konfiguracji  
  
1.  Dodaj <xref:System.Activities.Tracking.EtwTrackingParticipant> przy użyciu <`behavior`> w pliku konfiguracji, jak pokazano w poniższym przykładzie.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  Uproszczona konfiguracja używa powyższego przykładu konfiguracji. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Uproszczony konfiguracji](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Dodaje powyższego przykładu konfiguracji <xref:System.Activities.Tracking.EtwTrackingParticipant> i określa śledzenia nazwy profilu. Do tworzenia profilów śledzenia <`trackingProfile`> w elemencie <`tracking`> elementu. Profil śledzenia zawiera zapytania dotyczące śledzenia, które umożliwiają śledzenie uczestnika do subskrybowanie zdarzeń przepływu pracy, które są emitowane po zmianie stanu wystąpienia przepływu pracy w czasie wykonywania. Poniższy przykład przedstawia sposób tworzenia profilu śledzenia.  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Śledzenie profilów, zobacz [śledzenia profile](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Ogólnie rzecz biorąc, śledzenie Zobacz [przepływu pracy śledzenia i śledzenia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).  
  
### <a name="configure-tracking-in-code"></a>Konfigurowanie śledzenia w kodzie  
  
1.  Dodaj <xref:System.Activities.Tracking.EtwTrackingParticipant> przy użyciu <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> zachowanie w kodzie, jak pokazano w poniższym przykładzie.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     Dodaje w poprzednim przykładzie kodu <xref:System.Activities.Tracking.EtwTrackingParticipant> i określa śledzenia nazwy profilu. Do tworzenia profilów śledzenia <`trackingProfile`> w elemencie <`tracking`> element, jak pokazano w poprzedniej sekcji.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Śledzenie profilów, zobacz [śledzenia profile](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Ogólnie rzecz biorąc, śledzenie Zobacz [przepływu pracy śledzenia i śledzenia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md). Aby uzyskać przykład konfigurowania śledzenia programowo zobacz [Konfigurowanie śledzenia przepływu pracy](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Uproszczona konfiguracja usług WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)  
 [Usługi przepływu pracy](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Profile śledzenia](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
