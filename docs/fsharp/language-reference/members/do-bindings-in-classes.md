---
title: "do — Powiązania w klasach (F#)"
description: "Dowiedz się, jak używać F # \"do\" powiązanie w definicji klasy, która wykonuje akcje podczas konstruowania obiektu lub przy pierwszym użyciu typu."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="49a9c-104">do — Powiązania w klasach</span><span class="sxs-lookup"><span data-stu-id="49a9c-104">do Bindings in Classes</span></span>

<span data-ttu-id="49a9c-105">A `do` powiązanie w definicji klasy wykonuje akcje podczas konstruowania obiektu lub, w przypadku statycznego `do` powiązanie, gdy typ jest najpierw używany.</span><span class="sxs-lookup"><span data-stu-id="49a9c-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="49a9c-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="49a9c-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="49a9c-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="49a9c-107">Remarks</span></span>
<span data-ttu-id="49a9c-108">A `do` powiązania pojawi się wraz z lub po `let` powiązania, ale przed definicji elementu członkowskiego w definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="49a9c-109">Mimo że `do` — słowo kluczowe jest opcjonalne dla `do` powiązania na poziomie modułu nie jest opcjonalny w przypadku `do` powiązania w definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="49a9c-110">Do tworzenia każdy obiekt dowolnego danego typu, niestatyczna `do` powiązania i niestatyczna `let` powiązania są wykonywane w kolejności, w jakiej występują w definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="49a9c-111">Wiele `do` powiązania może wystąpić w jednym typie.</span><span class="sxs-lookup"><span data-stu-id="49a9c-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="49a9c-112">Niestatyczna `let` powiązania i niestatyczna `do` powiązania stają się treści podstawowego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="49a9c-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="49a9c-113">Kod w niestatycznym `do` sekcji powiązania może odwoływać się parametrami konstruktora podstawowego oraz wartości lub funkcje, które są zdefiniowane w `let` sekcji powiązania.</span><span class="sxs-lookup"><span data-stu-id="49a9c-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="49a9c-114">Niestatyczne `do` powiązania mogą uzyskiwać dostęp do elementów członkowskich klasy, tak długo, jak klasa ma własnego identyfikatora, który jest zdefiniowany przez `as` — słowo kluczowe w klasie, nagłówek i tak długo, jak wszystkie używa tych członków jest kwalifikowany za pomocą własnego identyfikatora klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="49a9c-115">Ponieważ `let` powiązania zainicjować pól prywatnych klasy, która jest często zagwarantowanie, że członkowie działać zgodnie z oczekiwaniami, `do` powiązania są zwykle umieszczane po `let` powiązania, który kod w `do` może powiązania wykonywane za pomocą obiektu pełni zainicjowany.</span><span class="sxs-lookup"><span data-stu-id="49a9c-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="49a9c-116">Jeśli kod spróbuje przed zakończeniem inicjowania, należy użyć członka, InvalidOperationException jest wywoływane.</span><span class="sxs-lookup"><span data-stu-id="49a9c-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="49a9c-117">Statyczne `do` powiązania może odwoływać się elementy członkowskie static lub pola otaczającej klasy, ale nie wystąpienia elementów członkowskich lub pól.</span><span class="sxs-lookup"><span data-stu-id="49a9c-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="49a9c-118">Statyczne `do` powiązania staną się częścią inicjator statyczny dla klasy, która może wykonać przed pierwszym użyciu tej klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="49a9c-119">Atrybuty są ignorowane w przypadku `do` powiązania w typach.</span><span class="sxs-lookup"><span data-stu-id="49a9c-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="49a9c-120">Jeśli atrybut jest wymagany dla kodu, który wykonuje `do` powiązanie, jego musi odnosić się do podstawowego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="49a9c-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="49a9c-121">W poniższym kodzie klasa ma statycznych `do` powiązania i niestatyczną `do` powiązania.</span><span class="sxs-lookup"><span data-stu-id="49a9c-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="49a9c-122">Obiekt ma konstruktora, który zawiera dwa parametry `a` i `b`, i dwa pola prywatne są zdefiniowane w `let` powiązania dla tej klasy.</span><span class="sxs-lookup"><span data-stu-id="49a9c-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="49a9c-123">Również zdefiniowano dwie właściwości.</span><span class="sxs-lookup"><span data-stu-id="49a9c-123">Two properties are also defined.</span></span> <span data-ttu-id="49a9c-124">Wszystkie te są w zakresie niestatyczna `do` sekcji powiązania, jak to pokazano wiersza, który wyświetla wszystkie te wartości.</span><span class="sxs-lookup"><span data-stu-id="49a9c-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="49a9c-125">Dane wyjściowe są następujące:</span><span class="sxs-lookup"><span data-stu-id="49a9c-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="49a9c-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49a9c-126">See Also</span></span>
[<span data-ttu-id="49a9c-127">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="49a9c-127">Members</span></span>](index.md)

[<span data-ttu-id="49a9c-128">Klasy</span><span class="sxs-lookup"><span data-stu-id="49a9c-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="49a9c-129">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="49a9c-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="49a9c-130">`let`Powiązania w klasach</span><span class="sxs-lookup"><span data-stu-id="49a9c-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="49a9c-131">`do`Powiązania</span><span class="sxs-lookup"><span data-stu-id="49a9c-131">`do` Bindings</span></span>](../functions/do-Bindings.md)