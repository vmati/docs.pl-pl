---
title: "Przy użyciu klasy Activity tworzenia działania przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f4fc6d0807c07952e9b3abe2861ef04bc225142f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="2d5f7-102">Przy użyciu klasy Activity tworzenia działania przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2d5f7-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="2d5f7-103">Najprostszym sposobem tworzenia działania przy użyciu [!INCLUDE[wf](../../../includes/wf-md.md)] w [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] polega na utworzeniu klasy, która dziedziczy <xref:System.Activities.Activity> tworzącą funkcji przez łączenie niestandardowe działania lub działania z [Biblioteka działań wbudowanych ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="2d5f7-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="2d5f7-104">W tym temacie przedstawiono sposób tworzenia działania, która zapisuje dwa komunikaty do konsoli.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="2d5f7-105">Aby utworzyć niestandardowe działanie przy użyciu narzędzia Projektant działań</span><span class="sxs-lookup"><span data-stu-id="2d5f7-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="2d5f7-106">Otwórz [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d5f7-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d5f7-107">Wybierz plik, nowe, projektu.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-107">Select File, New, Project.</span></span> <span data-ttu-id="2d5f7-108">Wybierz **Workflow 4.0** w obszarze **Visual C#** w **typów projektów** okna, a następnie wybierz **v2010** węzła.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="2d5f7-109">Wybierz **Biblioteka działań** w **szablony** okna.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="2d5f7-110">Nazwa nowego projektu HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="2d5f7-111">Otwórz nowe działanie.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-111">Open the new activity.</span></span>  <span data-ttu-id="2d5f7-112">Przeciągnij <xref:System.Activities.Statements.Sequence> działania z przybornika na powierzchnię projektanta.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="2d5f7-113">Przeciągnij <xref:System.Activities.Statements.WriteLine> działania do <xref:System.Activities.Statements.Sequence> działania.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="2d5f7-114">Wprowadź `"Hello World"` (z cudzysłowami) do **tekst** pola.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="2d5f7-115">Przeciągnij drugi <xref:System.Activities.Statements.WriteLine> działania do <xref:System.Activities.Statements.Sequence> działania poniżej pierwsza z nich.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="2d5f7-116">Wprowadź `"Goodbye"` (z cudzysłowami) do **tekst** pola.</span><span class="sxs-lookup"><span data-stu-id="2d5f7-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>