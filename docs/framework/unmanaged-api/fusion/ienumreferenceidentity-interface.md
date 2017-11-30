---
title: "IEnumReferenceIdentity — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49e1425e8e7e3d09dc36915916b887d2887dccff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="077a2-102">IEnumReferenceIdentity — Interfejs</span><span class="sxs-lookup"><span data-stu-id="077a2-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="077a2-103">Służy jako moduł wyliczający kolekcji `IReferenceIdentity` obiektów.</span><span class="sxs-lookup"><span data-stu-id="077a2-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="077a2-104">Metody</span><span class="sxs-lookup"><span data-stu-id="077a2-104">Methods</span></span>  
  
|<span data-ttu-id="077a2-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="077a2-105">Method</span></span>|<span data-ttu-id="077a2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="077a2-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="077a2-107">Pobiera wskaźnika interfejsu na nowy `IEnumReferenceIdentity` zawierający członkowie to `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="077a2-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="077a2-108">Pobiera określoną liczbę `IReferenceIdentity` obiektów, zaczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="077a2-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="077a2-109">Przesuwa wskaźnik instrukcji na początku `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="077a2-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="077a2-110">Przenosi do przodu wskaźnik instrukcji przez określoną liczbę elementów, licząc w bieżącym położeniu.</span><span class="sxs-lookup"><span data-stu-id="077a2-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="077a2-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="077a2-111">Requirements</span></span>  
 <span data-ttu-id="077a2-112">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="077a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="077a2-113">**Nagłówek:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="077a2-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="077a2-114">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="077a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077a2-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="077a2-115">See Also</span></span>  
 [<span data-ttu-id="077a2-116">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="077a2-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="077a2-117">IReferenceIdentity — interfejs</span><span class="sxs-lookup"><span data-stu-id="077a2-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)