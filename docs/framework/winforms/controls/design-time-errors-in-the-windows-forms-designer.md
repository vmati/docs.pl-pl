---
title: "Błędy czasu projektowania w narzędziu Projektant dla formularzy systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 819b624e2abac09aea804311d661f78e2a1f5a7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="0332c-102">Błędy czasu projektowania w narzędziu Projektant dla formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0332c-102">Design-Time Errors in the Windows Forms Designer</span></span>
<span data-ttu-id="0332c-103">W tym temacie opisano, co oznacza i użyj listy błędów czasu projektowania, który jest wyświetlany w programie Microsoft Visual Studio, gdy projektant formularzy systemu Windows nie udało się załadować.</span><span class="sxs-lookup"><span data-stu-id="0332c-103">This topic explains the meaning and use of the design-time error list that appears in Microsoft Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="0332c-104">Jeśli zostanie wyświetlona lista ten błąd, użytkownik powinien nie go zinterpretować jako błąd w projektancie, ale jako pomoc do poprawiania błędów w kodzie.</span><span class="sxs-lookup"><span data-stu-id="0332c-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>  
  
 <span data-ttu-id="0332c-105">Podstawową wiedzę na temat tej listy błędów pomoże Ci debugowania aplikacji, zapewniając szczegółowe informacje o błędach i sugerowanie możliwych rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="0332c-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>  
  
## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="0332c-106">Interfejs listy błędów w czasie projektowania</span><span class="sxs-lookup"><span data-stu-id="0332c-106">The Design-Time Error List Interface</span></span>  
 <span data-ttu-id="0332c-107">Jeśli projektant formularzy systemu Windows nie może załadować, w Projektancie pojawi się lista błędów.</span><span class="sxs-lookup"><span data-stu-id="0332c-107">If the Windows Forms Designer fails to load, an error list will appear in the designer.</span></span> <span data-ttu-id="0332c-108">Błędy są podzielone na kategorie.</span><span class="sxs-lookup"><span data-stu-id="0332c-108">The errors are grouped into categories.</span></span> <span data-ttu-id="0332c-109">Na przykład jeśli cztery wystąpienia niezadeklarowany zmiennych, te zostaną zgrupowane w tej samej kategorii błąd.</span><span class="sxs-lookup"><span data-stu-id="0332c-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="0332c-110">Każda kategoria błędu zawiera krótki opis podsumowujący błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-110">Each error category includes a brief description that summarizes the error.</span></span>  
  
 <span data-ttu-id="0332c-111">Można rozwinąć lub zwinąć kategorię błędu, albo klikając nagłówek kategorii błąd lub klikając ikonę strzałki Rozwiń/Zwiń.</span><span class="sxs-lookup"><span data-stu-id="0332c-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="0332c-112">Po rozwinięciu kategorię błędu, wyświetlane są następujące dodatkowe pomocy:</span><span class="sxs-lookup"><span data-stu-id="0332c-112">When you expand an error category, the following additional help is displayed:</span></span>  
  
-   <span data-ttu-id="0332c-113">Wystąpienia tego błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-113">Instances of this error.</span></span>  
  
-   <span data-ttu-id="0332c-114">Pomoc dotyczącą tego błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-114">Help with this error.</span></span>  
  
-   <span data-ttu-id="0332c-115">Posty na forum dotyczące tego błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-115">Forum posts about this error.</span></span>  
  
