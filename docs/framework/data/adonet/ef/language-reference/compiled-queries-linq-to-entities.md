---
title: Skompilowane zapytania (LINQ to Entities)
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
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de490bac737520ffef5899c8515322c72b2a1144
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="compiled-queries--linq-to-entities"></a><span data-ttu-id="7700f-102">Skompilowane zapytania (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="7700f-102">Compiled Queries  (LINQ to Entities)</span></span>
<span data-ttu-id="7700f-103">Jeśli masz aplikację, która wykonuje zapytania strukturę podobną wielokrotnie w ramach jednostki często może zwiększyć wydajność kompilacji zapytania jeden raz i jej wykonanie kilka razy z innymi parametrami.</span><span class="sxs-lookup"><span data-stu-id="7700f-103">When you have an application that executes structurally similar queries many times in the Entity Framework, you can frequently increase performance by compiling the query one time and executing it several times with different parameters.</span></span> <span data-ttu-id="7700f-104">Na przykład aplikacje mogą mieć można pobrać wszystkich klientów określonego miasta; miasta określono w czasie wykonywania przez użytkownika w postaci.</span><span class="sxs-lookup"><span data-stu-id="7700f-104">For example, an application might have to retrieve all the customers in a particular city; the city is specified at runtime by the user in a form.</span></span> <span data-ttu-id="7700f-105">Składnik LINQ to Entities obsługuje przy użyciu skompilowane zapytania w tym celu.</span><span class="sxs-lookup"><span data-stu-id="7700f-105">LINQ to Entities supports using compiled queries for this purpose.</span></span>  
  
 <span data-ttu-id="7700f-106">Począwszy od programu .NET Framework 4.5, zapytań LINQ są buforowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="7700f-106">Starting with the .NET Framework 4.5, LINQ queries are cached automatically.</span></span> <span data-ttu-id="7700f-107">Jednak nadal umożliwia skompilowane zapytania składnika LINQ to kosztów w późniejszym wykonaniami i skompilowane zapytania może być skuteczniejsza niż zapytań LINQ, które są automatycznie buforowane.</span><span class="sxs-lookup"><span data-stu-id="7700f-107">However, you can still use compiled LINQ queries to reduce this cost in later executions and compiled queries can be more efficient than LINQ queries that are automatically cached.</span></span> <span data-ttu-id="7700f-108">Uwaga LINQ to Entities zapytań, które mają zastosowanie `Enumerable.Contains` operator do kolekcji w pamięci nie są automatycznie buforowane.</span><span class="sxs-lookup"><span data-stu-id="7700f-108">Note that LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="7700f-109">Parametryzacja również kolekcji w pamięci w skompilowanych zapytań LINQ jest niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="7700f-109">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
 <span data-ttu-id="7700f-110"><xref:System.Data.Objects.CompiledQuery> Klasa udostępnia kompilacji i buforowanie zapytania do ponownego użycia.</span><span class="sxs-lookup"><span data-stu-id="7700f-110">The <xref:System.Data.Objects.CompiledQuery> class provides compilation and caching of queries for reuse.</span></span> <span data-ttu-id="7700f-111">Koncepcyjnie, ta klasa zawiera <xref:System.Data.Objects.CompiledQuery>w `Compile` metody z kilka przeciążeń.</span><span class="sxs-lookup"><span data-stu-id="7700f-111">Conceptually, this class contains a <xref:System.Data.Objects.CompiledQuery>'s `Compile` method with several overloads.</span></span> <span data-ttu-id="7700f-112">Wywołanie `Compile` metodę, aby utworzyć nowe delegowanie do reprezentowania kompilowanym zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="7700f-112">Call the `Compile` method to create a new delegate to represent the compiled query.</span></span> <span data-ttu-id="7700f-113">`Compile` Metod udostępnianych z <xref:System.Data.Objects.ObjectContext> i wartości parametrów zwracany delegata, który daje w wyniku niektórych (takich jak <xref:System.Linq.IQueryable%601> wystąpienie).</span><span class="sxs-lookup"><span data-stu-id="7700f-113">The `Compile` methods, provided with a <xref:System.Data.Objects.ObjectContext> and parameter values, return a delegate that produces some result (such as an <xref:System.Linq.IQueryable%601> instance).</span></span> <span data-ttu-id="7700f-114">Zapytanie kompiluje raz podczas pierwszego wykonywania.</span><span class="sxs-lookup"><span data-stu-id="7700f-114">The query compiles once during only the first execution.</span></span> <span data-ttu-id="7700f-115">Opcje scalania ustawione dla zapytania w czasie kompilacji nie można zmienić później.</span><span class="sxs-lookup"><span data-stu-id="7700f-115">The merge options set for the query at the time of the compilation cannot be changed later.</span></span> <span data-ttu-id="7700f-116">Po kompilowania zapytania można podać tylko parametry typu pierwotnego, ale nie można zamienić części zapytania, która zmieniłaby wygenerowanego SQL.</span><span class="sxs-lookup"><span data-stu-id="7700f-116">Once the query is compiled you can only supply parameters of primitive type but you cannot replace parts of the query that would change the generated SQL.</span></span> <span data-ttu-id="7700f-117">Aby uzyskać więcej informacji, zobacz [Entity Framework scalania opcje i skompilowane zapytania](http://go.microsoft.com/fwlink/?LinkId=199591)</span><span class="sxs-lookup"><span data-stu-id="7700f-117">For more information, see [Entity Framework Merge Options and Compiled Queries](http://go.microsoft.com/fwlink/?LinkId=199591)</span></span>  
  
 <span data-ttu-id="7700f-118">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] Zapytania wyrażenie który <xref:System.Data.Objects.CompiledQuery>w `Compile` kompiluje metody jest reprezentowane przez jedną z ogólnych `Func` deleguje, takich jak <xref:System.Func%605>.</span><span class="sxs-lookup"><span data-stu-id="7700f-118">The [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query expression that the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method compiles is represented by one of the generic `Func` delegates, such as <xref:System.Func%605>.</span></span> <span data-ttu-id="7700f-119">Co najwyżej umożliwiająca Hermetyzowanie wyrażenia zapytania `ObjectContext` parametru, parametr zwrotnego i 16 parametry zapytania.</span><span class="sxs-lookup"><span data-stu-id="7700f-119">At most, the query expression can encapsulate an `ObjectContext` parameter, a return parameter, and 16 query parameters.</span></span> <span data-ttu-id="7700f-120">Jeśli więcej niż 16 parametry zapytania są wymagane, można utworzyć struktury, którego właściwości reprezentują parametry zapytania.</span><span class="sxs-lookup"><span data-stu-id="7700f-120">If more than 16 query parameters are required, you can create a structure whose properties represent query parameters.</span></span> <span data-ttu-id="7700f-121">Po ustawieniu właściwości można następnie użyć właściwości struktury w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="7700f-121">You can then use the properties on the structure in the query expression after you set the properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7700f-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-122">Example</span></span>  
 <span data-ttu-id="7700f-123">Poniższy przykład kompiluje, a następnie wywołuje kwerendę, która akceptuje <xref:System.Decimal> parametr wejściowy i zwraca Sekwencja zamówień, w których termin całkowita jest większa niż lub równa $200,00:</span><span class="sxs-lookup"><span data-stu-id="7700f-123">The following example compiles and then invokes a query that accepts a <xref:System.Decimal> input parameter and returns a sequence of orders where the total due is greater than or equal to $200.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## <a name="example"></a><span data-ttu-id="7700f-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-124">Example</span></span>  
 <span data-ttu-id="7700f-125">Poniższy przykład tworzy, a następnie wywołuje zapytanie zwracające <xref:System.Data.Objects.ObjectQuery%601> wystąpienie:</span><span class="sxs-lookup"><span data-stu-id="7700f-125">The following example compiles and then invokes a query that returns an <xref:System.Data.Objects.ObjectQuery%601> instance:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## <a name="example"></a><span data-ttu-id="7700f-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-126">Example</span></span>  
 <span data-ttu-id="7700f-127">Poniższy przykład kompiluje, a następnie wywołuje zapytanie zwracające średniej ceny listy produktu jako <xref:System.Decimal> wartość:</span><span class="sxs-lookup"><span data-stu-id="7700f-127">The following example compiles and then invokes a query that returns the average of the product list prices as a <xref:System.Decimal> value:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## <a name="example"></a><span data-ttu-id="7700f-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-128">Example</span></span>  
 <span data-ttu-id="7700f-129">Poniższy przykład kompiluje, a następnie wywołuje kwerendę, która akceptuje <xref:System.String> danych wejściowych parametru, a następnie zwraca `Contact` którego adres e-mail zaczyna się od określonego ciągu:</span><span class="sxs-lookup"><span data-stu-id="7700f-129">The following example compiles and then invokes a query that accepts a <xref:System.String> input parameter and then returns a `Contact` whose e-mail address starts with the specified string:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## <a name="example"></a><span data-ttu-id="7700f-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-130">Example</span></span>  
 <span data-ttu-id="7700f-131">Poniższy przykład kompiluje, a następnie wywołuje kwerendę, która akceptuje <xref:System.DateTime> i <xref:System.Decimal> parametry wejściowe i zwraca sekwencji zlecenia, których data zamówienia jest późniejsza niż 8 marca 2003 i łącznie ze względu jest mniejsza niż 300.00 $:</span><span class="sxs-lookup"><span data-stu-id="7700f-131">The following example compiles and then invokes a query that accepts <xref:System.DateTime> and <xref:System.Decimal> input parameters and returns a sequence of orders where the order date is later than March 8, 2003, and the total due is less than $300.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## <a name="example"></a><span data-ttu-id="7700f-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-132">Example</span></span>  
 <span data-ttu-id="7700f-133">Poniższy przykład kompiluje, a następnie wywołuje kwerendę, która akceptuje <xref:System.DateTime> parametr wejściowy i zwraca sekwencję zleceń, których data zamówienia jest późniejsza niż 8 marca 2004.</span><span class="sxs-lookup"><span data-stu-id="7700f-133">The following example compiles and then invokes a query that accepts a <xref:System.DateTime> input parameter and returns a sequence of orders where the order date is later than March 8, 2004.</span></span> <span data-ttu-id="7700f-134">Ta kwerenda zwraca informacje o kolejności sekwencję typy anonimowe.</span><span class="sxs-lookup"><span data-stu-id="7700f-134">This query returns the order information as a sequence of anonymous types.</span></span> <span data-ttu-id="7700f-135">Typy anonimowe są wykryta przez kompilator, więc nie można określić parametrów typu w <xref:System.Data.Objects.CompiledQuery>w `Compile` — metoda i typ jest zdefiniowany w samej kwerendzie.</span><span class="sxs-lookup"><span data-stu-id="7700f-135">Anonymous types are inferred by the compiler, so you cannot specify type parameters in the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method and the type is defined in the query itself.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## <a name="example"></a><span data-ttu-id="7700f-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="7700f-136">Example</span></span>  
 <span data-ttu-id="7700f-137">Poniższy przykład kompiluje, a następnie wywołuje kwerendę, która przyjmuje parametr wejściowy struktury zdefiniowane przez użytkownika i zwraca sekwencję zleceń.</span><span class="sxs-lookup"><span data-stu-id="7700f-137">The following example compiles and then invokes a query that accepts a user-defined structure input parameter and returns a sequence of orders.</span></span> <span data-ttu-id="7700f-138">Struktura definiuje Data rozpoczęcia, Data zakończenia i sum powodu parametry zapytania, a zapytanie zwraca zamówienia między 3 marca i 8 marca 2003 w sumie powodu większa niż 700.00 $.</span><span class="sxs-lookup"><span data-stu-id="7700f-138">The structure defines start date, end date, and total due query parameters, and the query returns orders shipped between March 3 and March 8, 2003 with a total due greater than $700.00.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 <span data-ttu-id="7700f-139">Struktura, która definiuje parametry zapytania:</span><span class="sxs-lookup"><span data-stu-id="7700f-139">The structure that defines the query parameters:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## <a name="see-also"></a><span data-ttu-id="7700f-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7700f-140">See Also</span></span>  
 [<span data-ttu-id="7700f-141">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7700f-141">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="7700f-142">LINQ do jednostek</span><span class="sxs-lookup"><span data-stu-id="7700f-142">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [<span data-ttu-id="7700f-143">Opcje scalania Entity Framework i skompilowane zapytania</span><span class="sxs-lookup"><span data-stu-id="7700f-143">Entity Framework Merge Options and Compiled Queries</span></span>](http://go.microsoft.com/fwlink/?LinkId=199591)