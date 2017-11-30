---
title: Funkcje (F#)
description: "Poznaj funkcje F # oraz jak F # obsługuje typowych narzędzi programistycznych funkcjonalności."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6dea2c3e-2f9d-4c9d-97a2-d8f9a72b6f4c
ms.openlocfilehash: 9750e37647a3e382c7a8308c3ffede15729012d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="functions"></a><span data-ttu-id="49ec4-104">Funkcje</span><span class="sxs-lookup"><span data-stu-id="49ec4-104">Functions</span></span>

<span data-ttu-id="49ec4-105">Funkcje są podstawową jednostkę wykonywania programu w dowolnym języku programowania.</span><span class="sxs-lookup"><span data-stu-id="49ec4-105">Functions are the fundamental unit of program execution in any programming language.</span></span> <span data-ttu-id="49ec4-106">Jak w innych językach funkcja F # o nazwie, może mieć parametry i argumenty podjęcia i ma treść.</span><span class="sxs-lookup"><span data-stu-id="49ec4-106">As in other languages, an F# function has a name, can have parameters and take arguments, and has a body.</span></span> <span data-ttu-id="49ec4-107">F # obsługuje również funkcjonalności narzędzi programistycznych, takich jak traktowanie funkcje jako wartości, przy użyciu funkcji bez nazwy w wyrażeniach kompozycja funkcji do utworzenia nowych funkcji, funkcje rozwinięte i niejawnego definiowania funkcji i częściowe Stosowanie argumentów funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-107">F# also supports functional programming constructs such as treating functions as values, using unnamed functions in expressions, composition of functions to form new functions, curried functions, and the implicit definition of functions by way of the partial application of function arguments.</span></span>

<span data-ttu-id="49ec4-108">Należy zdefiniować przy użyciu funkcji `let` — słowo kluczowe, lub, jeśli funkcja jest rekursywny, `let rec` kombinacja słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="49ec4-108">You define functions by using the `let` keyword, or, if the function is recursive, the `let rec` keyword combination.</span></span>


## <a name="syntax"></a><span data-ttu-id="49ec4-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="49ec4-109">Syntax</span></span>

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a><span data-ttu-id="49ec4-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="49ec4-110">Remarks</span></span>
<span data-ttu-id="49ec4-111">*Nazwy funkcji* jest identyfikatorem, który reprezentuje funkcję.</span><span class="sxs-lookup"><span data-stu-id="49ec4-111">The *function-name* is an identifier that represents the function.</span></span> <span data-ttu-id="49ec4-112">*Listy parametrów* składa się z kolejnymi parametrów, które są rozdzielone spacjami.</span><span class="sxs-lookup"><span data-stu-id="49ec4-112">The *parameter-list* consists of successive parameters that are separated by spaces.</span></span> <span data-ttu-id="49ec4-113">Zgodnie z opisem w sekcji Parametry można określić jawnego typu dla każdego parametru.</span><span class="sxs-lookup"><span data-stu-id="49ec4-113">You can specify an explicit type for each parameter, as described in the Parameters section.</span></span> <span data-ttu-id="49ec4-114">Jeśli nie określisz typu określonego argumentu, kompilator próbuje wnioskować o typie z treści funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-114">If you do not specify a specific argument type, the compiler attempts to infer the type from the function body.</span></span> <span data-ttu-id="49ec4-115">*Treści funkcji* składa się z wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="49ec4-115">The *function-body* consists of an expression.</span></span> <span data-ttu-id="49ec4-116">Wyrażenie, które tworzą treść funkcji jest zwykle wyrażenia złożone składający się z liczby wyrażeń, które kulminacyjny w wyrażeniu końcowym, która jest zwracana wartość.</span><span class="sxs-lookup"><span data-stu-id="49ec4-116">The expression that makes up the function body is typically a compound expression consisting of a number of expressions that culminate in a final expression that is the return value.</span></span> <span data-ttu-id="49ec4-117">*Zwracanego typu* dwukropek następuje typ i jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="49ec4-117">The *return-type* is a colon followed by a type and is optional.</span></span> <span data-ttu-id="49ec4-118">Jeśli nie zostanie jawnie typ zwracanej wartości, kompilator Określa typ zwracany z ostatniego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="49ec4-118">If you do not specify the type of the return value explicitly, the compiler determines the return type from the final expression.</span></span>

<span data-ttu-id="49ec4-119">Definicja funkcji prostego podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="49ec4-119">A simple function definition resembles the following:</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="49ec4-120">W poprzednim przykładzie nazwa funkcji jest `f`, argument jest `x`, który ma typ `int`, treść funkcji jest `x + 1`, i jest zwracana wartość typu `int`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-120">In the previous example, the function name is `f`, the argument is `x`, which has type `int`, the function body is `x + 1`, and the return value is of type `int`.</span></span>

<span data-ttu-id="49ec4-121">Funkcje mogą być oznaczane `inline`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-121">Functions can be marked `inline`.</span></span> <span data-ttu-id="49ec4-122">Aby uzyskać informacje o `inline`, zobacz [funkcji śródwierszowych](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="49ec4-122">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>


## <a name="scope"></a><span data-ttu-id="49ec4-123">Zakres</span><span class="sxs-lookup"><span data-stu-id="49ec4-123">Scope</span></span>
<span data-ttu-id="49ec4-124">Na dowolnym poziomie zakresu innego niż zakres modułu nie jest błąd, aby ponownie użyć nazwy wartości lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-124">At any level of scope other than module scope, it is not an error to reuse a value or function name.</span></span> <span data-ttu-id="49ec4-125">Ponowne użycie nazwy, nazwa zadeklarowana później zasłania nazwa zadeklarowana wcześniej.</span><span class="sxs-lookup"><span data-stu-id="49ec4-125">If you reuse a name, the name declared later shadows the name declared earlier.</span></span> <span data-ttu-id="49ec4-126">Jednak w zakresie najwyższego poziomu w module, nazwy muszą być unikatowe.</span><span class="sxs-lookup"><span data-stu-id="49ec4-126">However, at the top level scope in a module, names must be unique.</span></span> <span data-ttu-id="49ec4-127">Na przykład poniższy kod tworzy błąd, gdy znajduje się na zakres modułu, a nie wydaje się wewnątrz funkcji:</span><span class="sxs-lookup"><span data-stu-id="49ec4-127">For example, the following code produces an error when it appears at module scope, but not when it appears inside a function:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

<span data-ttu-id="49ec4-128">Ale następujący kod na dowolnym poziomie zakresu:</span><span class="sxs-lookup"><span data-stu-id="49ec4-128">But the following code is acceptable at any level of scope:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet102.fs)]
    
