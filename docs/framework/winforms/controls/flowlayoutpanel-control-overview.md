---
title: "FlowLayoutPanel — Informacje o formancie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f19e53a2dfd2c659a3ba111a80a35cd0737fa163
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="f4c8e-102">FlowLayoutPanel — Informacje o formancie</span><span class="sxs-lookup"><span data-stu-id="f4c8e-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="f4c8e-103"><xref:System.Windows.Forms.FlowLayoutPanel> Kontroli rozmieszcza jego zawartość w kierunku przepływu pozioma lub pionowa.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="f4c8e-104">Można zawijać zawartość formantu z jednego wiersza do następnego lub jedną kolumnę do następnego.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="f4c8e-105">Alternatywnie można przyciąć zamiast zawijania jego zawartość.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="f4c8e-106">Określ kierunek przepływu, ustawiając wartość <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="f4c8e-107"><xref:System.Windows.Forms.FlowLayoutPanel> Kontroli poprawnie cofa jego kierunek przepływu układów od prawej do lewej (od prawej do lewej).</span><span class="sxs-lookup"><span data-stu-id="f4c8e-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="f4c8e-108">Można również określić, czy <xref:System.Windows.Forms.FlowLayoutPanel> zawartość formantu jest zawijany lub przycinana przez ustawienie wartości <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="f4c8e-109"><xref:System.Windows.Forms.FlowLayoutPanel> Automatycznie kontrolować rozmiary, do jego zawartości po ustawieniu <xref:System.Windows.Forms.Control.AutoSize%2A> właściwości `true`.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="f4c8e-110">Zapewnia także **FlowBreak** właściwości formantów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="f4c8e-111">Ustawienie wartości dla właściwości FlowBreak `true` powoduje, że <xref:System.Windows.Forms.FlowLayoutPanel> formant przestanie układania formantów w bieżącym kierunek przepływu i zawijania do następnego wiersza lub kolumny.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="f4c8e-112">Wszystkie kontrolki formularza systemu Windows może być elementem podrzędnym elementu <xref:System.Windows.Forms.FlowLayoutPanel> formantu, łącznie z innymi wystąpieniami <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="f4c8e-113">Dzięki tej możliwości można utworzyć układy zaawansowane dostosowania formularza wymiarów w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f4c8e-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="f4c8e-114">Zobacz też [wskazówki: rozmieszczanie formantów w Windows Forms za pomocą FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f4c8e-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c8e-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f4c8e-115">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="f4c8e-116">FlowLayoutPanel — formant</span><span class="sxs-lookup"><span data-stu-id="f4c8e-116">FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)