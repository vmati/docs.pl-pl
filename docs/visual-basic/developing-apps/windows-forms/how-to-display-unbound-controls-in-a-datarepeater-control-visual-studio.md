---
title: "Porady: wyświetlanie formantów niepowiązanych w formancie DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3e96219f0ea8b8198967e9fa3c6e5afb824352db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="ac744-102">Porady: wyświetlanie formantów niepowiązanych w formancie DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ac744-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="ac744-103">Oprócz formanty powiązane, można dodać inne formanty <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, na przykład statyczną etykietę lub obraz jest powtarzany na każdej pozycji w <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac744-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac744-104">Musi mieć co najmniej jeden formant związany <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> lub nie będą wyświetlane żadne w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ac744-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="ac744-105">Aby dodać niepowiązanych formantów DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ac744-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="ac744-106">Przeciągnij <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> kontrolować z **Visual Basic PowerPacks** karcie **przybornika** formularza lub kontenera formantu.</span><span class="sxs-lookup"><span data-stu-id="ac744-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="ac744-107">Przeciągnij uchwyt zmiany rozmiaru i pozycji do rozmiaru i pozycji formantu.</span><span class="sxs-lookup"><span data-stu-id="ac744-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="ac744-108">Możesz również rozmiar i położenie kontrolki, zmieniając **rozmiar** i **pozycji** właściwości w oknie właściwości.</span><span class="sxs-lookup"><span data-stu-id="ac744-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="ac744-109">Dodaj co najmniej jeden formant powiązany z danymi do <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac744-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="ac744-110">Aby uzyskać więcej informacji, zobacz [porady: wyświetlanie powiązanych danych w formancie Datarepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ac744-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="ac744-111">Przeciągnij formant z **przybornika** na region szablonu elementu <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac744-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ac744-112">Należy pamiętać, że kontrolka ma dwóch regionach prostokątny.</span><span class="sxs-lookup"><span data-stu-id="ac744-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="ac744-113">Wewnętrzny region jest *szablon elementu*; formanty dodawane do szablonu zostanie powtórzona w każdej pozycji w <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> formantu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ac744-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="ac744-114">Zewnętrzne region jest *okienka ekranu*, której elementy będą wyświetlane; formantów, które są dodawane do tego obszaru nie będą wyświetlane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ac744-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac744-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac744-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="ac744-116">Wprowadzenie do formantu DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ac744-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ac744-117">Rozwiązywanie problemów z formantem DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ac744-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ac744-118">Porady: wyświetlanie powiązanych danych w formancie Datarepeater</span><span class="sxs-lookup"><span data-stu-id="ac744-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="ac744-119">Porady: Tworzenie formularza wzorzec/szczegół za pomocą dwóch formantów DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ac744-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="ac744-120">Porady: Zmienianie wyglądu formantu DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ac744-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)