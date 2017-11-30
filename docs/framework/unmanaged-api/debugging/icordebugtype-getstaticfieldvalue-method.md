---
title: "ICorDebugType::GetStaticFieldValue — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="eec02-102">ICorDebugType::GetStaticFieldValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="eec02-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="eec02-103">Pobiera token w ramce stosu określonego wskaźnika interfejsu do obiektu ICorDebugValue, który zawiera wartość pola statycznego odwołuje się określonego pola.</span><span class="sxs-lookup"><span data-stu-id="eec02-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec02-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="eec02-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eec02-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="eec02-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="eec02-106">[in] `mdFieldDef` Token, który określa pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="eec02-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="eec02-107">[in] Wskaźnik do ICorDebugFrame, który reprezentuje ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="eec02-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="eec02-108">[out] Wskaźnik do adresu `ICorDebugValue` zawiera wartość pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="eec02-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eec02-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eec02-109">Remarks</span></span>  
 <span data-ttu-id="eec02-110">`GetStaticFieldValue` Metoda może być stosowana tylko wtedy, gdy typ jest po elemencie ELEMENT_TYPE_CLASS lub ELEMENT_TYPE_VALUETYPE, wskazywany przez [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="eec02-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="eec02-111">Dla typu nieogólnego, działanie wykonywane przez `GetStaticFieldValue` jest taka sama jak wywołanie [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) dla obiektu ICorDebugClass, który jest zwracany przez [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="eec02-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="eec02-112">Dla typów ogólnych będzie wartość pola statycznego względem konkretnego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="eec02-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="eec02-113">Ponadto jeśli pola statycznego może być względem wątku, kontekst lub domeny aplikacji, ramki stosu pomoże debugera określić poprawną wartość.</span><span class="sxs-lookup"><span data-stu-id="eec02-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eec02-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eec02-114">Remarks</span></span>  
 <span data-ttu-id="eec02-115">`GetStaticFieldValue`można użyć tylko w przypadku wywołania `ICorDebugType::GetType` zwraca wartość po elemencie ELEMENT_TYPE_CLASS lub ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="eec02-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eec02-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="eec02-116">Requirements</span></span>  
 <span data-ttu-id="eec02-117">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eec02-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eec02-118">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eec02-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eec02-119">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eec02-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eec02-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eec02-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>