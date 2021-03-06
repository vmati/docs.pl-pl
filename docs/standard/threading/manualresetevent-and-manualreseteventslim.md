---
title: ManualResetEvent i ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b90a84cf87c6c64d48d89840e2213d83b2e39d44
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent i ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Klasa reprezentuje zdarzenie dojścia oczekiwania lokalnych, które można ręcznie zresetować po zostanie zasygnalizowane. Ta klasa reprezentuje szczególnych przypadkach klasy podstawowej, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Zobacz [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) dokumentacja koncepcyjna wykorzystania i funkcje ręczne Resetowanie zdarzenia.  
  
 A <xref:System.Threading.ManualResetEvent> obiekt pozostaje sygnałowego aż do jego <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> metoda jest wywoływana. Liczba wątków lub wątków oczekiwania na zdarzenie po zostały sygnalizuje, może być zwolnione, gdy stan obiektu jest sygnalizowane. <xref:System.Threading.ManualResetEvent>odpowiada Win32 `CreateEvent` wywołać, określając `true` dla `bManualReset` argumentu.  
  
 W [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], można użyć <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> klasy w celu poprawy wydajności podczas powinny być bardzo krótkie czasy oczekiwania i zdarzenia nie przecina granicę procesu. <xref:System.Threading.ManualResetEventSlim>używa wirowania przez krótki czas podczas oczekiwania na zdarzenia stają się sygnalizowane zajęty. W przypadku krótki czas oczekiwania Obracająca może być znacznie mniej kosztowne niż czekanie przy użyciu uchwyty oczekiwania. Jednak jeśli zdarzenia stają się nie sygnalizowano w przedziale czasu, <xref:System.Threading.ManualResetEventSlim> uporządkowana do regularnego zdarzenia dojścia oczekiwania.  
  
## <a name="see-also"></a>Zobacz też  
 [Wątkowość](../../../docs/standard/threading/index.md)  
 [Wątkowość obiektów i funkcji](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Uchwyty oczekiwania](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore i SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
