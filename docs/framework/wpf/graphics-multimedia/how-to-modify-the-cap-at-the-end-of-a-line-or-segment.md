---
title: "Jak modyfikować zakończenie na końcu linii lub segmentu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e062b82e698a99705a2b06588aa9aae3a0c93157
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="cd1cd-102">Jak modyfikować zakończenie na końcu linii lub segmentu</span><span class="sxs-lookup"><span data-stu-id="cd1cd-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="cd1cd-103">W tym przykładzie przedstawiono sposób modyfikowania kształt na początek lub koniec Otwórz <xref:System.Windows.Shapes.Shape> elementu.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="cd1cd-104">Aby zmienić zakończenie na początku otwarty <xref:System.Windows.Shapes.Shape>, użyj jej <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="cd1cd-105">Aby zmienić limit na koniec Otwórz <xref:System.Windows.Shapes.Shape>, użyj jej <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="cd1cd-106">Aby wyświetlić zakończeniem linii dostępności, zobacz <xref:System.Windows.Media.PenLineCap> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd1cd-107">Ta właściwość ma wpływ tylko na otwarty kształt, takich jak <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, lub Otwórz <xref:System.Windows.Shapes.Path> elementu.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="cd1cd-108">Poniższy przykład rysuje cztery <xref:System.Windows.Shapes.Polyline> elementów i korzysta z innego zestawu kształtów w elementach end, każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="cd1cd-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd1cd-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="cd1cd-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="cd1cd-110">Ten przykład jest częścią większego przykładu; pełny przykład, zobacz [przykładowe elementy kształtu](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="cd1cd-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1cd-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd1cd-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>