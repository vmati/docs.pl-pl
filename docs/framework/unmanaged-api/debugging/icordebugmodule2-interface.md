---
title: ICorDebugModule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97259783d34babe3f0f229f5d62b3e945c0ac624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="98395-102">ICorDebugModule2 Interface1</span><span class="sxs-lookup"><span data-stu-id="98395-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="98395-103">Służy jako logiczne rozszerzenia interfejsu ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="98395-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98395-104">Metody</span><span class="sxs-lookup"><span data-stu-id="98395-104">Methods</span></span>  
  
|<span data-ttu-id="98395-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="98395-105">Method</span></span>|<span data-ttu-id="98395-106">Opis</span><span class="sxs-lookup"><span data-stu-id="98395-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98395-107">ApplyChanges — metoda</span><span class="sxs-lookup"><span data-stu-id="98395-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="98395-108">Stosuje zmiany w metadanych i zmian w kodzie języka pośredniego (MSIL) firmy Microsoft do uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="98395-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="98395-109">GetJITCompilerFlags — metoda</span><span class="sxs-lookup"><span data-stu-id="98395-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="98395-110">Pobiera flagi sterujące kompilacji just-in-time (JIT) dla tego `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="98395-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="98395-111">ResolveAssembly — metoda</span><span class="sxs-lookup"><span data-stu-id="98395-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="98395-112">Usuwa zestaw odwołuje się token określonych metadanych.</span><span class="sxs-lookup"><span data-stu-id="98395-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="98395-113">SetJITCompilerFlags — metoda</span><span class="sxs-lookup"><span data-stu-id="98395-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="98395-114">Ustawia flagi sterujące kompilacji JIT to `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="98395-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="98395-115">SetJMCStatus — metoda</span><span class="sxs-lookup"><span data-stu-id="98395-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="98395-116">Ustawia stan tylko mój kod (JMC) wszystkich metod wszystkie klasy w tym `ICorDebugModule2` na określoną wartość, z wyjątkiem tych `pTokens` tablicy, która ustawia przeciwną wartość.</span><span class="sxs-lookup"><span data-stu-id="98395-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98395-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="98395-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98395-118">Ten interfejs nie obsługuje wywoływany zdalnie, między komputerami lub między procesami.</span><span class="sxs-lookup"><span data-stu-id="98395-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98395-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="98395-119">Requirements</span></span>  
 <span data-ttu-id="98395-120">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98395-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98395-121">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98395-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98395-122">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98395-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98395-123">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98395-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98395-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="98395-124">See Also</span></span>  
 [<span data-ttu-id="98395-125">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="98395-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)