---
title: "Porady: grupowanie formantów RadioButton formularzy systemu Windows, aby działały jak zestaw"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c92048374941f735568bcd758ed475eba78b81e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Porady: grupowanie formantów RadioButton formularzy systemu Windows, aby działały jak zestaw
Formularze systemu Windows <xref:System.Windows.Forms.RadioButton> formanty mają na celu zapewniają użytkownikom wybór między co najmniej dwa ustawienia, których można przypisać tylko jeden z nich do procedury lub obiektu. Na przykład grupa <xref:System.Windows.Forms.RadioButton> formanty mogą być wyświetlane wybór pakietu nośniki zamówienia, ale tylko jeden z nośników będą używane. W związku z tym tylko jeden <xref:System.Windows.Forms.RadioButton> jednocześnie można wybrać, nawet jeśli jest częścią grupy funkcjonalne.  
  
 Grupa przycisków radiowych za pomocą rysowania wewnątrz kontenera takich jak <xref:System.Windows.Forms.Panel> kontroli, <xref:System.Windows.Forms.GroupBox> kontroli lub formularz. Wszystkie przycisków radiowych dodane bezpośrednio do jednej grupy stają się formularza. Aby dodać oddzielnych grup, trzeba je umieścić wewnątrz paneli lub pola grupy. Aby uzyskać więcej informacji na temat paneli lub pola grupy, zobacz [Panel — Informacje o formancie](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) lub [informacje o formancie GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Do grupy kontrolek RadioButton jako zestaw funkcji, niezależnie od innych zestawów  
  
1.  Przeciągnij <xref:System.Windows.Forms.GroupBox> lub <xref:System.Windows.Forms.Panel> kontrolować z **formularzy systemu Windows** karcie na **przybornika** na formularzu.  
  
2.  Rysuj <xref:System.Windows.Forms.RadioButton> formantów na <xref:System.Windows.Forms.GroupBox> lub <xref:System.Windows.Forms.Panel> formantu.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.RadioButton>  
 [RadioButton, kontrolka — omówienie](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Panel, kontrolka — omówienie](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [GroupBox, kontrolka — omówienie](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [CheckBox, kontrolka — omówienie](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [RadioButton, kontrolka](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
