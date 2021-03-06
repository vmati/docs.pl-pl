---
title: "Inne struktury sterujące (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a>Inne struktury sterujące (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]zapewnia struktury sterujące, które ułatwiają Usuwanie zasobu lub Zmniejsz liczbę razy, należy powtórzyć odwołanie do obiektu.  
  
## <a name="usingend-using-construction"></a>Za pomocą... Przy użyciu konstrukcji końcowych  
 `Using...End Using` Konstrukcji określa blok instrukcji, w którym należy korzystać z zasobów, takich jak połączenia SQL. Opcjonalnie można uzyskać zasobu o `Using` instrukcji. Po zakończeniu `Using` bloku [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatycznie usuwa zasobu, aby była ona dostępna dla innych kodu do użycia. Zasób musi być lokalny i możliwe do rozporządzania. Aby uzyskać więcej informacji, zobacz [instrukcji Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Z... Kończyć konstrukcji  
 `With...End With` Konstrukcji pozwala określić odwołanie do obiektu raz, a następnie uruchom serię instrukcji, które uzyskują dostęp do jego elementów członkowskich. Może to uprościć kod i zwiększyć wydajność, ponieważ [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nie trzeba ponownie ustanowić odwołania dla każdej instrukcji, który uzyskuje dostęp do jej. Aby uzyskać więcej informacji, zobacz [z... End With — instrukcja](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Przepływ sterowania](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Struktury decyzji](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Struktury pętli](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Zagnieżdżone struktury sterujące](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using — instrukcja](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [Z... End With — instrukcja](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
