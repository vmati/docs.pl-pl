---
title: "Silverlight — debugowanie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf39d2dd12207d594c7bf5bd5b249d82c3f15d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="silverlight-debugging"></a><span data-ttu-id="31c84-102">Silverlight — debugowanie</span><span class="sxs-lookup"><span data-stu-id="31c84-102">Silverlight Debugging</span></span>
<span data-ttu-id="31c84-103">W tematach w tej sekcji opisano środowisko i interfejsów, które udostępnia środowisko uruchomieniowe języka wspólnego (CLR) do obsługi debugowania aplikacji Silverlight, uruchomionych w systemie operacyjnym Windows lub na platformie Macintosh.</span><span class="sxs-lookup"><span data-stu-id="31c84-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31c84-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="31c84-104">In This Section</span></span>  
 [<span data-ttu-id="31c84-105">Enumerateclrs — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="31c84-106">Udostępnia mechanizm dla wyliczania CLRs w procesie.</span><span class="sxs-lookup"><span data-stu-id="31c84-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="31c84-107">Closeclrenumeration — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="31c84-108">Zamyka prawidłowy zdarzeń kontynuować uruchamianie CLR znajduje się w tablicy dojść zwrócony przez [enumerateclrs — funkcja](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)i zwalnia pamięć dla tablic dojście i ciągu ścieżki.</span><span class="sxs-lookup"><span data-stu-id="31c84-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="31c84-109">Createcoreclrdebugtarget — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="31c84-110">Tworzy połączenie dla zdalnego miejsca docelowego, proces i środowiska uruchomieniowego wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="31c84-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="31c84-111">Createcordbobject — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="31c84-112">Tworzy interfejs debugera dostarczająca funkcje dla sesji debugowania zarządzanego dla procesu zdalnego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="31c84-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="31c84-113">Createversionstringfrommodule — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="31c84-114">Tworzy ciąg wersji ze ścieżki CLR w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="31c84-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="31c84-115">Createdebugginginterfacefromversion — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="31c84-116">Akceptuje zwrócony ciąg wersji aparatu CLR z [createversionstringfrommodule — funkcja](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)funkcji i zwraca odpowiedniego interfejsu debugera.</span><span class="sxs-lookup"><span data-stu-id="31c84-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="31c84-117">Coreclrdebugprocinfo — struktura</span><span class="sxs-lookup"><span data-stu-id="31c84-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="31c84-118">Reprezentuje proces, który jest uruchomiony na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="31c84-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="31c84-119">Coreclrdebugruntimeinfo — struktura</span><span class="sxs-lookup"><span data-stu-id="31c84-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="31c84-120">Reprezentuje wystąpienie środowiska CLR, który jest ładowany w ramach procesu na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="31c84-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="31c84-121">Getstartupnotificationevent — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="31c84-122">Tworzy lub otwiera obsługi zdarzenia, które są sygnalizowane po przez dowolnego środowisko uruchomieniowe języka wspólnego (CLR), który jest ładowany w procesie określonego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="31c84-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="31c84-123">Icoreclrdebugtarget — interfejs</span><span class="sxs-lookup"><span data-stu-id="31c84-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="31c84-124">Tworzy połączenie dla zdalnego miejsca docelowego, proces i środowiska uruchomieniowego wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="31c84-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="31c84-125">Initdbgtransportmanager — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="31c84-126">Inicjuje menedżera transportu do nawiązania połączenia zdalnego celu wyliczenie procesu i środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="31c84-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="31c84-127">Shutdowndbgtransportmanager — funkcja</span><span class="sxs-lookup"><span data-stu-id="31c84-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="31c84-128">Zamknięcie menedżera transportu na połączenie komputera zdalnego docelowej.</span><span class="sxs-lookup"><span data-stu-id="31c84-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c84-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="31c84-129">See Also</span></span>  
 [<span data-ttu-id="31c84-130">Klasy coclass debugowania</span><span class="sxs-lookup"><span data-stu-id="31c84-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [<span data-ttu-id="31c84-131">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="31c84-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="31c84-132">Statyczne funkcje globalne debugowania</span><span class="sxs-lookup"><span data-stu-id="31c84-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [<span data-ttu-id="31c84-133">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="31c84-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="31c84-134">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="31c84-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)