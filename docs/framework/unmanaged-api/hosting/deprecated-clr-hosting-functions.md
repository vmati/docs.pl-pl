---
title: "Przestarzałe funkcje hostingu środowiska CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="d2368-102">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="d2368-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="d2368-103">W tej sekcji opisano niezarządzane statyczne funkcje globalne, które używany w starszych wersjach programu obsługi interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="d2368-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="d2368-104">Z wyjątkiem funkcji infrastruktury (`_Cor*` funkcji), które są używane tylko w programie .NET Framework, te funkcje są przestarzałe w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2368-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="d2368-105">Funkcje aktywacji</span><span class="sxs-lookup"><span data-stu-id="d2368-105">Activation functions</span></span>  
 [<span data-ttu-id="d2368-106">ClrCreateManagedInstance — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="d2368-107">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-107">Deprecated.</span></span> <span data-ttu-id="d2368-108">Tworzy wystąpienie określonego typu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="d2368-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="d2368-109">CoInitializeCor — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="d2368-110">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="d2368-110">Obsolete.</span></span> <span data-ttu-id="d2368-111">Aby zainicjować środowisko uruchomieniowe języka wspólnego (CLR), użyj [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) lub [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="d2368-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="d2368-112">CoInitializeEE — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="d2368-113">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-113">Deprecated.</span></span> <span data-ttu-id="d2368-114">Zapewnia, że aparat CLR wykonywania jest ładowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="d2368-115">Użyj [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metody zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="d2368-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="d2368-116">CorBindToCurrentRuntime — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="d2368-117">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-117">Deprecated.</span></span> <span data-ttu-id="d2368-118">Ładuje środowisko uruchomieniowe języka wspólnego (CLR) do procesu za pomocą wersji informacje przechowywane w pliku XML.</span><span class="sxs-lookup"><span data-stu-id="d2368-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="d2368-119">CorBindToRuntime — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="d2368-120">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-120">Deprecated.</span></span> <span data-ttu-id="d2368-121">Umożliwia niezarządzane hostów można załadować środowiska CLR do procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="d2368-122">CorBindToRuntimeByCfg — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="d2368-123">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-123">Deprecated.</span></span> <span data-ttu-id="d2368-124">Ładuje środowiska CLR do procesu za pomocą informacji o wersji, która jest do odczytu z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="d2368-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="d2368-125">CorBindToRuntimeEx — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="d2368-126">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-126">Deprecated.</span></span> <span data-ttu-id="d2368-127">Umożliwia hostom niezarządzane można załadować środowiska CLR do procesu, a można ustawić flagi, aby określić zachowanie środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="d2368-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="d2368-128">CorBindToRuntimeHost — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="d2368-129">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-129">Deprecated.</span></span> <span data-ttu-id="d2368-130">Umożliwia hostom do ładowania określonej wersji środowiska CLR do procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="d2368-131">GetCORRequiredVersion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="d2368-132">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-132">Deprecated.</span></span> <span data-ttu-id="d2368-133">Pobiera wymagany numer wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="d2368-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="d2368-134">GetCORSystemDirectory — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="d2368-135">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-135">Deprecated.</span></span> <span data-ttu-id="d2368-136">Zwraca katalog instalacyjny środowiska CLR, który jest ładowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="d2368-137">GetRealProcAddress — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="d2368-138">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-138">Deprecated.</span></span> <span data-ttu-id="d2368-139">Pobiera adres określonej funkcji, który został wyeksportowany z najnowszej zainstalowanej wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="d2368-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="d2368-140">GetRequestedRuntimeInfo — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="d2368-141">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-141">Deprecated.</span></span> <span data-ttu-id="d2368-142">Pobiera informacje o wersji i katalogu o CLR żądany przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="d2368-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="d2368-143">Funkcje wersji środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="d2368-143">CLR version functions</span></span>  
 <span data-ttu-id="d2368-144">Funkcje w tej sekcji zwracają wersję środowiska CLR; nie należy aktywować środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="d2368-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="d2368-145">GetCORVersion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="d2368-146">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-146">Deprecated.</span></span> <span data-ttu-id="d2368-147">Zwraca numer wersji środowiska CLR, która działa w ramach bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="d2368-148">GetFileVersion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="d2368-149">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-149">Deprecated.</span></span> <span data-ttu-id="d2368-150">Pobiera informacje o wersji środowiska CLR określonego pliku, używając określonego bufora.</span><span class="sxs-lookup"><span data-stu-id="d2368-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="d2368-151">GetRequestedRuntimeVersion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="d2368-152">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-152">Deprecated.</span></span> <span data-ttu-id="d2368-153">Pobiera numer wersji środowiska CLR zażądał określonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2368-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="d2368-154">Jeśli ta wersja nie jest zainstalowany, otrzymuje najnowszą wersję, która została zainstalowana przed żądanej wersji.</span><span class="sxs-lookup"><span data-stu-id="d2368-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="d2368-155">GetRequestedRuntimeVersionForCLSID — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="d2368-156">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-156">Deprecated.</span></span> <span data-ttu-id="d2368-157">Pobiera odpowiednie informacje o wersji środowiska CLR dla klasy o określonym identyfikatorze CLSID.</span><span class="sxs-lookup"><span data-stu-id="d2368-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="d2368-158">GetVersionFromProcess — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="d2368-159">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-159">Deprecated.</span></span> <span data-ttu-id="d2368-160">Pobiera numer wersji środowiska CLR skojarzony z dojściem określony proces.</span><span class="sxs-lookup"><span data-stu-id="d2368-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="d2368-161">LockClrVersion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="d2368-162">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-162">Deprecated.</span></span> <span data-ttu-id="d2368-163">Umożliwia hosta określić wersję środowiska CLR będzie używany w ramach procesu przed jawnie inicjowania CLR.</span><span class="sxs-lookup"><span data-stu-id="d2368-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="d2368-164">Funkcje hostingu</span><span class="sxs-lookup"><span data-stu-id="d2368-164">Hosting functions</span></span>  
 [<span data-ttu-id="d2368-165">CallFunctionShim — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="d2368-166">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-166">Deprecated.</span></span> <span data-ttu-id="d2368-167">Wykonuje wywołanie funkcji, które ma określoną nazwę i parametrów w określonej bibliotece.</span><span class="sxs-lookup"><span data-stu-id="d2368-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="d2368-168">CoEEShutDownCOM — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="d2368-169">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-169">Deprecated.</span></span> <span data-ttu-id="d2368-170">Zwalnia zestawem COM z procesu.</span><span class="sxs-lookup"><span data-stu-id="d2368-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="d2368-171">CorExitProcess — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="d2368-172">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-172">Deprecated.</span></span> <span data-ttu-id="d2368-173">Zamyka bieżący proces niezarządzany.</span><span class="sxs-lookup"><span data-stu-id="d2368-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="d2368-174">CorLaunchApplication — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="d2368-175">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-175">Deprecated.</span></span> <span data-ttu-id="d2368-176">Uruchamia aplikację w ścieżce określonej sieci przy użyciu określonego manifestów i innych danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2368-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="d2368-177">CorMarkThreadInThreadPool — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="d2368-178">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-178">Deprecated.</span></span> <span data-ttu-id="d2368-179">Oznacza aktualnie wykonywane wątku puli wątków dla wykonania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="d2368-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="d2368-180">W programie .NET Framework w wersji 2.0, ta funkcja nie ma znaczenia.</span><span class="sxs-lookup"><span data-stu-id="d2368-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="d2368-181">Nie jest wymagane, a można ją usunąć z kodu.</span><span class="sxs-lookup"><span data-stu-id="d2368-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="d2368-182">CoUninitializeCor — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="d2368-183">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="d2368-183">Obsolete.</span></span> <span data-ttu-id="d2368-184">Środowisko CLR nie może być zwolniony z procesem.</span><span class="sxs-lookup"><span data-stu-id="d2368-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="d2368-185">CoUninitializeEE — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="d2368-186">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="d2368-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="d2368-187">Createdebugginginterfacefromversion — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="d2368-188">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-188">Deprecated.</span></span> <span data-ttu-id="d2368-189">Tworzy [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) obiekt na podstawie określonej wersji informacji.</span><span class="sxs-lookup"><span data-stu-id="d2368-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="d2368-190">CreateICeeFileGen — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="d2368-191">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-191">Deprecated.</span></span> <span data-ttu-id="d2368-192">Tworzy [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) obiektu.</span><span class="sxs-lookup"><span data-stu-id="d2368-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="d2368-193">DestroyICeeFileGen — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="d2368-194">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-194">Deprecated.</span></span> <span data-ttu-id="d2368-195">Niszczy [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) obiektu.</span><span class="sxs-lookup"><span data-stu-id="d2368-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="d2368-196">Fexecuteinappdomaincallback — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="d2368-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="d2368-197">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-197">Deprecated.</span></span> <span data-ttu-id="d2368-198">Wskazuje funkcję, która wywołuje środowiska CLR do wykonania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="d2368-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="d2368-199">Flockclrversioncallback — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="d2368-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="d2368-200">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-200">Deprecated.</span></span> <span data-ttu-id="d2368-201">Punkty funkcji, które wywołuje CLR powiadomiono hosta tego inicjowania albo rozpoczął się lub zakończona.</span><span class="sxs-lookup"><span data-stu-id="d2368-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="d2368-202">GetCLRIdentityManager — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="d2368-203">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-203">Deprecated.</span></span> <span data-ttu-id="d2368-204">Pobiera wskaźnik do interfejsu, który umożliwia CLR do zarządzania tożsamościami.</span><span class="sxs-lookup"><span data-stu-id="d2368-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="d2368-205">LoadLibraryShim — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="d2368-206">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-206">Deprecated.</span></span> <span data-ttu-id="d2368-207">Ładuje określona wersja biblioteki DLL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2368-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="d2368-208">LoadStringRC — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="d2368-209">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-209">Deprecated.</span></span> <span data-ttu-id="d2368-210">Tłumaczy wartość HRESULT na komunikat o błędzie, za pomocą domyślną kulturę bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="d2368-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="d2368-211">LoadStringRCEx — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="d2368-212">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-212">Deprecated.</span></span> <span data-ttu-id="d2368-213">Tłumaczy wartość HRESULT odpowiedni komunikat o błędzie dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="d2368-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="d2368-214">Lpoverlapped_completion_routine — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="d2368-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="d2368-215">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-215">Deprecated.</span></span> <span data-ttu-id="d2368-216">Wskazuje funkcji, które powiadamia hosta przy nakładających się (oznacza to, asynchroniczne) zostało ukończone operacje We/Wy na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="d2368-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="d2368-217">Lpthread_start_routine — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="d2368-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="d2368-218">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-218">Deprecated.</span></span> <span data-ttu-id="d2368-219">Punkty funkcji, które powiadamia hosta, który wątek został uruchomiony w trybie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d2368-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="d2368-220">RunDll32ShimW — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="d2368-221">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-221">Deprecated.</span></span> <span data-ttu-id="d2368-222">Wykonuje określone polecenie.</span><span class="sxs-lookup"><span data-stu-id="d2368-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="d2368-223">Waitortimercallback — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="d2368-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="d2368-224">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="d2368-224">Deprecated.</span></span> <span data-ttu-id="d2368-225">Punkty funkcji, które powiadamia hosta, że dojście oczekiwania albo został sygnalizowane lub upłynął limit czasu.</span><span class="sxs-lookup"><span data-stu-id="d2368-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="d2368-226">Funkcje infrastruktury</span><span class="sxs-lookup"><span data-stu-id="d2368-226">Infrastructure functions</span></span>  
 <span data-ttu-id="d2368-227">Funkcje w tej sekcji służą do użytku przez tylko platformę .NET.</span><span class="sxs-lookup"><span data-stu-id="d2368-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="d2368-228">_CorDllMain — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="d2368-229">Inicjuje środowisko CLR, lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu biblioteki DLL i rozpoczyna się wykonanie.</span><span class="sxs-lookup"><span data-stu-id="d2368-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="d2368-230">_CorExeMain — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="d2368-231">Inicjuje środowisko CLR, lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu pliku wykonywalnego i rozpoczyna się wykonanie.</span><span class="sxs-lookup"><span data-stu-id="d2368-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="d2368-232">_CorExeMain2 — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="d2368-233">Wykonuje punkt wejścia określony kod mapowanych na pamięć.</span><span class="sxs-lookup"><span data-stu-id="d2368-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="d2368-234">Ta funkcja jest wywoływana przez moduł ładujący systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="d2368-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="d2368-235">_CorImageUnloading — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="d2368-236">Powiadamia program ładujący, gdy moduł zarządzany obrazy są usuwane z pamięci.</span><span class="sxs-lookup"><span data-stu-id="d2368-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="d2368-237">_CorValidateImage — funkcja</span><span class="sxs-lookup"><span data-stu-id="d2368-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="d2368-238">Weryfikuje obrazy moduł zarządzany i powiadamia modułu ładującego systemu operacyjnego po ich załadowaniu.</span><span class="sxs-lookup"><span data-stu-id="d2368-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2368-239">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d2368-239">See Also</span></span>  
 [<span data-ttu-id="d2368-240">.NET framework 4 statyczne funkcje globalne hostingu</span><span class="sxs-lookup"><span data-stu-id="d2368-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 