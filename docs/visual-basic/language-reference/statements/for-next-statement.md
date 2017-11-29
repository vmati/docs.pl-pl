---
title: "For...Next — Instrukcja (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="94a6e-102">For...Next — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94a6e-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="94a6e-103">Powtarza określoną liczbę razy grupę instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a6e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="94a6e-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="94a6e-105">Części</span><span class="sxs-lookup"><span data-stu-id="94a6e-105">Parts</span></span>  
  
|<span data-ttu-id="94a6e-106">Część</span><span class="sxs-lookup"><span data-stu-id="94a6e-106">Part</span></span>|<span data-ttu-id="94a6e-107">Opis</span><span class="sxs-lookup"><span data-stu-id="94a6e-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="94a6e-108">Wymagane w `For` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-108">Required in the `For` statement.</span></span> <span data-ttu-id="94a6e-109">Zmienna numeryczna.</span><span class="sxs-lookup"><span data-stu-id="94a6e-109">Numeric variable.</span></span> <span data-ttu-id="94a6e-110">Zmienna sterująca pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-110">The control variable for the loop.</span></span> <span data-ttu-id="94a6e-111">Aby uzyskać więcej informacji, zobacz [Argument licznika](#BKMK_Counter) dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="94a6e-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="94a6e-112">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="94a6e-112">Optional.</span></span> <span data-ttu-id="94a6e-113">Typ danych `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-113">Data type of `counter`.</span></span> <span data-ttu-id="94a6e-114">Aby uzyskać więcej informacji, zobacz [Argument licznika](#BKMK_Counter) dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="94a6e-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="94a6e-115">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="94a6e-115">Required.</span></span> <span data-ttu-id="94a6e-116">Wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="94a6e-116">Numeric expression.</span></span> <span data-ttu-id="94a6e-117">Początkowa wartość `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="94a6e-118">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="94a6e-118">Required.</span></span> <span data-ttu-id="94a6e-119">Wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="94a6e-119">Numeric expression.</span></span> <span data-ttu-id="94a6e-120">Końcowa wartość `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="94a6e-121">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="94a6e-121">Optional.</span></span> <span data-ttu-id="94a6e-122">Wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="94a6e-122">Numeric expression.</span></span> <span data-ttu-id="94a6e-123">Wartość, o którą `counter` jest zwiększany po każdej za pomocą pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="94a6e-124">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="94a6e-124">Optional.</span></span> <span data-ttu-id="94a6e-125">Co najmniej jeden instrukcji między `For` i `Next` uruchomioną określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="94a6e-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="94a6e-126">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="94a6e-126">Optional.</span></span> <span data-ttu-id="94a6e-127">Transfer kontroli do następnej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="94a6e-128">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="94a6e-128">Optional.</span></span> <span data-ttu-id="94a6e-129">Przekazuje sterowanie poza `For` pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="94a6e-130">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="94a6e-130">Required.</span></span> <span data-ttu-id="94a6e-131">Kończy definicję `For` pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="94a6e-132">`To` Słowo kluczowe jest używane w tej instrukcji, aby określić zakres licznika.</span><span class="sxs-lookup"><span data-stu-id="94a6e-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="94a6e-133">Można również użyć słowa kluczowego w [wybierz... Case — instrukcja](../../../visual-basic/language-reference/statements/select-case-statement.md) w deklaracje tablicy.</span><span class="sxs-lookup"><span data-stu-id="94a6e-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="94a6e-134">Aby uzyskać więcej informacji na temat deklaracje tablicy, zobacz [instrukcji Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="94a6e-135">Proste przykłady</span><span class="sxs-lookup"><span data-stu-id="94a6e-135">Simple Examples</span></span>  
 <span data-ttu-id="94a6e-136">Możesz użyć `For`... `Next` struktury, gdy ma zostać powtórzony zestaw instrukcji określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="94a6e-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="94a6e-137">W poniższym przykładzie `index` zmiennej rozpoczyna się od wartości 1 i jest zwiększany przy każdej iteracji pętli kończące się po wartości `index` osiągnie 5.</span><span class="sxs-lookup"><span data-stu-id="94a6e-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 <span data-ttu-id="94a6e-138">W poniższym przykładzie `number` zmiennej rozpoczyna się od 2 i zostanie zmniejszona 0,25 w każdej iteracji pętli kończące się po wartości `number` wynosić 0.</span><span class="sxs-lookup"><span data-stu-id="94a6e-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="94a6e-139">`Step` Argument `-.25` zmniejsza wartość o 0,25 w każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  <span data-ttu-id="94a6e-140">A [podczas... End While — instrukcja](../../../visual-basic/language-reference/statements/while-end-while-statement.md) lub [czy... Instrukcji pętli](../../../visual-basic/language-reference/statements/do-loop-statement.md) działa dobrze, jeśli nie wiadomo, wcześniej ile razy, aby uruchomić instrukcje w pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="94a6e-141">Jednak jeśli oczekujesz do uruchamiania w pętli określoną liczbę razy, `For`... `Next` pętla jest lepszym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="94a6e-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="94a6e-142">Liczba iteracji jest określania, kiedy użytkownik wprowadzi pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="94a6e-143">Zagnieżdżania pętle</span><span class="sxs-lookup"><span data-stu-id="94a6e-143">Nesting Loops</span></span>  
 <span data-ttu-id="94a6e-144">Można zagnieżdżać `For` pętle, ustawiając dla pętli w innym.</span><span class="sxs-lookup"><span data-stu-id="94a6e-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="94a6e-145">W poniższym przykładzie pokazano zagnieżdżonych `For`... `Next` struktur, które mają krok różnych wartości.</span><span class="sxs-lookup"><span data-stu-id="94a6e-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="94a6e-146">Zewnętrzne pętli tworzy ciąg dla każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="94a6e-147">Wewnętrzny pętla zmniejsza zmiennej licznika pętli dla każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 <span data-ttu-id="94a6e-148">Podczas zagnieżdżania pętle, każdej pętli musi mieć unikatową `counter` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="94a6e-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="94a6e-149">Struktury sterujące różnych rodzajów wewnątrz innych można zagnieżdżać.</span><span class="sxs-lookup"><span data-stu-id="94a6e-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="94a6e-150">Aby uzyskać więcej informacji, zobacz [zagnieżdżone struktury sterujące](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="94a6e-151">Zakończ dla i Kontynuuj dla</span><span class="sxs-lookup"><span data-stu-id="94a6e-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="94a6e-152">`Exit For` Instrukcji natychmiast kończy pracę `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="94a6e-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="94a6e-153">pętli i transfer kontroli do instrukcji następującej `Next` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="94a6e-154">`Continue For` Instrukcji sterowania natychmiast przenosi do następnej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="94a6e-155">Aby uzyskać więcej informacji, zobacz [kontynuować instrukcji](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="94a6e-156">Poniższy przykład przedstawia użycie `Continue For` i `Exit For` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="94a6e-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 <span data-ttu-id="94a6e-157">Można wprowadzić dowolną liczbę `Exit For` instrukcje w `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="94a6e-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="94a6e-158">pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-158">loop.</span></span> <span data-ttu-id="94a6e-159">Gdy jest używany w zagnieżdżonych `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="94a6e-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="94a6e-160">pętle, `Exit For` kończy tryb pętli najbardziej i przekazuje sterowanie do następnego wyższego poziomu zagnieżdżenia.</span><span class="sxs-lookup"><span data-stu-id="94a6e-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="94a6e-161">`Exit For`jest często używana po przeprowadzeniu oceny spełnienia określonego warunku (na przykład w `If`... `Then`... `Else` struktury).</span><span class="sxs-lookup"><span data-stu-id="94a6e-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="94a6e-162">Możesz chcieć użyć `Exit For` następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="94a6e-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="94a6e-163">Kontynuowanie wykonania iteracji jest niepotrzebne lub niemożliwe.</span><span class="sxs-lookup"><span data-stu-id="94a6e-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="94a6e-164">Błędna wartość lub żądanie zakończenia może utworzenia tego warunku.</span><span class="sxs-lookup"><span data-stu-id="94a6e-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="94a6e-165">A `Try`... `Catch`... `Finally` wyjątek zostanie przechwycony instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="94a6e-166">Można na przykład `Exit For` na końcu `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="94a6e-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="94a6e-167">Masz nieskończonej pętli, czyli pętli, które można uruchomić dużych lub nawet nieskończoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="94a6e-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="94a6e-168">W przypadku wykrycia takim stanie, można użyć `Exit For` wyjścia z pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="94a6e-169">Aby uzyskać więcej informacji, zobacz [czy... Pętla instrukcji](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="94a6e-170">Realizacja techniczna</span><span class="sxs-lookup"><span data-stu-id="94a6e-170">Technical Implementation</span></span>  
 <span data-ttu-id="94a6e-171">Gdy `For`... `Next` rozpoczyna pętli, ocenia Visual Basic `start`, `end`, i `step`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="94a6e-172">Visual Basic ocenia te wartości tylko w tym czasie, a następnie przypisuje `start` do `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="94a6e-173">Przed rozpoczęciem instrukcji uruchamia blok, porównuje Visual Basic `counter` do `end`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="94a6e-174">Jeśli `counter` już jest większy niż `end` wartości (lub mniejszy, jeśli `step` jest ujemna), `For` kończy się w pętli i kontrola przechodzi do instrukcji następującej `Next` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="94a6e-175">W przeciwnym razie uruchamia blok instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="94a6e-176">Po każdej aktualizacji Visual Basic napotka `Next` instrukcji, zwiększa `counter` przez `step` , przywracając `For` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="94a6e-177">Ponownie porównuje `counter` do `end`, i ponownie go uruchamia blok albo kończy tryb pętli, w zależności od wyniku.</span><span class="sxs-lookup"><span data-stu-id="94a6e-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="94a6e-178">Ten proces jest kontynuowany do momentu `counter` przekazuje `end` lub `Exit For` napotkano instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="94a6e-179">Pętla nie zatrzymania do momentu `counter` minął `end`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="94a6e-180">Jeśli `counter` jest równa `end`, pętla będzie kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="94a6e-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="94a6e-181">Porównanie, która określa, czy do uruchomienia bloku jest `counter`  <=  `end` Jeśli `step` jest dodatnia i `counter`  >=  `end` Jeśli `step` jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="94a6e-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="94a6e-182">W przypadku zmiany wartości `counter` znajduje się wewnątrz pętli, może być trudne do odczytu i debugowania kodu.</span><span class="sxs-lookup"><span data-stu-id="94a6e-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="94a6e-183">Zmiana wartości `start`, `end`, lub `step` nie ma wpływu na wartości iteracji, które zostały uznane za najpierw wprowadzenie pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="94a6e-184">Jeśli zagnieździć pętle, kompilator sygnalizuje błąd, jeśli wystąpi `Next` instrukcji zewnętrzne poziom zagnieżdżenia przed `Next` instrukcji wewnętrzny poziom.</span><span class="sxs-lookup"><span data-stu-id="94a6e-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="94a6e-185">Jednak kompilator wykryć nakładających się błędu tylko w przypadku określenia `counter` w każdym `Next` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="94a6e-186">Argument kroku</span><span class="sxs-lookup"><span data-stu-id="94a6e-186">Step Argument</span></span>  
 <span data-ttu-id="94a6e-187">Wartość `step` może być liczbą dodatnią lub ujemną.</span><span class="sxs-lookup"><span data-stu-id="94a6e-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="94a6e-188">Ten parametr określa przetwarzanie pętli zgodnie z poniższą tabelą:</span><span class="sxs-lookup"><span data-stu-id="94a6e-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="94a6e-189">**Wartość kroku**</span><span class="sxs-lookup"><span data-stu-id="94a6e-189">**Step value**</span></span>|<span data-ttu-id="94a6e-190">**Wykonuje pętlę, jeśli**</span><span class="sxs-lookup"><span data-stu-id="94a6e-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="94a6e-191">Dodatnia lub równa zero</span><span class="sxs-lookup"><span data-stu-id="94a6e-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="94a6e-192">Ujemne</span><span class="sxs-lookup"><span data-stu-id="94a6e-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="94a6e-193">Wartość domyślna `step` 1.</span><span class="sxs-lookup"><span data-stu-id="94a6e-193">The default value of `step` is 1.</span></span>  
  
