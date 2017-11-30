---
title: "Łączenie dwóch sekwencji"
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="1e19a-102">Łączenie dwóch sekwencji</span><span class="sxs-lookup"><span data-stu-id="1e19a-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="1e19a-103">Użyj <xref:System.Linq.Queryable.Concat%2A> operator do łączenia dwóch sekwencji.</span><span class="sxs-lookup"><span data-stu-id="1e19a-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="1e19a-104"><xref:System.Linq.Queryable.Concat%2A> Operator jest zdefiniowany dla uporządkowanych multisets gdzie zamówień odbiornika i argument są takie same.</span><span class="sxs-lookup"><span data-stu-id="1e19a-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="1e19a-105">Kolejność w programie SQL jest ostatnim krokiem przed wyniki są tworzone.</span><span class="sxs-lookup"><span data-stu-id="1e19a-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="1e19a-106">Z tego powodu <xref:System.Linq.Queryable.Concat%2A> operator jest implementowane za pomocą `UNION ALL` i kolejność jej argumenty nie zostaną zachowane.</span><span class="sxs-lookup"><span data-stu-id="1e19a-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="1e19a-107">Aby upewnić się, że porządkowania jest prawidłowa w wynikach, upewnij się, że jawnie kolejność wyników.</span><span class="sxs-lookup"><span data-stu-id="1e19a-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e19a-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="1e19a-108">Example</span></span>  
 <span data-ttu-id="1e19a-109">W tym przykładzie użyto <xref:System.Linq.Queryable.Concat%2A> do zwrócenia sekwencji wszystkich `Customer` i `Employee` numerem telefonu i faksu.</span><span class="sxs-lookup"><span data-stu-id="1e19a-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="1e19a-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="1e19a-110">Example</span></span>  
 <span data-ttu-id="1e19a-111">W tym przykładzie użyto <xref:System.Linq.Queryable.Concat%2A> do zwrócenia sekwencji wszystkich `Customer` i `Employee` nazwy i mapowania numeru telefonu.</span><span class="sxs-lookup"><span data-stu-id="1e19a-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="1e19a-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1e19a-112">See Also</span></span>  
 [<span data-ttu-id="1e19a-113">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="1e19a-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="1e19a-114">Translacja Operator zapytania standardowe</span><span class="sxs-lookup"><span data-stu-id="1e19a-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)