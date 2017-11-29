---
title: "Wspólne anulowanie wątków"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="1d0e4-102">Wspólne anulowanie wątków</span><span class="sxs-lookup"><span data-stu-id="1d0e4-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="1d0e4-103">Przed [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework podane ma wbudowane możliwości wspólne anulowanie wątku po jego uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="1d0e4-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="1d0e4-104">Jednak w [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], umożliwia anulowanie tokenów anulowanie wątków, tak samo, jak można je anulować <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> obiektów lub zapytania dotyczące technologii PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1d0e4-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="1d0e4-105">Mimo że <xref:System.Threading.Thread?displayProperty=nameWithType> klasy nie oferuje wbudowaną obsługę anulowanie tokenów, można przekazać tokenu do procedury wątku przy użyciu <xref:System.Threading.Thread> konstruktora przyjmującego <xref:System.Threading.ParameterizedThreadStart> delegowanie.</span><span class="sxs-lookup"><span data-stu-id="1d0e4-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="1d0e4-106">Poniższy przykład demonstruje, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="1d0e4-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="1d0e4-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1d0e4-107">See Also</span></span>  
 [<span data-ttu-id="1d0e4-108">Używanie wątków i wątkowości</span><span class="sxs-lookup"><span data-stu-id="1d0e4-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)