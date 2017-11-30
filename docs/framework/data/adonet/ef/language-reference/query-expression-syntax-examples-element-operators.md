---
title: "Przykłady składni wyrażeń zapytania: Operatory Element"
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
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9d919af04c3c8d75be5f4d4571cff719f899d433
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="aaad5-102">Przykłady składni wyrażeń zapytania: Operatory Element</span><span class="sxs-lookup"><span data-stu-id="aaad5-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="aaad5-103">Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.First%2A> metody query [modelu sprzedaży AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) przy użyciu składni wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="aaad5-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="aaad5-104">Model sprzedaży AdventureWorks używany w tym przykładzie jest tworzony z kontaktu, adres produktu, SalesOrderHeader i szczegóły zamówienia sprzedaży tabele w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="aaad5-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="aaad5-105">Przykłady w tym temacie należy użyć następującego `using` / `Imports` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="aaad5-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="aaad5-106">pierwszy</span><span class="sxs-lookup"><span data-stu-id="aaad5-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="aaad5-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="aaad5-107">Example</span></span>  
 <span data-ttu-id="aaad5-108">W poniższym przykładzie użyto <xref:System.Linq.Enumerable.First%2A> metodę, aby zwrócić którego imię pierwszego kontaktu jest "Brooke".</span><span class="sxs-lookup"><span data-stu-id="aaad5-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="aaad5-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aaad5-109">See Also</span></span>  
 [<span data-ttu-id="aaad5-110">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="aaad5-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)