### <a name="instances-of-this-error"></a><span data-ttu-id="0332c-116">Wystąpienia tego błędu</span><span class="sxs-lookup"><span data-stu-id="0332c-116">Instances of This Error</span></span>  
 <span data-ttu-id="0332c-117">Dodatkowej pomocy, wyświetlić listę wszystkich wystąpień błędu w bieżącym projekcie.</span><span class="sxs-lookup"><span data-stu-id="0332c-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="0332c-118">Wiele błędów obejmują dokładna lokalizacja w następującym formacie: *[Nazwa projektu]* *[nazwa formularza]* wiersza:*[numer]* kolumny:*[numer kolumny]*.</span><span class="sxs-lookup"><span data-stu-id="0332c-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="0332c-119">**Przejdź do kodu** łącze prowadzi do lokalizacji w kodzie, w którym występuje błąd.</span><span class="sxs-lookup"><span data-stu-id="0332c-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>  
  
 <span data-ttu-id="0332c-120">Jeśli stos wywołań jest skojarzony z powodu błędu, możesz kliknąć **Pokaż stos wywołań** łącza, które dodatkowo rozszerza błędu można wyświetlić stosu wywołań.</span><span class="sxs-lookup"><span data-stu-id="0332c-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="0332c-121">Badanie stosu zapewniają cenne informacje debugowania.</span><span class="sxs-lookup"><span data-stu-id="0332c-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="0332c-122">Na przykład można śledzić funkcje, które zostały wywołane przed wystąpieniem błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="0332c-123">Stos wywołań jest możliwy, dzięki czemu można skopiować i zapisać go.</span><span class="sxs-lookup"><span data-stu-id="0332c-123">The call stack is selectable so that you can copy and save it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0332c-124">W języku Visual Basic listy błędów czasu projektowania nie są wyświetlane więcej niż jeden błąd, ale mogą wyświetlać wiele wystąpień tego samego błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="0332c-125">W programie Visual C++ błędy nie mają przejdź do kodu numer łącza łącza/linii.</span><span class="sxs-lookup"><span data-stu-id="0332c-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>  
  
### <a name="help-with-this-error"></a><span data-ttu-id="0332c-126">Pomoc dotyczącą tego błędu</span><span class="sxs-lookup"><span data-stu-id="0332c-126">Help with This Error</span></span>  
 <span data-ttu-id="0332c-127">Jeśli błąd zawiera łącze do skojarzonego tematu pomocy MSDN, uzyskać dodatkową pomoc zawiera łącze do tematu Pomocy.</span><span class="sxs-lookup"><span data-stu-id="0332c-127">If the error contains a link to an associated MSDN help topic, the additional help will include a link to the help topic.</span></span> <span data-ttu-id="0332c-128">Po kliknięciu łącza skojarzonego tematu Pomocy pojawia się w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0332c-128">When you click the link, the associated help topic appears in Visual Studio.</span></span>  
  
### <a name="forum-posts-about-this-error"></a><span data-ttu-id="0332c-129">Posty na forum dotyczące tego błędu</span><span class="sxs-lookup"><span data-stu-id="0332c-129">Forum posts about this error</span></span>  
 <span data-ttu-id="0332c-130">Uzyskać dodatkową pomoc zawiera łącze do wpisów forum MSDN dotyczące błędu.</span><span class="sxs-lookup"><span data-stu-id="0332c-130">The additional help will include a link to MSDN forum posts related to the error.</span></span> <span data-ttu-id="0332c-131">Fora przeszukiwane są oparte na ciąg komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="0332c-131">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="0332c-132">Można też spróbować wyszukiwanie fora następujące:</span><span class="sxs-lookup"><span data-stu-id="0332c-132">You can also try searching the following forums:</span></span>  
  
-   [<span data-ttu-id="0332c-133">Forum projektanta formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0332c-133">Windows Forms Designer Forum</span></span>](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [<span data-ttu-id="0332c-134">Fora formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0332c-134">Windows Forms Forums</span></span>](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a><span data-ttu-id="0332c-135">Ignoruj i Kontynuuj</span><span class="sxs-lookup"><span data-stu-id="0332c-135">Ignore and Continue</span></span>  
 <span data-ttu-id="0332c-136">Można zignorować błąd i kontynuować ładowania projektanta.</span><span class="sxs-lookup"><span data-stu-id="0332c-136">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="0332c-137">Wybranie tej akcji może spowodować nieoczekiwane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="0332c-137">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="0332c-138">Na przykład formanty nie może występować na powierzchni projektu.</span><span class="sxs-lookup"><span data-stu-id="0332c-138">For example, controls may not appear on the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0332c-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0332c-139">See Also</span></span>  
 [<span data-ttu-id="0332c-140">Rozwiązywanie problemów z Programowanie w czasie projektowania</span><span class="sxs-lookup"><span data-stu-id="0332c-140">Troubleshooting Design-Time Development</span></span>](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="0332c-141">Rozwiązywanie problemów z formantami oraz autoryzacją</span><span class="sxs-lookup"><span data-stu-id="0332c-141">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [<span data-ttu-id="0332c-142">Opracowywanie formularzy systemu Windows formantów w czasie projektowania</span><span class="sxs-lookup"><span data-stu-id="0332c-142">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="0332c-143">Komunikaty projektanta formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0332c-143">Windows Forms Designer Error Messages</span></span>](http://msdn.microsoft.com/en-us/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)