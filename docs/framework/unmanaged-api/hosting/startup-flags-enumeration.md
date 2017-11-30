---
title: "STARTUP_FLAGS — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: STARTUP_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: STARTUP_FLAGS
helpviewer_keywords: STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebfb45e6d568b4fa1db209264e02332df636474f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="a2e95-102">STARTUP_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="a2e95-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="a2e95-103">Zawiera wartości, które wskazują zachowanie uruchamiania środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="a2e95-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="a2e95-104">Domyślnie, wyrzucanie elementów bezużytecznych jest niewspółbieżnego i tylko biblioteki klasy podstawowej są ładowane do obszaru neutralne dla domen.</span><span class="sxs-lookup"><span data-stu-id="a2e95-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e95-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a2e95-105">Syntax</span></span>  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a2e95-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="a2e95-106">Members</span></span>  
  
|<span data-ttu-id="a2e95-107">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="a2e95-107">Member</span></span>|<span data-ttu-id="a2e95-108">Opis</span><span class="sxs-lookup"><span data-stu-id="a2e95-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="a2e95-109">Określa, czy ma być używany współbieżne odzyskiwanie pamięci.</span><span class="sxs-lookup"><span data-stu-id="a2e95-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="a2e95-110">Jeśli element wywołujący pyta o kompilacji serwera i współbieżne odzyskiwanie pamięci na komputerze z jednym procesorem, należy zamiast tego uruchomić są kompilacji stacji roboczej i niewspółbieżnego wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="a2e95-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="a2e95-111">**Uwaga:** współbieżne odzyskiwanie pamięci nie jest obsługiwany w aplikacji, które są uruchomione WOW64 x86 emulator na 64-bitowe systemy, które implementują architektura Intel Itanium (nazywanych IA-64).</span><span class="sxs-lookup"><span data-stu-id="a2e95-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="a2e95-112">Aby uzyskać więcej informacji o używaniu WOW64 na 64-bitowym systemie Windows, temacie [uruchomiona 32-bitowych aplikacji](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2e95-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="a2e95-113">Określa, że ma miejsce tej optymalizacji modułu ładującego.</span><span class="sxs-lookup"><span data-stu-id="a2e95-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="a2e95-114">Określa, że zestawy nie są ładowane jako neutralne dla domen.</span><span class="sxs-lookup"><span data-stu-id="a2e95-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="a2e95-115">Określa, że wszystkie zestawy są ładowane jako neutralne dla domen.</span><span class="sxs-lookup"><span data-stu-id="a2e95-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="a2e95-116">Określa, że wszystkie zestawy o silnych nazwach są ładowane jako neutralne dla domen.</span><span class="sxs-lookup"><span data-stu-id="a2e95-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="a2e95-117">Określa, że zasady wersji środowiska CLR nie zostaną zastosowane do wersji przekazano.</span><span class="sxs-lookup"><span data-stu-id="a2e95-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="a2e95-118">Zostanie załadowana dokładnej wersji określony środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="a2e95-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="a2e95-119">Podkładka nie może oszacować zasady, aby określić najnowszą zgodnej wersji.</span><span class="sxs-lookup"><span data-stu-id="a2e95-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="a2e95-120">Określa, że preferowanego środowiska uruchomieniowego zostanie ustawiony, ale faktycznie nie jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="a2e95-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="a2e95-121">Określa użytą pamięci serwera.</span><span class="sxs-lookup"><span data-stu-id="a2e95-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="a2e95-122">Określa, że wyrzucanie elementów bezużytecznych zachowa wirtualny adres używany.</span><span class="sxs-lookup"><span data-stu-id="a2e95-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="a2e95-123">Określa, czy mieszanie interfejsu obsługi będzie niemożliwe.</span><span class="sxs-lookup"><span data-stu-id="a2e95-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="a2e95-124">Określa, czy personifikacja nie powinien przepływ między punktami asynchroniczne domyślnie.</span><span class="sxs-lookup"><span data-stu-id="a2e95-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="a2e95-125">Określa, że stosu wątku pełne nie powinny być zatwierdzone, gdy wątek zacznie działać.</span><span class="sxs-lookup"><span data-stu-id="a2e95-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="a2e95-126">Określa, że zarządzane impersonations i impersonations, stosując platformy wywoływał będą przepływać między punktami asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="a2e95-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="a2e95-127">Domyślnie tylko zarządzane impersonations będą przepływać między punktami asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="a2e95-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="a2e95-128">Określa, że wyrzucanie elementów bezużytecznych będzie używać mniej przydzielone miejsce, gdy jest za mało pamięci systemu.</span><span class="sxs-lookup"><span data-stu-id="a2e95-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="a2e95-129">Zobacz `gcTrimCommitOnLowMemory` w [optymalizacji usługi hostingu sieci Web udostępnionego](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="a2e95-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="a2e95-130">Określa, że śledzenie zdarzeń systemu Windows (ETW) jest włączone dla zdarzenia środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="a2e95-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="a2e95-131">Począwszy od systemu Windows Vista, śledzenie zdarzeń jest zawsze włączony, dlatego ta flaga nie ma wpływu.</span><span class="sxs-lookup"><span data-stu-id="a2e95-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="a2e95-132">Zobacz [kontrolowanie .NET Framework rejestrowania](../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a2e95-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="a2e95-133">Określa, czy jest włączone monitorowanie zasobów domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a2e95-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="a2e95-134">Zobacz <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> właściwości i [ \<appdomainresourcemonitoring — > elementu](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="a2e95-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2e95-135">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a2e95-135">Requirements</span></span>  
 <span data-ttu-id="a2e95-136">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2e95-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e95-137">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2e95-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2e95-138">**Biblioteka:** biblioteki MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2e95-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2e95-139">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e95-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e95-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2e95-140">See Also</span></span>  
 [<span data-ttu-id="a2e95-141">Hosting — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="a2e95-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)