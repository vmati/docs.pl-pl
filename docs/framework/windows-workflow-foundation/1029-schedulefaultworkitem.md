---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a>1029 - ScheduleFaultWorkItem
## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID|1029|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows aplikacji debugowania serwera — aplikacje|  
  
## <a name="description"></a>Opis  
 Wskazuje, że zaplanowano element roboczy FaultWorkItem.  
  
## <a name="message"></a>Komunikat  
 Zaplanowano element roboczy FaultWorkItem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: '%3'.  Wyjątek pochodzi z działania %4, nazwa wyświetlana: %5, identyfikator wystąpienia: '%6'.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:String|Nazwa typu działania błędów.|  
|FaultActivityDisplayName|xs:String|Nazwa wyświetlana działania błędów.|  
|FaultActivityInstanceId|xs:String|Identyfikator wystąpienia działania błędów.|  
|ExceptionActivity|xs:String|Nazwa typu działania, która zgłosiła wyjątek.|  
|ExceptionActivityDisplayName|xs:String|Nazwa wyświetlana działania, która zgłosiła wyjątek.|  
|ExceptionActivityInstanceId|xs:String|Identyfikator wystąpienia działania, która zgłosiła wyjątek.|  
|Wyjątek|xs:String|Szczegóły wyjątku dla wyjątku|  
|Domeny aplikacji|xs:String|Długość ciągu zwróconego przez AppDomain.CurrentDomain.FriendlyName.|
