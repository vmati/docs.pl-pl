---
title: "Optymalizacja wydajności: układ i projekt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 13763e0487314fdbe7ab6fcb8b7b8711715e7a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-layout-and-design"></a><span data-ttu-id="76f44-102">Optymalizacja wydajności: układ i projekt</span><span class="sxs-lookup"><span data-stu-id="76f44-102">Optimizing Performance: Layout and Design</span></span>
<span data-ttu-id="76f44-103">Projekt sieci [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikacji może wpłynąć na jego wydajność, tworząc niepotrzebnego obciążenia obliczania układ i sprawdzanie poprawności odwołania do obiektów.</span><span class="sxs-lookup"><span data-stu-id="76f44-103">The design of your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can impact its performance by creating unnecessary overhead in calculating layout and validating object references.</span></span> <span data-ttu-id="76f44-104">Konstrukcja obiektów, szczególnie w czasie wykonywania mogą wpłynąć na charakterystykę wydajności aplikacji.</span><span class="sxs-lookup"><span data-stu-id="76f44-104">The construction of objects, particularly at run time, can affect the performance characteristics of your application.</span></span>  
  
 <span data-ttu-id="76f44-105">Ten temat zawiera zalecenia dotyczące wydajności w następujących obszarach.</span><span class="sxs-lookup"><span data-stu-id="76f44-105">This topic provides performance recommendations in these areas.</span></span>  
  
## <a name="layout"></a><span data-ttu-id="76f44-106">Układ</span><span class="sxs-lookup"><span data-stu-id="76f44-106">Layout</span></span>  
 <span data-ttu-id="76f44-107">Termin "przebiegu układu" opisano proces pomiarów i rozmieszczanie elementów członkowskich <xref:System.Windows.Controls.Panel>-pochodnych kolekcję elementów podrzędnych, a następnie je na ekranie rysowania obiektu.</span><span class="sxs-lookup"><span data-stu-id="76f44-107">The term "layout pass" describes the process of measuring and arranging the members of a <xref:System.Windows.Controls.Panel>-derived object's collection of children, and then drawing them onscreen.</span></span> <span data-ttu-id="76f44-108">Przebiegu układ jest procesem ze sobą matematycznie intensywnie — im jest większa liczba elementów podrzędnych w kolekcji, im większa liczba wyliczenia wymagane.</span><span class="sxs-lookup"><span data-stu-id="76f44-108">The layout pass is a mathematically-intensive process—the larger the number of children in the collection, the greater the number of calculations required.</span></span> <span data-ttu-id="76f44-109">Na przykład po każdej aktualizacji elementu podrzędnego <xref:System.Windows.UIElement> obiektu w kolekcji zmianę położenia, ma możliwość wyzwolenia nowy przebieg przez system układu.</span><span class="sxs-lookup"><span data-stu-id="76f44-109">For example, each time a child <xref:System.Windows.UIElement> object in the collection changes its position, it has the potential to trigger a new pass by the layout system.</span></span> <span data-ttu-id="76f44-110">Z powodu zamknięcia relacji między właściwości obiektu i zachowanie układu ważne jest zrozumienie typ zdarzenia, które może wywołać układu systemu.</span><span class="sxs-lookup"><span data-stu-id="76f44-110">Because of the close relationship between object characteristics and layout behavior, it's important to understand the type of events that can invoke the layout system.</span></span> <span data-ttu-id="76f44-111">Aplikacji będą działać lepiej zmniejszając możliwie przekazać wszelkie niepotrzebne wywołania układu.</span><span class="sxs-lookup"><span data-stu-id="76f44-111">Your application will perform better by reducing as much as possible any unnecessary invocations of the layout pass.</span></span>  
  
 <span data-ttu-id="76f44-112">Układ systemu wykonuje dwie przejścia dla każdego elementu podrzędnego w kolekcji: przebiegu miary i przekazać Rozmieść.</span><span class="sxs-lookup"><span data-stu-id="76f44-112">The layout system completes two passes for each child member in a collection: a measure pass, and an arrange pass.</span></span> <span data-ttu-id="76f44-113">Każdy obiekt podrzędny zawiera własną implementację przesłoniętych <xref:System.Windows.UIElement.Measure%2A> i <xref:System.Windows.UIElement.Arrange%2A> metody w celu zapewnienia zachowania określonych układu.</span><span class="sxs-lookup"><span data-stu-id="76f44-113">Each child object provides its own overridden implementation of the <xref:System.Windows.UIElement.Measure%2A> and <xref:System.Windows.UIElement.Arrange%2A> methods in order to provide its own specific layout behavior.</span></span> <span data-ttu-id="76f44-114">W najprostszym układu to system cyklicznej, który prowadzi do elementu trwa o rozmiarze, znajduje się i rysowane na ekranie.</span><span class="sxs-lookup"><span data-stu-id="76f44-114">At its simplest, layout is a recursive system that leads to an element being sized, positioned, and drawn onscreen.</span></span>  
  
-   <span data-ttu-id="76f44-115">Element podrzędny <xref:System.Windows.UIElement> obiektu rozpoczyna proces układu przez jego właściwości core mierzony uprzedniego.</span><span class="sxs-lookup"><span data-stu-id="76f44-115">A child <xref:System.Windows.UIElement> object begins the layout process by first having its core properties measured.</span></span>  
  
-   <span data-ttu-id="76f44-116">Obiektu <xref:System.Windows.FrameworkElement> właściwości, które są związane z rozmiar, takich jak <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, i <xref:System.Windows.FrameworkElement.Margin%2A>, są sprawdzane.</span><span class="sxs-lookup"><span data-stu-id="76f44-116">The object's <xref:System.Windows.FrameworkElement> properties that are related to size, such as <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.Margin%2A>, are evaluated.</span></span>  
  
-   <span data-ttu-id="76f44-117"><xref:System.Windows.Controls.Panel>— Logika charakterystyczna zostanie zastosowana, takich jak <xref:System.Windows.Controls.DockPanel.Dock%2A> właściwość <xref:System.Windows.Controls.DockPanel>, lub <xref:System.Windows.Controls.StackPanel.Orientation%2A> właściwość <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="76f44-117"><xref:System.Windows.Controls.Panel>-specific logic is applied, such as the <xref:System.Windows.Controls.DockPanel.Dock%2A> property of the <xref:System.Windows.Controls.DockPanel>, or the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
-   <span data-ttu-id="76f44-118">Zawartość jest rozmieszczone lub znajduje się po zostały zmierzone wszystkich obiektów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="76f44-118">Content is arranged, or positioned, after all child objects have been measured.</span></span>  
  
-   <span data-ttu-id="76f44-119">Kolekcja obiektów podrzędnych jest rysowana na ekranie.</span><span class="sxs-lookup"><span data-stu-id="76f44-119">The collection of child objects is drawn to the screen.</span></span>  
  
 <span data-ttu-id="76f44-120">Proces przekazywania układ jest wywoływana ponownie, jeśli wystąpienia któregokolwiek z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="76f44-120">The layout pass process is invoked again if any of the following actions occur:</span></span>  
  
-   <span data-ttu-id="76f44-121">Obiekt podrzędny jest dodawany do kolekcji.</span><span class="sxs-lookup"><span data-stu-id="76f44-121">A child object is added to the collection.</span></span>  
  
-   <span data-ttu-id="76f44-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> jest stosowany do obiektu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="76f44-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> is applied to the child object.</span></span>  
  
-   <span data-ttu-id="76f44-123"><xref:System.Windows.UIElement.UpdateLayout%2A> Metoda jest wywoływana dla obiekt podrzędny.</span><span class="sxs-lookup"><span data-stu-id="76f44-123">The <xref:System.Windows.UIElement.UpdateLayout%2A> method is called for the child object.</span></span>  
  
-   <span data-ttu-id="76f44-124">Gdy nastąpi zmiana wartości właściwości zależności, która jest oznaczony atrybutem metadanych wpływających na miary lub rozmieszczania przebiegów.</span><span class="sxs-lookup"><span data-stu-id="76f44-124">When a change occurs to the value of a dependency property that is marked with metadata affecting the measure or arrange passes.</span></span>  
  
### <a name="use-the-most-efficient-panel-where-possible"></a><span data-ttu-id="76f44-125">Skorzystaj z panelu najbardziej efektywne, gdy jest to możliwe</span><span class="sxs-lookup"><span data-stu-id="76f44-125">Use the Most Efficient Panel where Possible</span></span>  
 <span data-ttu-id="76f44-126">Złożoności procesu układu bezpośrednio opiera się na zachowanie układu <xref:System.Windows.Controls.Panel>-używasz elementów pochodnych.</span><span class="sxs-lookup"><span data-stu-id="76f44-126">The complexity of the layout process is directly based on the layout behavior of the <xref:System.Windows.Controls.Panel>-derived elements you use.</span></span> <span data-ttu-id="76f44-127">Na przykład <xref:System.Windows.Controls.Grid> lub <xref:System.Windows.Controls.StackPanel> kontroli udostępnia znacznie więcej funkcji niż <xref:System.Windows.Controls.Canvas> formantu.</span><span class="sxs-lookup"><span data-stu-id="76f44-127">For example, a <xref:System.Windows.Controls.Grid> or <xref:System.Windows.Controls.StackPanel> control provides much more functionality than a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="76f44-128">Cena za większy wzrost funkcji jest większa wzrost wydajności kosztów.</span><span class="sxs-lookup"><span data-stu-id="76f44-128">The price for this greater increase in functionality is a greater increase in performance costs.</span></span> <span data-ttu-id="76f44-129">Jednak jeśli nie potrzebujesz funkcji który <xref:System.Windows.Controls.Grid> zawiera formant, należy użyć mniej kosztowne rozwiązań alternatywnych, takich jak <xref:System.Windows.Controls.Canvas> lub niestandardowy panel.</span><span class="sxs-lookup"><span data-stu-id="76f44-129">However, if you do not require the functionality that a <xref:System.Windows.Controls.Grid> control provides, you should use the less costly alternatives, such as a <xref:System.Windows.Controls.Canvas> or a custom panel.</span></span>  
  
 <span data-ttu-id="76f44-130">Aby uzyskać więcej informacji, zobacz [omówienie panele](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76f44-130">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
### <a name="update-rather-than-replace-a-rendertransform"></a><span data-ttu-id="76f44-131">Zaktualizuj zamiast zastąpić właściwość RenderTransform</span><span class="sxs-lookup"><span data-stu-id="76f44-131">Update Rather than Replace a RenderTransform</span></span>  
 <span data-ttu-id="76f44-132">Można aktualizować <xref:System.Windows.Media.Transform> zamiast zastąpienie jako wartość <xref:System.Windows.UIElement.RenderTransform%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="76f44-132">You may be able to update a <xref:System.Windows.Media.Transform> rather than replacing it as the value of a <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="76f44-133">Jest to szczególnie istotne w scenariuszach obejmujących animacji.</span><span class="sxs-lookup"><span data-stu-id="76f44-133">This is particularly true in scenarios that involve animation.</span></span> <span data-ttu-id="76f44-134">Aktualizacja istniejącej <xref:System.Windows.Media.Transform>, można uniknąć, inicjowanie obliczeń niepotrzebnych układu.</span><span class="sxs-lookup"><span data-stu-id="76f44-134">By updating an existing <xref:System.Windows.Media.Transform>, you avoid initiating an unnecessary layout calculation.</span></span>  
  
### <a name="build-your-tree-top-down"></a><span data-ttu-id="76f44-135">Tworzenie z drzewa góra dół</span><span class="sxs-lookup"><span data-stu-id="76f44-135">Build Your Tree Top-Down</span></span>  
 <span data-ttu-id="76f44-136">Gdy węzeł zostanie dodany lub usunięty z drzewa logicznego, pojawienia się właściwości invalidations nadrzędnego węzła i wszystkich jego obiektów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="76f44-136">When a node is added or removed from the logical tree, property invalidations are raised on the node's parent and all its children.</span></span> <span data-ttu-id="76f44-137">W związku z tym wzorzec konstrukcji góra dół zawsze można wykonać w celu uniknięcia koszt niepotrzebnych invalidations w węzłach, które już zostały zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="76f44-137">As a result, a top-down construction pattern should always be followed to avoid the cost of unnecessary invalidations on nodes that have already been validated.</span></span> <span data-ttu-id="76f44-138">W poniższej tabeli przedstawiono różnice szybkość wykonywania między tworzenia drzewa góra dół w zależności od dołu do góry, gdzie drzewa jest 150 poziomów w głąb za pomocą jednej <xref:System.Windows.Controls.TextBlock> i <xref:System.Windows.Controls.DockPanel> na każdym poziomie.</span><span class="sxs-lookup"><span data-stu-id="76f44-138">The following table shows the difference in execution speed between building a tree top-down versus bottom-up, where the tree is 150 levels deep with a single <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Controls.DockPanel> at each level.</span></span>  
  
|<span data-ttu-id="76f44-139">**Akcja**</span><span class="sxs-lookup"><span data-stu-id="76f44-139">**Action**</span></span>|<span data-ttu-id="76f44-140">**Drzewo kompilacji (w ms)**</span><span class="sxs-lookup"><span data-stu-id="76f44-140">**Tree building (in ms)**</span></span>|<span data-ttu-id="76f44-141">**Renderowanie — zawiera drzewa kompilacji (w ms)**</span><span class="sxs-lookup"><span data-stu-id="76f44-141">**Render—includes tree building (in ms)**</span></span>|  
|----------------|---------------------------------|-------------------------------------------------|  
|<span data-ttu-id="76f44-142">Dołu do góry</span><span class="sxs-lookup"><span data-stu-id="76f44-142">Bottom-up</span></span>|<span data-ttu-id="76f44-143">366</span><span class="sxs-lookup"><span data-stu-id="76f44-143">366</span></span>|<span data-ttu-id="76f44-144">454</span><span class="sxs-lookup"><span data-stu-id="76f44-144">454</span></span>|  
|<span data-ttu-id="76f44-145">Góra dół</span><span class="sxs-lookup"><span data-stu-id="76f44-145">Top-down</span></span>|<span data-ttu-id="76f44-146">11</span><span class="sxs-lookup"><span data-stu-id="76f44-146">11</span></span>|<span data-ttu-id="76f44-147">96</span><span class="sxs-lookup"><span data-stu-id="76f44-147">96</span></span>|  
  
 <span data-ttu-id="76f44-148">Poniższy przykładowy kod przedstawia sposób tworzenia top drzewa w dół.</span><span class="sxs-lookup"><span data-stu-id="76f44-148">The following code example demonstrates how to create a tree top down.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 <span data-ttu-id="76f44-149">Aby uzyskać więcej informacji na drzewie logicznym, zobacz [drzewa WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="76f44-149">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f44-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="76f44-150">See Also</span></span>  
 [<span data-ttu-id="76f44-151">Optymalizacja wydajności aplikacji WPF</span><span class="sxs-lookup"><span data-stu-id="76f44-151">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="76f44-152">Planowanie wydajności aplikacji</span><span class="sxs-lookup"><span data-stu-id="76f44-152">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [<span data-ttu-id="76f44-153">Dzięki funkcji sprzętu</span><span class="sxs-lookup"><span data-stu-id="76f44-153">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [<span data-ttu-id="76f44-154">Grafika 2W i utworzenia obrazu</span><span class="sxs-lookup"><span data-stu-id="76f44-154">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="76f44-155">Zachowanie obiektu</span><span class="sxs-lookup"><span data-stu-id="76f44-155">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [<span data-ttu-id="76f44-156">Zasoby aplikacji</span><span class="sxs-lookup"><span data-stu-id="76f44-156">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [<span data-ttu-id="76f44-157">Tekst</span><span class="sxs-lookup"><span data-stu-id="76f44-157">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [<span data-ttu-id="76f44-158">Powiązanie danych</span><span class="sxs-lookup"><span data-stu-id="76f44-158">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="76f44-159">Inne zalecenia dotyczące wydajności</span><span class="sxs-lookup"><span data-stu-id="76f44-159">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [<span data-ttu-id="76f44-160">Układ</span><span class="sxs-lookup"><span data-stu-id="76f44-160">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)