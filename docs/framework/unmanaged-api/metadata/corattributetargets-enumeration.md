---
title: "CorAttributeTargets — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets — Wyliczenie
Określa elementy aplikacji, na których jest on prawidłowy do zastosowania atrybutu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`catAssembly`|Atrybut można stosować do zestawu.|  
|`catModule`|Atrybut można stosować do przenośnego pliku wykonywalnego modułu (.dll lub .exe).|  
|`catClass`|Atrybut można stosować do klasy.|  
|`catStruct`|Atrybut można stosować do struktury; oznacza to, że wartość typu.|  
|`catEnum`|Atrybut można stosować do wyliczenia.|  
|`catConstructor`|Atrybut można stosować do konstruktora.|  
|`catMethod`|Atrybut można stosować do metody.|  
|`catProperty`|Atrybut można stosować do właściwości.|  
|`catField`|Atrybut można stosować do pola.|  
|`catEvent`|Atrybut można zastosować do zdarzenia.|  
|`catInterface`|Atrybut można stosować do interfejsu.|  
|`catParameter`|Atrybut można stosować do parametru.|  
|`catDelegate`|Atrybut można stosować do delegata.|  
|`catGenericParameter`|Atrybut można stosować do parametru ogólnego.|  
|`catAll`|Atrybut można stosować do dowolnych aplikacji.|  
|`catClassMembers`|Atrybut można stosować do elementu członkowskiego klasy.|  
  
## <a name="remarks"></a>Uwagi  
 `CorAttributeTargets` Wartości wyliczenia można łączyć z operacji lub pobrać preferowanych kombinacji.  
  
 `CorAttributeTargets` Równoleżnikami zarządzanej <xref:System.AttributeTargets?displayProperty=nameWithType> wyliczenia.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorHdr.h  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia metadanych](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
