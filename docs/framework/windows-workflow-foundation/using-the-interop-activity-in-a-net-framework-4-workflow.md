---
title: "Za pomocą działania Interop w przepływie pracy .NET Framework 4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c485a1c2c69169812e69c3bc1ea9969d12467d53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="02a0f-102">Za pomocą działania Interop w przepływie pracy .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="02a0f-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="02a0f-103">Działania utworzone przy użyciu [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] lub [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] mogą być używane w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływu pracy przy użyciu <xref:System.Activities.Statements.Interop> działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="02a0f-104">Ten temat zawiera omówienie sposobu użycia <xref:System.Activities.Statements.Interop> działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02a0f-105"><xref:System.Activities.Statements.Interop> Przybornika projektanta przepływów pracy nie ma działania, chyba że ma projektu przepływu pracy jego **platformy docelowej** ustawienie **.Net Framework 4** lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="02a0f-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="02a0f-106">Za pomocą działania Interop w przepływach pracy programu .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="02a0f-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="02a0f-107">W tym temacie [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] utworzeniu biblioteki działania, który zawiera `DiscountCalculator` działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="02a0f-108">`DiscountCalculator` Jest obliczana na podstawie kwoty zakupu rabat i składa się z <xref:System.Workflow.Activities.SequenceActivity> zawierający <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="02a0f-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02a0f-109">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] Używa działanie utworzone w tym temacie <xref:System.Workflow.Activities.PolicyActivity> wdrożyć logikę działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="02a0f-110">Nie jest wymagane do używania niestandardowej [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] działania lub <xref:System.Activities.Statements.Interop> działania, aby można było używać reguł w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="02a0f-111">Na przykład przy użyciu reguł w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływu pracy bez użycia <xref:System.Activities.Statements.Interop> działania, zobacz [działania zasad w programie .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="02a0f-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="02a0f-112">Aby utworzyć projekt biblioteki działań programu .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="02a0f-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="02a0f-113">Otwórz [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] i wybierz **nowy** , a następnie **projektu...**</span><span class="sxs-lookup"><span data-stu-id="02a0f-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="02a0f-114">z **pliku** menu.</span><span class="sxs-lookup"><span data-stu-id="02a0f-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="02a0f-115">Rozwiń węzeł **inne typy projektów** w węźle **zainstalowane szablony** okienka, a następnie wybierz **rozwiązań programu Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="02a0f-116">Wybierz **puste rozwiązanie** z **rozwiązań programu Visual Studio** listy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="02a0f-117">Typ `PolicyInteropDemo` w **nazwa** polu i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="02a0f-118">Kliknij prawym przyciskiem myszy **PolicyInteropDemo** w **Eksploratora rozwiązań** i wybierz **Dodaj** , a następnie **nowy projekt...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="02a0f-119">Jeśli **Eksploratora rozwiązań** okno nie jest widoczny, wybierz pozycję **Eksploratora rozwiązań** z **widoku** menu.</span><span class="sxs-lookup"><span data-stu-id="02a0f-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="02a0f-120">W **zainstalowane szablony** listy, wybierz **Visual C#** , a następnie **przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="02a0f-121">Wybierz **.NET Framework 3.5** z listy rozwijanej wersji .NET Framework, a następnie wybierz **biblioteki działań przepływów pracy** z **szablony** listy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="02a0f-122">Typ `PolicyActivityLibrary` w **nazwa** polu i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="02a0f-123">Kliknij prawym przyciskiem myszy **Activity1.cs** w **Eksploratora rozwiązań** i wybierz **usunąć**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="02a0f-124">Kliknij przycisk **OK** o potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="02a0f-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="02a0f-125">Aby utworzyć działanie DiscountCalculator</span><span class="sxs-lookup"><span data-stu-id="02a0f-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="02a0f-126">Kliknij prawym przyciskiem myszy **PolicyActivityLibrary** w **Eksploratora rozwiązań** i wybierz **Dodaj** , a następnie **działanie...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="02a0f-127">Wybierz **działania (z separacją kodu)** z **Visual C# elementów** listy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="02a0f-128">Typ `DiscountCalculator` w **nazwa** polu i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="02a0f-129">Kliknij prawym przyciskiem myszy **DiscountCalculator.xoml** w **Eksploratora rozwiązań** i wybierz **kod widoku**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="02a0f-130">Dodaj następujące trzy właściwości `DiscountCalculator` klasy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="02a0f-131">Kliknij prawym przyciskiem myszy **DiscountCalculator.xoml** w **Eksploratora rozwiązań** i wybierz **Widok projektanta**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="02a0f-132">Przeciągnij **zasad** działania z **Windows Workflow 3.0** sekcji **przybornika** i upuść je w **DiscountCalculator** działania .</span><span class="sxs-lookup"><span data-stu-id="02a0f-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="02a0f-133">Jeśli **przybornika** okno nie jest widoczny, wybierz pozycję **przybornika** z **widoku** menu.</span><span class="sxs-lookup"><span data-stu-id="02a0f-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="02a0f-134">Aby skonfigurować reguły</span><span class="sxs-lookup"><span data-stu-id="02a0f-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="02a0f-135">Kliknij nowo dodany **zasad** działania, aby wybrać, jeśli nie została jeszcze wybrana.</span><span class="sxs-lookup"><span data-stu-id="02a0f-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="02a0f-136">Kliknij przycisk **RuleSetReference** właściwości w **właściwości** okno, aby go zaznaczyć, a następnie kliknij przycisk wielokropka z prawej strony właściwości.</span><span class="sxs-lookup"><span data-stu-id="02a0f-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="02a0f-137">Jeśli **właściwości** okna nie jest widoczne, wybierz **okna właściwości** z **widoku** menu.</span><span class="sxs-lookup"><span data-stu-id="02a0f-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="02a0f-138">Wybierz **kliknij nowy...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="02a0f-139">Kliknij przycisk **Dodaj regułę**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="02a0f-140">Wpisz następujące wyrażenie w **warunku** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="02a0f-141">Wpisz następujące wyrażenie w **następnie akcje** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="02a0f-142">Kliknij przycisk **Dodaj regułę**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="02a0f-143">Wpisz następujące wyrażenie w **warunku** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="02a0f-144">Wpisz następujące wyrażenie w **następnie akcje** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="02a0f-145">Kliknij przycisk **Dodaj regułę**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="02a0f-146">Wpisz następujące wyrażenie w **warunku** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="02a0f-147">Wpisz następujące wyrażenie w **następnie akcje** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="02a0f-148">Wpisz następujące wyrażenie w **Else akcje** pole.</span><span class="sxs-lookup"><span data-stu-id="02a0f-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="02a0f-149">Kliknij przycisk **OK** zamknąć **Edytor ustawić reguły** okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="02a0f-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="02a0f-150">Upewnij się, że nowo utworzonego <xref:System.Workflow.Activities.Rules.RuleSet> wybrano **nazwa** listy, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="02a0f-151">Naciśnij klawisze CTRL + SHIFT + B w celu skompilowania rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="02a0f-152">Dodane do reguły `DiscountCalculator` działania w tej procedurze przedstawiono w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="02a0f-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="02a0f-153">Podczas <xref:System.Workflow.Activities.PolicyActivity> wykonuje te trzy zasady oceny i zmodyfikuj `Subtotal`, `DiscountPercent`, i `Total` wartości właściwości `DiscountCalculator` do obliczania rabatu odpowiednie działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="02a0f-154">Używanie działania DiscountCalculator z działania Interop</span><span class="sxs-lookup"><span data-stu-id="02a0f-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="02a0f-155">Aby użyć `DiscountCalculator` działania wewnątrz [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływu pracy, <xref:System.Activities.Statements.Interop> to działanie służy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="02a0f-156">W tej sekcji dwa przepływy pracy są tworzone, jeden przy użyciu kodu i jeden za pomocą projektanta przepływów pracy, które pokazują, jak używać <xref:System.Activities.Statements.Interop> działania `DiscountCalculator` działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="02a0f-157">Ta sama aplikacja hosta jest używana dla obu przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="02a0f-158">Aby utworzyć aplikację hosta</span><span class="sxs-lookup"><span data-stu-id="02a0f-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="02a0f-159">Kliknij prawym przyciskiem myszy **PolicyInteropDemo** w **Eksploratora rozwiązań** i wybierz **Dodaj**, a następnie **nowy projekt...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="02a0f-160">Upewnij się, że **.NET Framework 4.5** jest zaznaczona na liście rozwijanej wersji .NET Framework, a następnie wybierz **Aplikacja konsoli przepływu pracy** z **Visual C# elementów** listy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="02a0f-161">Typ `PolicyInteropHost` do **nazwa** polu i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="02a0f-162">Kliknij prawym przyciskiem myszy **PolicyInteropHost** w **Eksploratora rozwiązań** i wybierz **właściwości**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="02a0f-163">W **platformy docelowej** listy rozwijanej liście, wybór z **.NET Framework 4 Client Profile** do **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="02a0f-164">Kliknij przycisk **tak** o potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="02a0f-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="02a0f-165">Kliknij prawym przyciskiem myszy **PolicyInteropHost** w **Eksploratora rozwiązań** i wybierz **Dodawanie odwołania...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="02a0f-166">Wybierz **PolicyActivityLibrary** z **projekty** i kliknij polecenie **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="02a0f-167">Kliknij prawym przyciskiem myszy **PolicyInteropHost** w **Eksploratora rozwiązań** i wybierz **Dodawanie odwołania...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="02a0f-168">Wybierz **System.Workflow.Activities**, **System.Workflow.ComponentModel**, a następnie **System.Workflow.Runtime** z **.NET**i kliknij polecenie **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="02a0f-169">Kliknij prawym przyciskiem myszy **PolicyInteropHost** w **Eksploratora rozwiązań** i wybierz **Ustaw jako projekt startowy**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="02a0f-170">Naciśnij klawisze CTRL + SHIFT + B w celu skompilowania rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="02a0f-171">Za pomocą działania Interop w kodzie</span><span class="sxs-lookup"><span data-stu-id="02a0f-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="02a0f-172">W tym przykładzie definicji przepływu pracy jest tworzony przy użyciu kodu, który zawiera <xref:System.Activities.Statements.Interop> działania i `DiscountCalculator` działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="02a0f-173">Ten przepływ pracy jest wywoływana przy użyciu <xref:System.Activities.WorkflowInvoker> i wyniki oceny reguły są zapisywane w konsoli przy użyciu <xref:System.Activities.Statements.WriteLine> działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="02a0f-174">Aby użyć działania Interop w kodzie</span><span class="sxs-lookup"><span data-stu-id="02a0f-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="02a0f-175">Kliknij prawym przyciskiem myszy **Program.cs** w **Eksploratora rozwiązań** i wybierz **kod widoku**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="02a0f-176">Dodaj następujące `using` instrukcji w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="02a0f-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="02a0f-177">Usuń zawartość `Main` metodę i Zastąp następujący kod.</span><span class="sxs-lookup"><span data-stu-id="02a0f-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="02a0f-178">Utworzenie nowej metody w `Program` klasy o nazwie `CalculateDiscountUsingCodeWorkflow` zawierający następujący kod.</span><span class="sxs-lookup"><span data-stu-id="02a0f-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="02a0f-179">`Subtotal`, `DiscountPercent`, I `Total` właściwości `DiscountCalculator` działania są udostępniane jako argumenty <xref:System.Activities.Statements.Interop> działania i zmienne powiązane z lokalnego przepływu pracy w <xref:System.Activities.Statements.Interop> działania <xref:System.Activities.Statements.Interop.ActivityProperties%2A> Kolekcja.</span><span class="sxs-lookup"><span data-stu-id="02a0f-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="02a0f-180">`Subtotal`zostanie dodany jako <xref:System.Activities.ArgumentDirection.In> argument ponieważ `Subtotal` dane przepływają w <xref:System.Activities.Statements.Interop> działania, i `DiscountPercent` i `Total` są dodawane jako <xref:System.Activities.ArgumentDirection.Out> argumenty ponieważ ich dane przepływają poza <xref:System.Activities.Statements.Interop> działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="02a0f-181">Należy pamiętać, że dwa <xref:System.Activities.ArgumentDirection.Out> argumenty są dodawane z nazwami `DiscountPercentOut` i `TotalOut` aby wskazać, że reprezentują <xref:System.Activities.ArgumentDirection.Out> argumentów.</span><span class="sxs-lookup"><span data-stu-id="02a0f-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="02a0f-182">`DiscountCalculator` Typ jest określony jako <xref:System.Activities.Statements.Interop> działania <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span><span class="sxs-lookup"><span data-stu-id="02a0f-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="02a0f-183">Naciśnij klawisze CTRL + F5, aby skompilować i uruchomić aplikację.</span><span class="sxs-lookup"><span data-stu-id="02a0f-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="02a0f-184">Zastąp różnych wartości `Subtotal` wartość przetestować poziomy różnych rabat pochodzącymi `DiscountCalculator` działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="02a0f-185">Za pomocą działania Interop w Projektancie przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="02a0f-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="02a0f-186">W tym przykładzie przepływ pracy jest tworzony przy użyciu projektanta przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="02a0f-187">Ten przepływ pracy ma te same funkcje co w poprzednim przykładzie, z wyjątkiem niż zamiast <xref:System.Activities.Statements.WriteLine> działanie, aby wyświetlić rabatu aplikacji hosta pobiera i wyświetla informacje o rabat po zakończeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="02a0f-188">Ponadto zamiast za pomocą zmiennych lokalnych przepływu pracy zawierają dane, argumenty są tworzone w Projektancie przepływów pracy i wartości są przekazywane w z hosta po wywołaniu przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="02a0f-189">Do obsługi działania PolicyActivity za pomocą przepływu pracy utworzone w Projektancie przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="02a0f-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="02a0f-190">Kliknij prawym przyciskiem myszy **Workflow1.xaml** w **Eksploratora rozwiązań** i wybierz **usunąć**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="02a0f-191">Kliknij przycisk **OK** o potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="02a0f-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="02a0f-192">Kliknij prawym przyciskiem myszy **PolicyInteropHost** w **Eksploratora rozwiązań** i wybierz **Dodaj**, **nowy element...** .</span><span class="sxs-lookup"><span data-stu-id="02a0f-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="02a0f-193">Rozwiń węzeł **Visual C# elementów** a następnie wybierz węzeł **przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="02a0f-194">Wybierz **działania** z **Visual C# elementów** listy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="02a0f-195">Typ `DiscountWorkflow` do **nazwa** polu i kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="02a0f-196">Kliknij przycisk **argumenty** przycisk na dole po lewej stronie projektanta przepływów pracy, aby wyświetlić **argumenty** okienka.</span><span class="sxs-lookup"><span data-stu-id="02a0f-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="02a0f-197">Kliknij przycisk **utworzenia argumentu**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="02a0f-198">Typ `Subtotal` do **nazwa** wybierz opcję **w** z **kierunek** listy rozwijanej, wybierz pozycję **podwójne** z **Typ argumentu** listy rozwijanej, a następnie naciśnij klawisz ENTER, aby zapisać argument.</span><span class="sxs-lookup"><span data-stu-id="02a0f-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a0f-199">Jeśli **podwójne** nie znajduje się w **typ argumentu** listy rozwijanej wybierz **Przeglądaj w poszukiwaniu typów...** , typ `System.Double` w **nazwy typu** i kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="02a0f-200">Kliknij przycisk **utworzenia argumentu**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="02a0f-201">Typ `DiscountPercent` do **nazwa** wybierz opcję **limit** z **kierunek** listy rozwijanej, wybierz pozycję **podwójne** z **Typ argumentu** listy rozwijanej, a następnie naciśnij klawisz ENTER, aby zapisać argument.</span><span class="sxs-lookup"><span data-stu-id="02a0f-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="02a0f-202">Kliknij przycisk **utworzenia argumentu**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="02a0f-203">Typ `Total` do **nazwa** wybierz opcję **limit** z **kierunek** listy rozwijanej, wybierz pozycję **podwójne** z **Typ argumentu** listy rozwijanej, a następnie naciśnij klawisz ENTER, aby zapisać argument.</span><span class="sxs-lookup"><span data-stu-id="02a0f-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="02a0f-204">Kliknij przycisk **argumenty** przycisk na dole po lewej stronie projektanta przepływów pracy, aby zamknąć **argumenty** okienka.</span><span class="sxs-lookup"><span data-stu-id="02a0f-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="02a0f-205">Przeciągnij **sekwencji** działania z **przepływ sterowania** sekcji **przybornika** i upuść ją na powierzchnię projektanta przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="02a0f-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="02a0f-206">Przeciągnij **międzyoperacyjności** działania z **migracji** sekcji **przybornika** i upuść je w **sekwencji** działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="02a0f-207">Kliknij przycisk **międzyoperacyjności** działania na **kliknij, aby przeglądać...**</span><span class="sxs-lookup"><span data-stu-id="02a0f-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="02a0f-208">Etykieta, wpisz **DiscountCalculator** w **nazwy typu** i kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a0f-209">Gdy <xref:System.Activities.Statements.Interop> działania zostanie dodany do przepływu pracy i `DiscountCalculator` typ jest określony jako jego <xref:System.Activities.Statements.Interop.ActivityType%2A>, <xref:System.Activities.Statements.Interop> działania udostępnia trzy <xref:System.Activities.ArgumentDirection.In> argumentów i trzy <xref:System.Activities.ArgumentDirection.Out> argumenty, które reprezentują trzy publicznego właściwości `DiscountCalculator` działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="02a0f-210"><xref:System.Activities.ArgumentDirection.In> Argumenty mają taką samą nazwę jak trzy właściwości publiczne i trzech <xref:System.Activities.ArgumentDirection.Out> argumenty mają takie same nazwy z **limit** dołączonym do nazwy właściwości.</span><span class="sxs-lookup"><span data-stu-id="02a0f-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="02a0f-211">W poniższych krokach argumenty przepływu pracy utworzone w poprzednich krokach jest powiązana z <xref:System.Activities.Statements.Interop> argumentów działania.</span><span class="sxs-lookup"><span data-stu-id="02a0f-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="02a0f-212">Typ `DiscountPercent` do **wprowadź wyrażenia języka VB.** pole z prawej strony **DiscountPercentOut** właściwości i naciśnij klawisz TAB.</span><span class="sxs-lookup"><span data-stu-id="02a0f-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="02a0f-213">Typ `Subtotal` do **wprowadź wyrażenia języka VB.** pole z prawej strony **Suma częściowa** właściwości i naciśnij klawisz TAB.</span><span class="sxs-lookup"><span data-stu-id="02a0f-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="02a0f-214">Typ `Total` do **wprowadź wyrażenia języka VB.** pole z prawej strony **TotalOut** właściwości i naciśnij klawisz TAB.</span><span class="sxs-lookup"><span data-stu-id="02a0f-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="02a0f-215">Kliknij prawym przyciskiem myszy **Program.cs** w **Eksploratora rozwiązań** i wybierz **kod widoku**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="02a0f-216">Dodaj następujące `using` instrukcji w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="02a0f-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="02a0f-217">Komentarz wywołanie `CalculateDiscountInCode` metoda `Main` — metoda i Dodaj następujący kod.</span><span class="sxs-lookup"><span data-stu-id="02a0f-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a0f-218">Jeśli nie wykonaniu poprzedniej procedury i domyślnie `Main` kodu, Zastąp zawartość `Main` z następującym kodem.</span><span class="sxs-lookup"><span data-stu-id="02a0f-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="02a0f-219">Utworzenie nowej metody w `Program` klasy o nazwie `CalculateDiscountUsingDesignerWorkflow` zawierający następujący kod.</span><span class="sxs-lookup"><span data-stu-id="02a0f-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="02a0f-220">Naciśnij klawisze CTRL + F5, aby skompilować i uruchomić aplikację.</span><span class="sxs-lookup"><span data-stu-id="02a0f-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="02a0f-221">Aby określić inną `Subtotal` ilość, zmień wartość `SubtotalValue` w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="02a0f-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="02a0f-222">Przegląd funkcji reguły</span><span class="sxs-lookup"><span data-stu-id="02a0f-222">Rules Features Overview</span></span>  
 <span data-ttu-id="02a0f-223">[!INCLUDE[wf1](../../../includes/wf1-md.md)] Aparatu reguł zapewnia obsługę przetwarzania reguły w sposób oparte na priorytetach obsługę do przodu łańcucha.</span><span class="sxs-lookup"><span data-stu-id="02a0f-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="02a0f-224">Reguły może przyjąć pojedynczy element lub elementy w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="02a0f-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="02a0f-225">Omówienie zasad i informacji na temat reguł określonych funkcji można znaleźć w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="02a0f-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="02a0f-226">Funkcja reguł</span><span class="sxs-lookup"><span data-stu-id="02a0f-226">Rules Feature</span></span>|<span data-ttu-id="02a0f-227">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="02a0f-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="02a0f-228">Przegląd zasad</span><span class="sxs-lookup"><span data-stu-id="02a0f-228">Rules Overview</span></span>|[<span data-ttu-id="02a0f-229">Wprowadzenie do aparatu reguł systemu Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="02a0f-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="02a0f-230">Zestaw reguł</span><span class="sxs-lookup"><span data-stu-id="02a0f-230">RuleSet</span></span>|<span data-ttu-id="02a0f-231">[Używanie zestawów reguł w przepływach pracy](http://go.microsoft.com/fwlink/?LinkId=178516) i<xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="02a0f-231">[Using RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="02a0f-232">Ocena zasad</span><span class="sxs-lookup"><span data-stu-id="02a0f-232">Evaluation of Rules</span></span>|[<span data-ttu-id="02a0f-233">Zasady oceny w zestawy reguł</span><span class="sxs-lookup"><span data-stu-id="02a0f-233">Rules Evaluation in RuleSets</span></span>](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="02a0f-234">Reguły łańcucha</span><span class="sxs-lookup"><span data-stu-id="02a0f-234">Rules Chaining</span></span>|<span data-ttu-id="02a0f-235">[Przekazuj łańcucha kontroli](http://go.microsoft.com/fwlink/?LinkId=178518) i [do przodu łańcucha zasad](http://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="02a0f-235">[Forward Chaining Control](http://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](http://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="02a0f-236">Przetwarzanie kolekcje reguł</span><span class="sxs-lookup"><span data-stu-id="02a0f-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="02a0f-237">Przetwarzanie kolekcje reguł</span><span class="sxs-lookup"><span data-stu-id="02a0f-237">Processing Collections in Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="02a0f-238">Za pomocą działania PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="02a0f-238">Using the PolicyActivity</span></span>|<span data-ttu-id="02a0f-239">[Za pomocą działania działania PolicyActivity](http://go.microsoft.com/fwlink/?LinkId=178521) i<xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="02a0f-239">[Using the PolicyActivity Activity](http://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="02a0f-240">Przepływy pracy utworzone w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] nie korzystać ze wszystkich funkcji zasad udostępnionych przez [!INCLUDE[wf1](../../../includes/wf1-md.md)], takie jak warunki deklaratywne działania i warunkowego działań, takich jak <xref:System.Workflow.Activities.ConditionedActivityGroup> i <xref:System.Workflow.Activities.ReplicatorActivity>.</span><span class="sxs-lookup"><span data-stu-id="02a0f-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="02a0f-241">Jeśli jest to wymagane, ta funkcja jest dostępna dla przepływów pracy utworzony za pomocą [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] i [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a0f-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="02a0f-242">[Wskazówki dotyczące migracji](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="02a0f-242"> [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>