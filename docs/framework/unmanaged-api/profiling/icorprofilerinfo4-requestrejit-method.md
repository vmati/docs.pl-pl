---
title: "ICorProfilerInfo4::RequestReJIT — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.RequestReJIT
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d62dbb2829480e8972d1d4966673ba8eb58f1831
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="d0405-102">ICorProfilerInfo4::RequestReJIT — Metoda</span><span class="sxs-lookup"><span data-stu-id="d0405-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="d0405-103">Żądania kompilacji JIT, wszystkich wystąpień określonych funkcji.</span><span class="sxs-lookup"><span data-stu-id="d0405-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0405-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d0405-104">Syntax</span></span>  
  
```  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0405-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d0405-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="d0405-106">[in] Liczba funkcji ponowną kompilację.</span><span class="sxs-lookup"><span data-stu-id="d0405-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="d0405-107">[in] Określa `moduleId` część (`module`, `methodDef`) pary, które identyfikują funkcje do ponownej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="d0405-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="d0405-108">[in] Określa `methodId` część (`module`, `methodDef`) pary, które identyfikują funkcje do ponownej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="d0405-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0405-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d0405-109">Return Value</span></span>  
 <span data-ttu-id="d0405-110">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="d0405-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d0405-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0405-111">HRESULT</span></span>|<span data-ttu-id="d0405-112">Opis</span><span class="sxs-lookup"><span data-stu-id="d0405-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0405-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0405-113">S_OK</span></span>|<span data-ttu-id="d0405-114">Nastąpiła próba można oznaczyć wszystkie metody na potrzeby ponownej kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="d0405-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="d0405-115">Profiler musi implementować [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) metodę, aby określić, które metody pomyślnie zostały oznaczona do ponownej kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="d0405-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="d0405-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="d0405-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="d0405-117">Profiler musi implementować [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfejs dla tego wywołania do obsługi.</span><span class="sxs-lookup"><span data-stu-id="d0405-117">The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="d0405-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="d0405-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="d0405-119">Nie włączono ponownej kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="d0405-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="d0405-120">Należy włączyć ponownej kompilacji JIT podczas inicjowania przy użyciu [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodę, aby ustawić `COR_PRF_ENABLE_REJIT` flagi.</span><span class="sxs-lookup"><span data-stu-id="d0405-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="d0405-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d0405-121">E_INVALIDARG</span></span>|<span data-ttu-id="d0405-122">`cFunctions`ma wartość 0, lub `moduleIds` lub `methodIds` jest `NULL`.</span><span class="sxs-lookup"><span data-stu-id="d0405-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="d0405-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0405-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d0405-124">Środowisko CLR nie może wykonać żądania, ponieważ zabrakło pamięci.</span><span class="sxs-lookup"><span data-stu-id="d0405-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0405-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0405-125">Remarks</span></span>  
 <span data-ttu-id="d0405-126">Wywołanie `RequestReJIT` Aby ponownie skompilować określony zestaw funkcji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="d0405-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="d0405-127">Profiler kodu można następnie użyć [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfejsu, aby dopasować kod, który jest generowany, gdy te funkcje są ponownie kompilowana.</span><span class="sxs-lookup"><span data-stu-id="d0405-127">A code profiler can then use the [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="d0405-128">Nie dotyczy to aktualnie wykonywane funkcje, wywołania funkcji tylko w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="d0405-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="d0405-129">Jeśli określona funkcje poprzednio JIT ponownie skompilowana, żądanie ponownej jest odpowiednikiem przywrócenie i ponownie funkcji.</span><span class="sxs-lookup"><span data-stu-id="d0405-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="d0405-130">Aby zachować stosownie, kiedy przy użyciu kompilatora JIT kompiluje z oryginalną wersją funkcji, traktuje oryginalnej wersji jego callees ze śródwierszowaniem decyzji.</span><span class="sxs-lookup"><span data-stu-id="d0405-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="d0405-131">Kompilator JIT rekompiluje funkcję, traktuje bieżące wersje jego callees dla (ponownej kompilacji lub oryginalnego) ze śródwierszowaniem.</span><span class="sxs-lookup"><span data-stu-id="d0405-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="d0405-132">Profiler zwykle wymaga `RequestReJIT` w odpowiedzi na żądanie, że profiler Instrumentacja co najmniej jedną metodę wprowadzania danych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0405-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="d0405-133">`RequestReJIT`zwykle wstrzymuje środowiska uruchomieniowego w celu wykonania określonej prac i może potencjalnie wyzwalacza wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d0405-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="d0405-134">W efekcie powinny wywoływać profilera `RequestReJIT` wprowadzanych przez wątek on wcześniej utworzony, a nie z wątku utworzone CLR który jest obecnie wykonywane wywołanie zwrotne profilera.</span><span class="sxs-lookup"><span data-stu-id="d0405-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0405-135">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d0405-135">Requirements</span></span>  
 <span data-ttu-id="d0405-136">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0405-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0405-137">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0405-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0405-138">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0405-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0405-139">**Wersje programu .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0405-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0405-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0405-140">See Also</span></span>  
 [<span data-ttu-id="d0405-141">ICorProfilerInfo4 — interfejs</span><span class="sxs-lookup"><span data-stu-id="d0405-141">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="d0405-142">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="d0405-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="d0405-143">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="d0405-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)