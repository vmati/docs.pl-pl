---
title: "Jak wyszukać zegar synchronicznie"
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
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90611e0b18e58e4c24b44e7c87cba56e4b0b01ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a>Jak wyszukać zegar synchronicznie
Użyj <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metody można synchronicznie wyszukiwanie zegarze do określonego punktu. W poniższym przykładzie pokazano zarówno <xref:System.Windows.Media.Animation.ClockController.Seek%2A> i <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metody <xref:System.Windows.Media.Animation.ClockController>.  
  
 W tym przykładzie przedstawiono sposób wyszukiwania <xref:System.Windows.Media.Animation.Clock>; przykład pokazujący sposób wyszukiwania scenorysu, zobacz [wyszukiwanie scenorysu synchronicznie](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Przykład  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
