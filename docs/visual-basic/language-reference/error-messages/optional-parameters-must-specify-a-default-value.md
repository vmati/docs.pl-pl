---
title: "Parametry opcjonalne muszą określać wartość domyślną"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords: BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e9ec6d044ba0a1bb904030ddbb4c4fa406c3ba63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Parametry opcjonalne muszą określać wartość domyślną
Parametry opcjonalne podać wartości domyślne, które mogą być używane, jeśli parametr nie zostanie podany przez wywołanie procedury.  
  
 **Identyfikator błędu:** BC30812  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Określ wartości domyślne dla parametrów opcjonalnych; na przykład:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Opcjonalne](../../../visual-basic/language-reference/modifiers/optional.md)