#### <a name="parameters"></a><span data-ttu-id="49ec4-129">Parametry</span><span class="sxs-lookup"><span data-stu-id="49ec4-129">Parameters</span></span>
<span data-ttu-id="49ec4-130">Nazwy parametrów są wyświetlane po nazwie funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-130">Names of parameters are listed after the function name.</span></span> <span data-ttu-id="49ec4-131">Typ parametru, można określić, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="49ec4-131">You can specify a type for a parameter, as shown in the following example:</span></span>

```fsharp
let f (x : int) = x + 1
```

<span data-ttu-id="49ec4-132">Jeśli określisz typu następuje nazwa parametru, a jest oddzielona od nazwy dwukropkiem.</span><span class="sxs-lookup"><span data-stu-id="49ec4-132">If you specify a type, it follows the name of the parameter and is separated from the name by a colon.</span></span> <span data-ttu-id="49ec4-133">W przypadku pominięcia typ parametru, typ parametru jest wykryta przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="49ec4-133">If you omit the type for the parameter, the parameter type is inferred by the compiler.</span></span> <span data-ttu-id="49ec4-134">Na przykład w definicji funkcji następujący argument `x` jest wartością typu `int` ponieważ 1 jest typu `int`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-134">For example, in the following function definition, the argument `x` is inferred to be of type `int` because 1 is of type `int`.</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="49ec4-135">Jednak kompilator nawiązania funkcji co.</span><span class="sxs-lookup"><span data-stu-id="49ec4-135">However, the compiler will attempt to make the function as generic as possible.</span></span> <span data-ttu-id="49ec4-136">Na przykład należy uwzględnić następujący kod:</span><span class="sxs-lookup"><span data-stu-id="49ec4-136">For example, note the following code:</span></span>

```fsharp
let f x = (x, x)
```

