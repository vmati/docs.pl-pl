---
title: "Niezawodność"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd13a09e66c865630b9db3210bbd95bab14cb214
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="reliability"></a><span data-ttu-id="00b65-102">Niezawodność</span><span class="sxs-lookup"><span data-stu-id="00b65-102">Reliability</span></span>
<span data-ttu-id="00b65-103">Należy pamiętać, że wykonywanie kodu w środowisku serwerów, takich jak SQL Server ochronę przed asynchroniczne wyjątki.</span><span class="sxs-lookup"><span data-stu-id="00b65-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="00b65-104">Niezawodność, zgodnie z opisem w tym miejscu nie jest specyficzne dla programu SQL Server, ale do pisania niezawodnej kodu dla każdego hosta w wersji programu .NET Framework 2.0 środowiska.</span><span class="sxs-lookup"><span data-stu-id="00b65-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="00b65-105">Program SQL Server jest jednak pierwszej usługi wprowadzania szeroką gamę korzysta z nowych funkcji niezawodność w wersji 2.0, dlatego służy jako przykład.</span><span class="sxs-lookup"><span data-stu-id="00b65-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="00b65-106">Kodu uruchomionego w programie SQL Server musi uwzględniać bardziej rygorystyczne wytyczne niezawodność niż innych środowisk serwera.</span><span class="sxs-lookup"><span data-stu-id="00b65-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="00b65-107">Jest to spowodowane operacja stałej programu SQL Server na brzegu zużycia zasobów.</span><span class="sxs-lookup"><span data-stu-id="00b65-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="00b65-108"><xref:System.OutOfMemoryException>i <xref:System.Threading.ThreadAbortException> wyjątków nie są rzadko w środowisku programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00b65-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="00b65-109">Wskazówki te zwykle są mniej ukierunkowanych na niezawodność i jeden na stosowanie pełni zaufany zarządzane niepowodzenie bezpiecznie face z kodu <xref:System.AppDomain>— poziom odtwarzania, sposób podstawowy serwer przechowuje spójności i dostępności.</span><span class="sxs-lookup"><span data-stu-id="00b65-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00b65-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="00b65-110">In This Section</span></span>  
 [<span data-ttu-id="00b65-111">Atrybuty ochrony hosta i programowanie SQL Server</span><span class="sxs-lookup"><span data-stu-id="00b65-111">SQL Server Programming and Host Protection Attributes</span></span>](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="00b65-112">Opisuje sposób <xref:System.Security.Permissions.HostProtectionAttribute> atrybut jest używany przez program SQL Server do ograniczania wykonywanie kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="00b65-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="00b65-113">Najlepsze rozwiązania dotyczące niezawodności</span><span class="sxs-lookup"><span data-stu-id="00b65-113">Reliability Best Practices</span></span>](../../../docs/framework/performance/reliability-best-practices.md)  
 <span data-ttu-id="00b65-114">Wskazówki dotyczące pisania kodu, który spełnia wymagania dotyczące niezawodności.</span><span class="sxs-lookup"><span data-stu-id="00b65-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="00b65-115">Ograniczone regiony wykonania</span><span class="sxs-lookup"><span data-stu-id="00b65-115">Constrained Execution Regions</span></span>](../../../docs/framework/performance/constrained-execution-regions.md)  
 <span data-ttu-id="00b65-116">Zawiera opis funkcji i zachowanie ograniczone regiony wykonania (CERs).</span><span class="sxs-lookup"><span data-stu-id="00b65-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="00b65-117">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="00b65-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>