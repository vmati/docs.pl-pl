---
title: 'Porady: dziedziczenie z klasy UserControl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8d04eb3c0f9ad3ef9f316bf156a9cc9568e7f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Porady: dziedziczenie z klasy UserControl
Aby połączyć funkcji formanty formularzy systemu Windows co najmniej jeden z kodu niestandardowego, można utworzyć *kontrolki użytkownika*. Formanty użytkownika Scalaj programowanie szybkiej kontroli, standardowych formularzy systemu Windows kontrolować funkcjonalność i wszechstronność niestandardowe właściwości i metod. Po rozpoczęciu tworzenia kontrolki użytkownika, są prezentowane w Projektancie widoczne, na której można umieścić standardowe formanty formularzy systemu Windows. Formanty zachować wszystkie ich związanego z używaniem funkcji, a także wygląd i zachowanie (wygląd i działanie) standardowych kontrolek. Po tych kontrolek są wbudowane w formancie użytkownika, jednak nie są one dostępne za pośrednictwem kodu. Kontrola użytkownika nie własną rysowania i również obsługuje wszystkie podstawowe funkcje związane z formantami.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-user-control"></a>Aby utworzyć kontrolkę użytkownika  
  
1.  Utwórz nową **Biblioteka formantów systemu Windows** projektu.  
  
     Nowy projekt zostanie utworzona z kontrola pustego użytkownika.  
  
2.  Przeciągnij formanty z **formularzy systemu Windows** karcie **przybornika** na z projektantem.  
  
3.  Formanty należy znajduje się i zaprojektowane jak mają być wyświetlane w formancie użytkownika końcowego. Umożliwia deweloperom korzystanie formanty składników, musi zadeklarować je jako public lub selektywnie ujawnić właściwości formantu składników. Aby uzyskać więcej informacji, zobacz [porady: udostępnianie właściwości formantów składnika](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implementowanie niestandardowych metod ani właściwości zawierające formantu.  
  
5.  Naciśnij klawisz F5, aby skompilować projekt i uruchomić kontrolę w **kontener testu UserControl**. Aby uzyskać więcej informacji, zobacz [porady: testowanie zachowania UserControl w czasie wykonywania](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Różne typy kontrolek niestandardowych](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Instrukcje: dziedziczenie z klasy kontrolek](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Instrukcje: dziedziczenie z istniejących kontrolek formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Instrukcje: tworzenie kontrolek dla formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Rozwiązywanie problemów z odziedziczonymi programami obsługi zdarzeń w języku Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Instrukcje: testowanie zachowania UserControl w czasie wykonywania](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
