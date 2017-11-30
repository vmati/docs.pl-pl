---
title: "ICLRDomainManager — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75a7e93d26a5c77484d78ad4632bedf8def6a44b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="65c1a-102">ICLRDomainManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65c1a-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="65c1a-103">Umożliwia hosta określić Menedżer domeny aplikacji, który będzie używany do inicjowania domyślnej domeny aplikacji i określić właściwości inicjowania.</span><span class="sxs-lookup"><span data-stu-id="65c1a-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65c1a-104">Metody</span><span class="sxs-lookup"><span data-stu-id="65c1a-104">Methods</span></span>  
  
|<span data-ttu-id="65c1a-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="65c1a-105">Method</span></span>|<span data-ttu-id="65c1a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="65c1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65c1a-107">SetAppDomainManagerType — metoda</span><span class="sxs-lookup"><span data-stu-id="65c1a-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="65c1a-108">Określa typ pochodny <xref:System.AppDomainManager?displayProperty=nameWithType> klasy Menedżer domeny aplikacji, które będą używane do inicjowania domyślnej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="65c1a-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="65c1a-109">SetPropertiesForDefaultAppDomain — metoda</span><span class="sxs-lookup"><span data-stu-id="65c1a-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="65c1a-110">Ustawia właściwości, które będą używane do inicjowania domyślnej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="65c1a-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65c1a-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="65c1a-111">Remarks</span></span>  
 <span data-ttu-id="65c1a-112">Aby pobrać wystąpienia tego interfejsu, należy wywołać [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metody z typem Menedżera IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="65c1a-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65c1a-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65c1a-113">Requirements</span></span>  
 <span data-ttu-id="65c1a-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65c1a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65c1a-115">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="65c1a-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="65c1a-116">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65c1a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65c1a-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65c1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c1a-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65c1a-118">See Also</span></span>  
 [<span data-ttu-id="65c1a-119">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="65c1a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="65c1a-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="65c1a-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)