<span data-ttu-id="49ec4-137">Funkcja tworzy spójną kolekcję z jednym argumentem dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="49ec4-137">The function creates a tuple from one argument of any type.</span></span> <span data-ttu-id="49ec4-138">Ponieważ typ nie jest określony, można użyć funkcji, w przypadku każdego typu argumentu.</span><span class="sxs-lookup"><span data-stu-id="49ec4-138">Because the type is not specified, the function can be used with any argument type.</span></span> <span data-ttu-id="49ec4-139">Aby uzyskać więcej informacji, zobacz [automatyczna Generalizacja](../generics/automatic-generalization.md).</span><span class="sxs-lookup"><span data-stu-id="49ec4-139">For more information, see [Automatic Generalization](../generics/automatic-generalization.md).</span></span>


## <a name="function-bodies"></a><span data-ttu-id="49ec4-140">Funkcja fragmentów</span><span class="sxs-lookup"><span data-stu-id="49ec4-140">Function Bodies</span></span>
<span data-ttu-id="49ec4-141">Treść funkcji może zawierać definicje zmiennych lokalnych i funkcje.</span><span class="sxs-lookup"><span data-stu-id="49ec4-141">A function body can contain definitions of local variables and functions.</span></span> <span data-ttu-id="49ec4-142">Tych zmiennych i funkcji znajdują się w zakresie w treści bieżącej funkcji, ale nie poza nią.</span><span class="sxs-lookup"><span data-stu-id="49ec4-142">Such variables and functions are in scope in the body of the current function but not outside it.</span></span> <span data-ttu-id="49ec4-143">Jeśli opcja lightweight — składnia włączone, należy użyć wcięcie do wskazywania definicję w treści funkcji, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="49ec4-143">When you have the lightweight syntax option enabled, you must use indentation to indicate that a definition is in a function body, as shown in the following example:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

