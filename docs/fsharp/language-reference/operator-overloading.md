---
title: "Przeładowanie operatora (F#)"
description: "Dowiedz się, jak przeciążenia operatorów arytmetycznych w klasie lub typ rekordu i na poziomie globalnym w języku F #."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 019277ed-f649-4fa5-ad43-097865f449d9
ms.openlocfilehash: 76ddab5339e11d71bb326b60d727017eb838ccf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="operator-overloading"></a><span data-ttu-id="62ad0-104">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="62ad0-104">Operator Overloading</span></span>

<span data-ttu-id="62ad0-105">W tym temacie opisano sposób przeciążania operatorów arytmetycznych w klasie lub typie rekordu oraz na poziomie globalnym.</span><span class="sxs-lookup"><span data-stu-id="62ad0-105">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="62ad0-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="62ad0-106">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="62ad0-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="62ad0-107">Remarks</span></span>
<span data-ttu-id="62ad0-108">W poprzednich składni *symbol operatora* jest jednym z `+`, `-`, `*`, `/`, `=`i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="62ad0-108">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="62ad0-109">*Listy parametrów* Określa argumenty operacji w kolejności pojawią się one w zwykłym składni dla tego operatora.</span><span class="sxs-lookup"><span data-stu-id="62ad0-109">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="62ad0-110">*Treści metody* tworzy wynikowej wartości.</span><span class="sxs-lookup"><span data-stu-id="62ad0-110">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="62ad0-111">Przeciążenia operatorów muszą być statyczne.</span><span class="sxs-lookup"><span data-stu-id="62ad0-111">Operator overloads for operators must be static.</span></span> <span data-ttu-id="62ad0-112">Operator overloads operatory jednoargumentowe, takich jak `+` i `-`, należy użyć tyldy (`~`) w *symbol operatora* do wskazywania operator Jednoargumentowy operator i nie operatora binarnego, jak pokazano w Po deklaracji.</span><span class="sxs-lookup"><span data-stu-id="62ad0-112">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="62ad0-113">Kod poniżej ilustruje klasę wektorową, która ma tylko dwa operatory: jeden dla jednoargumentowego znaku minusa, a drugi dla mnożenia przez wartość skalarną.</span><span class="sxs-lookup"><span data-stu-id="62ad0-113">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="62ad0-114">W przykładzie są wymagane dwa przeciążenia mnożenia skalarnego, ponieważ operator musi działać niezależnie od kolejności występowania wartości wektorowej i skalarnej.</span><span class="sxs-lookup"><span data-stu-id="62ad0-114">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="62ad0-115">Tworzenie nowych operatorów</span><span class="sxs-lookup"><span data-stu-id="62ad0-115">Creating New Operators</span></span>
<span data-ttu-id="62ad0-116">Można przeciążać wszystkie operatory standardowe, ale także tworzyć nowe operatory z sekwencji określonych znaków.</span><span class="sxs-lookup"><span data-stu-id="62ad0-116">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="62ad0-117">Dozwolone są znaki operator `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, i `~`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-117">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="62ad0-118">Znak `~` odgrywa specjalną rolę (oznacza operator jednoargumentowy) i nie jest częścią sekwencji znaków operatora.</span><span class="sxs-lookup"><span data-stu-id="62ad0-118">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="62ad0-119">Nie wszystkie operatory nie jest możliwe jednoargumentowy.</span><span class="sxs-lookup"><span data-stu-id="62ad0-119">Not all operators can be made unary.</span></span>

<span data-ttu-id="62ad0-120">W zależności od konkretnej sekwencji użytych znaków operator będzie miał określone pierwszeństwo i łączność.</span><span class="sxs-lookup"><span data-stu-id="62ad0-120">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="62ad0-121">Łączność może być typu od lewej do prawej lub od prawej do lewej. Jest wykorzystywana zawsze wtedy, gdy operatory o tym samym poziomie pierwszeństwa występują w sekwencji bez nawiasów.</span><span class="sxs-lookup"><span data-stu-id="62ad0-121">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="62ad0-122">Znak operatora `.` nie wpływa na pierwszeństwo, dlatego na przykład w celu zdefiniowania własnej wersji mnożenia, która ma takie samo pierwszeństwo i łączność jak zwykłe mnożenie, można utworzyć operatora `.*` albo podobnego.</span><span class="sxs-lookup"><span data-stu-id="62ad0-122">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="62ad0-123">Tylko operatory `?` i `?<-` mogą rozpoczynać się `?`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-123">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="62ad0-124">Tabelę przedstawiającą priorytet wszystkich operatorów w języku F # można znaleźć w [Operator odwołanie do symbolu i](symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="62ad0-124">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="62ad0-125">Nazwy przeciążonych operatorów</span><span class="sxs-lookup"><span data-stu-id="62ad0-125">Overloaded Operator Names</span></span>
<span data-ttu-id="62ad0-126">Gdy kompilator języka F# kompiluje wyrażenie operatora, tworzy dla tego operatora metodę o wygenerowanej przez siebie nazwie.</span><span class="sxs-lookup"><span data-stu-id="62ad0-126">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="62ad0-127">Ta nazwa metody jest wyświetlana w składni języka Microsoft Intermediate Language (MSIL), w odbiciu oraz w narzędziu IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="62ad0-127">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="62ad0-128">Zazwyczaj nie trzeba używać tych nazw w kodzie języka F#.</span><span class="sxs-lookup"><span data-stu-id="62ad0-128">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="62ad0-129">W tabeli poniżej pokazano standardowe operatory oraz odpowiadające im wygenerowane nazwy.</span><span class="sxs-lookup"><span data-stu-id="62ad0-129">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="62ad0-130">Operator</span><span class="sxs-lookup"><span data-stu-id="62ad0-130">Operator</span></span>|<span data-ttu-id="62ad0-131">Wygenerowana nazwa</span><span class="sxs-lookup"><span data-stu-id="62ad0-131">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|
<span data-ttu-id="62ad0-132">Jako operatorów można również używać innych, niewymienionych tutaj kombinacji znaków operatorów. Ich nazwy mogą powstawać z połączenia nazw poszczególnych znaków podanych w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="62ad0-132">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="62ad0-133">Na przykład +!</span><span class="sxs-lookup"><span data-stu-id="62ad0-133">For example, +!</span></span> <span data-ttu-id="62ad0-134">staje się `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-134">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="62ad0-135">Znak operatora</span><span class="sxs-lookup"><span data-stu-id="62ad0-135">Operator character</span></span>|<span data-ttu-id="62ad0-136">Nazwa</span><span class="sxs-lookup"><span data-stu-id="62ad0-136">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="62ad0-137">Operatory przedrostkowe i wrostkowe</span><span class="sxs-lookup"><span data-stu-id="62ad0-137">Prefix and Infix Operators</span></span>
<span data-ttu-id="62ad0-138">*Prefiks* operatory powinny można umieścić operand lub argumentów operacji, podobnie jak w funkcji.</span><span class="sxs-lookup"><span data-stu-id="62ad0-138">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="62ad0-139">*Element infiksu* operatory powinny być umieszczone między dwóch argumentów operacji.</span><span class="sxs-lookup"><span data-stu-id="62ad0-139">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="62ad0-140">Jako operatorów przedrostkowych można używać tylko niektórych operatorów.</span><span class="sxs-lookup"><span data-stu-id="62ad0-140">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="62ad0-141">Niektóre operatory są zawsze operatorami przedrostkowymi, inne mogą być wrostkowe lub przedrostkowe, a pozostałe są zawsze operatorami wrostkowymi.</span><span class="sxs-lookup"><span data-stu-id="62ad0-141">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="62ad0-142">Operatory, które zaczynają się znakiem `!` (z wyjątkiem `!=`), oraz operator `~` lub powtarzające się sekwencje operatora `~`, są zawsze operatorami przedrostkowymi.</span><span class="sxs-lookup"><span data-stu-id="62ad0-142">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="62ad0-143">Operatory `+`, `-`, `+.`, `-.`, `&`, `&&`, `%` i `%%` mogą być przedrostkowe lub wrostkowe.</span><span class="sxs-lookup"><span data-stu-id="62ad0-143">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="62ad0-144">Przedrostkowe wersje tych operatorów można odróżnić od wersji wrostkowych przez dodanie znaku `~` na początku operatora przedrostkowego podczas jego definiowania.</span><span class="sxs-lookup"><span data-stu-id="62ad0-144">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="62ad0-145">Znak `~` nie jest wykorzystywany podczas używania operatora, a tylko podczas jego definiowania.</span><span class="sxs-lookup"><span data-stu-id="62ad0-145">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="62ad0-146">Przykład</span><span class="sxs-lookup"><span data-stu-id="62ad0-146">Example</span></span>

