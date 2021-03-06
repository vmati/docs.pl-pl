---
title: "= — Operator (odwołanie w C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: =_CSharpKeyword
helpviewer_keywords: = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c7188abe54cb69678720b4dbbf4dbdea1be4abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>= — Operator (odwołanie w C#)
Operator przypisania (`=`) przechowuje wartość jego prawostronny operand w lokalizacji przechowywania, właściwość lub indeksator wskazywane przez jej argument po lewej stronie i zwraca wartość wyniku. Argumenty operacji musi być tego samego typu (lub prawostronny operand musi być umożliwiają niejawnej konwersji na typ lewego operandu).  
  
## <a name="remarks"></a>Uwagi  
 Operator przypisania nie może być przeciążony. Można jednak zdefiniować operatory niejawnej konwersji typu, które umożliwiają korzystanie z tych typów operator przypisania. Aby uzyskać więcej informacji, zobacz [przy użyciu operatorów konwersji](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie w C#](../../../csharp/language-reference/index.md)  
 [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
 [Operatory C#](../../../csharp/language-reference/operators/index.md)
