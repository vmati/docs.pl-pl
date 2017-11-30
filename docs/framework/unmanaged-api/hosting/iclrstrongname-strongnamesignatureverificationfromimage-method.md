---
title: "ICLRStrongName::StrongNameSignatureVerificationFromImage — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f312e1eade6de57df9660a349570398d9cd912b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="1d58b-102">ICLRStrongName::StrongNameSignatureVerificationFromImage — Metoda</span><span class="sxs-lookup"><span data-stu-id="1d58b-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="1d58b-103">Sprawdza, czy zestaw, który został już zmapowany do pamięci jest nieprawidłowa dla klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="1d58b-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d58b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1d58b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d58b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1d58b-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="1d58b-106">[in] Wirtualny adres względny manifestu zestawu mapowane.</span><span class="sxs-lookup"><span data-stu-id="1d58b-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="1d58b-107">[in] Rozmiar w bajtach zamapowanych obrazu.</span><span class="sxs-lookup"><span data-stu-id="1d58b-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="1d58b-108">[in] Flagi wpływające na zachowanie weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="1d58b-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="1d58b-109">Obsługiwane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1d58b-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="1d58b-110">`SN_INFLAG_FORCE_VER`(0x00000001) - wymusza weryfikacji, nawet jeśli jest konieczne w celu zastąpienia ustawień rejestru.</span><span class="sxs-lookup"><span data-stu-id="1d58b-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="1d58b-111">`SN_INFLAG_INSTALL`(0x00000002) — określa, że jest to pierwszy weryfikacji wykonywane na ten obraz.</span><span class="sxs-lookup"><span data-stu-id="1d58b-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="1d58b-112">`SN_INFLAG_ADMIN_ACCESS`(0x00000004) — określa, że pamięć podręczna będzie zezwalał na dostęp tylko do użytkowników, którzy mają uprawnienia administracyjne.</span><span class="sxs-lookup"><span data-stu-id="1d58b-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="1d58b-113">`SN_INFLAG_USER_ACCESS`(0x00000008) — określa, czy zestaw będzie dostępny tylko dla bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1d58b-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="1d58b-114">`SN_INFLAG_ALL_ACCESS`(0x00000010) — określa, czy pamięć podręczna zapewni żadnych gwarancji ograniczeń dostępu.</span><span class="sxs-lookup"><span data-stu-id="1d58b-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="1d58b-115">`SN_INFLAG_RUNTIME`(0x80000000) - zarezerwowane dla wewnętrznego debugowania.</span><span class="sxs-lookup"><span data-stu-id="1d58b-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="1d58b-116">[out] Flaga informacje dodatkowe dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="1d58b-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="1d58b-117">Obsługiwane jest następującą wartość:</span><span class="sxs-lookup"><span data-stu-id="1d58b-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="1d58b-118">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001) — ta wartość jest równa `false` do określenia, czy Weryfikacja powiodła się z powodu ustawień rejestru.</span><span class="sxs-lookup"><span data-stu-id="1d58b-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d58b-119">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1d58b-119">Return Value</span></span>  
 <span data-ttu-id="1d58b-120">`S_OK`Jeśli metoda zakończyła się pomyślnie; w przeciwnym razie wartość HRESULT, która wskazuje niepowodzenie (zobacz [wspólne wartości HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) lista).</span><span class="sxs-lookup"><span data-stu-id="1d58b-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d58b-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1d58b-121">Requirements</span></span>  
 <span data-ttu-id="1d58b-122">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d58b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d58b-123">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1d58b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1d58b-124">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d58b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d58b-125">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d58b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d58b-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1d58b-126">See Also</span></span>  
 [<span data-ttu-id="1d58b-127">ICLRStrongName — interfejs</span><span class="sxs-lookup"><span data-stu-id="1d58b-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)