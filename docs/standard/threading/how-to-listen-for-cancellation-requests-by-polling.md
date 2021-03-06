---
title: "Porady: nasłuchiwanie żądań anulowania za pomocą sondowania"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 56a927e10cb026814302728a72acb2f32223b29b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Porady: nasłuchiwanie żądań anulowania za pomocą sondowania
W poniższym przykładzie przedstawiono jeden sposób, aby kod użytkownika można sondować token anulowania w regularnych odstępach czasu, aby zobaczyć, czy z wątku wywołującym zażądano anulowania. W tym przykładzie użyto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> typu, ale tego samego wzorca dotyczy operacji asynchronicznych utworzone bezpośrednio przez <xref:System.Threading.ThreadPool?displayProperty=nameWithType> typu lub <xref:System.Threading.Thread?displayProperty=nameWithType> typu.  
  
## <a name="example"></a>Przykład  
 Sondowanie wymaga określonego rodzaju pętli lub cykliczne kod, który może odczytywać okresowo wartość typu Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> właściwości. Jeśli używasz <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> typu i oczekują na wykonanie zadania w wątku wywołującym, możesz użyć <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> metody do sprawdzenia właściwości i zgłoszenie wyjątku. Za pomocą tej metody, można zapewnić, że poprawne wyjątku w odpowiedzi na żądanie. Jeśli używasz <xref:System.Threading.Tasks.Task>, następnie wywołaniem tej metody jest lepszym rozwiązaniem niż ręcznie zgłaszanie <xref:System.OperationCanceledException>. Jeśli nie masz ma zostać zgłoszony wyjątek, a następnie można po prostu Sprawdź właściwość i zwracany przez metodę, jeśli właściwość jest `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Wywoływanie <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> jest bardzo szybkie i nie powodować znaczne obciążenie w pętli.  
  
 Jeśli wywołujesz <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, należy jawnie sprawdziła <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> właściwości, jeśli masz inne pracy w odpowiedzi na anulowanie oprócz Zgłaszanie wyjątku. W tym przykładzie widać, że kod faktycznie uzyskuje dostęp do właściwości dwa razy: raz w jawny dostęp i ponownie w <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> metody. Jednak ponieważ act odczytu <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> właściwości obejmuje tylko jedno pole nietrwałe instrukcji na dostęp do odczytu, double dostępu nie jest istotne z punktu widzenia wydajności. Zaleca się nadal do wywołania metody, zamiast ręcznie throw <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Zobacz też  
 [Anulowanie w zarządzanych wątkach](../../../docs/standard/threading/cancellation-in-managed-threads.md)
