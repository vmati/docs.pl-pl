---
title: "SetAssemblyFile — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyFile
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile
helpviewer_keywords: SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d83062db41b5fa1485555de40be0a39a65e0459a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="f5847-102">SetAssemblyFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="f5847-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="f5847-103">Przypisuje nazwę zestawu, który ma zostać utworzony.</span><span class="sxs-lookup"><span data-stu-id="f5847-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="f5847-104">Nie do użytku podczas produkowania niepowiązane modułów.</span><span class="sxs-lookup"><span data-stu-id="f5847-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5847-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f5847-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5847-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f5847-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f5847-107">Pełna nazwa pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="f5847-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="f5847-108">Wskaźnik do [IMetaDataEmit — interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="f5847-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="f5847-109">Flagi zgodnie z definicją w [AssemblyFlags — wyliczenie](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f5847-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="f5847-110">Wskaźnik do Identyfikatora zestawu wynikowego.</span><span class="sxs-lookup"><span data-stu-id="f5847-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5847-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f5847-111">Return Value</span></span>  
 <span data-ttu-id="f5847-112">Zwraca wartość S_OK, jeśli metoda zakończy się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="f5847-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5847-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f5847-113">Requirements</span></span>  
 <span data-ttu-id="f5847-114">Wymaga alink.h.</span><span class="sxs-lookup"><span data-stu-id="f5847-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5847-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f5847-115">See Also</span></span>  
 [<span data-ttu-id="f5847-116">Ialink — interfejs</span><span class="sxs-lookup"><span data-stu-id="f5847-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f5847-117">Ialink2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="f5847-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f5847-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="f5847-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)