---
title: "CorDeclSecurity — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDeclSecurity
api_location: mscoree.dll
api_type: COM
f1_keywords: CorDeclSecurity
helpviewer_keywords: CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e5ba8de0a8db315e5c06586ad2248cfea241653b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="460b4-102">CorDeclSecurity — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="460b4-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="460b4-103">Określa akcje zabezpieczeń, które mogą być wykonywane przy użyciu zabezpieczeń deklaratywnych.</span><span class="sxs-lookup"><span data-stu-id="460b4-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460b4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="460b4-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="460b4-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="460b4-105">Members</span></span>  
  
|<span data-ttu-id="460b4-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="460b4-106">Member</span></span>|<span data-ttu-id="460b4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="460b4-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="460b4-108">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="460b4-109">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="460b4-110">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="460b4-111">Wszystkie obiekty wywołujące wyżej w stosie wywołań są wymagane do otrzymali uprawnienia określone przez bieżący obiekt uprawnień.</span><span class="sxs-lookup"><span data-stu-id="460b4-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="460b4-112">Kod wywołujący ma dostęp do zasobu identyfikowana na podstawie bieżącego obiektu uprawnienia, nawet jeśli wyżej w stosie wywołań nie przyznano uprawnień dostępu do zasobu</span><span class="sxs-lookup"><span data-stu-id="460b4-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="460b4-113">Możliwość dostępu do zasobu określonego przez bieżący obiekt uprawnienia Odmowa dla kodu wywołującego, nawet wtedy, gdy przyznano im uprawnienia dostępu do niego.</span><span class="sxs-lookup"><span data-stu-id="460b4-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="460b4-114">Tylko zasoby określone przez ten obiekt uprawnienia są dostępne, nawet jeśli kod ma uprawnienia dostępu do innych zasobów.</span><span class="sxs-lookup"><span data-stu-id="460b4-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="460b4-115">Bezpośredniego obiektu wywołującego jest wymagany do przyznano określonego uprawnienia w danym okresie czasu.</span><span class="sxs-lookup"><span data-stu-id="460b4-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="460b4-116">Klasy pochodnej dziedziczenia innej klasy lub przesłaniania metody jest wymagany do przyznano określonego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="460b4-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="460b4-117">Obiekt wywołujący może wysłać żądanie minimalne uprawnienia wymagane przez kod wymagany do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="460b4-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="460b4-118">Ta akcja można używać tylko w zakresie zestawu.</span><span class="sxs-lookup"><span data-stu-id="460b4-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="460b4-119">Obiekt wywołujący może wysłać żądanie uzyskania dodatkowych uprawnień, które są opcjonalne (nie trzeba uruchamiać).</span><span class="sxs-lookup"><span data-stu-id="460b4-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="460b4-120">To żądanie odmawia niejawnie innych uprawnień nie pobrany na żądanie.</span><span class="sxs-lookup"><span data-stu-id="460b4-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="460b4-121">Ta akcja można używać tylko w zakresie zestawu.</span><span class="sxs-lookup"><span data-stu-id="460b4-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="460b4-122">Nie otrzyma żądanie wywołującego uprawnienia, które mogą być używane.</span><span class="sxs-lookup"><span data-stu-id="460b4-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="460b4-123">Ta akcja można używać tylko w zakresie zestawu.</span><span class="sxs-lookup"><span data-stu-id="460b4-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="460b4-124">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="460b4-125">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="460b4-126">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="460b4-127">Bezpośredniego obiektu wywołującego jest wymagany do przyznano określonego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="460b4-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="460b4-128">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="460b4-129">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="460b4-130">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="460b4-131">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="460b4-132">Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="460b4-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="460b4-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="460b4-133">Requirements</span></span>  
 <span data-ttu-id="460b4-134">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="460b4-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="460b4-135">**Nagłówek:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="460b4-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="460b4-136">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="460b4-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460b4-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="460b4-137">See Also</span></span>  
 [<span data-ttu-id="460b4-138">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="460b4-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)