<span data-ttu-id="62ad0-147">Poniższy kod ilustruje zastosowania przeciążenia operatora w celu zaimplementowania typu ułamkowego.</span><span class="sxs-lookup"><span data-stu-id="62ad0-147">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="62ad0-148">Ułamek jest reprezentowany przez licznik i mianownik.</span><span class="sxs-lookup"><span data-stu-id="62ad0-148">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="62ad0-149">Funkcja `hcf` służy do określenia największego wspólnego dzielnika, który pozwala zmniejszyć ułamek.</span><span class="sxs-lookup"><span data-stu-id="62ad0-149">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="62ad0-150">**Dane wyjściowe:**</span><span class="sxs-lookup"><span data-stu-id="62ad0-150">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="62ad0-151">Operatory na poziomie globalnym</span><span class="sxs-lookup"><span data-stu-id="62ad0-151">Operators at the Global Level</span></span>
<span data-ttu-id="62ad0-152">Operatory można również definiować na poziomie globalnym.</span><span class="sxs-lookup"><span data-stu-id="62ad0-152">You can also define operators at the global level.</span></span> <span data-ttu-id="62ad0-153">Poniższy kod definiuje operator `+?`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-153">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="62ad0-154">Danymi wyjściowymi powyższego kodu jest wartość `12`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-154">The output of the above code is `12`.</span></span>

<span data-ttu-id="62ad0-155">W ten sposób można zmieniać definicje zwykłych operatorów arytmetycznych, ponieważ reguły określania zakresów w języku F# narzucają pierwszeństwo nowo definiowanych operatorów przed operatorami wbudowanymi.</span><span class="sxs-lookup"><span data-stu-id="62ad0-155">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="62ad0-156">W połączeniu z operatorami globalnymi często używa się słowa kluczowego `inline`, ponieważ operatory te są przeważnie małymi funkcjami, które najlepiej integrować w kodzie wywołującym.</span><span class="sxs-lookup"><span data-stu-id="62ad0-156">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="62ad0-157">Wbudowanie funkcji operatorów umożliwia im także współpracę z parametrami typów rozpoznawanymi statycznie i dzięki temu generowanie statycznie rozpoznawanego kodu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="62ad0-157">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="62ad0-158">Aby uzyskać więcej informacji, zobacz [funkcji śródwierszowych](functions/inline-functions.md) i [statycznie rozwiązane parametrów typu](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="62ad0-158">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="62ad0-159">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62ad0-159">See Also</span></span>
[<span data-ttu-id="62ad0-160">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="62ad0-160">Members</span></span>](members/index.md)