---
title: Typy kopiowalne i niekopiowalne
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b05d77df28b560b9236e467a914229c0fa9ae7e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="461bf-102">Typy kopiowalne i niekopiowalne</span><span class="sxs-lookup"><span data-stu-id="461bf-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="461bf-103">Większość typów danych ma reprezentacji w postaci typowych w pamięci zarządzane i niezarządzane i nie wymagają specjalnej obsługi przez organizatora międzyoperacyjnego.</span><span class="sxs-lookup"><span data-stu-id="461bf-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="461bf-104">Te typy są nazywane *typy kopiowalne* ponieważ one nie wymagają konwersji, gdy są one przekazywane między zarządzanych i niezarządzanych kodu.</span><span class="sxs-lookup"><span data-stu-id="461bf-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="461bf-105">Struktury, które są zwracane z platformy wywołania wywołania musi być typy kopiowalne.</span><span class="sxs-lookup"><span data-stu-id="461bf-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="461bf-106">Wywołanie platformy nie obsługuje niekopiowalnej struktury jako typów zwracanych.</span><span class="sxs-lookup"><span data-stu-id="461bf-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="461bf-107">Następujące typy z <xref:System> przestrzeni nazw są typy danych kopiowalnych:</span><span class="sxs-lookup"><span data-stu-id="461bf-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="461bf-108">Typy kopiowalne są również następujące typy złożone:</span><span class="sxs-lookup"><span data-stu-id="461bf-108">The following complex types are also blittable types:</span></span>  
  
