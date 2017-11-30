---
title: "Interceptory (usługi danych WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7aad516b819723c97a40a016a46ddcbe0fcdf4d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="004e0-102">Interceptory (usługi danych WCF)</span><span class="sxs-lookup"><span data-stu-id="004e0-102">Interceptors (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="004e0-103">umożliwia aplikacji przechwycić komunikaty żądania, aby mogli dodawać niestandardowej logiki do operacji.</span><span class="sxs-lookup"><span data-stu-id="004e0-103"> enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="004e0-104">Można użyć tej niestandardowej logiki do sprawdzania poprawności danych w komunikatach przychodzących.</span><span class="sxs-lookup"><span data-stu-id="004e0-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="004e0-105">Można również użyć bardziej ograniczyć zakres żądania zapytania, takie jak, aby wstawić niestandardowych zasad autoryzacji na podstawie danego żądania.</span><span class="sxs-lookup"><span data-stu-id="004e0-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="004e0-106">Przechwycenie odbywa się za pomocą metod specjalnie oparte na atrybutach usługi danych.</span><span class="sxs-lookup"><span data-stu-id="004e0-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="004e0-107">Te metody są wywoływane przez [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] we właściwym momencie podczas przetwarzania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="004e0-107">These methods are called by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] at the appropriate point in message processing.</span></span> <span data-ttu-id="004e0-108">Interceptory są zdefiniowane na podstawie zestawu na jednostki i metody interceptora nie może przyjmować parametrów z żądania, jak operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="004e0-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="004e0-109">Metody interceptora zapytań, które są wywoływane podczas przetwarzania żądania HTTP GET, musi zwracać Wyrażenie lambda, które określa, czy wystąpienie jednostki interceptora ustawić powinny być zwracane w wynikach zapytania.</span><span class="sxs-lookup"><span data-stu-id="004e0-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="004e0-110">To wyrażenie jest używane przez usługę danych do uściślenia żądanej operacji.</span><span class="sxs-lookup"><span data-stu-id="004e0-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="004e0-111">Oto przykład definicji interceptora zapytań.</span><span class="sxs-lookup"><span data-stu-id="004e0-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="004e0-112">Aby uzyskać więcej informacji, zobacz [porady: Przechwytywanie danych komunikatów usługi](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="004e0-112">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="004e0-113">Interceptory zmiany, które są wywoływane podczas przetwarzania operacji-query, musi zwracać `void` (`Nothing` w języku Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="004e0-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="004e0-114">Metody interceptora zmian, musisz zaakceptować poniższe dwa parametry:</span><span class="sxs-lookup"><span data-stu-id="004e0-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1.  <span data-ttu-id="004e0-115">Parametr typu, który jest zgodny z typem jednostki z zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="004e0-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="004e0-116">Gdy usługa danych wywołuje interceptora zmian, wartość tego parametru, zostaną one zastosowane informacje jednostki, które są wysyłane przez żądanie.</span><span class="sxs-lookup"><span data-stu-id="004e0-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2.  <span data-ttu-id="004e0-117">Parametr typu <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="004e0-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="004e0-118">Gdy usługa danych wywołuje interceptora zmian, wartość tego parametru, zostaną one zastosowane żądanie próbuje wykonać operację.</span><span class="sxs-lookup"><span data-stu-id="004e0-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="004e0-119">Oto przykład definicji interceptora zmian.</span><span class="sxs-lookup"><span data-stu-id="004e0-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="004e0-120">Aby uzyskać więcej informacji, zobacz [porady: Przechwytywanie danych komunikatów usługi](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="004e0-120">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="004e0-121">Następujące atrybuty są obsługiwane w przypadku zatrzymania.</span><span class="sxs-lookup"><span data-stu-id="004e0-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="004e0-122">**[QueryInterceptor (** *EnitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="004e0-122">**[QueryInterceptor(** *EnitySetName* **)]**</span></span>  
 <span data-ttu-id="004e0-123">Metody z <xref:System.Data.Services.QueryInterceptorAttribute> atrybutu stosowane są wywoływane po odebraniu żądania HTTP GET dla docelowej jednostki zestawu zasobów.</span><span class="sxs-lookup"><span data-stu-id="004e0-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="004e0-124">Te metody zawsze musi zwracać wyrażenia lambda w formie `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="004e0-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="004e0-125">**[ChangeInterceptor (** *EnitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="004e0-125">**[ChangeInterceptor(** *EnitySetName* **)]**</span></span>  
 <span data-ttu-id="004e0-126">Metody z <xref:System.Data.Services.ChangeInterceptorAttribute> atrybutu stosowane są wywoływane po odebraniu żądania HTTP innych niż żądanie HTTP GET dla docelowej jednostki zestawu zasobów.</span><span class="sxs-lookup"><span data-stu-id="004e0-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="004e0-127">Te metody muszą zawsze zwracać `void` (`Nothing` w języku Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="004e0-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="004e0-128">Aby uzyskać więcej informacji, zobacz [porady: Przechwytywanie danych komunikatów usługi](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="004e0-128">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004e0-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="004e0-129">See Also</span></span>  
 [<span data-ttu-id="004e0-130">Operacje usługi</span><span class="sxs-lookup"><span data-stu-id="004e0-130">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)