---
title: "Porady: zakotwiczenie i dokowanie formantów podrzędnych w formancie FlowLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfcb802df01ce9d8f1cbaaf72dcf00d06028fb36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Porady: zakotwiczenie i dokowanie formantów podrzędnych w formancie FlowLayoutPanel
<xref:System.Windows.Forms.FlowLayoutPanel> Sterowanie obsługuje <xref:System.Windows.Forms.Control.Anchor%2A> i <xref:System.Windows.Forms.Control.Dock%2A> właściwości w jej kontrolkach podrzędnych.  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Aby zakotwiczenie i dokowanie formantów podrzędnych w formancie FlowLayoutPanel  
  
1.  Utwórz <xref:System.Windows.Forms.FlowLayoutPanel> kontrolkę w formularzu.  
  
2.  Ustaw <xref:System.Windows.Forms.Control.Width%2A> z <xref:System.Windows.Forms.FlowLayoutPanel> formant **300**i ustaw jej <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> do <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
3.  Utwórz dwa <xref:System.Windows.Forms.Button> steruje i umieść je w <xref:System.Windows.Forms.FlowLayoutPanel> formantu.  
  
4.  Ustaw <xref:System.Windows.Forms.Control.Width%2A> pierwszego przycisku, aby **200**.  
  
5.  Ustaw <xref:System.Windows.Forms.Control.Dock%2A> właściwości drugiego przycisku <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    > [!NOTE]
    >  Drugi przycisk zakłada szerokość przycisku pierwszej. Nie stretch poprzek <xref:System.Windows.Forms.FlowLayoutPanel> formantu.  
  
6.  Ustaw <xref:System.Windows.Forms.Control.Dock%2A> właściwości drugiego przycisku `None`. Powoduje to, że przycisk założenie oryginalną szerokość.  
  
7.  Ustaw <xref:System.Windows.Forms.Control.Anchor%2A> właściwości drugiego przycisku `Left, Right`.  
  
    > [!IMPORTANT]
    >  Drugi przycisk zakłada szerokość przycisku pierwszej. Nie stretch poprzek <xref:System.Windows.Forms.FlowLayoutPanel> formantu. To ogólna reguła Zakotwiczanie i dokowanie w <xref:System.Windows.Forms.FlowLayoutPanel> kontroli: dla pionowego przepływu kierunków, <xref:System.Windows.Forms.FlowLayoutPanel> kontroli oblicza szerokość domniemanych kolumny z najszerszych formant podrzędny w tej kolumnie. Wszystkie inne formanty w tej kolumnie z <xref:System.Windows.Forms.Control.Anchor%2A> lub <xref:System.Windows.Forms.Control.Dock%2A> właściwości są wyrównane lub rozciągany tak, aby zmieścić ją w tej kolumnie domyślnych. Zachowanie działa w podobny sposób jak dla kierunków przepływu poziomej. <xref:System.Windows.Forms.FlowLayoutPanel> Kontroli oblicza wysokość wiersza domyślnych z najwyższego formantu podrzędnego w wierszu, a wszystkie formanty podrzędne zadokowanych lub zakotwiczonych w tym wierszu są wyrównane lub dopasowana domniemanych wiersza.  
  
## <a name="example"></a>Przykład  
 Na poniższej ilustracji przedstawiono cztery przyciski, które zakotwiczona i zadokowane względem niebieski przycisk w <xref:System.Windows.Forms.FlowLayoutPanel>. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Jest <xref:System.Windows.Forms.FlowDirection.LeftToRight>.  
  
 ![Formantu FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.gif "NET_FLPanchorExp")  
  
 Na poniższej ilustracji przedstawiono cztery przyciski, które zakotwiczona i zadokowane względem niebieski przycisk w <xref:System.Windows.Forms.FlowLayoutPanel>. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Jest <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
 ![Formantu FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.gif "VS_FLPanchor2")  
  
 Poniższy przykład kodu pokazuje różnych <xref:System.Windows.Forms.Control.Anchor%2A> wartości właściwości <xref:System.Windows.Forms.Button> kontroli w <xref:System.Windows.Forms.FlowLayoutPanel> formantu.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów systemu, dane systemowe, System.Drawing i System.Windows.Forms.  
  
 Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.  Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [FlowLayoutPanel, kontrolka — omówienie](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)
