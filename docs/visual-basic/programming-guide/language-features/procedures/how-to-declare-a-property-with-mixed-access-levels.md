---
title: "Porady: deklarowanie właściwości z mieszanymi poziomami dostępu (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="3f0df-102">Porady: deklarowanie właściwości z mieszanymi poziomami dostępu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f0df-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="3f0df-103">Jeśli chcesz `Get` i `Set` procedur we właściwości w celu mają różne poziomy dostępu, można użyć poziomu mniej ograniczająca w `Property` instrukcji i bardziej restrykcyjne poziomu w jednym `Get` lub `Set` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3f0df-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="3f0df-104">Mieszanymi poziomami dostępu można używać we właściwości, gdy chce niektórych części kodu, aby można było pobrać wartości właściwości i części kodu, aby można było zmienić wartość.</span><span class="sxs-lookup"><span data-stu-id="3f0df-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="3f0df-105">Aby uzyskać więcej informacji na temat poziomów dostępu, zobacz [poziomy w języku Visual Basic dostępu](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3f0df-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="3f0df-106">Deklarowanie właściwości z mieszanymi poziomami dostępu</span><span class="sxs-lookup"><span data-stu-id="3f0df-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="3f0df-107">Deklarowanie właściwości w zwykły sposób, a następnie określ poziom dostępu mniej restrykcyjny (takich jak `Public`) w `Property` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3f0df-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="3f0df-108">Deklarowanie albo `Get` lub `Set` procedurę określając bardziej restrykcyjne poziom dostępu (takie jak `Friend`).</span><span class="sxs-lookup"><span data-stu-id="3f0df-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="3f0df-109">Nie określaj poziom dostępu w procedurze właściwości.</span><span class="sxs-lookup"><span data-stu-id="3f0df-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="3f0df-110">Zakłada się poziom dostępu zadeklarowany w `Property` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3f0df-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="3f0df-111">Można ograniczyć dostęp tylko dla jednej z właściwości procedur.</span><span class="sxs-lookup"><span data-stu-id="3f0df-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="3f0df-112">W poprzednim przykładzie `Get` procedura ma taką samą `Protected` dostępu jako właściwość, gdy `Set` procedura ma `Private` dostępu.</span><span class="sxs-lookup"><span data-stu-id="3f0df-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="3f0df-113">Klasa pochodna od `employee` może odczytywać `salary` wartość, ale tylko `employee` klasy może go ustawić.</span><span class="sxs-lookup"><span data-stu-id="3f0df-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0df-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f0df-114">See Also</span></span>  
 [<span data-ttu-id="3f0df-115">Procedury</span><span class="sxs-lookup"><span data-stu-id="3f0df-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3f0df-116">Procedury własności</span><span class="sxs-lookup"><span data-stu-id="3f0df-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3f0df-117">Parametry i argumenty procedur</span><span class="sxs-lookup"><span data-stu-id="3f0df-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3f0df-118">Property — instrukcja</span><span class="sxs-lookup"><span data-stu-id="3f0df-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="3f0df-119">Różnice pomiędzy właściwościami i zmiennymi w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f0df-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="3f0df-120">Porady: Tworzenie właściwości</span><span class="sxs-lookup"><span data-stu-id="3f0df-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="3f0df-121">Porady: wywoływanie procedury właściwości</span><span class="sxs-lookup"><span data-stu-id="3f0df-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="3f0df-122">Porady: deklarowanie i wywoływanie w właściwości domyślnej w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f0df-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="3f0df-123">Porady: umieszczanie wartości we właściwości</span><span class="sxs-lookup"><span data-stu-id="3f0df-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="3f0df-124">Porady: pobieranie wartości z właściwości</span><span class="sxs-lookup"><span data-stu-id="3f0df-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)