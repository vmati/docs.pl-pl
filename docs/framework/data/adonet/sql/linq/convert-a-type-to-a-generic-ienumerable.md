---
title: "Przekonwertować typem rodzajowym interfejsem IEnumerable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f2e91a5fe4b27891b1750b0d74a8e9b01ad68449
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="ce6c3-102">Przekonwertować typem rodzajowym interfejsem IEnumerable</span><span class="sxs-lookup"><span data-stu-id="ce6c3-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="ce6c3-103">Użyj <xref:System.Linq.Enumerable.AsEnumerable%2A> być zwracany argument typu ogólnego `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="ce6c3-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce6c3-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="ce6c3-104">Example</span></span>  
 <span data-ttu-id="ce6c3-105">W tym przykładzie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (przy użyciu domyślnego ogólnego `Query`) może spróbować skonwertować kwerendy do bazy danych SQL i wykonaj go na serwerze.</span><span class="sxs-lookup"><span data-stu-id="ce6c3-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="ce6c3-106">Ale `where` klauzuli odwołuje się do metody zdefiniowanej przez użytkownika po stronie klienta (`isValidProduct`), którego nie można przekonwertować do bazy danych SQL.</span><span class="sxs-lookup"><span data-stu-id="ce6c3-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="ce6c3-107">Rozwiązanie jest określenie ogólnego po stronie klienta <xref:System.Collections.Generic.IEnumerable%601> implementacja `where` do zastąpienia ogólnego <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="ce6c3-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ce6c3-108">W tym celu wywoływania <xref:System.Linq.Enumerable.AsEnumerable%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="ce6c3-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="ce6c3-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ce6c3-109">See Also</span></span>  
 [<span data-ttu-id="ce6c3-110">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="ce6c3-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)