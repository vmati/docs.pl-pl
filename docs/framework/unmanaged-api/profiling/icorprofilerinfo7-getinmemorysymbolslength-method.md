---
title: "ICorProfilerInfo7::GetInMemorySymbolsLength — metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type: COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c1299429e9173069c5a39fe4a2b82d1db5938f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength — metoda
[Obsługiwane w programie .NET Framework 4.6.1 i nowszych wersjach]  
  
 Zwraca długość strumienia symbol w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] Identyfikator modułu zawierającego strumienia w pamięci.  
  
 pCountSymbolBytes  
 [out] Wskaźnik do `DWORD` wartość, gdy metoda zwróci wartość, zawiera długość strumienia w bajtach.  
  
## <a name="return-value"></a>Wartość zwracana  
 Metoda zwraca `S_OK` Jeśli długość strumienia pamięci można ustalić, nawet jeśli jest ona zero (0).  
  
 Metoda zwraca `CORPROF_E_MODULE_IS_DYNAMIC` Jeśli metoda została utworzona przy użyciu <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli moduł zawiera symbole w pamięci, długość strumienia jest umieszczany w `pCountSymbolBytes`. Jeśli moduł nie ma symboli w pamięci `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  Bieżąca implementacja nie obsługuje Reflection.Emit. Jeśli moduł został utworzony przy użyciu Reflection.Emit, metoda zwraca `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerInfo7, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
