---
title: "Funkcja QualifierSet_EndEnumeration (niezarządzany wykaz interfejsów API)"
description: "Funkcja QualifierSet_EndEnumeration kończy wyliczenia."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="1553f-103">Funkcja QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="1553f-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="1553f-104">Kończy wyliczenie uruchomione za pomocą wywołania [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="1553f-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1553f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1553f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="1553f-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1553f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1553f-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="1553f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1553f-108">[in] Wskaźnik do [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1553f-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="1553f-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1553f-109">Return value</span></span>

<span data-ttu-id="1553f-110">Następującą wartość zwracana przez tę funkcję jest zdefiniowany w *WbemCli.h* pliku nagłówka, lub można zdefiniować ją jako stała w kodzie:</span><span class="sxs-lookup"><span data-stu-id="1553f-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="1553f-111">Stała</span><span class="sxs-lookup"><span data-stu-id="1553f-111">Constant</span></span>  |<span data-ttu-id="1553f-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="1553f-112">Value</span></span>  |<span data-ttu-id="1553f-113">Opis</span><span class="sxs-lookup"><span data-stu-id="1553f-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1553f-114">0</span><span class="sxs-lookup"><span data-stu-id="1553f-114">0</span></span> | <span data-ttu-id="1553f-115">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="1553f-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1553f-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1553f-116">Remarks</span></span>

<span data-ttu-id="1553f-117">Ta funkcja jest zawijana wywołanie [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="1553f-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1553f-118">To wywołanie jest zalecane, ale nie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="1553f-118">This call is recommended, but not required.</span></span> <span data-ttu-id="1553f-119">Natychmiast zwalnia zasoby skojarzone z wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="1553f-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="1553f-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1553f-120">Requirements</span></span>  

<span data-ttu-id="1553f-121">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1553f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="1553f-122">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1553f-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="1553f-123">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1553f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1553f-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1553f-124">See also</span></span>  
[<span data-ttu-id="1553f-125">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="1553f-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)