-   <span data-ttu-id="461bf-109">Tablice jednowymiarowe typy danych kopiowalnych, takich jak tablica liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="461bf-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="461bf-110">Typ zawierający tablicę zmiennych typów danych kopiowalnych nie jest jednak sam danych kopiowalnych.</span><span class="sxs-lookup"><span data-stu-id="461bf-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
-   <span data-ttu-id="461bf-111">Sformatowana wartość typy, które zawierają typy kopiowalne tylko (i klasy, jeśli są one organizowane jako typy sformatowany).</span><span class="sxs-lookup"><span data-stu-id="461bf-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="461bf-112">Aby uzyskać więcej informacji na temat typów sformatowana wartość zobacz [domyślny Marshaling dla typów wartości](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a).</span><span class="sxs-lookup"><span data-stu-id="461bf-112">For more information about formatted value types, see [Default Marshaling for Value Types](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a).</span></span>  
  
 <span data-ttu-id="461bf-113">Odwołania do obiektów nie są danych kopiowalnych.</span><span class="sxs-lookup"><span data-stu-id="461bf-113">Object references are not blittable.</span></span> <span data-ttu-id="461bf-114">W tym tablicę odwołania do obiektów, które są kopiowalne samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="461bf-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="461bf-115">Na przykład można zdefiniować struktury, która jest możliwość kopiowania, ale nie można zdefiniować typu danych kopiowalnych, który zawiera tablicę odwołania do tych konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="461bf-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="461bf-116">Do optymalizacji są tablice typy kopiowalne i klasy, które zawierają tylko elementy członkowskie danych kopiowalnych [przypięty](../../../docs/framework/interop/copying-and-pinning.md) zamiast skopiowanych podczas przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="461bf-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](../../../docs/framework/interop/copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="461bf-117">Te typy może wydawać można zorganizować jako we/wy parametrów, gdy obiekt wywołujący i wywoływany znajdują się w tym samym apartamencie.</span><span class="sxs-lookup"><span data-stu-id="461bf-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="461bf-118">Jednak te typy są faktycznie przekazywane tak jak parametry i należy zastosować <xref:System.Runtime.InteropServices.InAttribute> i <xref:System.Runtime.InteropServices.OutAttribute> atrybutów, aby kierować argument jako In/Out parametru.</span><span class="sxs-lookup"><span data-stu-id="461bf-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="461bf-119">Niektóre typy zarządzanych danych wymagają różnych reprezentacji w środowisku niezarządzane.</span><span class="sxs-lookup"><span data-stu-id="461bf-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="461bf-120">Te typy danych niekopiowalnych należy przekonwertować do formularza, które mogą być przekazywane.</span><span class="sxs-lookup"><span data-stu-id="461bf-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="461bf-121">Na przykład ciągi zarządzane są niekopiowalne, ponieważ muszą zostać przekonwertowane na obiektów string, zanim one mogą być przekazywane.</span><span class="sxs-lookup"><span data-stu-id="461bf-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="461bf-122">W poniższej tabeli wymieniono niekopiowalne z <xref:System> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="461bf-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="461bf-123">[Obiekty delegowane](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2), struktury danych, które odwołują się do metody statycznej lub do wystąpienia klasy, które są również są niekopiowalne.</span><span class="sxs-lookup"><span data-stu-id="461bf-123">[Delegates](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="461bf-124">Typ danych kopiowalnych inne niż</span><span class="sxs-lookup"><span data-stu-id="461bf-124">Non-blittable type</span></span>|<span data-ttu-id="461bf-125">Opis</span><span class="sxs-lookup"><span data-stu-id="461bf-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="461bf-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="461bf-126">System.Array</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="461bf-127">Konwertuje tablicę stylu języka C lub `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="461bf-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="461bf-128">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="461bf-128">System.Boolean</span></span>](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|<span data-ttu-id="461bf-129">Konwertuje wartość 1, 2 lub 4-bajtowych wartości z `true` jako 1 lub -1.</span><span class="sxs-lookup"><span data-stu-id="461bf-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|[<span data-ttu-id="461bf-130">System.Char</span><span class="sxs-lookup"><span data-stu-id="461bf-130">System.Char</span></span>](http://msdn.microsoft.com/en-us/cecc87c1-075e-4cde-aa56-33d189f66feb)|<span data-ttu-id="461bf-131">Konwertuje znak Unicode lub ANSI.</span><span class="sxs-lookup"><span data-stu-id="461bf-131">Converts to a Unicode or ANSI character.</span></span>|  
|[<span data-ttu-id="461bf-132">System.Class</span><span class="sxs-lookup"><span data-stu-id="461bf-132">System.Class</span></span>](http://msdn.microsoft.com/en-us/fe334af5-0123-43d8-be84-26f6f023ddb6)|<span data-ttu-id="461bf-133">Konwertuje interfejsu klasy.</span><span class="sxs-lookup"><span data-stu-id="461bf-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="461bf-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="461bf-134">System.Object</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)|<span data-ttu-id="461bf-135">Konwertuje wariant lub interfejs.</span><span class="sxs-lookup"><span data-stu-id="461bf-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="461bf-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="461bf-136">System.Mdarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="461bf-137">Konwertuje tablicę stylu języka C lub `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="461bf-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="461bf-138">System.String</span><span class="sxs-lookup"><span data-stu-id="461bf-138">System.String</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)|<span data-ttu-id="461bf-139">Konwertuje ciąg przerywanie w odwołanie o wartości null lub BSTR.</span><span class="sxs-lookup"><span data-stu-id="461bf-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|[<span data-ttu-id="461bf-140">Element System.Valuetype</span><span class="sxs-lookup"><span data-stu-id="461bf-140">System.Valuetype</span></span>](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a)|<span data-ttu-id="461bf-141">Konwertuje struktury z układem stałym pamięci.</span><span class="sxs-lookup"><span data-stu-id="461bf-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="461bf-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="461bf-142">System.Szarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="461bf-143">Konwertuje tablicę stylu języka C lub `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="461bf-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="461bf-144">Typy klas i obiektów są obsługiwane tylko przez COM interop.</span><span class="sxs-lookup"><span data-stu-id="461bf-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="461bf-145">Dla odpowiednich typów w [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# i C++, zobacz [Przegląd biblioteki klas](../../../docs/standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="461bf-145">For corresponding types in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++, see the [Class Library Overview](../../../docs/standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461bf-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="461bf-146">See Also</span></span>  
 [<span data-ttu-id="461bf-147">Domyślne zachowanie Marshalingu</span><span class="sxs-lookup"><span data-stu-id="461bf-147">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)