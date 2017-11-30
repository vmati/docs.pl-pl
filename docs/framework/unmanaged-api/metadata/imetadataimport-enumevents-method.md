---
title: "IMetaDataImport::EnumEvents — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumEvents
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba893d59f9f119ce2f7eaf1af4ce268b6534acd1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="27e71-102">IMetaDataImport::EnumEvents — Metoda</span><span class="sxs-lookup"><span data-stu-id="27e71-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="27e71-103">Wylicza tokeny definicji zdarzenia dla określony token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="27e71-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e71-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="27e71-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27e71-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="27e71-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27e71-106">[w, out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="27e71-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="27e71-107">[in] Element TypeDef token definicje zdarzeń, których mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="27e71-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="27e71-108">[out] Tablica zwrócona zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="27e71-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27e71-109">[in] Maksymalny rozmiar `rEvents` tablicy.</span><span class="sxs-lookup"><span data-stu-id="27e71-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="27e71-110">[out] Rzeczywista liczba zdarzeń zwróconych w `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="27e71-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27e71-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="27e71-111">Return Value</span></span>  
  
|<span data-ttu-id="27e71-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27e71-112">HRESULT</span></span>|<span data-ttu-id="27e71-113">Opis</span><span class="sxs-lookup"><span data-stu-id="27e71-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="27e71-114">`EnumEvents`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="27e71-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27e71-115">Brak zdarzeń do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="27e71-115">There are no events to enumerate.</span></span> <span data-ttu-id="27e71-116">W takim przypadku `pcEvents` wynosi zero.</span><span class="sxs-lookup"><span data-stu-id="27e71-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27e71-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="27e71-117">Requirements</span></span>  
 <span data-ttu-id="27e71-118">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27e71-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e71-119">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27e71-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27e71-120">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27e71-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27e71-121">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e71-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e71-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27e71-122">See Also</span></span>  
 [<span data-ttu-id="27e71-123">IMetaDataImport — interfejs</span><span class="sxs-lookup"><span data-stu-id="27e71-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="27e71-124">IMetaDataImport2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="27e71-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)