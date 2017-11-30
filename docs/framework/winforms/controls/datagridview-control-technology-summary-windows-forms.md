---
title: "Podsumowanie informacji o technologii formantów DataGridView (Formularze systemu Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f172d28e5f03e1177db6ad1bd9e98f4c68267765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-technology-summary-windows-forms"></a><span data-ttu-id="97805-102">Podsumowanie informacji o technologii formantów DataGridView (Formularze systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="97805-102">DataGridView Control Technology Summary (Windows Forms)</span></span>
<span data-ttu-id="97805-103">Ten temat zawiera podsumowanie informacji o `DataGridView` kontroli i klasy, które obsługują jej zastosowania.</span><span class="sxs-lookup"><span data-stu-id="97805-103">This topic summarizes information about the `DataGridView` control and the classes that support its use.</span></span>  
  
 <span data-ttu-id="97805-104">Wyświetlanie danych w formacie tabelarycznym jest zadaniem, które prawdopodobnie będą wykonywane.</span><span class="sxs-lookup"><span data-stu-id="97805-104">Displaying data in a tabular format is a task you are likely to perform frequently.</span></span> <span data-ttu-id="97805-105">`DataGridView` Kontrolki została zaprojektowana jako kompletnego rozwiązania prezentacji danych w siatce.</span><span class="sxs-lookup"><span data-stu-id="97805-105">The `DataGridView` control is designed to be a complete solution for presenting data in a grid.</span></span>  
  
## <a name="keywords"></a><span data-ttu-id="97805-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="97805-106">Keywords</span></span>  
 <span data-ttu-id="97805-107">Formant DataGridView, BindingSource, tabeli, komórki, powiązania danych, tryb wirtualny</span><span class="sxs-lookup"><span data-stu-id="97805-107">DataGridView, BindingSource, table, cell, data binding, virtual mode</span></span>  
  
## <a name="namespaces"></a><span data-ttu-id="97805-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="97805-108">Namespaces</span></span>  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a><span data-ttu-id="97805-109">Powiązane technologie</span><span class="sxs-lookup"><span data-stu-id="97805-109">Related Technologies</span></span>  
 `BindingSource`  
  
## <a name="background"></a><span data-ttu-id="97805-110">Tło</span><span class="sxs-lookup"><span data-stu-id="97805-110">Background</span></span>  
 <span data-ttu-id="97805-111">Projektanci interfejsu użytkownika często być konieczne do wyświetlenia użytkownikom danych tabelarycznych.</span><span class="sxs-lookup"><span data-stu-id="97805-111">User interface (UI) designers frequently find it necessary to display tabular data to users.</span></span> <span data-ttu-id="97805-112">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Zapewnia wiele sposobów wyświetlania danych w tabeli lub siatki.</span><span class="sxs-lookup"><span data-stu-id="97805-112">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides several ways to show data in a table or grid.</span></span> <span data-ttu-id="97805-113">`DataGridView` Kontroli reprezentuje najnowsze zmiany tej technologii dla aplikacji formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="97805-113">The `DataGridView` control represents the latest evolution of this technology for Windows Forms applications.</span></span>  
  
 <span data-ttu-id="97805-114">`DataGridView` Formant może wyświetlać wiersze danych z magazynu danych.</span><span class="sxs-lookup"><span data-stu-id="97805-114">The `DataGridView` control can display rows of data from a data store.</span></span> <span data-ttu-id="97805-115">Wiele typów magazynów danych są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="97805-115">Many types of data stores are supported.</span></span> <span data-ttu-id="97805-116">Magazyn danych można zapisać proste, bez typu danych, takich jak tablicą jednowymiarową lub może on przechowywać wprowadzonych danych, takich jak <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="97805-116">The data store can hold simple, untyped data, such as a one-dimensional array, or it can hold typed data, such as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="97805-117">Aby uzyskać więcej informacji, zobacz [porady: powiązanie danych z formantem DataGridView formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="97805-117">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="97805-118">`DataGridView` Kontrola zapewnia wydajny i elastyczny sposób wyświetlania danych w formacie tabelarycznym.</span><span class="sxs-lookup"><span data-stu-id="97805-118">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="97805-119">Formant służy do wyświetlenia tylko do odczytu lub nie można edytować widoki małych bardzo dużych zestawów danych.</span><span class="sxs-lookup"><span data-stu-id="97805-119">You can use the control to show read-only or editable views of small to very large sets of data.</span></span>  
  
 <span data-ttu-id="97805-120">Można rozszerzyć `DataGridView` sterowania na kilka sposobów do tworzenia niestandardowych zachowania w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="97805-120">You can extend the `DataGridView` control in several ways to build custom behavior into your applications.</span></span> <span data-ttu-id="97805-121">Na przykład można programowo określić własne sortowanie algorytmów i własnych typów komórek.</span><span class="sxs-lookup"><span data-stu-id="97805-121">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="97805-122">Można łatwo dostosować wygląd `DataGridView` kontroli, wybierając spośród kilku właściwości.</span><span class="sxs-lookup"><span data-stu-id="97805-122">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="97805-123">Wiele typów magazynów danych może służyć jako źródła danych lub `DataGridView` formant może działać bez powiązane z nim źródła danych.</span><span class="sxs-lookup"><span data-stu-id="97805-123">Many types of data stores can be used as a data source, or the `DataGridView` control can operate without a data source bound to it.</span></span>  
  
## <a name="implementing-datagridview-classes"></a><span data-ttu-id="97805-124">Implementowanie klas DataGridView</span><span class="sxs-lookup"><span data-stu-id="97805-124">Implementing DataGridView Classes</span></span>  
 <span data-ttu-id="97805-125">Istnieje kilka sposobów, aby móc korzystać z `DataGridView` funkcji rozszerzeń formantu.</span><span class="sxs-lookup"><span data-stu-id="97805-125">There are several ways for you to take advantage of the `DataGridView` control's extensibility features.</span></span> <span data-ttu-id="97805-126">Można dostosować wiele aspektów sterowanie za pośrednictwem właściwości i zdarzenia, ale niektóre dostosowania wymagają utworzenia nowej klasy pochodzące od istniejącego `DataGridView` klasy.</span><span class="sxs-lookup"><span data-stu-id="97805-126">You can customize many aspects of the control through events and properties, but some customizations require you to create new classes derived from existing `DataGridView` classes.</span></span>  
  
 <span data-ttu-id="97805-127">Najczęściej używane klasy podstawowe są `DataGridViewCell` i `DataGridViewColumn`.</span><span class="sxs-lookup"><span data-stu-id="97805-127">The most typically used base classes are `DataGridViewCell` and `DataGridViewColumn`.</span></span> <span data-ttu-id="97805-128">Mogą pochodzić własne klasy komórki z `DataGridViewCell` lub żadnej z jej klas podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="97805-128">You can derive your own cell class from `DataGridViewCell` or any of its child classes.</span></span> <span data-ttu-id="97805-129">Mimo że dowolnego typu komórki można dodać do dowolnej kolumny, będzie zwykle również klasa wyprowadzona z Pomocnika kolumny z `DataGridViewColumn` obsługującego komórek danego typu niestandardowego komórki domyślnie.</span><span class="sxs-lookup"><span data-stu-id="97805-129">Although you can add any cell type to any column, you will typically also derive a companion column class from `DataGridViewColumn` that hosts cells of your custom cell type by default.</span></span>  
  
 <span data-ttu-id="97805-130">Można zaimplementować `IDataGridViewEditingCell` interfejsu w klasie pochodnej komórki, aby utworzyć typ komórki ma funkcji edytowania, która nie obsługuje formantu w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="97805-130">You can implement the `IDataGridViewEditingCell` interface in your derived cell class to create a cell type that has editing functionality but does not host a control in editing mode.</span></span> <span data-ttu-id="97805-131">Aby utworzyć formant, który może obsługiwać w komórce w trybie edycji, można zaimplementować `IDataGridViewEditingControl` interfejsu w klasie pochodnej z <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="97805-131">To create a control that you can host in a cell in editing mode, you can implement the `IDataGridViewEditingControl` interface in a class derived from <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="97805-132">Aby uzyskać więcej informacji, zobacz [porady: dostosowywanie komórek i kolumn w formancie DataGridView formularzy systemu Windows przez rozszerzanie ich zachowania i wyglądu](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) i [porady: formanty hosta w komórkach DataGridView formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="97805-132">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) and [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="datagridview-classes-at-a-glance"></a><span data-ttu-id="97805-133">Klasy DataGridView w skrócie</span><span class="sxs-lookup"><span data-stu-id="97805-133">DataGridView Classes at a Glance</span></span>  
 <xref:System.Windows.Forms>  
  
|<span data-ttu-id="97805-134">Obszar technologii</span><span class="sxs-lookup"><span data-stu-id="97805-134">Technology Area</span></span>|<span data-ttu-id="97805-135">Elementy klasy/interfejsy/konfiguracji</span><span class="sxs-lookup"><span data-stu-id="97805-135">Classes/interfaces/configuration elements</span></span>|  
|---------------------|-------------------------------------------------|  
|<span data-ttu-id="97805-136">Powiązanie danych</span><span class="sxs-lookup"><span data-stu-id="97805-136">Data Binding</span></span>|<xref:System.Windows.Forms.BindingSource>|  
|<span data-ttu-id="97805-137">Prezentacja danych</span><span class="sxs-lookup"><span data-stu-id="97805-137">Data Presentation</span></span>|<xref:System.Windows.Forms.DataGridView><br /><br /> <span data-ttu-id="97805-138"><xref:System.Windows.Forms.DataGridViewCell>i klasy pochodne</span><span class="sxs-lookup"><span data-stu-id="97805-138"><xref:System.Windows.Forms.DataGridViewCell> and derived classes</span></span><br /><br /> <span data-ttu-id="97805-139"><xref:System.Windows.Forms.DataGridViewRow>i klasy pochodne</span><span class="sxs-lookup"><span data-stu-id="97805-139"><xref:System.Windows.Forms.DataGridViewRow> and derived classes</span></span><br /><br /> <span data-ttu-id="97805-140"><xref:System.Windows.Forms.DataGridViewColumn>i klasy pochodne</span><span class="sxs-lookup"><span data-stu-id="97805-140"><xref:System.Windows.Forms.DataGridViewColumn> and derived classes</span></span><br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<span data-ttu-id="97805-141"><xref:System.Windows.Forms.DataGridView>Rozszerzalność</span><span class="sxs-lookup"><span data-stu-id="97805-141"><xref:System.Windows.Forms.DataGridView> Extensibility</span></span>|<span data-ttu-id="97805-142"><xref:System.Windows.Forms.DataGridViewCell>i klasy pochodne</span><span class="sxs-lookup"><span data-stu-id="97805-142"><xref:System.Windows.Forms.DataGridViewCell> and derived classes</span></span><br /><br /> <span data-ttu-id="97805-143"><xref:System.Windows.Forms.DataGridViewColumn>i klasy pochodne</span><span class="sxs-lookup"><span data-stu-id="97805-143"><xref:System.Windows.Forms.DataGridViewColumn> and derived classes</span></span><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a><span data-ttu-id="97805-144">Nowości</span><span class="sxs-lookup"><span data-stu-id="97805-144">What's New</span></span>  
 <span data-ttu-id="97805-145"><xref:System.Windows.Forms.DataGridView> Kontrolki została zaprojektowana jako kompletnego rozwiązania do wyświetlania danych tabelarycznych w formularzach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="97805-145">The <xref:System.Windows.Forms.DataGridView> control is designed to be a complete solution for displaying tabular data with Windows Forms.</span></span> <span data-ttu-id="97805-146">Należy rozważyć użycie <xref:System.Windows.Forms.DataGridView> kontrolować przed innych rozwiązań, takich jak <xref:System.Windows.Forms.DataGrid>, podczas tworzenia nowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="97805-146">You should consider using the <xref:System.Windows.Forms.DataGridView> control before other solutions, such as <xref:System.Windows.Forms.DataGrid>, when you are authoring a new application.</span></span> <span data-ttu-id="97805-147">Aby uzyskać więcej informacji, zobacz [różnice między Windows Forms formantami DataGridView i DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="97805-147">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="97805-148"><xref:System.Windows.Forms.DataGridView> Formant może działać Zamknij razem z <xref:System.Windows.Forms.BindingSource> składnika.</span><span class="sxs-lookup"><span data-stu-id="97805-148">The <xref:System.Windows.Forms.DataGridView> control can work in close conjunction with the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="97805-149">Ten składnik została zaprojektowana jako podstawowego źródła danych formularza.</span><span class="sxs-lookup"><span data-stu-id="97805-149">This component is designed to be the primary data source of a form.</span></span> <span data-ttu-id="97805-150">Można zarządzać interakcji między <xref:System.Windows.Forms.DataGridView> typ źródła danych, niezależnie od danych i kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="97805-150">It can manage the interaction between a <xref:System.Windows.Forms.DataGridView> control and its data source, regardless of the data source type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97805-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="97805-151">See Also</span></span>  
 [<span data-ttu-id="97805-152">Informacje o formancie DataGridView</span><span class="sxs-lookup"><span data-stu-id="97805-152">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [<span data-ttu-id="97805-153">DataGridView — architektura formantu</span><span class="sxs-lookup"><span data-stu-id="97805-153">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="97805-154">Ochrona informacji o połączeniu</span><span class="sxs-lookup"><span data-stu-id="97805-154">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)