<span data-ttu-id="49ec4-144">Aby uzyskać więcej informacji, zobacz [wytyczne formatowania kodu](../code-formatting-guidelines.md) i [Pełna składnia](../verbose-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="49ec4-144">For more information, see [Code Formatting Guidelines](../code-formatting-guidelines.md) and [Verbose Syntax](../verbose-syntax.md).</span></span>


## <a name="return-values"></a><span data-ttu-id="49ec4-145">Wartości zwrócone</span><span class="sxs-lookup"><span data-stu-id="49ec4-145">Return Values</span></span>
<span data-ttu-id="49ec4-146">Kompilator używa ostatniego wyrażenia w treści funkcji do określenia typu i wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="49ec4-146">The compiler uses the final expression in a function body to determine the return value and type.</span></span> <span data-ttu-id="49ec4-147">Kompilator może wnioskować o typie ostatniego wyrażenia z poprzedniego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="49ec4-147">The compiler might infer the type of the final expression from previous expressions.</span></span> <span data-ttu-id="49ec4-148">W funkcji `cylinderVolume`, podanymi w poprzedniej sekcji, typ `pi` zależy od typu literał `3.14159` jako `float`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-148">In the function `cylinderVolume`, shown in the previous section, the type of `pi` is determined from the type of the literal `3.14159` to be `float`.</span></span> <span data-ttu-id="49ec4-149">Kompilator używa typu `pi` można określić typu wyrażenia `h * pi * r * r` jako `float`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-149">The compiler uses the type of `pi` to determine the type of the expression `h * pi * r * r` to be `float`.</span></span> <span data-ttu-id="49ec4-150">W związku z tym jest ogólnie zwracany typ funkcji `float`.</span><span class="sxs-lookup"><span data-stu-id="49ec4-150">Therefore, the overall return type of the function is `float`.</span></span>

<span data-ttu-id="49ec4-151">Aby jawnie określić wartość zwracana, wpisz następujący kod:</span><span class="sxs-lookup"><span data-stu-id="49ec4-151">To specify the return value explicitly, write the code as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

<span data-ttu-id="49ec4-152">Jak kod napisano powyżej, kompilator stosuje **float** do całej funkcji; Jeśli chcesz zastosować je na typy parametrów, użyj następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="49ec4-152">As the code is written above, the compiler applies **float** to the entire function; if you mean to apply it to the parameter types as well, use the following code:</span></span>

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a><span data-ttu-id="49ec4-153">Wywołanie funkcji</span><span class="sxs-lookup"><span data-stu-id="49ec4-153">Calling a Function</span></span>
<span data-ttu-id="49ec4-154">Wywołania funkcji, określając nazwę funkcji, następuje spacja i następnie żadnych argumentów, które są rozdzielone spacjami.</span><span class="sxs-lookup"><span data-stu-id="49ec4-154">You call functions by specifying the function name followed by a space and then any arguments separated by spaces.</span></span> <span data-ttu-id="49ec4-155">Na przykład, aby wywołać funkcję **cylinderVolume** i przypisz wynik do wartości **obj.**, wpisz następujący kod:</span><span class="sxs-lookup"><span data-stu-id="49ec4-155">For example, to call the function **cylinderVolume** and assign the result to the value **vol**, you write the following code:</span></span>

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a><span data-ttu-id="49ec4-156">Częściowe stosowanie argumentów</span><span class="sxs-lookup"><span data-stu-id="49ec4-156">Partial Application of Arguments</span></span>
<span data-ttu-id="49ec4-157">Jeśli podasz mniej niż określona liczba argumentów, utworzysz nową funkcję, która oczekuje pozostałych argumentów.</span><span class="sxs-lookup"><span data-stu-id="49ec4-157">If you supply fewer than the specified number of arguments, you create a new function that expects the remaining arguments.</span></span> <span data-ttu-id="49ec4-158">Ta metoda obsługi argumentów jest określany jako *currying* i jest to cecha funkcjonalności języków programowania, takich jak F #.</span><span class="sxs-lookup"><span data-stu-id="49ec4-158">This method of handling arguments is referred to as *currying* and is a characteristic of functional programming languages like F#.</span></span> <span data-ttu-id="49ec4-159">Na przykład, załóżmy, że korzystasz z dwóch rozmiary potoku: jeden z nich ma radius z **2.0** i innych ma radius z **3.0**.</span><span class="sxs-lookup"><span data-stu-id="49ec4-159">For example, suppose you are working with two sizes of pipe: one has a radius of **2.0** and the other has a radius of **3.0**.</span></span> <span data-ttu-id="49ec4-160">Można utworzyć funkcji określające wolumin potoku, w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="49ec4-160">You could create functions that determine the volume of pipe as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

<span data-ttu-id="49ec4-161">Następnie musi dostarczać dodatkowego argumentu, zgodnie z potrzebami dla różnych długości potoku dwóch różnych rozmiarów:</span><span class="sxs-lookup"><span data-stu-id="49ec4-161">You would then supply the additional argument as needed for various lengths of pipe of the two different sizes:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet107.fs)]
    
## <a name="recursive-functions"></a><span data-ttu-id="49ec4-162">Funkcje rekursywne</span><span class="sxs-lookup"><span data-stu-id="49ec4-162">Recursive Functions</span></span>
<span data-ttu-id="49ec4-163">*Funkcje rekursywne* są funkcje, które wywołują się.</span><span class="sxs-lookup"><span data-stu-id="49ec4-163">*Recursive functions* are functions that call themselves.</span></span> <span data-ttu-id="49ec4-164">Wymagają one, że możesz określić **rec** następujące słowa kluczowego **let** — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="49ec4-164">They require that you specify the **rec** keyword following the **let** keyword.</span></span> <span data-ttu-id="49ec4-165">Wywołania funkcji cyklicznej w treści funkcji tak samo, jak powodowałoby wywołanie wszystkie wywołania funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-165">Invoke the recursive function from within the body of the function just as you would invoke any function call.</span></span> <span data-ttu-id="49ec4-166">Oblicza następujących funkcji recursive  *n* th Fibonacci numer.</span><span class="sxs-lookup"><span data-stu-id="49ec4-166">The following recursive function computes the *n*th Fibonacci number.</span></span> <span data-ttu-id="49ec4-167">Sekwencja numer Fibonacci wiadomo, że od momentu antyków i jest sekwencję, w którym każdą liczbę kolejnych to suma poprzednich dwóch liczb w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-167">The Fibonacci number sequence has been known since antiquity and is a sequence in which each successive number is the sum of the previous two numbers in the sequence.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

