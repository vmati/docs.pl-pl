---
title: "ETaskType — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ETaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ETaskType
helpviewer_keywords: ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52e027c5d2ead70bbd624fafe3021121557cd261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="06a3b-102">ETaskType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="06a3b-102">ETaskType Enumeration</span></span>
<span data-ttu-id="06a3b-103">Zawiera wartości, które wskazują na typ task, która jest reprezentowana przez albo [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) lub [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="06a3b-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a3b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="06a3b-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="06a3b-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="06a3b-105">Members</span></span>  
  
|<span data-ttu-id="06a3b-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="06a3b-106">Member</span></span>|<span data-ttu-id="06a3b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="06a3b-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="06a3b-108">Interfejs reprezentuje zadania zwalniania domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="06a3b-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="06a3b-109">Interfejs reprezentuje zadania pomocnika debugera.</span><span class="sxs-lookup"><span data-stu-id="06a3b-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="06a3b-110">Interfejs reprezentuje zadania finalizatora.</span><span class="sxs-lookup"><span data-stu-id="06a3b-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="06a3b-111">Interfejs reprezentuje zadanie odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="06a3b-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="06a3b-112">Interfejs reprezentuje zadania wątku bramy.</span><span class="sxs-lookup"><span data-stu-id="06a3b-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="06a3b-113">Interfejs reprezentuje zadania wątków We/Wy lub wątku portu ukończenia zadania.</span><span class="sxs-lookup"><span data-stu-id="06a3b-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="06a3b-114">Interfejs reprezentuje zadanie czasomierza wątku.</span><span class="sxs-lookup"><span data-stu-id="06a3b-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="06a3b-115">Interfejs reprezentuje oczekiwania wątku zadania.</span><span class="sxs-lookup"><span data-stu-id="06a3b-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="06a3b-116">Interfejs reprezentuje zadania wątku roboczego.</span><span class="sxs-lookup"><span data-stu-id="06a3b-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="06a3b-117">Zadanie jest nieznany.</span><span class="sxs-lookup"><span data-stu-id="06a3b-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="06a3b-118">Interfejs reprezentuje zadanie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="06a3b-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06a3b-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="06a3b-119">Requirements</span></span>  
 <span data-ttu-id="06a3b-120">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06a3b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a3b-121">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06a3b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06a3b-122">**Biblioteka:** biblioteki MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06a3b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06a3b-123">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a3b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a3b-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="06a3b-124">See Also</span></span>  
 [<span data-ttu-id="06a3b-125">Hosting — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="06a3b-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)