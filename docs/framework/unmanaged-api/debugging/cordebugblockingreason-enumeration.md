---
title: "CorDebugBlockingReason — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingReason
helpviewer_keywords: CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84c09de4e0ce6e436c2c814c4cd9990db012d422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason — Wyliczenie
Określa przyczyny, dlaczego wątek może stać się zablokowane na dany obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`BLOCKING_NONE`|Tylko do użytku wewnętrznego.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Wątek próbuje pobrać krytyczne sekcja, która jest skojarzona z monitora blokady obiektu. Zazwyczaj dzieje się tak podczas wywoływania jednej z <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> lub <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> metody.|  
|`BLOCKING_MONITOR_EVENT`|Wątek oczekuje na zdarzenie, które jest skojarzone z monitora blokady dla obiekt. Zazwyczaj dzieje się tak podczas wywoływania jednej z <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` metody.|  
  
## <a name="remarks"></a>Uwagi  
 Gdy `BLOCKING_MONITOR_CRITICAL_SECTION` lub `BLOCKING_MONITOR_EVENT` element członkowski jest używany w [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struktury, `pBlockingObject` członkiem punktami struktury interfejs "ICorDebugValue", który reprezentuje obiekt, który jest wprowadzane . Również gwarantowane zaimplementować [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interfejsu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie, wyliczenia](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
