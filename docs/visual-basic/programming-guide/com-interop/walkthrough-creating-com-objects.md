---
title: "Wskazówki: tworzenie obiektów COM z Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff7d3868a2e3ddaba06ebc6f98c8eacfc7299366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Wskazówki: tworzenie obiektów COM z Visual Basic
Podczas tworzenia nowej aplikacji i składników, najlepiej utworzyć zestawy .NET Framework. Jednak [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] również ułatwia udostępnianie składników .NET Framework modelowi COM. Umożliwia podanie nowych składników starszych pakietów aplikacji wymagających składników COM. W tym przewodniku przedstawiono sposób użycia [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] do udostępnienia [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] obiekty jako obiekty COM, zarówno z i bez szablonu klasy COM.  
  
 Najłatwiejszym sposobem na uwidocznienie obiektów COM jest przy użyciu szablonu klasy COM. Szablon klasy COM tworzy nową klasę, a następnie konfiguruje projektu do generowania klasy i współdziałanie warstwy jako obiekt COM i zarejestrowanie go za pomocą systemu operacyjnego.  
  
> [!NOTE]
>  Mimo że można również ujawniać klasy utworzonej w [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] jako obiektu COM dla niezarządzanego kodu do użycia, nie jest obiektem COM. wartość true i nie może być używany przez [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Aby uzyskać więcej informacji, zobacz [współdziałanie COM w aplikacjach .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Aby utworzyć obiekt COM za pomocą szablonu klasy COM  
  
1.  Otwórz nowy projekt aplikacji systemu Windows z **pliku** menu, klikając **nowy projekt**.  
  
2.  W **nowy projekt** okno dialogowe, w obszarze **typów projektów** pola, sprawdź, czy wybrano systemu Windows. Wybierz **biblioteki klas** z **szablony** , a następnie kliknij przycisk **OK**. Zostanie wyświetlony nowy projekt.  
  
3.  Wybierz **Dodaj nowy element** z **projektu** menu. **Dodaj nowy element** zostanie wyświetlone okno dialogowe.  
  
4.  Wybierz **klasy COM** z **szablony** , a następnie kliknij przycisk **Dodaj**. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Dodaje nową klasę i konfiguruje nowy projekt dla modelu COM interop.  
  
5.  Dodaj kod, takie jak właściwości, metod i zdarzeń do klasy COM.  
  
6.  Wybierz **kompilacji ClassLibrary1** z **kompilacji** menu. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Tworzy zestaw i rejestruje obiektu modelu COM w systemie operacyjnym.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Tworzenie obiektów COM bez szablonu klasy COM  
 Można również utworzyć ręcznie, zamiast używać szablonu klasy COM klasy COM. Ta procedura jest przydatne podczas pracy z poziomu wiersza polecenia lub gdy chcesz mieć większą kontrolę nad sposób definiowania obiektów COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Aby skonfigurować projekt do wygenerowania obiektów COM  
  
1.  Otwórz nowy projekt aplikacji systemu Windows z **pliku** menu, klikając **NewProject**.  
  
2.  W **nowy projekt** okno dialogowe, w obszarze **typów projektów** pola, sprawdź, czy wybrano systemu Windows. Wybierz **biblioteki klas** z **szablony** , a następnie kliknij przycisk **OK**. Zostanie wyświetlony nowy projekt.  
  
3.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy projekt, a następnie kliknij przycisk **właściwości**. **Projektanta projektu** jest wyświetlany.  
  
4.  Kliknij przycisk **skompilować** kartę.  
  
5.  Wybierz **Zarejestruj dla międzyoperacyjności z modelem COM** pole wyboru.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Aby skonfigurować kod w klasie do utworzenia obiektu modelu COM  
  
1.  W **Eksploratora rozwiązań**, kliknij dwukrotnie **Class1.vb** Aby wyświetlić jego kod.  
  
2.  Zmień nazwę klasy, która ma `ComClass1`.  
  
3.  Dodaj następujące ograniczenia do `ComClass1`. Zapisze one stałe Unikatowy identyfikator globalny (GUID), które obiekty COM są muszą być zainstalowane.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  Na **narzędzia** menu, kliknij przycisk **utworzyć identyfikatora Guid**. W **utworzyć identyfikatora GUID** okno dialogowe, kliknij przycisk **Format rejestru** , a następnie kliknij przycisk **kopiowania**. Kliknij przycisk **zakończenia**.  
  
5.  Zastąp ciąg pusty dla `ClassId` o identyfikatorze GUID, nawiasy klamrowe usuwanie wiodące i końcowe. Na przykład, jeżeli został podany identyfikator GUID przez Guidgen jest `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , a następnie kod powinien wyglądać następująco.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Powtórz poprzednie kroki dla `InterfaceId` i `EventsId` stałe, jak w poniższym przykładzie.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Upewnij się, że identyfikatory GUID są nowych i unikatowych; w przeciwnym razie składnika COM może powodować konflikt z innymi składnikami COM.  
  
7.  Dodaj `ComClass` atrybutu `ComClass1`, określając identyfikatory GUID dla klasy: ID, identyfikator interfejsu i identyfikator zdarzenia jak w poniższym przykładzie:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Klasy COM musi mieć bez parametrów `Public Sub New()` konstruktora lub tej klasy nie spowoduje zarejestrowania poprawnie. Dodaj konstruktora do klasy:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Dodaj właściwości, metod i zdarzeń do klasy, kończy je z `End Class` instrukcji. Wybierz **Kompiluj rozwiązanie** z **kompilacji** menu. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Tworzy zestaw i rejestruje obiektu modelu COM w systemie operacyjnym.  
  
    > [!NOTE]
    >  Obiekty COM Generowanie z [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nie można używać w innych [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] aplikacji, ponieważ nie mają wartość true, obiekty COM. Próby dodania odwołania do takich obiektów COM zgłosi błąd. Aby uzyskać więcej informacji, zobacz [współdziałanie COM w aplikacjach .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [Współdziałanie z COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Wskazówki: Wdrażanie dziedziczenia z obiektami COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [#Region — dyrektywa](../../../visual-basic/language-reference/directives/region-directive.md)  
 [Współdziałanie COM w aplikacjach .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Problemów związanych ze współdziałaniem](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
