---
title: "EClrFailure — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e25a5378349dd476321765bb085db958e29670e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="eclrfailure-enumeration"></a>EClrFailure — Wyliczenie
W tym artykule opisano zestaw awarie, dla których hosta można ustawić akcje zasady.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Wystąpił błąd podczas próby przydzielić zasobów (np. wątek, blok pamięci lub blokady) w regionie niekrytyczne kodu.|  
|`FAIL_CriticalResource`|Wystąpił błąd podczas próby przydzielić zasobów (np. wątek, blok pamięci lub blokady) w regionie krytyczne kodu.|  
|`FAIL_FatalRuntime`|Środowisko uruchomieniowe języka wspólnego (CLR) nie jest już mogli uruchamiać kodu zarządzanego w procesie. Odtąd wartość HRESULT HOST_E_CLRNOTAVAILABLE zwracana wywołania wszystkie funkcje hostingu.|  
|`FAIL_OrphanedLock`|Wątek nie powiodło się zwolnić blokady na zwracanie z <xref:System.AppDomain> obiektu. Hosta nie można ustawić tego błędu powoduje wątku do przerwania.|  
|`FAIL_StackOverflow`|Ma doszło do przepełnienia stosu.|  
|`FAIL_AccessViolation`|Nastąpiła próba odczytu lub zapisu pamięci chronionej. Nieobsługiwane w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Wystąpił błąd kontraktu kodu. Zobacz [kodu kontrakty](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Uwagi  
 Zobacz [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metody listę [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) wartości hosta można użyć do określenia akcje zasad warunki błędu. Aby uzyskać więcej informacji na temat regionów krytyczne i niekrytyczne kod, zobacz [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** biblioteki MSCorEE.dll  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICLRPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Hosting — wyliczenia](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
