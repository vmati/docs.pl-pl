---
title: "Obsługa automatyzacji interfejsu użytkownika dla typu formantu TabItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tab Item control type
- control types, Tab Item
- UI Automation, Tab Item control type
ms.assetid: 9b21160d-e1c2-468b-9275-26e4369ae40d
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0968118fa2c9c755ad88627a8ee09bed6eb3d19b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-tabitem-control-type"></a><span data-ttu-id="2702e-102">Obsługa automatyzacji interfejsu użytkownika dla kontrolek typu TabItem</span><span class="sxs-lookup"><span data-stu-id="2702e-102">UI Automation Support for the TabItem Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="2702e-103">Ta dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2702e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2702e-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="2702e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="2702e-105">Ten temat zawiera informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] obsługi dla typu formantu TabItem.</span><span class="sxs-lookup"><span data-stu-id="2702e-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the TabItem control type.</span></span> <span data-ttu-id="2702e-106">W [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], typu formantu to zestaw warunków, które muszą spełniać formantu, aby można było używać <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> właściwości.</span><span class="sxs-lookup"><span data-stu-id="2702e-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="2702e-107">Takie szczegółowe wytyczne dla [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struktury drzewa [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] wartości właściwości i wzorce formantu.</span><span class="sxs-lookup"><span data-stu-id="2702e-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values and control patterns.</span></span>  
  
 <span data-ttu-id="2702e-108">Kontrolki elementu karcie jest używana jako kontrolki wewnątrz formantu karty, który wybiera określonej strony ma być wyświetlany w oknie.</span><span class="sxs-lookup"><span data-stu-id="2702e-108">A tab item control is used as the control within a tab control that selects a specific page to be shown in a window.</span></span>  
  
 <span data-ttu-id="2702e-109">Następujące sekcje definiują wymaganych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struktury, właściwości, wzorców formantu i zdarzenia dla typu formantu TabItem drzewa.</span><span class="sxs-lookup"><span data-stu-id="2702e-109">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the TabItem control type.</span></span> <span data-ttu-id="2702e-110">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Wymagania dotyczą wszystkich kontrolek elementu kartę, czy [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], lub [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2702e-110">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all tab item controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="2702e-111">Struktura drzewa automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-111">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="2702e-112">Poniższa tabela przedstawia kontroli i widok zawartości [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewa, które odnoszą się do elementu kartę steruje i opisano, jakie mogą być zawarte w każdym widoku.</span><span class="sxs-lookup"><span data-stu-id="2702e-112">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to tab item controls and describes what can be contained in each view.</span></span> <span data-ttu-id="2702e-113">Aby uzyskać więcej informacji na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewa, zobacz [Przegląd drzewa automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2702e-113">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="2702e-114">Kontrolki widoku</span><span class="sxs-lookup"><span data-stu-id="2702e-114">Control View</span></span>|<span data-ttu-id="2702e-115">Widok zawartości</span><span class="sxs-lookup"><span data-stu-id="2702e-115">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="2702e-116">TabItem</span><span class="sxs-lookup"><span data-stu-id="2702e-116">TabItem</span></span><br /><br /> <ul><li><span data-ttu-id="2702e-117">Obraz (0 lub 1)</span><span class="sxs-lookup"><span data-stu-id="2702e-117">Image (0 or 1)</span></span></li><li><span data-ttu-id="2702e-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="2702e-118">Text</span></span></li><li><span data-ttu-id="2702e-119">Pane</span><span class="sxs-lookup"><span data-stu-id="2702e-119">Pane</span></span><br /><br /> <ul><li><span data-ttu-id="2702e-120">Różnych formantów (0 lub więcej)</span><span class="sxs-lookup"><span data-stu-id="2702e-120">Various controls (0 or more)</span></span></li></ul></li></ul>|<span data-ttu-id="2702e-121">TabItem</span><span class="sxs-lookup"><span data-stu-id="2702e-121">TabItem</span></span><br /><br /> <ul><li><span data-ttu-id="2702e-122">Pane</span><span class="sxs-lookup"><span data-stu-id="2702e-122">Pane</span></span><br /><br /> <ul><li><span data-ttu-id="2702e-123">Różnych formantów (0 lub więcej)</span><span class="sxs-lookup"><span data-stu-id="2702e-123">Various controls (0 or more)</span></span></li></ul></li></ul>|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="2702e-124">Właściwości automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-124">Required UI Automation Properties</span></span>  
 <span data-ttu-id="2702e-125">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] właściwości, której wartość lub definicji jest szczególnie istotne formantów elementu karty.</span><span class="sxs-lookup"><span data-stu-id="2702e-125">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to tab item controls.</span></span> <span data-ttu-id="2702e-126">Aby uzyskać więcej informacji na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] właściwości, zobacz [właściwości automatyzacji interfejsu użytkownika dla klientów](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2702e-126">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="2702e-127">Właściwość</span><span class="sxs-lookup"><span data-stu-id="2702e-127"> Property</span></span>|<span data-ttu-id="2702e-128">Wartość</span><span class="sxs-lookup"><span data-stu-id="2702e-128">Value</span></span>|<span data-ttu-id="2702e-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2702e-129">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="2702e-130">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="2702e-130">See notes.</span></span>|<span data-ttu-id="2702e-131">Wartość tej właściwości musi być unikatowy w obrębie wszystkich kontrolek w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2702e-131">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="2702e-132">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="2702e-132">See notes.</span></span>|<span data-ttu-id="2702e-133">Prostokąt peryferyjnych zawiera całą formantu.</span><span class="sxs-lookup"><span data-stu-id="2702e-133">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="2702e-134">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="2702e-134">See notes.</span></span>|<span data-ttu-id="2702e-135">Karta kontrolki elementu musi mieć kliknięcia, który powoduje, że zostaje zaznaczony element.</span><span class="sxs-lookup"><span data-stu-id="2702e-135">The tab item control must have a clickable point that causes the item to become selected.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="2702e-136">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="2702e-136">See notes.</span></span>|<span data-ttu-id="2702e-137">Formant może przyjmować fokus klawiatury, musi obsługiwać tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="2702e-137">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="2702e-138">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="2702e-138">See notes.</span></span>|<span data-ttu-id="2702e-139">Element formantu jest własnym etykietą.</span><span class="sxs-lookup"><span data-stu-id="2702e-139">The tab item control is self-labeled.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|<span data-ttu-id="2702e-140">Element formantu nie ma etykiety tekst statyczny.</span><span class="sxs-lookup"><span data-stu-id="2702e-140">The tab item control does not have a static text label.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="2702e-141">TabItem</span><span class="sxs-lookup"><span data-stu-id="2702e-141">TabItem</span></span>|<span data-ttu-id="2702e-142">Ta wartość jest taka sama dla wszystkich platform interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2702e-142">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="2702e-143">"element karty"</span><span class="sxs-lookup"><span data-stu-id="2702e-143">"tab item"</span></span>|<span data-ttu-id="2702e-144">Zlokalizowany ciąg odpowiadający tego typu formantu.</span><span class="sxs-lookup"><span data-stu-id="2702e-144">Localized string corresponding to this control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="2702e-145">Wartość true</span><span class="sxs-lookup"><span data-stu-id="2702e-145">True</span></span>|<span data-ttu-id="2702e-146">Element formantu karty musi być zawsze zawartości.</span><span class="sxs-lookup"><span data-stu-id="2702e-146">The tab item control must always be content.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="2702e-147">Wartość true</span><span class="sxs-lookup"><span data-stu-id="2702e-147">True</span></span>|<span data-ttu-id="2702e-148">Element formantu karty musi być zawsze formantu.</span><span class="sxs-lookup"><span data-stu-id="2702e-148">The tab item control must always be a control.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="2702e-149">Wzorce formantów automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-149">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="2702e-150">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] kontrolować wzorców, trzeba być obsługiwana przez formanty elementu kart.</span><span class="sxs-lookup"><span data-stu-id="2702e-150">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by tab item controls.</span></span> <span data-ttu-id="2702e-151">Aby uzyskać więcej informacji na wzorce formantów, zobacz [Przegląd wzorców formantu automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2702e-151">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="2702e-152">— Wzorzec formantu</span><span class="sxs-lookup"><span data-stu-id="2702e-152">Control Pattern</span></span>|<span data-ttu-id="2702e-153">Obsługa</span><span class="sxs-lookup"><span data-stu-id="2702e-153">Support</span></span>|<span data-ttu-id="2702e-154">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2702e-154">Notes</span></span>|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|<span data-ttu-id="2702e-155">Tak</span><span class="sxs-lookup"><span data-stu-id="2702e-155">Yes</span></span>|<span data-ttu-id="2702e-156">Element formantu karty musi obsługiwać klasy SelectionItemPattern.</span><span class="sxs-lookup"><span data-stu-id="2702e-156">The tab item control must support SelectionItemPattern.</span></span>|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|<span data-ttu-id="2702e-157">Nie</span><span class="sxs-lookup"><span data-stu-id="2702e-157">No</span></span>|<span data-ttu-id="2702e-158">Element formantu nigdy nie obsługuje klasy InvokePattern.</span><span class="sxs-lookup"><span data-stu-id="2702e-158">The tab item control never supports InvokePattern.</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="2702e-159">Zdarzeń automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-159">Required UI Automation Events</span></span>  
 <span data-ttu-id="2702e-160">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] zdarzenia wymagane obsługiwane przez wszystkie formanty elementu kart.</span><span class="sxs-lookup"><span data-stu-id="2702e-160">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all tab item controls.</span></span> <span data-ttu-id="2702e-161">Aby uzyskać więcej informacji o zdarzeniach, zobacz [Przegląd zdarzeń automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2702e-161">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="2702e-162">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="2702e-162"> Event</span></span>|<span data-ttu-id="2702e-163">Obsługa</span><span class="sxs-lookup"><span data-stu-id="2702e-163">Support</span></span>|<span data-ttu-id="2702e-164">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2702e-164">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="2702e-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="2702e-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="2702e-166">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-166">Required</span></span>|<span data-ttu-id="2702e-167">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-167">None</span></span>|  
|<span data-ttu-id="2702e-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="2702e-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="2702e-169">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-169">Required</span></span>|<span data-ttu-id="2702e-170">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-170">None</span></span>|  
|<span data-ttu-id="2702e-171"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="2702e-171"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="2702e-172">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-172">Required</span></span>|<span data-ttu-id="2702e-173">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-173">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="2702e-174">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-174">Required</span></span>|<span data-ttu-id="2702e-175">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-175">None</span></span>|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|<span data-ttu-id="2702e-176">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-176">Required</span></span>|<span data-ttu-id="2702e-177">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-177">None</span></span>|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|<span data-ttu-id="2702e-178">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-178">Required</span></span>|<span data-ttu-id="2702e-179">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-179">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="2702e-180">Wymagane</span><span class="sxs-lookup"><span data-stu-id="2702e-180">Required</span></span>|<span data-ttu-id="2702e-181">Brak</span><span class="sxs-lookup"><span data-stu-id="2702e-181">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2702e-182">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2702e-182">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.TabItem>  
 [<span data-ttu-id="2702e-183">Przegląd typów formantu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="2702e-183">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="2702e-184">Przegląd automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="2702e-184">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)