---
title: "Implements — Klauzula (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="14ffc-102">Implements — Klauzula (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14ffc-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="14ffc-103">Wskazuje, że element członkowski klasy lub struktury dostarcza implementację dla elementu członkowskiego zdefiniowanego w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="14ffc-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14ffc-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="14ffc-104">Remarks</span></span>  
<span data-ttu-id="14ffc-105">`Implements` — Słowo kluczowe nie jest taka sama jak [Implements — instrukcja](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="14ffc-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="14ffc-106">Możesz użyć `Implements` instrukcji, aby określić, że klasy lub struktury implementuje co najmniej jeden interfejs, a następnie dla każdego elementu członkowskiego możesz użyć `Implements` — słowo kluczowe, aby określić, które interfejs i który element członkowski implementuje.</span><span class="sxs-lookup"><span data-stu-id="14ffc-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="14ffc-107">Jeśli klasy lub struktury implementuje interfejs, musi on zawierać `Implements` instrukcji natychmiast po [Class — instrukcja](../../../visual-basic/language-reference/statements/class-statement.md) lub [Structure — instrukcja](../../../visual-basic/language-reference/statements/structure-statement.md), i musi on implementować wszystkie elementy członkowskie zdefiniowane przez interfejs.</span><span class="sxs-lookup"><span data-stu-id="14ffc-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="14ffc-108">Ponowna implementacja</span><span class="sxs-lookup"><span data-stu-id="14ffc-108">Reimplementation</span></span>  
<span data-ttu-id="14ffc-109">W klasie pochodnej można reimplement elementu członkowskiego interfejsu, która już została zaimplementowana klasy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="14ffc-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="14ffc-110">Różni się to od zastępowania elementu członkowskiego klasy podstawowej w następujących aspektach:</span><span class="sxs-lookup"><span data-stu-id="14ffc-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="14ffc-111">Element członkowski klasy podstawowej muszą być [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) do można reimplemented.</span><span class="sxs-lookup"><span data-stu-id="14ffc-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="14ffc-112">Można reimplement elementu członkowskiego z inną nazwą.</span><span class="sxs-lookup"><span data-stu-id="14ffc-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="14ffc-113">`Implements` — Słowo kluczowe może być używana w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="14ffc-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="14ffc-114">Event — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="14ffc-115">Function — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="14ffc-116">Property — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="14ffc-117">Sub — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="14ffc-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="14ffc-118">See Also</span></span>  
 [<span data-ttu-id="14ffc-119">Implements — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="14ffc-120">Interface — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="14ffc-121">Class — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="14ffc-122">Structure — instrukcja</span><span class="sxs-lookup"><span data-stu-id="14ffc-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)