---
title: "Porady: łączenie równoległych i sekwencyjnych zapytań LINQ"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="8418b-102">Porady: łączenie równoległych i sekwencyjnych zapytań LINQ</span><span class="sxs-lookup"><span data-stu-id="8418b-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="8418b-103">Ten przykład przedstawia sposób użycia <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metody nakazać programowi PLINQ sekwencyjnie przetworzyć wszystkie kolejne operatory w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="8418b-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="8418b-104">Mimo że zazwyczaj wolniej niż równoległego przetwarzania sekwencyjnych czasami jest potrzebne do wygenerowania poprawnych wyników.</span><span class="sxs-lookup"><span data-stu-id="8418b-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8418b-105">W tym przykładzie jest jedynie do zademonstrowania użycia i mogą nie działać szybciej niż równoważne sekwencyjnych zapytań LINQ do obiektów zapytania.</span><span class="sxs-lookup"><span data-stu-id="8418b-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="8418b-106">Aby uzyskać więcej informacji na temat przyspieszenie, zobacz [przyspieszeniach w PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="8418b-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8418b-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="8418b-107">Example</span></span>  
 <span data-ttu-id="8418b-108">W poniższym przykładzie przedstawiono jeden scenariusz, w którym <xref:System.Linq.ParallelEnumerable.AsSequential%2A> jest wymagane, a mianowicie zachowania kolejności, który został ustanowiony w klauzuli poprzedniego zapytania.</span><span class="sxs-lookup"><span data-stu-id="8418b-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8418b-109">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="8418b-109">Compiling the Code</span></span>  
 <span data-ttu-id="8418b-110">Aby skompilować i uruchomić ten kod, wklej ją do [próbka danych PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) projekt, Dodaj wiersz, aby wywołać metodę z `Main`, i naciśnij klawisz F5.</span><span class="sxs-lookup"><span data-stu-id="8418b-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8418b-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8418b-111">See Also</span></span>  
 [<span data-ttu-id="8418b-112">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8418b-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)