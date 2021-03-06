---
title: "Uwagi odnośnie do hostowania kontrolki ActiveX na formularzu systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e35679245d93a98b76bff31d97c6111146348a00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Uwagi odnośnie do hostowania kontrolki ActiveX na formularzu systemu Windows
Mimo że program Windows Forms zostały zoptymalizowane do hosta formanty formularzy systemu Windows, można nadal używać formantów ActiveX. Podczas planowania aplikacji korzystającej z kontrolki ActiveX, należy pamiętać o następujących kwestiach:  
  
-   **Zabezpieczenia** środowisko uruchomieniowe języka wspólnego została rozszerzona w odniesieniu do zabezpieczenia dostępu kodu. Aplikacje z formularzy systemu Windows można uruchomić w pełni zaufanym środowisku bez problemu i częściowo zaufanym środowisku z większością funkcji dostępny. Formanty formularzy systemu Windows mogą być hostowane w przeglądarce za pomocą nie komplikacje. Formantów na formularzach systemu Windows nie można jednak korzystać z tych ulepszeń zabezpieczeń. Uruchomienie formantu ActiveX wymaga uprawnienie kodu niezarządzanego, które ustawiono <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> właściwości. Aby uzyskać więcej informacji dotyczących zabezpieczeń i uprawnień kodu niezarządzanego, zobacz <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
-   **Całkowity koszt użytkowania** formantów ActiveX dodany do formularza systemu Windows zostały wdrożone za pomocą formularza systemu Windows w całości, można znacznie zwiększają rozmiar plików utworzony. Ponadto za pomocą formantów na formularzach systemu Windows wymaga zapisu do rejestru. Jest to bardziej inwazyjne na komputerze użytkownika niż formanty formularzy systemu Windows, które nie wymagają to.  
  
    > [!NOTE]
    >  Praca z ActiveX formantu wymaga użycia otoka COM interop. Aby uzyskać więcej informacji, zobacz [współdziałanie COM w języku Visual Basic i Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Jeśli nazwa elementu członkowskiego formantu ActiveX zgodna nazwą zdefiniowaną w [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], następnie Importer kontrolki ActiveX będzie przed nazwą elementu członkowskiego **Ctl** po tworzy <xref:System.Windows.Forms.AxHost> pochodnej klasy. Na przykład, jeśli formant ActiveX ma element członkowski o nazwie **układu**, jego nazwa zostanie zmieniona **CtlLayout** w klasie pochodnej AxHost ponieważ **układu** zdarzeń jest zdefiniowana w [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: dodawanie kontrolek ActiveX do formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Zabezpieczenia dostępu kodu](../../../../docs/framework/misc/code-access-security.md)  
 [Formanty i obiektów programowalnych w różnych językach i biblioteki](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Umieszczanie kontrolek na formularzach Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Kontrolki formularzy Windows Forms](../../../../docs/framework/winforms/controls/index.md)