<span data-ttu-id="49ec4-168">Niektóre funkcje rekursywne może przepełnienie stosu program lub Niewydajne wykonania, jeśli użytkownik nie zapisuj je ostrożność i z funkcją rozpoznawanie specjalne technik, takich jak użycie akumulatorów i kontynuacje.</span><span class="sxs-lookup"><span data-stu-id="49ec4-168">Some recursive functions might overflow the program stack or perform inefficiently if you do not write them with care and with awareness of special techniques, such as the use of accumulators and continuations.</span></span>


## <a name="function-values"></a><span data-ttu-id="49ec4-169">Wartości funkcji</span><span class="sxs-lookup"><span data-stu-id="49ec4-169">Function Values</span></span>
<span data-ttu-id="49ec4-170">W języku F # wszystkie funkcje są traktowane jako wartości. w rzeczywistości są określane jako *funkcji wartości*.</span><span class="sxs-lookup"><span data-stu-id="49ec4-170">In F#, all functions are considered values; in fact, they are known as *function values*.</span></span> <span data-ttu-id="49ec4-171">Ponieważ funkcje wartości, użyciem jako argumenty do innych funkcji, lub w innych kontekstach, gdzie są używane wartości.</span><span class="sxs-lookup"><span data-stu-id="49ec4-171">Because functions are values, they can be used as arguments to other functions or in other contexts where values are used.</span></span> <span data-ttu-id="49ec4-172">Poniżej przedstawiono przykład funkcji, która przyjmuje wartość funkcji jako argument:</span><span class="sxs-lookup"><span data-stu-id="49ec4-172">Following is an example of a function that takes a function value as an argument:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

<span data-ttu-id="49ec4-173">Określ typ wartości funkcji przy użyciu `->` tokenu.</span><span class="sxs-lookup"><span data-stu-id="49ec4-173">You specify the type of a function value by using the `->` token.</span></span> <span data-ttu-id="49ec4-174">Po lewej stronie token ten jest typem argumentu, a po prawej stronie jest zwracana wartość.</span><span class="sxs-lookup"><span data-stu-id="49ec4-174">On the left side of this token is the type of the argument, and on the right side is the return value.</span></span> <span data-ttu-id="49ec4-175">W poprzednim przykładzie `apply1` to funkcja, która przyjmuje funkcji `transform` jako argument, gdzie `transform` jest funkcją, która przyjmuje całkowitą i zwraca inną liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="49ec4-175">In the previous example, `apply1` is a function that takes a function `transform` as an argument, where `transform` is a function that takes an integer and returns another integer.</span></span> <span data-ttu-id="49ec4-176">Poniższy kod przedstawia sposób użycia `apply1`:</span><span class="sxs-lookup"><span data-stu-id="49ec4-176">The following code shows how to use `apply1`:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

<span data-ttu-id="49ec4-177">Wartość `result` będzie 101 po poprzednim kodzie.</span><span class="sxs-lookup"><span data-stu-id="49ec4-177">The value of `result` will be 101 after the previous code runs.</span></span>

<span data-ttu-id="49ec4-178">Używanie wielu argumentów są rozdzielone przez kolejne `->` tokeny, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="49ec4-178">Multiple arguments are separated by successive `->` tokens, as shown in the following example:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

<span data-ttu-id="49ec4-179">Wynik jest 200.</span><span class="sxs-lookup"><span data-stu-id="49ec4-179">The result is 200.</span></span>


## <a name="lambda-expressions"></a><span data-ttu-id="49ec4-180">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="49ec4-180">Lambda Expressions</span></span>
<span data-ttu-id="49ec4-181">A *wyrażenia lambda* jest funkcja bez nazwy.</span><span class="sxs-lookup"><span data-stu-id="49ec4-181">A *lambda expression* is an unnamed function.</span></span> <span data-ttu-id="49ec4-182">W poprzednich przykładach, zamiast definiować o nazwie funkcji **przyrostu** i **mul**, można użyć wyrażenia lambda w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="49ec4-182">In the previous examples, instead of defining named functions **increment** and **mul**, you could use lambda expressions as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

