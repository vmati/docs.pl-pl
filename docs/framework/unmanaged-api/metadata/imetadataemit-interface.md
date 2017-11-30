---
title: "IMetaDataEmit — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit
helpviewer_keywords: IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b62e11f8237330122ccd2bd8775f8d113545dd95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit-interface"></a><span data-ttu-id="dce08-102">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dce08-102">IMetaDataEmit Interface</span></span>
<span data-ttu-id="dce08-103">Udostępnia metody do tworzenia, modyfikacji i zapisać metadane dotyczące zestawu w aktualnie określonego zakresu.</span><span class="sxs-lookup"><span data-stu-id="dce08-103">Provides methods to create, modify, and save metadata about the assembly in the currently defined scope.</span></span> <span data-ttu-id="dce08-104">Metadane można przechowywane w pamięci lub zapisanej na dysku.</span><span class="sxs-lookup"><span data-stu-id="dce08-104">The metadata can be stored in memory or saved to disk.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dce08-105">Metody</span><span class="sxs-lookup"><span data-stu-id="dce08-105">Methods</span></span>  
  
|<span data-ttu-id="dce08-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-106">Method</span></span>|<span data-ttu-id="dce08-107">Opis</span><span class="sxs-lookup"><span data-stu-id="dce08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dce08-108">ApplyEditAndContinue — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-108">ApplyEditAndContinue Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|<span data-ttu-id="dce08-109">Aktualizuje bieżącego zakresu zestawu zmiany wprowadzone w określonym `pImport`.</span><span class="sxs-lookup"><span data-stu-id="dce08-109">Updates the current assembly scope with the changes made in the specified `pImport`.</span></span>|  
|[<span data-ttu-id="dce08-110">DefineCustomAttribute — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-110">DefineCustomAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|<span data-ttu-id="dce08-111">Tworzy definicji dla atrybutu niestandardowego o sygnaturze określonych metadanych, jest dołączony do określonego obiektu i pobiera token do tej definicji atrybutu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="dce08-111">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>|  
|[<span data-ttu-id="dce08-112">DefineEvent — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-112">DefineEvent Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|<span data-ttu-id="dce08-113">Tworzy definicję zdarzenie o sygnaturze określonych metadanych, a następnie pobiera token do tej definicji zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="dce08-113">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>|  
|[<span data-ttu-id="dce08-114">DefineField — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-114">DefineField Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|<span data-ttu-id="dce08-115">Tworzy definicję pola z podpisem określonych metadanych i pobiera token do tej definicji pola.</span><span class="sxs-lookup"><span data-stu-id="dce08-115">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>|  
|[<span data-ttu-id="dce08-116">DefineImportMember — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-116">DefineImportMember Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|<span data-ttu-id="dce08-117">Tworzy definicji dla elementu członkowskiego typu, który jest zdefiniowany w module spoza zakresu i pobiera token dla tej definicji odwołania.</span><span class="sxs-lookup"><span data-stu-id="dce08-117">Creates a definition for a member of a type that is defined in a module outside the current scope, and gets a token for that reference definition.</span></span>|  
|[<span data-ttu-id="dce08-118">DefineImportType — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-118">DefineImportType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|<span data-ttu-id="dce08-119">Tworzy definicję dla odwołania do typu, który jest zdefiniowany w module poza bieżącym zakresem i pobiera token do tej definicji odwołania.</span><span class="sxs-lookup"><span data-stu-id="dce08-119">Creates a definition for a reference to a type that is defined in a module outside the current scope, and gets a token to that reference definition.</span></span>|  
|[<span data-ttu-id="dce08-120">DefineMemberRef — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-120">DefineMemberRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|<span data-ttu-id="dce08-121">Tworzy definicję dla odwołania do elementu członkowskiego modułu poza bieżącym zakresem i pobiera token do tej definicji odwołania.</span><span class="sxs-lookup"><span data-stu-id="dce08-121">Creates a definition for a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>|  
|[<span data-ttu-id="dce08-122">DefineMethod — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-122">DefineMethod Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|<span data-ttu-id="dce08-123">Tworzy definicję metody z określoną sygnaturą i zwraca token do tej definicji metody.</span><span class="sxs-lookup"><span data-stu-id="dce08-123">Creates a definition for a method with the specified signature, and returns a token to that method definition.</span></span>|  
|[<span data-ttu-id="dce08-124">DefineMethodImpl — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-124">DefineMethodImpl Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|<span data-ttu-id="dce08-125">Tworzy definicję dla implementacji metody dziedziczone z interfejsem i zwraca token do tej definicji implementacji metody.</span><span class="sxs-lookup"><span data-stu-id="dce08-125">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>|  
|[<span data-ttu-id="dce08-126">DefineModuleRef — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-126">DefineModuleRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|<span data-ttu-id="dce08-127">Tworzy podpis metadane dla modułu o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="dce08-127">Creates the metadata signature for a module with the specified name.</span></span>|  
|[<span data-ttu-id="dce08-128">DefineNestedType — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-128">DefineNestedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|<span data-ttu-id="dce08-129">Tworzy podpisu metadanych definicją typu i zwraca `mdTypeDef` tokenu dla tego typu, który jest również określenie, że zdefiniowanego typu jest elementem członkowskim typu odwołuje się `tdEncloser`.</span><span class="sxs-lookup"><span data-stu-id="dce08-129">Creates the metadata signature of a type definition and returns an `mdTypeDef` token for that type, additionally specifying that the defined type is a member of the type referenced by `tdEncloser`.</span></span>|  
|[<span data-ttu-id="dce08-130">DefineParam — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-130">DefineParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|<span data-ttu-id="dce08-131">Tworzy definicję parametru z określoną sygnaturą dla metody odwołuje się określony token i pobiera token dla tej definicji parametru.</span><span class="sxs-lookup"><span data-stu-id="dce08-131">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>|  
|[<span data-ttu-id="dce08-132">DefinePermissionSet — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-132">DefinePermissionSet Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|<span data-ttu-id="dce08-133">Tworzy definicji zestawu uprawnień o podpisu określonych metadanych, a następnie pobiera token do tej definicji zestawu uprawnień.</span><span class="sxs-lookup"><span data-stu-id="dce08-133">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>|  
|[<span data-ttu-id="dce08-134">DefinePinvokeMap — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-134">DefinePinvokeMap Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|<span data-ttu-id="dce08-135">Ustawia funkcje metody odwołuje się określony token podpisu funkcji PInvoke.</span><span class="sxs-lookup"><span data-stu-id="dce08-135">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-136">DefineProperty — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-136">DefineProperty Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|<span data-ttu-id="dce08-137">Utworzenie definicji właściwości dla określonego typu z określonym `get` i `set` akcesorów — metoda i pobiera token do tej definicji właściwości.</span><span class="sxs-lookup"><span data-stu-id="dce08-137">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>|  
|[<span data-ttu-id="dce08-138">DefineSecurityAttributeSet — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-138">DefineSecurityAttributeSet Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|<span data-ttu-id="dce08-139">Tworzy zestaw uprawnień zabezpieczeń, aby dołączyć do obiektu odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-139">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-140">DefineTypeDef — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-140">DefineTypeDef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|<span data-ttu-id="dce08-141">Tworzy definicji typu dla typu środowiska uruchomieniowego języka wspólnego i pobiera token metadanych do tej definicji typu.</span><span class="sxs-lookup"><span data-stu-id="dce08-141">Creates a type definition for a common language runtime type, and gets a metadata token to that type definition.</span></span>|  
|[<span data-ttu-id="dce08-142">DefineTypeRefByName — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-142">DefineTypeRefByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|<span data-ttu-id="dce08-143">Pobiera token metadanych dla typu, który jest zdefiniowany w innym module spoza zakresu.</span><span class="sxs-lookup"><span data-stu-id="dce08-143">Gets a metadata token for a type that is defined in another module outside the current scope.</span></span>|  
|[<span data-ttu-id="dce08-144">DefineUserString — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-144">DefineUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|<span data-ttu-id="dce08-145">Pobiera metadane token dla określonego ciągu literału.</span><span class="sxs-lookup"><span data-stu-id="dce08-145">Gets a metadata token for the specified literal string.</span></span>|  
|[<span data-ttu-id="dce08-146">DeleteClassLayout — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-146">DeleteClassLayout Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|<span data-ttu-id="dce08-147">Niszczy podpisu metadanych układ klasy dla typu odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-147">Destroys the class layout metadata signature for the type referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-148">DeleteFieldMarshal — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-148">DeleteFieldMarshal Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|<span data-ttu-id="dce08-149">Niszczy PInvoke organizowanie podpisu metadanych dla obiekt odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-149">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-150">DeletePinvokeMap — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-150">DeletePinvokeMap Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|<span data-ttu-id="dce08-151">Niszczy metadanych mapowania PInvoke dla obiekt odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-151">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-152">DeleteToken — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-152">DeleteToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|<span data-ttu-id="dce08-153">Usuwa określony token z bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="dce08-153">Deletes the specified token from the current metadata scope.</span></span>|  
|[<span data-ttu-id="dce08-154">GetSaveSize — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-154">GetSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|<span data-ttu-id="dce08-155">Pobiera szacowany rozmiar binarnych zestawu w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="dce08-155">Gets the estimated binary size of the assembly in the current scope.</span></span>|  
|[<span data-ttu-id="dce08-156">GetTokenFromSig — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-156">GetTokenFromSig Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|<span data-ttu-id="dce08-157">Pobiera token podpisu określonych metadanych.</span><span class="sxs-lookup"><span data-stu-id="dce08-157">Gets a token for the specified metadata signature.</span></span>|  
|[<span data-ttu-id="dce08-158">GetTokenFromTypeSpec — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-158">GetTokenFromTypeSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|<span data-ttu-id="dce08-159">Pobiera token metadanych dla typu o sygnaturze określonych metadanych.</span><span class="sxs-lookup"><span data-stu-id="dce08-159">Gets a metadata token for the type with the specified metadata signature.</span></span>|  
|[<span data-ttu-id="dce08-160">Merge — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-160">Merge Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|<span data-ttu-id="dce08-161">Dodaje określony zakres zaimportowane do listy zakresów do scalenia.</span><span class="sxs-lookup"><span data-stu-id="dce08-161">Adds the specified imported scope to the list of scopes to be merged.</span></span>|  
|[<span data-ttu-id="dce08-162">MergeEnd — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-162">MergeEnd Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|<span data-ttu-id="dce08-163">Scalenia do bieżącego zakresu zakresy metadanych określonych przez jeden lub więcej poprzedniego wywołania `IMetaDataEmit::Merge`.</span><span class="sxs-lookup"><span data-stu-id="dce08-163">Merges into the current scope all the metadata scopes specified by one or more prior calls to `IMetaDataEmit::Merge`.</span></span>|  
|[<span data-ttu-id="dce08-164">Save — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-164">Save Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|<span data-ttu-id="dce08-165">Zapisuje wszystkie metadane w bieżącym zakresie pliku pod określonym adresem.</span><span class="sxs-lookup"><span data-stu-id="dce08-165">Saves all metadata in the current scope to the file at the specified address.</span></span>|  
|[<span data-ttu-id="dce08-166">SaveToMemory — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-166">SaveToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|<span data-ttu-id="dce08-167">Zapisuje wszystkie metadane w bieżącym zakresie do określonego obszaru pamięci.</span><span class="sxs-lookup"><span data-stu-id="dce08-167">Saves all metadata in the current scope to the specified area of memory.</span></span>|  
|[<span data-ttu-id="dce08-168">SaveToStream — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-168">SaveToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|<span data-ttu-id="dce08-169">Zapisuje wszystkie metadane w bieżącym zakresie do określonego `IStream`.</span><span class="sxs-lookup"><span data-stu-id="dce08-169">Saves all metadata in the current scope to the specified `IStream`.</span></span>|  
|[<span data-ttu-id="dce08-170">SetClassLayout — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-170">SetClassLayout Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|<span data-ttu-id="dce08-171">Ustawia lub aktualizuje podpis układ klasy typ zdefiniowany przez poprzednie wywołanie `IMetaDataEmit::DefineTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="dce08-171">Sets or updates the class layout signature of a type defined by a prior call to `IMetaDataEmit::DefineTypeDef`.</span></span>|  
|[<span data-ttu-id="dce08-172">SetCustomAttributeValue — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-172">SetCustomAttributeValue Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|<span data-ttu-id="dce08-173">Ustawia lub aktualizuje wartość atrybutu niestandardowego wynika z wcześniejszym wywołaniu `IMetaDataEmit::DefineCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="dce08-173">Sets or updates the value of a custom attribute defined by a prior call to `IMetaDataEmit::DefineCustomAttribute`.</span></span>|  
|[<span data-ttu-id="dce08-174">SetEventProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-174">SetEventProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|<span data-ttu-id="dce08-175">Ustawia lub aktualizuje określoną funkcję wynika z wcześniejszym wywołaniu zdarzenia `IMetaDataEmit::DefineEvent`.</span><span class="sxs-lookup"><span data-stu-id="dce08-175">Sets or updates the specified feature of an event defined by a prior call to `IMetaDataEmit::DefineEvent`.</span></span>|  
|[<span data-ttu-id="dce08-176">SetFieldMarshal — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-176">SetFieldMarshal Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|<span data-ttu-id="dce08-177">Ustawia PInvoke przekazywanie informacji dla parametru pola, zwracany — metoda lub metody odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-177">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-178">SetFieldProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-178">SetFieldProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|<span data-ttu-id="dce08-179">Ustawia lub aktualizuje wartość domyślna w polu odwołuje się token określonego pola.</span><span class="sxs-lookup"><span data-stu-id="dce08-179">Sets or updates the default value for the field referenced by the specified field token.</span></span>|  
|[<span data-ttu-id="dce08-180">SetFieldRVA — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-180">SetFieldRVA Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|<span data-ttu-id="dce08-181">Ustawia wartość zmiennej globalnej względną wirtualnego adresu pola odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="dce08-181">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-182">SetHandler — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-182">SetHandler Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|<span data-ttu-id="dce08-183">Ustawia metodę odwołuje się określony `IUnknown` wskaźnika jako wywołanie zwrotne powiadomienia dla tokenu ponowne mapowania.</span><span class="sxs-lookup"><span data-stu-id="dce08-183">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>|  
|[<span data-ttu-id="dce08-184">SetMethodImplFlags — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-184">SetMethodImplFlags Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|<span data-ttu-id="dce08-185">Ustawia lub aktualizuje podpis implementacji dziedziczonej metody odwołuje się określony token metadanych.</span><span class="sxs-lookup"><span data-stu-id="dce08-185">Sets or updates the metadata signature of the inherited method implementation referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dce08-186">SetMethodProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-186">SetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|<span data-ttu-id="dce08-187">Ustawia lub aktualizuje funkcję przechowywane w określonej wirtualnej adres względny, zdefiniowany przez poprzednie wywołanie do metody `IMetaDataEmit::DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="dce08-187">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to `IMetaDataEmit::DefineMethod`.</span></span>|  
|[<span data-ttu-id="dce08-188">SetModuleProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-188">SetModuleProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|<span data-ttu-id="dce08-189">Aktualizuje odwołania do modułu wynika z wcześniejszym wywołaniu `IMetaDataEmit::DefineModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="dce08-189">Updates references to a module defined by a prior call to `IMetaDataEmit::DefineModuleRef`.</span></span>|  
|[<span data-ttu-id="dce08-190">SetParamProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-190">SetParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|<span data-ttu-id="dce08-191">Ustawia lub zmienia funkcje parametru metody, która została zdefiniowana przez poprzednie wywołanie `IMetaDataEmit::DefineParam`.</span><span class="sxs-lookup"><span data-stu-id="dce08-191">Sets or changes features of a method parameter that was defined by a prior call to `IMetaDataEmit::DefineParam`.</span></span>|  
|[<span data-ttu-id="dce08-192">SetParent — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-192">SetParent Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|<span data-ttu-id="dce08-193">Ustali, że określony element członkowski, zdefiniowane przez poprzednie wywołanie `IMetaDataEmit::DefineMemberRef`, jest członkiem określonego typu, zgodnie z wcześniejszym wywołaniu `IMetaDataEmit::DefineTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="dce08-193">Establishes that the specified member, as defined by a prior call to `IMetaDataEmit::DefineMemberRef`, is a member of the specified type, as defined by a prior call to `IMetaDataEmit::DefineTypeDef`.</span></span>|  
|[<span data-ttu-id="dce08-194">SetPermissionSetProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-194">SetPermissionSetProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|<span data-ttu-id="dce08-195">Ustawia lub aktualizuje funkcje podpisu metadanych zestawu uprawnień wynika z wcześniejszym wywołaniu `IMetaDataEmit::DefinePermissionSet`.</span><span class="sxs-lookup"><span data-stu-id="dce08-195">Sets or updates features of the metadata signature of a permission set defined by a prior call to `IMetaDataEmit::DefinePermissionSet`.</span></span>|  
|[<span data-ttu-id="dce08-196">SetPinvokeMap — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-196">SetPinvokeMap Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|<span data-ttu-id="dce08-197">Ustawia lub zmienia funkcje podpisu funkcji PInvoke metody, zgodnie z wcześniejszym wywołaniu `IMetaDataEmit::DefinePinvokeMap`.</span><span class="sxs-lookup"><span data-stu-id="dce08-197">Sets or changes features of a method's PInvoke signature, as defined by a prior call to `IMetaDataEmit::DefinePinvokeMap`.</span></span>|  
|[<span data-ttu-id="dce08-198">SetPropertyProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-198">SetPropertyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|<span data-ttu-id="dce08-199">Ustawia przechowywane w metadanych dla właściwości zdefiniowane przez poprzednie wywołanie funkcji `IMetaDataEmit::DefineProperty`.</span><span class="sxs-lookup"><span data-stu-id="dce08-199">Sets the features stored in metadata for a property defined by a prior call to `IMetaDataEmit::DefineProperty`.</span></span>|  
|[<span data-ttu-id="dce08-200">SetRVA — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-200">SetRVA Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|<span data-ttu-id="dce08-201">Ustawia adres względny wirtualnego określonej metody.</span><span class="sxs-lookup"><span data-stu-id="dce08-201">Sets the relative virtual address of the specified method.</span></span>|  
|[<span data-ttu-id="dce08-202">SetTypeDefProps — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-202">SetTypeDefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|<span data-ttu-id="dce08-203">Ustawia typ zdefiniowany przez poprzednie wywołanie funkcji `IMetaDataEmit::DefineTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="dce08-203">Sets features of a type defined by a prior call to `IMetaDataEmit::DefineTypeDef`.</span></span>|  
|[<span data-ttu-id="dce08-204">TranslateSigWithScope — metoda</span><span class="sxs-lookup"><span data-stu-id="dce08-204">TranslateSigWithScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|<span data-ttu-id="dce08-205">Importuje zestawu do bieżącego zakresu i pobiera nowego podpisu metadanych dla zakresu scalone.</span><span class="sxs-lookup"><span data-stu-id="dce08-205">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dce08-206">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dce08-206">Requirements</span></span>  
 <span data-ttu-id="dce08-207">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce08-207">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce08-208">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dce08-208">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dce08-209">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dce08-209">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dce08-210">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce08-210">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce08-211">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dce08-211">See Also</span></span>  
 [<span data-ttu-id="dce08-212">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="dce08-212">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="dce08-213">IMetaDataEmit2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="dce08-213">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)