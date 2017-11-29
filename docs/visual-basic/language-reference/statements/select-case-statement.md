---
title: "Select...Case — Instrukcja (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7527763a05ec32af88c6ba66ef717d839c33154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="80d3f-102">Select...Case — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80d3f-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="80d3f-103">Uruchamia jedną lub kilka grup instrukcji w zależności od wartości wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="80d3f-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d3f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="80d3f-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="80d3f-105">Części</span><span class="sxs-lookup"><span data-stu-id="80d3f-105">Parts</span></span>  
  
|<span data-ttu-id="80d3f-106">Termin</span><span class="sxs-lookup"><span data-stu-id="80d3f-106">Term</span></span>|<span data-ttu-id="80d3f-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="80d3f-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="80d3f-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="80d3f-108">Required.</span></span> <span data-ttu-id="80d3f-109">Wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="80d3f-109">Expression.</span></span> <span data-ttu-id="80d3f-110">Musi być jednego z typów podstawowych danych (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, i `UShort`).</span><span class="sxs-lookup"><span data-stu-id="80d3f-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="80d3f-111">Wymagane w `Case` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="80d3f-111">Required in a `Case` statement.</span></span> <span data-ttu-id="80d3f-112">Lista klauzule wyrażenia reprezentujący dopasowania wartości `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="80d3f-113">Wiele klauzule wyrażenia są oddzielone przecinkami.</span><span class="sxs-lookup"><span data-stu-id="80d3f-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="80d3f-114">Każdej klauzuli można wykonać jedną z następujących formatów:</span><span class="sxs-lookup"><span data-stu-id="80d3f-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="80d3f-115">-   *wyrażenie1* `To` *wyrażenie2*</span><span class="sxs-lookup"><span data-stu-id="80d3f-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="80d3f-116">— [ `Is` ] *OperatorPorównania* *wyrażenia*</span><span class="sxs-lookup"><span data-stu-id="80d3f-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="80d3f-117">-   *wyrażenie*</span><span class="sxs-lookup"><span data-stu-id="80d3f-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="80d3f-118">Użyj `To` — słowo kluczowe, aby określić granice zakresu dopasowania wartości `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="80d3f-119">Wartość `expression1` musi być mniejsza niż wartość `expression2`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="80d3f-120">Użyj `Is` — słowo kluczowe z operatora porównania (`=`, `<>`, `<`, `<=`, `>`, lub `>=`) do określenia ograniczenie dla wartości dopasowania `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="80d3f-121">Jeśli `Is` — słowo kluczowe nie jest podany, automatycznie dodaje się go przed *OperatorPorównania*.</span><span class="sxs-lookup"><span data-stu-id="80d3f-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="80d3f-122">Formularz, określając tylko `expression` jest traktowany jako specjalny przypadek `Is` tworzą where *OperatorPorównania* jest znak równości (`=`).</span><span class="sxs-lookup"><span data-stu-id="80d3f-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="80d3f-123">Ten formularz jest szacowana jako `testexpression`  =  `expression`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="80d3f-124">Wyrażenia w `expressionlist` może być dowolnego typu danych, zakładając, że są one umożliwiają niejawnej konwersji na typ `testexpression` i odpowiednie `comparisonoperator` jest prawidłowy dla dwóch typów jest używany z.</span><span class="sxs-lookup"><span data-stu-id="80d3f-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="80d3f-125">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="80d3f-125">Optional.</span></span> <span data-ttu-id="80d3f-126">Jeden lub więcej następujących instrukcji `Case` wykonywania Jeśli `testexpression` odpowiada klauzuli w `expressionlist`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="80d3f-127">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="80d3f-127">Optional.</span></span> <span data-ttu-id="80d3f-128">Jeden lub więcej następujących instrukcji `Case Else` wykonywania Jeśli `testexpression` jest niezgodny z klauzuli w `expressionlist` któregokolwiek z `Case` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="80d3f-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="80d3f-129">Kończy definicję `Select`... `Case` konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="80d3f-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80d3f-130">Uwagi</span><span class="sxs-lookup"><span data-stu-id="80d3f-130">Remarks</span></span>  
 <span data-ttu-id="80d3f-131">Jeśli `testexpression` zgodny z dowolnym `Case` `expressionlist` klauzuli, instrukcje po `Case` instrukcji uruchamiany do następnego `Case`, `Case Else`, lub `End Select` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="80d3f-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="80d3f-132">Kontrola następnie przechodzi do instrukcji następującej `End Select`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="80d3f-133">Jeśli `testexpression` odpowiada `expressionlist` klauzuli w więcej niż jednym `Case` Uruchom tylko instrukcje po pierwsze dopasowanie klauzuli.</span><span class="sxs-lookup"><span data-stu-id="80d3f-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="80d3f-134">`Case Else` Wprowadzenie używana jest instrukcja `elsestatements` do uruchomienia, jeśli nie znaleziono między `testexpression` i `expressionlist` klauzuli w żadnym innym `Case` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="80d3f-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="80d3f-135">Mimo że nie jest to wymagane, to warto mieć `Case Else` instrukcji w Twojej `Select Case` konstrukcji, aby obsłużyć nieprzewidzianego `testexpression` wartości.</span><span class="sxs-lookup"><span data-stu-id="80d3f-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="80d3f-136">Jeśli nie `Case` `expressionlist` odpowiada klauzuli `testexpression` i ma nie `Case Else` instrukcji sterowania przekazywany do instrukcji następującej `End Select`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="80d3f-137">Można użyć wielu wyrażeń lub zakresów w każdym `Case` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="80d3f-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="80d3f-138">Na przykład następujący wiersz jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="80d3f-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="80d3f-139">`Is` Słowo kluczowe użyte w `Case` i `Case Else` instrukcji nie jest taka sama jak [operatora Is](../../../visual-basic/language-reference/operators/is-operator.md), które jest używane dla obiekt porównanie odwołań.</span><span class="sxs-lookup"><span data-stu-id="80d3f-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="80d3f-140">Można określić zakresy i wiele wyrażeń dla ciągów znaków.</span><span class="sxs-lookup"><span data-stu-id="80d3f-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="80d3f-141">W poniższym przykładzie `Case` dopasowuje dowolny ciąg, są dokładnie takie same "jabłek", ma wartość z zakresu od "nuts" i "zup" w kolejności alfabetycznej lub zawiera dokładnie samą wartość, jak bieżąca wartość `testItem`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="80d3f-142">Ustawienie `Option Compare` mogą mieć wpływ na porównywanie ciągów.</span><span class="sxs-lookup"><span data-stu-id="80d3f-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="80d3f-143">W obszarze `Option Compare Text`, ciągi "Jabłek" i "jabłek" porównania jako równe, ale w obszarze `Option Compare Binary`, nie ma.</span><span class="sxs-lookup"><span data-stu-id="80d3f-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80d3f-144">A `Case` instrukcji z wielu klauzul można zachowują znany jako *zwarcie*.</span><span class="sxs-lookup"><span data-stu-id="80d3f-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="80d3f-145">Visual Basic ocenia klauzule od lewej do prawej, a jeśli tworzy dopasowania `testexpression`, pozostałe klauzule nie są sprawdzane.</span><span class="sxs-lookup"><span data-stu-id="80d3f-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="80d3f-146">Zwarcie może zwiększyć wydajność, ale może spowodować nieoczekiwane wyniki, jeśli są oczekiwane co wyrażenie w `expressionlist` ma zostać obliczone.</span><span class="sxs-lookup"><span data-stu-id="80d3f-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="80d3f-147">Aby uzyskać więcej informacji dotyczących zwarcie, zobacz [wyrażeń logicznych](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="80d3f-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="80d3f-148">Jeśli kod w `Case` lub `Case Else` blok instrukcji nie trzeba uruchamiać więcej oświadczeń w bloku, go zamknąć bloku przy użyciu `Exit Select` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="80d3f-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="80d3f-149">Ten formant natychmiast przenosi do instrukcji następującej `End Select`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="80d3f-150">`Select Case`konstrukcje mogą być zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="80d3f-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="80d3f-151">Każdy zagnieżdżone `Select Case` konstrukcji musi mieć zgodną `End Select` instrukcji i musi być całkowicie zawarty w jednym `Case` lub `Case Else` blok instrukcji zewnętrznego `Select Case` konstrukcji, w którym jest zagnieżdżony.</span><span class="sxs-lookup"><span data-stu-id="80d3f-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80d3f-152">Przykład</span><span class="sxs-lookup"><span data-stu-id="80d3f-152">Example</span></span>  
 <span data-ttu-id="80d3f-153">W poniższym przykładzie użyto `Select Case` konstrukcji do zapisywania wiersza odpowiadającą wartości zmiennej `number`.</span><span class="sxs-lookup"><span data-stu-id="80d3f-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="80d3f-154">Drugi `Case` instrukcja zawiera wartość odpowiadającą bieżącej wartości `number`, więc instrukcji, która zapisuje "od 6 do 8 włącznie" jest uruchamiana.</span><span class="sxs-lookup"><span data-stu-id="80d3f-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="80d3f-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="80d3f-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [<span data-ttu-id="80d3f-156">End — instrukcja</span><span class="sxs-lookup"><span data-stu-id="80d3f-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="80d3f-157">IF... Następnie... Else — instrukcja</span><span class="sxs-lookup"><span data-stu-id="80d3f-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="80d3f-158">Option Compare — instrukcja</span><span class="sxs-lookup"><span data-stu-id="80d3f-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="80d3f-159">Exit — instrukcja</span><span class="sxs-lookup"><span data-stu-id="80d3f-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)