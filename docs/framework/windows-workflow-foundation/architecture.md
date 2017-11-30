---
title: "Architektura przepływu pracy systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c34b1af9c5fd93d57e94d959abe69f32572f7b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="windows-workflow-architecture"></a><span data-ttu-id="7de4b-102">Architektura przepływu pracy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="7de4b-102">Windows Workflow Architecture</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="7de4b-103">podnosi poziom abstrakcji umożliwiający projektowanie aplikacji interaktywnych długotrwałe.</span><span class="sxs-lookup"><span data-stu-id="7de4b-103"> raises the abstraction level for developing interactive long-running applications.</span></span> <span data-ttu-id="7de4b-104">Jednostki pracy są hermetyzowane jako działania.</span><span class="sxs-lookup"><span data-stu-id="7de4b-104">Units of work are encapsulated as activities.</span></span> <span data-ttu-id="7de4b-105">Działań uruchamianych w środowisku, które zapewnia ułatwienia sterowanie przepływem, obsługa wyjątków, błędów propagacji trwałości danych o stanie, ładowanie i zwalnianie przepływów pracy w toku z pamięci, śledzenia i przepływu transakcji.</span><span class="sxs-lookup"><span data-stu-id="7de4b-105">Activities run in an environment that provides facilities for flow control, exception handling, fault propagation, persistence of state data, loading and unloading of in-progress workflows from memory, tracking, and transaction flow.</span></span>  
  
## <a name="activity-architecture"></a><span data-ttu-id="7de4b-106">Architektura działania</span><span class="sxs-lookup"><span data-stu-id="7de4b-106">Activity Architecture</span></span>  
 <span data-ttu-id="7de4b-107">Działania są tworzone jako typów CLR, które pochodzą z dowolnej <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, lub <xref:System.Activities.NativeActivity>, lub ich wariantów, które zwracają wartości, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, lub <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="7de4b-107">Activities are developed as CLR types that derive from either <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>, or their variants that return a value, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, or <xref:System.Activities.NativeActivity%601>.</span></span> <span data-ttu-id="7de4b-108">Tworzenie działań, które pochodzą z <xref:System.Activities.Activity> zezwala użytkownikowi na składanie istniejące działania do szybkiego tworzenia jednostek pracy, które są wykonywane w środowisku przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="7de4b-108">Developing activities that derive from <xref:System.Activities.Activity> allows the user to assemble pre-existing activities to quickly create units of work that execute in the workflow environment.</span></span> <span data-ttu-id="7de4b-109"><xref:System.Activities.CodeActivity>, z drugiej strony, umożliwia wykonywanie logiki do maszyny wirtualnej można tworzyć za pomocą kodu zarządzanego <xref:System.Activities.CodeActivityContext> głównie do uzyskiwania dostępu do argumentów działania.</span><span class="sxs-lookup"><span data-stu-id="7de4b-109"><xref:System.Activities.CodeActivity>, on the other hand, enables execution logic to be authored in managed code using <xref:System.Activities.CodeActivityContext> primarily for access to activity arguments.</span></span> <span data-ttu-id="7de4b-110"><xref:System.Activities.AsyncCodeActivity>przypomina <xref:System.Activities.CodeActivity> z tą różnicą, że może służyć do wykonania zadania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="7de4b-110"><xref:System.Activities.AsyncCodeActivity> is similar to <xref:System.Activities.CodeActivity> except that it can be used to implement asynchronous tasks.</span></span> <span data-ttu-id="7de4b-111">Tworzenie działań, które pochodzą z <xref:System.Activities.NativeActivity> umożliwia użytkownikom uzyskiwanie dostępu do środowiska uruchomieniowego za pośrednictwem <xref:System.Activities.NativeActivityContext> dla funkcji takich jak zaplanowaniem działań podrzędnych, tworzenia zakładek, wywołania asynchroniczne, rejestrowania transakcji i inne.</span><span class="sxs-lookup"><span data-stu-id="7de4b-111">Developing activities that derive from <xref:System.Activities.NativeActivity> allows users to access the runtime through the <xref:System.Activities.NativeActivityContext> for functionality like scheduling children, creating bookmarks, invoking asynchronous work, registering transactions, and more.</span></span>  
  
 <span data-ttu-id="7de4b-112">Tworzenie działań, które pochodzą z <xref:System.Activities.Activity> jest deklaratywne i tych działań można tworzyć w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="7de4b-112">Authoring activities that derive from <xref:System.Activities.Activity> is declarative and these activities can be authored in XAML.</span></span> <span data-ttu-id="7de4b-113">W poniższym przykładzie działanie o nazwie `Prompt` jest tworzony przy użyciu innych działań dla treści wykonywania.</span><span class="sxs-lookup"><span data-stu-id="7de4b-113">In the following example, an activity called `Prompt` is created using other activities for the execution body.</span></span>  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a><span data-ttu-id="7de4b-114">Kontekst działania</span><span class="sxs-lookup"><span data-stu-id="7de4b-114">Activity Context</span></span>  
 <span data-ttu-id="7de4b-115"><xref:System.Activities.ActivityContext> Jest interfejsem autora działania do środowiska uruchomieniowego przepływu pracy i zapewnia dostęp do środowiska uruchomieniowego wiele funkcji.</span><span class="sxs-lookup"><span data-stu-id="7de4b-115">The <xref:System.Activities.ActivityContext> is the activity author's interface to the workflow runtime and provides access to the runtime's wealth of features.</span></span> <span data-ttu-id="7de4b-116">W poniższym przykładzie działanie zdefiniowano używaną do tworzenia zakładek (mechanizm, który umożliwia działanie, aby zarejestrować punkt kontynuacji można wznowić przez hosta przekazywanie danych do działania na jej wykonanie) kontekstu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="7de4b-116">In the following example, an activity is defined that uses the execution context to create a bookmark (the mechanism that allows an activity to register a continuation point in its execution that can be resumed by a host passing data into the activity).</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a><span data-ttu-id="7de4b-117">Cykl życia działania</span><span class="sxs-lookup"><span data-stu-id="7de4b-117">Activity Life Cycle</span></span>  
 <span data-ttu-id="7de4b-118">Wystąpienia działania rozpoczyna się <xref:System.Activities.ActivityInstanceState.Executing> stanu.</span><span class="sxs-lookup"><span data-stu-id="7de4b-118">An instance of an activity starts out in the <xref:System.Activities.ActivityInstanceState.Executing> state.</span></span> <span data-ttu-id="7de4b-119">Jeśli wystąpią wyjątki, pozostaje w tym stanie zakończenie wszystkich działań podrzędnych to wykonywania i inne oczekujące pracy (<xref:System.Activities.Bookmark> obiektów, na przykład) zostało zakończone, w tym momencie przejścia do <xref:System.Activities.ActivityInstanceState.Closed> stanu.</span><span class="sxs-lookup"><span data-stu-id="7de4b-119">Unless exceptions are encountered, it remains in this state until all child activities are finished executing and any other pending work (<xref:System.Activities.Bookmark> objects, for instance) is completed, at which point it transitions to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="7de4b-120">Element nadrzędny wystąpienia działania mogą żądać element podrzędny, aby anulować; Jeśli obiekt podrzędny jest w stanie anulować ukończy w <xref:System.Activities.ActivityInstanceState.Canceled> stanu.</span><span class="sxs-lookup"><span data-stu-id="7de4b-120">The parent of an activity instance can request a child to cancel; if the child is able to be canceled it completes in the <xref:System.Activities.ActivityInstanceState.Canceled> state.</span></span> <span data-ttu-id="7de4b-121">Jeśli podczas wykonywania jest zgłaszany wyjątek, środowisko uruchomieniowe umieszcza działania do <xref:System.Activities.ActivityInstanceState.Faulted> stanu i propaguje wyjątek zapasowej łańcucha nadrzędnego działań.</span><span class="sxs-lookup"><span data-stu-id="7de4b-121">If an exception is thrown during execution, the runtime puts the activity into the <xref:System.Activities.ActivityInstanceState.Faulted> state and propagates the exception up the parent chain of activities.</span></span> <span data-ttu-id="7de4b-122">Stany trzy zakończenia działania są następujące:</span><span class="sxs-lookup"><span data-stu-id="7de4b-122">Following are the three completion states of an activity:</span></span>  
  
