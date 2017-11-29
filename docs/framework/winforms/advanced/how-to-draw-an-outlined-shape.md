---
title: "Porady: rysowanie konturu kształtu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 05247d24f3db95d042cb4ac34ec6ed648ec1d997
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="fa6c2-102">Porady: rysowanie konturu kształtu</span><span class="sxs-lookup"><span data-stu-id="fa6c2-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="fa6c2-103">W tym przykładzie rysuje obramowane elipsy i prostokąty w formularzu.</span><span class="sxs-lookup"><span data-stu-id="fa6c2-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6c2-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="fa6c2-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa6c2-105">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="fa6c2-105">Compiling the Code</span></span>  
 <span data-ttu-id="fa6c2-106">Nie można wywołać tej metody <xref:System.Windows.Forms.Form.Load> obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="fa6c2-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="fa6c2-107">Narysowanego zawartość nie zostanie narysowany ponownie Jeśli zmiany rozmiaru lub zostanie przesłonięty przez inny formularz formularza.</span><span class="sxs-lookup"><span data-stu-id="fa6c2-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="fa6c2-108">Aby automatycznie odświeżenia zawartości, należy zastąpić <xref:System.Windows.Forms.Control.OnPaint%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="fa6c2-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fa6c2-109">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="fa6c2-109">Robust Programming</span></span>  
 <span data-ttu-id="fa6c2-110">Zawsze należy wywołać <xref:System.IDisposable.Dispose%2A> na wszystkie obiekty używające zasobów systemowych, takich jak <xref:System.Drawing.Pen> i <xref:System.Drawing.Graphics> obiektów.</span><span class="sxs-lookup"><span data-stu-id="fa6c2-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6c2-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fa6c2-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>  
 [<span data-ttu-id="fa6c2-112">Wprowadzenie do programowania grafiki</span><span class="sxs-lookup"><span data-stu-id="fa6c2-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="fa6c2-113">Rysowanie linii i kształtów za pomocą pióra</span><span class="sxs-lookup"><span data-stu-id="fa6c2-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="fa6c2-114">Grafika i rysowanie w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="fa6c2-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)