---
title: "override (odwołanie w C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords: override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 807fae02ca4e6f616c77877cc8815405baaf8428
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="override-c-reference"></a><span data-ttu-id="67a8b-102">override (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="67a8b-102">override (C# Reference)</span></span>
<span data-ttu-id="67a8b-103">`override` Modyfikator jest wymagana, aby rozszerzyć lub zmodyfikować abstrakcyjna lub wirtualna wykonania dziedziczonej metody, właściwość, indeksator lub zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="67a8b-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a8b-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="67a8b-104">Example</span></span>  
 <span data-ttu-id="67a8b-105">W tym przykładzie `Square` klasy musi zapewniać implementację przesłoniętych z `Area` ponieważ `Area` jest dziedziczona z klasy abstrakcyjnej `ShapesClass`:</span><span class="sxs-lookup"><span data-stu-id="67a8b-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 <span data-ttu-id="67a8b-106">`override` Metoda zawiera nową implementacją elementu członkowskiego, który jest dziedziczona z klasy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="67a8b-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="67a8b-107">Metoda, która zostanie zastąpiona przez `override` deklaracji nosi nazwę przesłoniętej metody podstawowej.</span><span class="sxs-lookup"><span data-stu-id="67a8b-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="67a8b-108">Przesłoniętej metody podstawowej musi mieć taką samą sygnaturę jak `override` metody.</span><span class="sxs-lookup"><span data-stu-id="67a8b-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="67a8b-109">Informacje o dziedziczeniu znajdują się w temacie [dziedziczenia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="67a8b-109">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="67a8b-110">Nie można zastąpić metodę niewirtualną lub statycznej.</span><span class="sxs-lookup"><span data-stu-id="67a8b-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="67a8b-111">Musi być przesłoniętej metody podstawowej `virtual`, `abstract`, lub `override`.</span><span class="sxs-lookup"><span data-stu-id="67a8b-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="67a8b-112">`override` Deklaracji nie można zmienić dostępności `virtual` metody.</span><span class="sxs-lookup"><span data-stu-id="67a8b-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="67a8b-113">Zarówno `override` — metoda i `virtual` metody muszą mieć ten sam [poziomu modyfikator dostępu](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="67a8b-113">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="67a8b-114">Nie można użyć `new`, `static`, lub `virtual` Modyfikatory do modyfikowania `override` metody.</span><span class="sxs-lookup"><span data-stu-id="67a8b-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="67a8b-115">Zastępowanie deklaracja właściwości należy określić dokładnie tego samego modyfikator dostępu, typ i nazwa jako właściwość dziedziczona i przesłanianej właściwości musi być `virtual`, `abstract`, lub `override`.</span><span class="sxs-lookup"><span data-stu-id="67a8b-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="67a8b-116">Aby uzyskać więcej informacji o sposobie używania `override` — słowo kluczowe, zobacz [przechowywanie wersji przesłonięć i nowych słów kluczowych](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [użycie zastępowania i nowych słów kluczowych](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="67a8b-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a8b-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="67a8b-117">Example</span></span>  
 <span data-ttu-id="67a8b-118">W tym przykładzie definiuje klasę podstawową o nazwie `Employee`, a klasa pochodna o nazwie `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="67a8b-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="67a8b-119">`SalesEmployee` Klasa zawiera dodatkowe właściwości `salesbonus`i zastępuje metodę `CalculatePay` w celu uwzględnienia konta.</span><span class="sxs-lookup"><span data-stu-id="67a8b-119">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="67a8b-120">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="67a8b-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67a8b-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="67a8b-121">See Also</span></span>  
 [<span data-ttu-id="67a8b-122">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="67a8b-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="67a8b-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="67a8b-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="67a8b-124">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="67a8b-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="67a8b-125">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="67a8b-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="67a8b-126">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="67a8b-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="67a8b-127">abstrakcyjny</span><span class="sxs-lookup"><span data-stu-id="67a8b-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="67a8b-128">wirtualny</span><span class="sxs-lookup"><span data-stu-id="67a8b-128">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="67a8b-129">Nowy</span><span class="sxs-lookup"><span data-stu-id="67a8b-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="67a8b-130">Polimorfizm</span><span class="sxs-lookup"><span data-stu-id="67a8b-130">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)