---
title: "&gt;&gt;= — Operator (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;= — Operator (Visual Basic)
Wykonuje arytmetyczne przesunięcie w prawo na wartość zmiennej lub właściwości i przypisuje wynik do zmiennej lub właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Części  
 `variableorproperty`  
 Wymagany. Zmienna lub właściwość typu całkowitego (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, lub `ULong`).  
  
 `amount`  
 Wymagany. Wyrażenia liczbowego typu danych rozszerzająca do `Integer`.  
  
## <a name="remarks"></a>Uwagi  
 Element po lewej stronie `>>=` operator może być zmienną skalarną proste, właściwością lub element tablicy. Zmienna lub właściwość nie może być [tylko do odczytu](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `>>=` Operator najpierw wykonuje arytmetyczne przesunięcie w prawo na wartość zmiennej lub właściwości. Następnie operator przypisuje wynik tej operacji do zmiennej lub właściwości.  
  
 Arytmetycznego przesunięcia nie są cykliczne, co oznacza, że bitów przesunąć poza jednym zakończeniu wynik nie są ponownie na drugim końcu. W arytmetyczne przesunięcie w prawo bitów przesunięty poza Pozycja bitu po prawej stronie zostaną odrzucone i lewej bit jest propagowana do pozycji z bitowego vacated po lewej stronie. Oznacza to, że jeśli `variableorproperty` ma wartość ujemną vacated pozycje są ustawione na jedną. Jeśli `variableorproperty` jest dodatnia, lub jeśli jego typem jest typ bez znaku, vacated pozycji zostaną ustawione na zero.  
  
## <a name="overloading"></a>Przeciążenie  
 [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) może być *przeciążony*, co oznacza, że klasy lub struktury ponownie zdefiniować jego zachowanie, gdy argument operacji ma typ tej klasy lub struktury. Przeciążanie `>>` operator wpływa na działanie `>>=` operatora. Jeśli używa Twój kod `>>=` na klasę lub strukturę, która overloads `>>`, trzeba koniecznie zapoznać się ponownie zdefiniowany zachowania. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `>>=` operator przesunięcia wzorca bitowego z `Integer` zmiennej bezpośrednio przez określony i przypisz wynik do zmiennej.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 [>> — Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [Operatory przypisania](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Bit Shift — operatory](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Kolejność wykonywania w języku Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operatory według funkcji](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Instrukcje](../../../visual-basic/programming-guide/language-features/statements.md)
