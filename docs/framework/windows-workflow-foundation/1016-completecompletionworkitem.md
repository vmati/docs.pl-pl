---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f9b09001212de6d5aa4f5fde577b9eeb9d967ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="1016---completecompletionworkitem"></a>1016 - CompleteCompletionWorkItem
## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID|1016|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows aplikacji debugowania serwera — aplikacje|  
  
## <a name="description"></a>Opis  
 Wskazuje, że element roboczy CompletionWorkItem została ukończona.  
  
## <a name="message"></a>Komunikat  
 Ukończono element roboczy CompletionWorkItem dla działania nadrzędnego %1, nazwa wyświetlana: %2, identyfikator wystąpienia: '%3'. Ukończono %4, nazwa wyświetlana: %5, identyfikator wystąpienia: '%6'.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie nadrzędne|xs:String|Nazwa typu działania nadrzędnego.|  
|ParentDisplayName|xs:String|Nazwa wyświetlana działania nadrzędnego.|  
|ParentInstanceId|xs:String|Identyfikator wystąpienia działania nadrzędnego.|  
|CompletedActivity|xs:String|Nazwa typu działania ukończone.|  
|CompletedActivityDisplayName|xs:String|Nazwa wyświetlana ukończonego działania.|  
|CompletedActivityInstanceId|xs:String|Identyfikator wystąpienia działania ukończone.|  
|Domeny aplikacji|xs:String|Długość ciągu zwróconego przez AppDomain.CurrentDomain.FriendlyName.|