###  <span data-ttu-id="94a6e-194"><a name="BKMK_Counter"></a>Argument licznika</span><span class="sxs-lookup"><span data-stu-id="94a6e-194"><a name="BKMK_Counter"></a> Counter Argument</span></span>  
 <span data-ttu-id="94a6e-195">W poniższej tabeli przedstawiono czy `counter` definiuje nowej zmiennej lokalnej, która ma zakres do całej `For…Next` pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="94a6e-196">To jest zależny od tego, czy `datatype` istnieje i czy `counter` jest już zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="94a6e-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="94a6e-197">Jest `datatype` obecny?</span><span class="sxs-lookup"><span data-stu-id="94a6e-197">Is `datatype` present?</span></span>|<span data-ttu-id="94a6e-198">Jest `counter` już zdefiniowane?</span><span class="sxs-lookup"><span data-stu-id="94a6e-198">Is `counter` already defined?</span></span>|<span data-ttu-id="94a6e-199">Wynik (czy `counter` definiuje nowej zmiennej lokalnej, która ma zakres do całej `For...Next` pętli)</span><span class="sxs-lookup"><span data-stu-id="94a6e-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="94a6e-200">Nie</span><span class="sxs-lookup"><span data-stu-id="94a6e-200">No</span></span>|<span data-ttu-id="94a6e-201">Tak</span><span class="sxs-lookup"><span data-stu-id="94a6e-201">Yes</span></span>|<span data-ttu-id="94a6e-202">Nie, ponieważ `counter` jest już zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="94a6e-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="94a6e-203">Jeśli zakres `counter` nie jest lokalny do procedury występuje ostrzeżenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="94a6e-204">Nie</span><span class="sxs-lookup"><span data-stu-id="94a6e-204">No</span></span>|<span data-ttu-id="94a6e-205">Nie</span><span class="sxs-lookup"><span data-stu-id="94a6e-205">No</span></span>|<span data-ttu-id="94a6e-206">Tak.</span><span class="sxs-lookup"><span data-stu-id="94a6e-206">Yes.</span></span> <span data-ttu-id="94a6e-207">Typ danych jest wywnioskowany na podstawie `start`, `end`, i `step` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="94a6e-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="94a6e-208">Aby uzyskać informacje o wnioskowanie o typie, zobacz [Option Infer — instrukcja](../../../visual-basic/language-reference/statements/option-infer-statement.md) i [wnioskowanie o typie lokalnym](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="94a6e-209">Tak</span><span class="sxs-lookup"><span data-stu-id="94a6e-209">Yes</span></span>|<span data-ttu-id="94a6e-210">Tak</span><span class="sxs-lookup"><span data-stu-id="94a6e-210">Yes</span></span>|<span data-ttu-id="94a6e-211">Tak, ale tylko wtedy, gdy istniejące `counter` zmiennej jest zdefiniowany poza procedurą.</span><span class="sxs-lookup"><span data-stu-id="94a6e-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="94a6e-212">Tej zmiennej pozostaje oddzielnym.</span><span class="sxs-lookup"><span data-stu-id="94a6e-212">That variable remains separate.</span></span> <span data-ttu-id="94a6e-213">Jeśli zakres istniejących `counter` zmiennej jest lokalny dla procedury, występuje błąd kompilacji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="94a6e-214">Tak</span><span class="sxs-lookup"><span data-stu-id="94a6e-214">Yes</span></span>|<span data-ttu-id="94a6e-215">Nie</span><span class="sxs-lookup"><span data-stu-id="94a6e-215">No</span></span>|<span data-ttu-id="94a6e-216">Tak.</span><span class="sxs-lookup"><span data-stu-id="94a6e-216">Yes.</span></span>|  
  
 <span data-ttu-id="94a6e-217">Typ danych miary `counter` Określa typ iteracji, który musi być jednym z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="94a6e-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="94a6e-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, lub `Double`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="94a6e-219">Wyliczenie zadeklarować przy użyciu [Enum — instrukcja](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="94a6e-220">`Object`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="94a6e-221">Typ `T` mający następujących operatorów, gdzie `B` jest typem, który może być używana w `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="94a6e-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="94a6e-222">Opcjonalnie można określić `counter` zmiennej w `Next` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="94a6e-223">Ta składnia poprawia czytelność programu, zwłaszcza, jeśli można zagnieżdżać `For` pętli.</span><span class="sxs-lookup"><span data-stu-id="94a6e-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="94a6e-224">Należy określić zmiennej, która jest wyświetlana w polu `For` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="94a6e-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="94a6e-225">`start`, `end`, I `step` wyrażenia może służyć do oceny do dowolnego typu danych rozszerzająca do typu `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="94a6e-226">Jeśli używasz typ zdefiniowany przez użytkownika `counter`, może być konieczne zdefiniowanie `CType` operatora konwersji do konwersji typów `start`, `end`, lub `step` do typu `counter`.</span><span class="sxs-lookup"><span data-stu-id="94a6e-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94a6e-227">Przykład</span><span class="sxs-lookup"><span data-stu-id="94a6e-227">Example</span></span>  
 <span data-ttu-id="94a6e-228">Poniższy przykład umożliwia usunięcie wszystkich elementów z listy ogólnej.</span><span class="sxs-lookup"><span data-stu-id="94a6e-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="94a6e-229">Zamiast [For Each... Następna instrukcja](../../../visual-basic/language-reference/statements/for-each-next-statement.md), w przykładzie `For`... `Next` instrukcji, która wykonuje iterację w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="94a6e-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="94a6e-230">W przykładzie użyto ta technika, ponieważ `removeAt` metoda powoduje elementów po elemencie usunięto mieć niższe wartości indeksu.</span><span class="sxs-lookup"><span data-stu-id="94a6e-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="94a6e-231">Przykład</span><span class="sxs-lookup"><span data-stu-id="94a6e-231">Example</span></span>  
 <span data-ttu-id="94a6e-232">Poniższy przykład iteruje wyliczenie zadeklarowana przy użyciu [Enum — instrukcja](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="94a6e-233">Przykład</span><span class="sxs-lookup"><span data-stu-id="94a6e-233">Example</span></span>  
 <span data-ttu-id="94a6e-234">W poniższym przykładzie parametrów instrukcji, użyj klasy, która ma przeciążeń operatora dla `+`, `-`, `>=`, i `<=` operatorów.</span><span class="sxs-lookup"><span data-stu-id="94a6e-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="94a6e-235">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="94a6e-235">See Also</span></span>  
 <xref:System.Collections.Generic.List%601>  
 [<span data-ttu-id="94a6e-236">Struktury pętli</span><span class="sxs-lookup"><span data-stu-id="94a6e-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="94a6e-237">While... End While — instrukcja</span><span class="sxs-lookup"><span data-stu-id="94a6e-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="94a6e-238">Czy... Loop — instrukcja</span><span class="sxs-lookup"><span data-stu-id="94a6e-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="94a6e-239">Zagnieżdżone struktury sterujące</span><span class="sxs-lookup"><span data-stu-id="94a6e-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="94a6e-240">Exit — instrukcja</span><span class="sxs-lookup"><span data-stu-id="94a6e-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="94a6e-241">Kolekcje</span><span class="sxs-lookup"><span data-stu-id="94a6e-241">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)