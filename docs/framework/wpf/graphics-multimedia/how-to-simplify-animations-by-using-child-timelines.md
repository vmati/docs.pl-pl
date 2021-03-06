---
title: "Jak uprościć animacje przy użyciu podrzędnych szeregów czasowych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d3b8f1ca1dbf7ba5452acffc62fdf0b655c9c12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Jak uprościć animacje przy użyciu podrzędnych szeregów czasowych
W tym przykładzie pokazano, jak uprościć animacji za pomocą podrzędnej <xref:System.Windows.Media.Animation.ParallelTimeline> obiektów. A <xref:System.Windows.Media.Animation.Storyboard> jest typem <xref:System.Windows.Media.Animation.Timeline> udostępniająca informacje określania wartości docelowej dla osi czasu, zawiera. Użyj <xref:System.Windows.Media.Animation.Storyboard> zapewnienie kierowanie informacji, w tym informacje o obiekcie i właściwości osi czasu.  
  
 Aby rozpocząć animacji, użyj jednej lub kilku <xref:System.Windows.Media.Animation.ParallelTimeline> obiekty jako elementy podrzędne zagnieżdżonych <xref:System.Windows.Media.Animation.Storyboard>. Te <xref:System.Windows.Media.Animation.ParallelTimeline> obiekty mogą zawierać inne animacji i w związku z tym można lepiej Hermetyzowanie sekwencji chronometrażu w złożonych animacji. Na przykład, jeśli są animacji <xref:System.Windows.Controls.TextBlock> i kilka kształtów w tej samej <xref:System.Windows.Media.Animation.Storyboard>, można oddzielić animacji dla <xref:System.Windows.Controls.TextBlock> i kształty umieszczanie każdego w osobnym <xref:System.Windows.Media.Animation.ParallelTimeline>. Ponieważ każdy <xref:System.Windows.Media.Animation.ParallelTimeline> ma własną <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> i wszystkie elementy podrzędne <xref:System.Windows.Media.Animation.ParallelTimeline> rozpocząć względem to <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, lepiej jest hermetyzowany chronometrażu.  
  
 Poniższy przykład animuje dwóch fragmentów tekstu (<xref:System.Windows.Controls.TextBlock> obiektów) od w tym samym <xref:System.Windows.Media.Animation.Storyboard>. A <xref:System.Windows.Media.Animation.ParallelTimeline> hermetyzuje animacji w jednej z <xref:System.Windows.Controls.TextBlock> obiektów.  
  
 **Wydajność Uwaga:** mimo że można zagnieżdżać <xref:System.Windows.Media.Animation.Storyboard> osi czasu wewnątrz innych, <xref:System.Windows.Media.Animation.ParallelTimeline>s są bardziej odpowiednie dla zagnieżdżania, ponieważ wymagają one mniejsze koszty. ( <xref:System.Windows.Media.Animation.Storyboard> Klasa dziedziczy <xref:System.Windows.Media.Animation.ParallelTimeline> klasy.)  
  
## <a name="example"></a>Przykład  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Zobacz też  
 [Animacja — przegląd](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Określanie elementu HandoffBehavior między animacjami scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
