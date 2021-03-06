---
title: "Ograniczenia składnika Timer formularzy systemu Windows &#39; właściwości interwału s"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec53957a61806239fdd41761de6e172681b7497b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Ograniczenia składnika Timer formularzy systemu Windows &#39; właściwości interwału s
Formularze systemu Windows <xref:System.Windows.Forms.Timer> składnik ma <xref:System.Windows.Forms.Timer.Interval%2A> właściwość, która określa liczbę milisekund, jaką między zdarzenie czasomierza jednego i drugiego. Jeśli składnik jest wyłączony, czasomierz będzie nadal otrzymywał <xref:System.Windows.Forms.Timer.Tick> zdarzeń w przybliżeniu równe odstępach czasu.  
  
 Ten składnik jest przeznaczony dla środowiska Windows Forms. Jeśli potrzebujesz czasomierza, które jest odpowiednie dla środowiska serwera, zobacz [wprowadzenie do serwerowych czasomierze](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Właściwości interwału  
 <xref:System.Windows.Forms.Timer.Interval%2A> Właściwość ma kilka ograniczeń dotyczących należy wziąć pod uwagę, gdy są programowania <xref:System.Windows.Forms.Timer> składnika:  
  
-   Jeśli aplikacji lub innej aplikacji jest wprowadzenie duże zapotrzebowanie na komputerze — takie jak pętle długie, znacznym obliczeń, lub dysk, sieci lub dostępu do portu — aplikacji nie może pobrać zdarzenia tyle razy, jako <xref:System.Windows.Forms.Timer.Interval%2A> określa właściwości.  
  
-   Interwał nie jest gwarantowana upłynąć dokładnie na czas. W celu zapewnienia dokładność, czasomierza powinien sprawdzić zegara systemowego zgodnie z potrzebami, a nie spróbuj do śledzenia skumulowany czas wewnętrznie.  
  
-   Dokładność <xref:System.Windows.Forms.Timer.Interval%2A> właściwości jest podana w milisekundach. Niektóre komputery zawierają wysokiej rozdzielczości licznik o rozdzielczości wyższej niż milisekund. Dostępność tych liczników jest zależna od sprzętu procesora komputera. Aby uzyskać więcej informacji zobacz artykuł 172338, "Jak Użyj QueryPerformanceCounter do czasu kod," w bazie wiedzy Microsoft Knowledge Base pod adresem http://support.microsoft.com.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.Timer>  
 [Timer, składnik](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Timer, składnik — omówienie](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
