---
title: "ICLRTask2 — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="d0ac7-102">ICLRTask2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d0ac7-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="d0ac7-103">Zawiera wszystkie funkcje [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfejsu; ponadto udostępnia metody umożliwiające przerwanie wątku opóźnionych w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0ac7-104">Metody</span><span class="sxs-lookup"><span data-stu-id="d0ac7-104">Methods</span></span>  
  
|<span data-ttu-id="d0ac7-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="d0ac7-105">Method</span></span>|<span data-ttu-id="d0ac7-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d0ac7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0ac7-107">BeginPreventAsyncAbort — metoda</span><span class="sxs-lookup"><span data-stu-id="d0ac7-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="d0ac7-108">Opóźnienia nowego wątku przerwać żądania w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="d0ac7-109">EndPreventAsyncAbort — metoda</span><span class="sxs-lookup"><span data-stu-id="d0ac7-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="d0ac7-110">Zezwala na nowe lub oczekujące żądania przerwania wątku w wątku przerywa w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0ac7-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0ac7-111">Remarks</span></span>  
 <span data-ttu-id="d0ac7-112">`ICLRTask2` Dziedziczy interfejs `ICLRTask` interfejsu i dodaje metod umożliwiających hosta opóźnienia wątku jest przerywana, aby chronić region kodu, który musi zakończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="d0ac7-113">Wywoływanie `BeginPreventAsyncAbort` zwiększa licznik opóźnienie wątku przerwania dla bieżącego wątku i wywoływania `EndPreventAsyncAbort` zmniejsza go.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="d0ac7-114">Wywołuje się `BeginPreventAsyncAbort` i `EndPreventAsyncAbort` mogą być zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="d0ac7-115">Tak długo, jak wartość licznika jest większa niż zero, opóźnienia przerwania wątku dla bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="d0ac7-116">Jeśli wywołań `BeginPreventAsyncAbort` i `EndPreventAsyncAbort` są nie łączyć, istnieje możliwość przejścia w wątku, który przerwań nie może zostać dostarczona do bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="d0ac7-117">Opóźnienie nie jest honorowana dla wątku, który przerywa samej siebie.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="d0ac7-118">Funkcje, które jest udostępniane przez tę funkcję jest używana wewnętrznie przez maszynę wirtualną (VM).</span><span class="sxs-lookup"><span data-stu-id="d0ac7-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="d0ac7-119">Nieprawidłowe użycie tych metod może spowodować nieokreślony zachowanie w maszynie Wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="d0ac7-120">Na przykład wywołanie elementu `EndPreventAsyncAbort` bez wywoływania pierwszego elementu `BeginPreventAsyncAbort` można ustawić licznik do zera, gdy maszyna wirtualna wcześniej ma zwiększany.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="d0ac7-121">Podobnie wewnętrzny licznik nie jest sprawdzany pod kątem przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="d0ac7-122">W razie przekroczenia limitu całkowitej, ponieważ jest zwiększany przez hosta i maszyny Wirtualnej, efekty jest nieokreślony.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="d0ac7-123">Dla informacji o elementach członkowskich odziedziczone `ICLRTask` i informacji na temat innych celów tego interfejsu, zobacz [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="d0ac7-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ac7-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d0ac7-124">Requirements</span></span>  
 <span data-ttu-id="d0ac7-125">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0ac7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ac7-126">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0ac7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0ac7-127">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0ac7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0ac7-128">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ac7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ac7-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0ac7-129">See Also</span></span>  
 [<span data-ttu-id="d0ac7-130">ICLRTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="d0ac7-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d0ac7-131">ICLRTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="d0ac7-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d0ac7-132">IHostTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="d0ac7-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d0ac7-133">IHostTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="d0ac7-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="d0ac7-134">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="d0ac7-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)