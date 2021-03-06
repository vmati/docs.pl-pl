---
title: "Porady: zapisywanie prostej pętli Parallel.ForEach"
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
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bb628c0de1f0e4452ae13b5f5ee392084118bea5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Porady: zapisywanie prostej pętli Parallel.ForEach
Ten przykład przedstawia sposób użycia <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> pętli, aby włączyć równoległość danych przez żadnego <xref:System.Collections.IEnumerable?displayProperty=nameWithType> lub <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> źródła danych.  
  
> [!NOTE]
>  Ta dokumentacja używa wyrażenia lambda, aby zdefiniować delegatów w PLINQ. Jeśli nie masz doświadczenia z wyrażenia lambda w języku C# lub Visual Basic, zobacz [wyrażenia Lambda w PLINQ i TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Przykład  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 A <xref:System.Threading.Tasks.Parallel.ForEach%2A> pętli działa jak <xref:System.Threading.Tasks.Parallel.For%2A> pętli. Kolekcja źródłowa jest podzielona na partycje i pracy jest zaplanowane na wiele wątków, w zależności od środowiska systemu. Więcej procesorów w systemie, tym szybciej równoległych metoda jest uruchamiana. Dla niektórych kolekcji źródłowej loop sekwencyjnych może być szybsze, w zależności od rozmiaru źródła i rodzaj wykonywanej pracy. Aby uzyskać więcej informacji o wydajności, zobacz [potencjalne pułapki związane z Równoległością danych i zadań](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Aby uzyskać więcej informacji na temat pętle równoległe, zobacz [porady: pisanie prostej równoległej pętli for](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Aby użyć <xref:System.Threading.Tasks.Parallel.ForEach%2A> z kolekcja nierodzajową, możesz użyć <xref:System.Linq.Enumerable.Cast%2A> — metoda rozszerzenia do przekonwertowania kolekcji do kolekcji uniwersalnej, jak pokazano w poniższym przykładzie:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Umożliwia także równoległe LINQ (PLINQ) do przetwarzania parallelize <xref:System.Collections.Generic.IEnumerable%601> źródeł danych. PLINQ pozwala na użycie składni zapytania deklaratywne Express zachowanie pętli. Aby uzyskać więcej informacji, zobacz [równoległe LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
-   Skopiuj i wklej go w [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 projekt aplikacji konsoli.  
  
-   Dodaj odwołanie do System.Drawing.dll  
  
-   Naciśnij klawisz F5  
  
## <a name="see-also"></a>Zobacz też  
 [Równoległość danych](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Programowanie równoległe](../../../docs/standard/parallel-programming/index.md)  
 [Równoległe LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
