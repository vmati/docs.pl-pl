---
title: "ICorDebugObjectValue::GetFieldValue — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33c3f368d9b78b899f54c989427ea1f660346487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="26932-102">ICorDebugObjectValue::GetFieldValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="26932-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="26932-103">Pobiera wartość określonego pola określonej klasy wartość tego obiektu.</span><span class="sxs-lookup"><span data-stu-id="26932-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26932-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="26932-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26932-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="26932-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="26932-106">[in] Wskaźnik do obiektu "ICorDebugClass", który reprezentuje klasę, dla którego można pobrać wartości pola.</span><span class="sxs-lookup"><span data-stu-id="26932-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="26932-107">[in] `mdFieldDef` Token, który odwołuje się do metadanych zawierająca opis w polu.</span><span class="sxs-lookup"><span data-stu-id="26932-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="26932-108">[out] Wskaźnik do obiektu "ICorDebugValue", który reprezentuje wartość określonego pola.</span><span class="sxs-lookup"><span data-stu-id="26932-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26932-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="26932-109">Remarks</span></span>  
 <span data-ttu-id="26932-110">Klasa określona w `pClass` parametru musi być w hierarchii klasy wartość obiektu, a pola musi należeć do tej klasy.</span><span class="sxs-lookup"><span data-stu-id="26932-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="26932-111">`GetFieldValue` Metody nadal się powieść ogólnego obiekty i klasy ogólne.</span><span class="sxs-lookup"><span data-stu-id="26932-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="26932-112">Na przykład jeśli MyDictionary\<V > dziedziczy ze słownika\<ciąg znaków, V >, i wartość do obiektu jest typu MyDictionary\<int32 >, przechodzącą `ICorDebugClass` obiekt słownika\<K, V > zostanie pomyślnie Pobierz pole słownika\<ciąg, int32 >.</span><span class="sxs-lookup"><span data-stu-id="26932-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26932-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="26932-113">Requirements</span></span>  
 <span data-ttu-id="26932-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26932-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26932-115">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26932-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26932-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26932-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26932-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26932-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26932-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="26932-118">See Also</span></span>  
    
 