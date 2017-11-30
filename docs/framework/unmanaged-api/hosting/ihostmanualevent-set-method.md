---
title: "IHostManualEvent::Set — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f093e1278e74553ed78445e0cb83127a219e622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="fbac3-102">IHostManualEvent::Set — Metoda</span><span class="sxs-lookup"><span data-stu-id="fbac3-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="fbac3-103">Ustawia bieżący [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) wystąpienia sygnałowego stanu.</span><span class="sxs-lookup"><span data-stu-id="fbac3-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbac3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fbac3-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fbac3-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="fbac3-105">Return Value</span></span>  
  
|<span data-ttu-id="fbac3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbac3-106">HRESULT</span></span>|<span data-ttu-id="fbac3-107">Opis</span><span class="sxs-lookup"><span data-stu-id="fbac3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbac3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbac3-108">S_OK</span></span>|<span data-ttu-id="fbac3-109">`Set`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="fbac3-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="fbac3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbac3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbac3-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="fbac3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fbac3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fbac3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fbac3-113">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="fbac3-113">The call timed out.</span></span>|  
|<span data-ttu-id="fbac3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fbac3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fbac3-115">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="fbac3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fbac3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fbac3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fbac3-117">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="fbac3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fbac3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbac3-118">E_FAIL</span></span>|<span data-ttu-id="fbac3-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="fbac3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fbac3-120">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="fbac3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fbac3-121">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fbac3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbac3-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fbac3-122">Requirements</span></span>  
 <span data-ttu-id="fbac3-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbac3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbac3-124">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbac3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbac3-125">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbac3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbac3-126">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbac3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbac3-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fbac3-127">See Also</span></span>  
 [<span data-ttu-id="fbac3-128">ICLRSyncManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="fbac3-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fbac3-129">IHostAutoEvent — interfejs</span><span class="sxs-lookup"><span data-stu-id="fbac3-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="fbac3-130">IHostManualEvent — interfejs</span><span class="sxs-lookup"><span data-stu-id="fbac3-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="fbac3-131">IHostSemaphore — interfejs</span><span class="sxs-lookup"><span data-stu-id="fbac3-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="fbac3-132">IHostSyncManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="fbac3-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)