---
title: "Przejdź (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c82149fb5d76ac7b95198ce2b29550eade54b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="097b0-102">Przejdź (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="097b0-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="097b0-103">Przechodzi przez relację między jednostkami.</span><span class="sxs-lookup"><span data-stu-id="097b0-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097b0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="097b0-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="097b0-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="097b0-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="097b0-106">Wystąpienie jednostki.</span><span class="sxs-lookup"><span data-stu-id="097b0-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="097b0-107">Nazwa typu relacji z pliku schematu koncepcyjnego definition language (CSDL).</span><span class="sxs-lookup"><span data-stu-id="097b0-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="097b0-108">`relationship-type` Jest kwalifikowana jako \<przestrzeń nazw >.\< Nazwa typu relacji >.</span><span class="sxs-lookup"><span data-stu-id="097b0-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="097b0-109">Zakończenie relacji.</span><span class="sxs-lookup"><span data-stu-id="097b0-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="097b0-110">Początek relacji.</span><span class="sxs-lookup"><span data-stu-id="097b0-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="097b0-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="097b0-111">Return Value</span></span>  
 <span data-ttu-id="097b0-112">Jeśli kardynalność do końca wynosi 1, jest zwracana wartość `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="097b0-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="097b0-113">Jeśli kardynalność na koniec jest n, jest zwracana wartość `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="097b0-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="097b0-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="097b0-114">Remarks</span></span>  
 <span data-ttu-id="097b0-115">Relacje są najwyższej jakości konstrukcje w [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span><span class="sxs-lookup"><span data-stu-id="097b0-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="097b0-116">Można utworzyć relacji między co najmniej dwa typy jednostek, a użytkownicy mogą uzyskać dostęp za pośrednictwem relacji z jednej strony (jednostka) do innego.</span><span class="sxs-lookup"><span data-stu-id="097b0-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="097b0-117">`from`i `to` są warunkowo opcjonalny, gdy istnieje nie niejednoznaczności w rozpoznawania nazw w relacji.</span><span class="sxs-lookup"><span data-stu-id="097b0-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="097b0-118">Nawigacja jest prawidłowa w przestrzeni O i C.</span><span class="sxs-lookup"><span data-stu-id="097b0-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="097b0-119">Ogólny kształt konstrukcji nawigacji jest następujący:</span><span class="sxs-lookup"><span data-stu-id="097b0-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="097b0-120">Przejdź (`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ]])</span><span class="sxs-lookup"><span data-stu-id="097b0-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="097b0-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="097b0-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="097b0-122">W przypadku OrderCustomer `relationship`, oraz klientów i kolejność są `to-end` (klienta) i `from-end` (kolejność) relacji.</span><span class="sxs-lookup"><span data-stu-id="097b0-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="097b0-123">Jeśli OrderCustomer został relacji n: 1, a następnie typ wyniku wyrażenia Nawigacja jest Ref\<klienta >.</span><span class="sxs-lookup"><span data-stu-id="097b0-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="097b0-124">Prostsze formę to wyrażenie jest następujący:</span><span class="sxs-lookup"><span data-stu-id="097b0-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="097b0-125">Podobnie, w kwerendzie mają następującą postać wyrażenia Nawigacja tworzy kolekcję < Ref\<kolejności >>.</span><span class="sxs-lookup"><span data-stu-id="097b0-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="097b0-126">Wyrażenia wystąpienia muszą być typu jednostki/ref.</span><span class="sxs-lookup"><span data-stu-id="097b0-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="097b0-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="097b0-127">Example</span></span>  
 <span data-ttu-id="097b0-128">Następujące zapytanie SQL jednostki używa operatora przejdź do nawigacji w relacji między adres i SalesOrderHeader typów jednostek.</span><span class="sxs-lookup"><span data-stu-id="097b0-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="097b0-129">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="097b0-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="097b0-130">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="097b0-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="097b0-131">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="097b0-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="097b0-132">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="097b0-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="097b0-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="097b0-133">See Also</span></span>  
 [<span data-ttu-id="097b0-134">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="097b0-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="097b0-135">Porady: nawigowanie relacje z Przejdź — Operator</span><span class="sxs-lookup"><span data-stu-id="097b0-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)