---
title: "Używanie właściwości (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aae36195f4a6eb2ab49ec27e1e07debff7289b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="using-properties-c-programming-guide"></a><span data-ttu-id="381c3-102">Używanie właściwości (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="381c3-102">Using Properties (C# Programming Guide)</span></span>
<span data-ttu-id="381c3-103">Właściwości łączyć aspekty pól i metod.</span><span class="sxs-lookup"><span data-stu-id="381c3-103">Properties combine aspects of both fields and methods.</span></span> <span data-ttu-id="381c3-104">Użytkownikowi obiektu właściwości wydaje się być polem, uzyskiwanie dostępu do właściwości wymaga takiej samej składni.</span><span class="sxs-lookup"><span data-stu-id="381c3-104">To the user of an object, a property appears to be a field, accessing the property requires the same syntax.</span></span> <span data-ttu-id="381c3-105">Realizator klasę, właściwości jest jeden lub dwa bloki kodu, reprezentujący [uzyskać](../../../csharp/language-reference/keywords/get.md) metody dostępu i/lub [ustawić](../../../csharp/language-reference/keywords/set.md) metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="381c3-105">To the implementer of a class, a property is one or two code blocks, representing a [get](../../../csharp/language-reference/keywords/get.md) accessor and/or a [set](../../../csharp/language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="381c3-106">Blok kodu dla `get` metody dostępu jest wykonywany podczas odczytywania właściwości; zablokować kod `set` metody dostępu jest wykonywane, gdy właściwość jest przypisywana nowa wartość.</span><span class="sxs-lookup"><span data-stu-id="381c3-106">The code block for the `get` accessor is executed when the property is read; the code block for the `set` accessor is executed when the property is assigned a new value.</span></span> <span data-ttu-id="381c3-107">Właściwość bez `set` metody dostępu jest traktowane jako tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="381c3-107">A property without a `set` accessor is considered read-only.</span></span> <span data-ttu-id="381c3-108">Właściwość bez `get` metody dostępu jest traktowane jako tylko do zapisu.</span><span class="sxs-lookup"><span data-stu-id="381c3-108">A property without a `get` accessor is considered write-only.</span></span> <span data-ttu-id="381c3-109">Właściwość, która ma obu metod dostępu jest do odczytu / zapisu.</span><span class="sxs-lookup"><span data-stu-id="381c3-109">A property that has both accessors is read-write.</span></span>  
  
 <span data-ttu-id="381c3-110">W przeciwieństwie do pola właściwości nie są sklasyfikowane jako zmienne.</span><span class="sxs-lookup"><span data-stu-id="381c3-110">Unlike fields, properties are not classified as variables.</span></span> <span data-ttu-id="381c3-111">W związku z tym nie można przekazać właściwości jako [ref](../../../csharp/language-reference/keywords/ref.md) lub [limit](../../../csharp/language-reference/keywords/out.md) parametru.</span><span class="sxs-lookup"><span data-stu-id="381c3-111">Therefore, you cannot pass a property as a [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameter.</span></span>  
  
 <span data-ttu-id="381c3-112">Właściwości mają wiele zastosowań: one sprawdzanie poprawności danych przed zezwoleniem na zmianę; przezroczysty mogą uwidaczniać danych dla klasy, których dane faktycznie jest pobierana z innego źródła, na przykład w bazie danych; Po zmianie danych, takich jak wywoływanie zdarzeń lub zmiana wartości innych pól potencjalnie akcji.</span><span class="sxs-lookup"><span data-stu-id="381c3-112">Properties have many uses: they can validate data before allowing a change; they can transparently expose data on a class where that data is actually retrieved from some other source, such as a database; they can take an action when data is changed, such as raising an event, or changing the value of other fields.</span></span>  
  
 <span data-ttu-id="381c3-113">Właściwości są zadeklarowane w bloku klasy, określając poziom dostępu do pola, następuje typ właściwości następuje nazwa właściwości i następuje blok kodu, który deklaruje `get`-metody dostępu i/lub `set` dostępu.</span><span class="sxs-lookup"><span data-stu-id="381c3-113">Properties are declared in the class block by specifying the access level of the field, followed by the type of the property, followed by the name of the property, and followed by a code block that declares a `get`-accessor and/or a `set` accessor.</span></span> <span data-ttu-id="381c3-114">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="381c3-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_1.cs)]  
  
 <span data-ttu-id="381c3-115">W tym przykładzie `Month` jest zadeklarowany jako właściwość tak że `set` akcesor można upewnij się, że `Month` wartość od 1 do 12.</span><span class="sxs-lookup"><span data-stu-id="381c3-115">In this example, `Month` is declared as a property so that the `set` accessor can make sure that the `Month` value is set between 1 and 12.</span></span> <span data-ttu-id="381c3-116">`Month` Właściwość używa prywatnego pola do śledzenia rzeczywistej wartości.</span><span class="sxs-lookup"><span data-stu-id="381c3-116">The `Month` property uses a private field to track the actual value.</span></span> <span data-ttu-id="381c3-117">Rzeczywista lokalizacja danych właściwości jest często określany jako wartość właściwości "magazynu zapasowego."</span><span class="sxs-lookup"><span data-stu-id="381c3-117">The real location of a property's data is often referred to as the property's "backing store."</span></span> <span data-ttu-id="381c3-118">Bardzo często właściwości do użycia jako magazynu zapasowego pól prywatnych.</span><span class="sxs-lookup"><span data-stu-id="381c3-118">It is common for properties to use private fields as a backing store.</span></span> <span data-ttu-id="381c3-119">Pole jest oznaczony jako prywatny, aby mieć pewność, że jego można zmienić tylko po wywołaniu właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-119">The field is marked private in order to make sure that it can only be changed by calling the property.</span></span> <span data-ttu-id="381c3-120">Aby uzyskać więcej informacji na temat ograniczeń dostępu publicznego i prywatnego, zobacz [modyfikatory dostępu](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-120">For more information about public and private access restrictions, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="381c3-121">Właściwości zaimplementowane automatycznie Podaj składni uproszczoną deklaracje właściwości prostej.</span><span class="sxs-lookup"><span data-stu-id="381c3-121">Auto-implemented properties provide simplified syntax for simple property declarations.</span></span> <span data-ttu-id="381c3-122">Aby uzyskać więcej informacji, zobacz [Auto-Implemented właściwości](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-122">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
## <a name="the-get-accessor"></a><span data-ttu-id="381c3-123">Metody dostępu get</span><span class="sxs-lookup"><span data-stu-id="381c3-123">The get Accessor</span></span>  
 <span data-ttu-id="381c3-124">Treść `get` akcesor podobny, które metody.</span><span class="sxs-lookup"><span data-stu-id="381c3-124">The body of the `get` accessor resembles that of a method.</span></span> <span data-ttu-id="381c3-125">Aplikacja musi zwracać wartość typu właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-125">It must return a value of the property type.</span></span> <span data-ttu-id="381c3-126">Wykonywanie `get` metody dostępu jest odpowiednikiem odczytywania wartości pola.</span><span class="sxs-lookup"><span data-stu-id="381c3-126">The execution of the `get` accessor is equivalent to reading the value of the field.</span></span> <span data-ttu-id="381c3-127">Na przykład podczas zwracania zmiennej prywatnej z `get` metody dostępu i optymalizację, które są włączone, można wywołać `get` metodę dostępu jest umieszczona w tekście przez kompilator, więc nie ma całkowitej wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="381c3-127">For example, when you are returning the private variable from the `get` accessor and optimizations are enabled, the call to the `get` accessor method is inlined by the compiler so there is no method-call overhead.</span></span> <span data-ttu-id="381c3-128">Jednak wirtualnej `get` metodę dostępu nie można wbudować elementu, ponieważ kompilator nie wie, w czasie kompilacji, która metoda faktycznie może zostać wywołana w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="381c3-128">However, a virtual `get` accessor method cannot be inlined because the compiler does not know at compile-time which method may actually be called at run time.</span></span> <span data-ttu-id="381c3-129">Poniżej przedstawiono `get` akcesor zwracającej wartość pola prywatne `name`:</span><span class="sxs-lookup"><span data-stu-id="381c3-129">The following is a `get` accessor that returns the value of a private field `name`:</span></span>  
  
 [!code-csharp[csProgGuideProperties#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_2.cs)]  
  
 <span data-ttu-id="381c3-130">Podając odniesienie właściwości, z wyjątkiem jako elementem docelowym przypisania, `get` metody dostępu jest wywoływane w celu odczytu wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-130">When you reference the property, except as the target of an assignment, the `get` accessor is invoked to read the value of the property.</span></span> <span data-ttu-id="381c3-131">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="381c3-131">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_3.cs)]  
  
 <span data-ttu-id="381c3-132">`get` Akcesora musi kończyć się [zwracać](../../../csharp/language-reference/keywords/return.md) lub [throw](../../../csharp/language-reference/keywords/throw.md) instrukcji i kontroli przepływu nie można wyłączyć treści metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="381c3-132">The `get` accessor must end in a [return](../../../csharp/language-reference/keywords/return.md) or [throw](../../../csharp/language-reference/keywords/throw.md) statement, and control cannot flow off the accessor body.</span></span>  
  
 <span data-ttu-id="381c3-133">Jest zła styl programowania zmiany stanu obiektu przy użyciu `get` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="381c3-133">It is a bad programming style to change the state of the object by using the `get` accessor.</span></span> <span data-ttu-id="381c3-134">Na przykład następujące metody dostępu tworzy ubocznym zmiany stanu obiektu za każdym razem, który `number` uzyskiwania dostępu do pola.</span><span class="sxs-lookup"><span data-stu-id="381c3-134">For example, the following accessor produces the side effect of changing the state of the object every time that the `number` field is accessed.</span></span>  
  
 [!code-csharp[csProgGuideProperties#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_4.cs)]  
  
 <span data-ttu-id="381c3-135">`get` Metody dostępu może służyć do zwrócenia wartości pola lub na potrzeby obliczania go i przywrócić go.</span><span class="sxs-lookup"><span data-stu-id="381c3-135">The `get` accessor can be used to return the field value or to compute it and return it.</span></span> <span data-ttu-id="381c3-136">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="381c3-136">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_5.cs)]  
  
 <span data-ttu-id="381c3-137">W poprzednich segment kodu, jeśli wartość nie należy przypisywać `Name` właściwości, zwróci wartość NA.</span><span class="sxs-lookup"><span data-stu-id="381c3-137">In the previous code segment, if you do not assign a value to the `Name` property, it will return the value NA.</span></span>  
  
## <a name="the-set-accessor"></a><span data-ttu-id="381c3-138">Zestaw metody dostępu</span><span class="sxs-lookup"><span data-stu-id="381c3-138">The set Accessor</span></span>  
 <span data-ttu-id="381c3-139">`set` Akcesor podobny metody, których typem zwracanym jest [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-139">The `set` accessor resembles a method whose return type is [void](../../../csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="381c3-140">Niejawny parametr o nazwie `value`, którego typem jest typ właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-140">It uses an implicit parameter called `value`, whose type is the type of the property.</span></span> <span data-ttu-id="381c3-141">W poniższym przykładzie `set` metody dostępu jest dodawany do `Name` właściwości:</span><span class="sxs-lookup"><span data-stu-id="381c3-141">In the following example, a `set` accessor is added to the `Name` property:</span></span>  
  
 [!code-csharp[csProgGuideProperties#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_6.cs)]  
  
 <span data-ttu-id="381c3-142">Podczas przypisywania wartości do właściwości, `set` metody dostępu jest wywoływana przy użyciu argumentu, który udostępnia nową wartość.</span><span class="sxs-lookup"><span data-stu-id="381c3-142">When you assign a value to the property, the `set` accessor is invoked by using an argument that provides the new value.</span></span> <span data-ttu-id="381c3-143">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="381c3-143">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_7.cs)]  
  
 <span data-ttu-id="381c3-144">Błąd do używania nazwy parametru niejawne `value`, dla deklaracji zmiennej lokalnej w `set` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="381c3-144">It is an error to use the implicit parameter name, `value`, for a local variable declaration in a `set` accessor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="381c3-145">Uwagi</span><span class="sxs-lookup"><span data-stu-id="381c3-145">Remarks</span></span>  
 <span data-ttu-id="381c3-146">Właściwości może być oznaczony jako `public`, `private`, `protected`, `internal`, `protected internal` lub `private protected`.</span><span class="sxs-lookup"><span data-stu-id="381c3-146">Properties can be marked as `public`, `private`, `protected`, `internal`, `protected internal` or `private protected`.</span></span> <span data-ttu-id="381c3-147">Te modyfikatorów dostępu zdefiniuj, jak użytkownicy klasy mogą uzyskiwać dostęp do właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-147">These access modifiers define how users of the class can access the property.</span></span> <span data-ttu-id="381c3-148">`get` i `set` metody dostępu dla tej właściwości może mieć modyfikatorów dostępu do innego.</span><span class="sxs-lookup"><span data-stu-id="381c3-148">The `get` and `set` accessors for the same property may have different access modifiers.</span></span> <span data-ttu-id="381c3-149">Na przykład `get` może być `public` się zezwolić na dostęp tylko do odczytu z zewnątrz typu i `set` może być `private` lub `protected`.</span><span class="sxs-lookup"><span data-stu-id="381c3-149">For example, the `get` may be `public` to allow read-only access from outside the type, and the `set` may be `private` or `protected`.</span></span> <span data-ttu-id="381c3-150">Aby uzyskać więcej informacji, zobacz [modyfikatory dostępu](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-150">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="381c3-151">Można zadeklarować właściwości jako właściwość statyczna przy użyciu `static` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="381c3-151">A property may be declared as a static property by using the `static` keyword.</span></span> <span data-ttu-id="381c3-152">To udostępnienie właściwości wywołań w dowolnym momencie, nawet jeśli nie ma wystąpień klasy.</span><span class="sxs-lookup"><span data-stu-id="381c3-152">This makes the property available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="381c3-153">Aby uzyskać więcej informacji, zobacz [klasy statyczne i statycznych elementów członkowskich klasy](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-153">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="381c3-154">Właściwość może być oznaczony jako właściwość wirtualnego przy użyciu [wirtualnego](../../../csharp/language-reference/keywords/virtual.md) — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="381c3-154">A property may be marked as a virtual property by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="381c3-155">Dzięki temu klasy pochodne zastąpić zachowanie właściwości przy użyciu [zastąpienia](../../../csharp/language-reference/keywords/override.md) — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="381c3-155">This enables derived classes to override the property behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="381c3-156">Aby uzyskać więcej informacji o tych opcjach, zobacz [dziedziczenia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-156">For more information about these options, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="381c3-157">Można także właściwością zastępowania wirtualnego właściwości [zapieczętowanego](../../../csharp/language-reference/keywords/sealed.md), określania, czy dla klas pochodnych nie jest już wirtualny.</span><span class="sxs-lookup"><span data-stu-id="381c3-157">A property overriding a virtual property can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), specifying that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="381c3-158">Ponadto można zadeklarować jako właściwości [abstrakcyjny](../../../csharp/language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-158">Lastly, a property can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="381c3-159">Oznacza to, że nie żadnej implementacji klasy, i klasy pochodne napisać własne implementacji.</span><span class="sxs-lookup"><span data-stu-id="381c3-159">This means that there is no implementation in the class, and derived classes must write their own implementation.</span></span> <span data-ttu-id="381c3-160">Aby uzyskać więcej informacji o tych opcjach, zobacz [abstrakcyjne i zapieczętowane klasy oraz członkowie klas](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-160">For more information about these options, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="381c3-161">Jest błędem [wirtualnego](../../../csharp/language-reference/keywords/virtual.md), [abstrakcyjny](../../../csharp/language-reference/keywords/abstract.md), lub [zastąpienia](../../../csharp/language-reference/keywords/override.md) modyfikator na akcesor [statycznych](../../../csharp/language-reference/keywords/static.md) właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-161">It is an error to use a [virtual](../../../csharp/language-reference/keywords/virtual.md), [abstract](../../../csharp/language-reference/keywords/abstract.md), or [override](../../../csharp/language-reference/keywords/override.md) modifier on an accessor of a [static](../../../csharp/language-reference/keywords/static.md) property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="381c3-162">Przykład</span><span class="sxs-lookup"><span data-stu-id="381c3-162">Example</span></span>  
 <span data-ttu-id="381c3-163">W przykładzie pokazano właściwości wystąpienia, statyczne i tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="381c3-163">This example demonstrates instance, static, and read-only properties.</span></span> <span data-ttu-id="381c3-164">Przyjmuje nazwę pracowników z klawiatury, zwiększa `NumberOfEmployees` 1 i wyświetla pracownik Określanie nazwy i numer.</span><span class="sxs-lookup"><span data-stu-id="381c3-164">It accepts the name of the employee from the keyboard, increments `NumberOfEmployees` by 1, and displays the Employee name and number.</span></span>  
  
 [!code-csharp[csProgGuideProperties#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_8.cs)]  
  
## <a name="example"></a><span data-ttu-id="381c3-165">Przykład</span><span class="sxs-lookup"><span data-stu-id="381c3-165">Example</span></span>  
 <span data-ttu-id="381c3-166">W tym przykładzie przedstawiono sposób dostępu do właściwości w klasie podstawowej, który jest ukryty przez inną właściwość, która ma taką samą nazwę w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="381c3-166">This example demonstrates how to access a property in a base class that is hidden by another property that has the same name in a derived class.</span></span>  
  
 [!code-csharp[csProgGuideProperties#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_9.cs)]  
  
 <span data-ttu-id="381c3-167">Poniżej przedstawiono ważne punktów w poprzednim przykładzie:</span><span class="sxs-lookup"><span data-stu-id="381c3-167">The following are important points in the previous example:</span></span>  
  
-   <span data-ttu-id="381c3-168">Właściwość `Name` w klasie pochodnej ukrywa właściwość `Name` w klasie podstawowej.</span><span class="sxs-lookup"><span data-stu-id="381c3-168">The property `Name` in the derived class hides the property `Name` in the base class.</span></span> <span data-ttu-id="381c3-169">W takim przypadku `new` modyfikator jest używany w deklaracji właściwości w klasie pochodnej:</span><span class="sxs-lookup"><span data-stu-id="381c3-169">In such a case, the `new` modifier is used in the declaration of the property in the derived class:</span></span>  
  
     [!code-csharp[csProgGuideProperties#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_10.cs)]  
  
-   <span data-ttu-id="381c3-170">Rzutowanie `(Employee)` służy do dostępu do ukrytych właściwości w klasie podstawowej:</span><span class="sxs-lookup"><span data-stu-id="381c3-170">The cast `(Employee)` is used to access the hidden property in the base class:</span></span>  
  
     [!code-csharp[csProgGuideProperties#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_11.cs)]  
  
     <span data-ttu-id="381c3-171">Aby uzyskać więcej informacji na składniki ukrywanie informacje, zobacz [new — modyfikator](../../../csharp/language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="381c3-171">For more information about hiding members, see the [new Modifier](../../../csharp/language-reference/keywords/new-modifier.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="381c3-172">Przykład</span><span class="sxs-lookup"><span data-stu-id="381c3-172">Example</span></span>  
 <span data-ttu-id="381c3-173">W tym przykładzie dwie klasy `Cube` i `Square`, zaimplementować klasę abstrakcyjną `Shape`i zastąp jego abstrakcyjny `Area` właściwości.</span><span class="sxs-lookup"><span data-stu-id="381c3-173">In this example, two classes, `Cube` and `Square`, implement an abstract class, `Shape`, and override its abstract `Area` property.</span></span> <span data-ttu-id="381c3-174">Zwróć uwagę na użycie [zastąpienia](../../../csharp/language-reference/keywords/override.md) modyfikator we właściwościach.</span><span class="sxs-lookup"><span data-stu-id="381c3-174">Note the use of the [override](../../../csharp/language-reference/keywords/override.md) modifier on the properties.</span></span> <span data-ttu-id="381c3-175">Program akceptuje po stronie jako dane wejściowe i oblicza obszarów kwadratowych i modułu.</span><span class="sxs-lookup"><span data-stu-id="381c3-175">The program accepts the side as an input and calculates the areas for the square and cube.</span></span> <span data-ttu-id="381c3-176">Również akceptuje obszaru jako dane wejściowe i oblicza odpowiednie po stronie kwadratowych i modułu.</span><span class="sxs-lookup"><span data-stu-id="381c3-176">It also accepts the area as an input and calculates the corresponding side for the square and cube.</span></span>  
  
 [!code-csharp[csProgGuideProperties#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_12.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="381c3-177">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="381c3-177">See Also</span></span>  
 [<span data-ttu-id="381c3-178">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="381c3-178">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="381c3-179">Właściwości</span><span class="sxs-lookup"><span data-stu-id="381c3-179">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="381c3-180">Właściwości interfejsu</span><span class="sxs-lookup"><span data-stu-id="381c3-180">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
 [<span data-ttu-id="381c3-181">Właściwości zaimplementowane automatycznie</span><span class="sxs-lookup"><span data-stu-id="381c3-181">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)