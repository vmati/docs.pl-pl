---
title: "ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.EvaluatePolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7471b77deca7b66ba0a30b08ccf934704a7ac61d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="82f8f-102">ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda</span><span class="sxs-lookup"><span data-stu-id="82f8f-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="82f8f-103">Ocenia zasady powiązanie imieniu hosta.</span><span class="sxs-lookup"><span data-stu-id="82f8f-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f8f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="82f8f-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82f8f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="82f8f-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="82f8f-106">[in] Odwołanie do zestawu przed oceny zasad.</span><span class="sxs-lookup"><span data-stu-id="82f8f-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="82f8f-107">[in] Wskaźnik do buforu, który zawiera dane zasad.</span><span class="sxs-lookup"><span data-stu-id="82f8f-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="82f8f-108">[in] Rozmiar `pbApplicationPolicy` buforu.</span><span class="sxs-lookup"><span data-stu-id="82f8f-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="82f8f-109">[out] Odwołanie do zestawu po dokonaniu oceny nowych danych zasad.</span><span class="sxs-lookup"><span data-stu-id="82f8f-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="82f8f-110">[w, out] Wskaźnik do rozmiar buforu odwołanie tożsamości zestawu po dokonaniu oceny nowych danych zasad.</span><span class="sxs-lookup"><span data-stu-id="82f8f-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="82f8f-111">[out] Wskaźnik do logicznego lub kombinację [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) wartości, wskazując, które zasady zostały zastosowane.</span><span class="sxs-lookup"><span data-stu-id="82f8f-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82f8f-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="82f8f-112">Return Value</span></span>  
  
|<span data-ttu-id="82f8f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82f8f-113">HRESULT</span></span>|<span data-ttu-id="82f8f-114">Opis</span><span class="sxs-lookup"><span data-stu-id="82f8f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82f8f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="82f8f-115">S_OK</span></span>|<span data-ttu-id="82f8f-116">Ocena została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="82f8f-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="82f8f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="82f8f-117">E_INVALIDARG</span></span>|<span data-ttu-id="82f8f-118">Albo `pwzReferenceIdentity` lub `pbApplicationPolicy` jest odwołanie o wartości null.</span><span class="sxs-lookup"><span data-stu-id="82f8f-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="82f8f-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="82f8f-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="82f8f-120">`cbAppPolicySize`jest za mały.</span><span class="sxs-lookup"><span data-stu-id="82f8f-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="82f8f-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82f8f-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82f8f-122">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="82f8f-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82f8f-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82f8f-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82f8f-124">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="82f8f-124">The call timed out.</span></span>|  
|<span data-ttu-id="82f8f-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82f8f-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82f8f-126">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="82f8f-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82f8f-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82f8f-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82f8f-128">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="82f8f-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82f8f-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82f8f-129">E_FAIL</span></span>|<span data-ttu-id="82f8f-130">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="82f8f-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82f8f-131">Po powrocie z metody E_FAIL CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="82f8f-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82f8f-132">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82f8f-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82f8f-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="82f8f-133">Remarks</span></span>  
 <span data-ttu-id="82f8f-134">`EvaluatePolicy` Metoda pozwala hosta wpływ zasad powiązania do obsługi zestawu specyficzne dla hosta wymagań dotyczących przechowywania wersji.</span><span class="sxs-lookup"><span data-stu-id="82f8f-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="82f8f-135">Aparat zasad sam pozostaje wewnątrz środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="82f8f-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f8f-136">Wymagania</span><span class="sxs-lookup"><span data-stu-id="82f8f-136">Requirements</span></span>  
 <span data-ttu-id="82f8f-137">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f8f-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f8f-138">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82f8f-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82f8f-139">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82f8f-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82f8f-140">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f8f-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f8f-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82f8f-141">See Also</span></span>  
 [<span data-ttu-id="82f8f-142">ICLRHostBindingPolicyManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="82f8f-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)