<span data-ttu-id="49ec4-183">Zdefiniuj wyrażenia lambda za pomocą `fun` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="49ec4-183">You define lambda expressions by using the `fun` keyword.</span></span> <span data-ttu-id="49ec4-184">Wyrażenia lambda podobny definicji funkcji, z wyjątkiem zamiast `=` token, `->` tokenu jest używany do oddzielania listy argumentów z treści funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-184">A lambda expression resembles a function definition, except that instead of the `=` token, the `->` token is used to separate the argument list from the function body.</span></span> <span data-ttu-id="49ec4-185">W definicji funkcji regularnym można wywnioskować lub jawnie określone typy argumentów, a zwracany typ wyrażenia lambda jest wywnioskowany na podstawie typ ostatniego wyrażenia w treści.</span><span class="sxs-lookup"><span data-stu-id="49ec4-185">As in a regular function definition, the argument types can be inferred or specified explicitly, and the return type of the lambda expression is inferred from the type of the last expression in the body.</span></span> <span data-ttu-id="49ec4-186">Aby uzyskać więcej informacji, zobacz [wyrażenia Lambda: `fun` — słowo kluczowe](../functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="49ec4-186">For more information, see [Lambda Expressions: The `fun` Keyword](../functions/lambda-expressions-the-fun-keyword.md).</span></span>


## <a name="function-composition-and-pipelining"></a><span data-ttu-id="49ec4-187">Kompozycja funkcji i przetwarzanie potokowe</span><span class="sxs-lookup"><span data-stu-id="49ec4-187">Function Composition and Pipelining</span></span>
<span data-ttu-id="49ec4-188">Funkcje języka F # może składać się z innych funkcji.</span><span class="sxs-lookup"><span data-stu-id="49ec4-188">Functions in F# can be composed from other functions.</span></span> <span data-ttu-id="49ec4-189">Kompozycja dwie funkcje **function1** i **function2** jest innej funkcji, która reprezentuje stosowania **function1** po zastosowaniu **function2**:</span><span class="sxs-lookup"><span data-stu-id="49ec4-189">The composition of two functions **function1** and **function2** is another function that represents the application of **function1** followed the application of **function2**:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

<span data-ttu-id="49ec4-190">Wynik jest 202.</span><span class="sxs-lookup"><span data-stu-id="49ec4-190">The result is 202.</span></span>

<span data-ttu-id="49ec4-191">Przetwarzanie potokowe umożliwia wywołania funkcji, można je połączyć ze sobą jako kolejnych czynności.</span><span class="sxs-lookup"><span data-stu-id="49ec4-191">Pipelining enables function calls to be chained together as successive operations.</span></span> <span data-ttu-id="49ec4-192">Przetwarzanie potokowe działa w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="49ec4-192">Pipelining works as follows:</span></span>

```fsharp
let result = 100 |> function1 |> function2
```

<span data-ttu-id="49ec4-193">Wynik jest ponownie 202.</span><span class="sxs-lookup"><span data-stu-id="49ec4-193">The result is again 202.</span></span>

<span data-ttu-id="49ec4-194">Operatory kompozycji przyjmować dwie funkcje i zwracać funkcji; z kolei operatorów potoku funkcji i argument i zwracać wartość.</span><span class="sxs-lookup"><span data-stu-id="49ec4-194">The composition operators take two functions and return a function; by contrast, the pipeline operators take a function and an argument and return a value.</span></span> <span data-ttu-id="49ec4-195">W poniższym przykładzie kodu pokazano różnicę między operatorów potoku i kompozycji, pokazując różnice w funkcji podpisów i użycia.</span><span class="sxs-lookup"><span data-stu-id="49ec4-195">The following code example shows the difference between the pipeline and composition operators by showing the differences in the function signatures and usage.</span></span>

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a><span data-ttu-id="49ec4-196">Przeładowywanie funkcji</span><span class="sxs-lookup"><span data-stu-id="49ec4-196">Overloading Functions</span></span>
<span data-ttu-id="49ec4-197">Można przeciążać metod z typem, ale nie działa.</span><span class="sxs-lookup"><span data-stu-id="49ec4-197">You can overload methods of a type but not functions.</span></span> <span data-ttu-id="49ec4-198">Aby uzyskać więcej informacji, zobacz [metody](../members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="49ec4-198">For more information, see [Methods](../members/methods.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="49ec4-199">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49ec4-199">See Also</span></span>
[<span data-ttu-id="49ec4-200">Wartości</span><span class="sxs-lookup"><span data-stu-id="49ec4-200">Values</span></span>](../values/index.md)

[<span data-ttu-id="49ec4-201">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="49ec4-201">F# Language Reference</span></span>](../index.md)