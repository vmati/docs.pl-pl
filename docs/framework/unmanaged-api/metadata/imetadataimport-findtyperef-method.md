---
title: "IMetaDataImport::FindTypeRef — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d742033788e270f01ee0cea70569ca65e7f35697
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="abbf6-102">IMetaDataImport::FindTypeRef — Metoda</span><span class="sxs-lookup"><span data-stu-id="abbf6-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="abbf6-103">Pobiera wskaźnik do elementu TypeRef token dla <xref:System.Type> odwołania, który znajduje się w określonym zakresie i który ma określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="abbf6-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abbf6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="abbf6-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abbf6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="abbf6-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="abbf6-106">[in] Token element ModuleRef, elementu AssemblyRef ani TypeRef, który określa zestawu, modułu lub typ, odpowiednio, w które odwołują się typ jest zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="abbf6-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="abbf6-107">[in] Nazwa odwołania typu do wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="abbf6-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="abbf6-108">[out] Wskaźnik do dopasowania token TypeRef.</span><span class="sxs-lookup"><span data-stu-id="abbf6-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abbf6-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="abbf6-109">Requirements</span></span>  
 <span data-ttu-id="abbf6-110">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abbf6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abbf6-111">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="abbf6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abbf6-112">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abbf6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abbf6-113">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abbf6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbf6-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="abbf6-114">See Also</span></span>  
 [<span data-ttu-id="abbf6-115">IMetaDataImport — interfejs</span><span class="sxs-lookup"><span data-stu-id="abbf6-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="abbf6-116">IMetaDataImport2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="abbf6-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)