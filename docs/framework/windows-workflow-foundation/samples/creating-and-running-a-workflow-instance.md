---
title: "Tworzenie i uruchamianie wystąpienia przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d6dd2f27a6db9770231a5c947c98614d4f6f175
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-running-a-workflow-instance"></a>Tworzenie i uruchamianie wystąpienia przepływu pracy
Ten przykład przedstawia sposób uruchomienia wystąpienia przepływu pracy. Widoczny jest sposób ją wykonać synchronicznego i asynchronicznego.  
  
## <a name="demonstrates"></a>Demonstracje  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Omówienie  
 Pierwsza część próbki używa <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Jest to najbardziej podstawową metodą wykonania przepływu pracy. Przepływy pracy wykonywane przy <xref:System.Activities.WorkflowInvoker.Invoke%2A> są wykonywane synchronicznie.  
  
 Druga część próbki używa <xref:System.Activities.WorkflowApplication> klasy. <xref:System.Activities.WorkflowApplication>pozwala na większą kontrolę nad każde wystąpienie, w tym możliwość interakcji z uruchomionym przepływem pracy i Uruchom przepływ pracy asynchronicznie.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Zobacz też  
 [Używanie obiektu WorkflowInvoker i WorkflowApplication](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
