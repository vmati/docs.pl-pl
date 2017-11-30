---
title: "TableLayoutPanel — Informacje o formancie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd8d68aa57ffe8b6fb84ceddf9d01aed56d40bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="fa842-102">TableLayoutPanel — Informacje o formancie</span><span class="sxs-lookup"><span data-stu-id="fa842-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="fa842-103"><xref:System.Windows.Forms.TableLayoutPanel> Kontroli rozmieszcza jego zawartość w siatce.</span><span class="sxs-lookup"><span data-stu-id="fa842-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="fa842-104">Ponieważ układ jest wykonywane zarówno w czasie projektowania i czas wykonywania, może zmieniać dynamicznie jako zmian środowiska aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fa842-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="fa842-105">To umożliwia formantów w panelu proporcjonalnie zmiany rozmiaru, dlatego mogą one odpowiadać na zmiany, takie jak zmiana rozmiaru kontrolki nadrzędnej lub tekst długość zmianę z powodu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="fa842-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="fa842-106">Wszystkie kontrolki formularza systemu Windows może być elementem podrzędnym elementu <xref:System.Windows.Forms.TableLayoutPanel> formantu, łącznie z innymi wystąpieniami <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="fa842-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="fa842-107">Dzięki temu można tworzyć zaawansowane układy dostosować do zmian w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="fa842-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="fa842-108"><xref:System.Windows.Forms.TableLayoutPanel> Formantu można rozwinąć w celu uwzględnienia nowych formantów, gdy zostaną dodane, w zależności od wartości <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, i <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="fa842-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="fa842-109">Ustawienie albo <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> lub <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> właściwości na wartość 0 oznacza, że <xref:System.Windows.Forms.TableLayoutPanel> zostanie anulowane w odpowiednich kierunku.</span><span class="sxs-lookup"><span data-stu-id="fa842-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="fa842-110">Można również sterować kierunek rozwoju (poziomą lub pionową) po <xref:System.Windows.Forms.TableLayoutPanel> formant jest pełna formantów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fa842-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="fa842-111">Domyślnie <xref:System.Windows.Forms.TableLayoutPanel> kontroli dół rozszerza przez dodanie wierszy.</span><span class="sxs-lookup"><span data-stu-id="fa842-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="fa842-112">Jeśli chcesz wierszy i kolumn, które działają inaczej niż domyślne zachowanie właściwości wierszy i kolumn można kontrolować przy użyciu <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> i <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="fa842-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="fa842-113">Można ustawić właściwości wierszy lub kolumn pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="fa842-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="fa842-114"><xref:System.Windows.Forms.TableLayoutPanel> Kontroli dodaje następujące właściwości do jej kontrolkach podrzędnych: `Cell`, `Column`, `Row`, `ColumnSpan`, i `RowSpan`.</span><span class="sxs-lookup"><span data-stu-id="fa842-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="fa842-115">Można scalać komórek w <xref:System.Windows.Forms.TableLayoutPanel> kontroli przez ustawienie `ColumnSpan` lub `RowSpan` właściwości kontrolki podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="fa842-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  <span data-ttu-id="fa842-116">[Porady: wyrównywanie i rozciąganie formantu w formancie TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fa842-116">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="fa842-117">[Porady: obejmowanie rzędów i kolumn w formancie TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fa842-117">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="fa842-118">[Porady: edytowanie rzędów i kolumn w formancie TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fa842-118">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="fa842-119">[Wskazówki: Rozmieszczanie formantów na formularzach systemu Windows za pomocą TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fa842-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa842-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fa842-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="fa842-121">Porady: Projektowanie układu, który dobrze reagującego na formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="fa842-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="fa842-122">Porady: Tworzenie formularza systemu Windows o zmiennych rozmiarach do wpisywania danych</span><span class="sxs-lookup"><span data-stu-id="fa842-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="fa842-123">Najlepsze praktyki dotyczące formantu TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fa842-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)