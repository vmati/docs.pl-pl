---
title: Interfejs ICorDebugSymbolProvider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f5d897b1f426fd85fd274d5e56e8726b8cb892
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="d662e-102">Interfejs ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d662e-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="d662e-103">Udostępnia metody, które mogą służyć do pobierania informacji o symbolach debugowania.</span><span class="sxs-lookup"><span data-stu-id="d662e-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d662e-104">Metody</span><span class="sxs-lookup"><span data-stu-id="d662e-104">Methods</span></span>  
  
|<span data-ttu-id="d662e-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-105">Method</span></span>|<span data-ttu-id="d662e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d662e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d662e-107">GetAssemblyImageBytes — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="d662e-108">Odczytuje dane z zestawu scalonych podany wirtualny adres względny (RVA) w zestawie scalone.</span><span class="sxs-lookup"><span data-stu-id="d662e-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="d662e-109">GetAssemblyImageMetadata — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="d662e-110">Zwraca metadane z zestawu scalone.</span><span class="sxs-lookup"><span data-stu-id="d662e-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="d662e-111">GetCodeRange — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="d662e-112">Pobiera adres początkowy — metoda i rozmiar podany wirtualny adres względny (RVA) w metodzie.</span><span class="sxs-lookup"><span data-stu-id="d662e-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="d662e-113">GetInstanceFieldSymbols — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="d662e-114">Pobiera wystąpienie symboli pola, które odpowiadają podpis elementu typespec.</span><span class="sxs-lookup"><span data-stu-id="d662e-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="d662e-115">GetMergedAssemblyRecords — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="d662e-116">Pobiera rekordy symboli scalone zestawy.</span><span class="sxs-lookup"><span data-stu-id="d662e-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="d662e-117">GetMethodLocalSymbols — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="d662e-118">Pobiera symbole lokalne metody podany wirtualny adres względny (RVA) tej metody.</span><span class="sxs-lookup"><span data-stu-id="d662e-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="d662e-119">GetMethodParameterSymbols — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="d662e-120">Pobiera symbole parametru metody podany wirtualny adres względny (RVA) tej metody.</span><span class="sxs-lookup"><span data-stu-id="d662e-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="d662e-121">GetMethodProps — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="d662e-122">Zwraca informacje o właściwości metody, takie jak token metadanych oraz informacje o jego parametrów ogólnych — metoda podany wirtualny adres względny (RVA) w tej metody.</span><span class="sxs-lookup"><span data-stu-id="d662e-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="d662e-123">GetObjectSize — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="d662e-124">Zwraca rozmiar obiektu dla obiektu, w oparciu o jego sygnatura elementu typespec.</span><span class="sxs-lookup"><span data-stu-id="d662e-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="d662e-125">GetStaticFieldSymbols — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="d662e-126">Pobiera symbole statycznego pola, które odpowiadają podpis elementu typespec.</span><span class="sxs-lookup"><span data-stu-id="d662e-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="d662e-127">GetTypeProps — metoda</span><span class="sxs-lookup"><span data-stu-id="d662e-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="d662e-128">Zwraca informacje dotyczące typu właściwości, takie jak liczba podpisu jego parametry ogólne, podany wirtualny adres względny (RVA) w vtable.</span><span class="sxs-lookup"><span data-stu-id="d662e-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d662e-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d662e-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d662e-130">Ten interfejs jest tylko dostępne z platformą .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d662e-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d662e-131">W przypadku zastosowania tego interfejsu dla scenariuszy ICorDebug poza platformy .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="d662e-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d662e-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d662e-132">Requirements</span></span>  
 <span data-ttu-id="d662e-133">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d662e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d662e-134">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d662e-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d662e-135">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d662e-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d662e-136">**Wersje programu .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d662e-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d662e-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d662e-137">See Also</span></span>  
 [<span data-ttu-id="d662e-138">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="d662e-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d662e-139">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="d662e-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)