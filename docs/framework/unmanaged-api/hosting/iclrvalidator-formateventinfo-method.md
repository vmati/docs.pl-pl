---
title: "ICLRValidator::FormatEventInfo — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.FormatEventInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d03864ac8e4e0423e45ac084e01af98e3eab13a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="466f7-102">ICLRValidator::FormatEventInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="466f7-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="466f7-103">Pobiera szczegółowy komunikat o błędzie sprawdzania poprawności określonego.</span><span class="sxs-lookup"><span data-stu-id="466f7-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466f7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="466f7-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="466f7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="466f7-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="466f7-106">[in] Wartość HRESULT, która została przekazana do obsługi błędów sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="466f7-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="466f7-107">[in] A `VEContext` wystąpienia, który zawiera informacje o kontekście dotyczące błędy sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="466f7-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="466f7-108">[w, out] Przyjazne komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="466f7-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="466f7-109">[in] Maksymalna długość komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="466f7-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="466f7-110">[in] Bezpieczną tablicą dodatkowe parametry, które mają być używane w komunikacie.</span><span class="sxs-lookup"><span data-stu-id="466f7-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="466f7-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="466f7-111">Return Value</span></span>  
  
|<span data-ttu-id="466f7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="466f7-112">HRESULT</span></span>|<span data-ttu-id="466f7-113">Opis</span><span class="sxs-lookup"><span data-stu-id="466f7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="466f7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="466f7-114">S_OK</span></span>|<span data-ttu-id="466f7-115">`FormatEventInfo`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="466f7-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="466f7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="466f7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="466f7-117">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="466f7-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="466f7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="466f7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="466f7-119">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="466f7-119">The call timed out.</span></span>|  
|<span data-ttu-id="466f7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="466f7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="466f7-121">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="466f7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="466f7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="466f7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="466f7-123">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="466f7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="466f7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="466f7-124">E_FAIL</span></span>|<span data-ttu-id="466f7-125">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="466f7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="466f7-126">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="466f7-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="466f7-127">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="466f7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="466f7-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="466f7-128">Requirements</span></span>  
 <span data-ttu-id="466f7-129">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="466f7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466f7-130">**Nagłówek:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="466f7-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="466f7-131">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="466f7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="466f7-132">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466f7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466f7-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="466f7-133">See Also</span></span>  
 [<span data-ttu-id="466f7-134">ICLRErrorReportingManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="466f7-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="466f7-135">ICLRValidator — interfejs</span><span class="sxs-lookup"><span data-stu-id="466f7-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)