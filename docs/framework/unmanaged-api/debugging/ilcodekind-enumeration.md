---
title: Wyliczenie ILCodeKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ILCodeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61fd5ad93c198000556e8e0be3a278a842ab5716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="a4d34-102">Wyliczenie ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="a4d34-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="a4d34-103">[Obsługiwane w programie .NET Framework 4.5.2 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="a4d34-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a4d34-104">Zawiera wartości, które określają, czy debuger jest w stanie uzyskać dostęp do zmiennych lokalnych lub kodzie dodanym w ReJIT Instrumentacji profilera.</span><span class="sxs-lookup"><span data-stu-id="a4d34-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d34-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a4d34-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="a4d34-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="a4d34-106">Members</span></span>  
  
|<span data-ttu-id="a4d34-107">Nazwa elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="a4d34-107">Member name</span></span>|<span data-ttu-id="a4d34-108">Opis</span><span class="sxs-lookup"><span data-stu-id="a4d34-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="a4d34-109">Debuger nie ma dostępu do informacji z ReJIT instrumentacji.</span><span class="sxs-lookup"><span data-stu-id="a4d34-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="a4d34-110">Debuger ma dostęp do informacji z ReJIT instrumentacji.</span><span class="sxs-lookup"><span data-stu-id="a4d34-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4d34-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a4d34-111">Remarks</span></span>  
 <span data-ttu-id="a4d34-112">Członek `ILCodeKind` wyliczenia mogą zostać przekazane do [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) i [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) metod umożliwiających ustalenie, czy debuger może uzyskiwać dostęp do zmiennych dodany do programu profiler Instrumentacja ReJIT i [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) metodę, aby określić, czy debuger może uzyskiwać dostęp do Instrumentacji IL.</span><span class="sxs-lookup"><span data-stu-id="a4d34-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d34-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a4d34-113">Requirements</span></span>  
 <span data-ttu-id="a4d34-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d34-115">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4d34-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4d34-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4d34-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4d34-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d34-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a4d34-118">See Also</span></span>  
 [<span data-ttu-id="a4d34-119">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="a4d34-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="a4d34-120">Interfejs ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="a4d34-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="a4d34-121">ReJIT: Przewodnik</span><span class="sxs-lookup"><span data-stu-id="a4d34-121">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)