-   <span data-ttu-id="7de4b-123">**Zamknięte:** ukończył pracę i zakończył działanie.</span><span class="sxs-lookup"><span data-stu-id="7de4b-123">**Closed:** The activity has completed its work and exited.</span></span>  
  
-   <span data-ttu-id="7de4b-124">**Anulowane:** działanie ma bezpiecznie porzucone jego pracy i zakończony.</span><span class="sxs-lookup"><span data-stu-id="7de4b-124">**Canceled:** The activity has gracefully abandoned its work and exited.</span></span> <span data-ttu-id="7de4b-125">Praca nie jest jawnie agregowana po wprowadzeniu tego stanu.</span><span class="sxs-lookup"><span data-stu-id="7de4b-125">Work is not explicitly rolled back when this state is entered.</span></span>  
  
-   <span data-ttu-id="7de4b-126">**Błąd:** działania napotkał błąd i zakończył działanie bez ukończenia pracy.</span><span class="sxs-lookup"><span data-stu-id="7de4b-126">**Faulted:** The activity has encountered an error and has exited without completing its work.</span></span>  
  
 <span data-ttu-id="7de4b-127">Działania pozostają w <xref:System.Activities.ActivityInstanceState.Executing> stanu, gdy są one utrwalona lub zwalnianie modułu.</span><span class="sxs-lookup"><span data-stu-id="7de4b-127">Activities remain in the <xref:System.Activities.ActivityInstanceState.Executing> state when they are persisted or unloaded.</span></span>