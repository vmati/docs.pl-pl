---
title: "Jak użyć słownika zasobów zakresu aplikacji"
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
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece6a5d2123bb118f11940081e3c1d939815a8ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Jak użyć słownika zasobów zakresu aplikacji
Ten przykład przedstawia sposób definiowania i użyć słownika zasobów niestandardowych zakresu aplikacji.  
  
## <a name="example"></a>Przykład  
 <xref:System.Windows.Application>udostępnia magazyn zakresu aplikacji do zasobów udostępnionych: <xref:System.Windows.Application.Resources%2A>. Domyślnie <xref:System.Windows.Application.Resources%2A> właściwość jest inicjowana przy użyciu wystąpienia <xref:System.Windows.ResourceDictionary> typu. Użyj tego wystąpienia, gdy get i set właściwości zakresu aplikacji za pomocą <xref:System.Windows.Application.Resources%2A>. Aby uzyskać więcej informacji, zobacz [porady: pobieranie i Ustawianie zakresu aplikacji zasobów](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).
  
 Jeśli masz wiele zasobów, które można ustawić za pomocą <xref:System.Windows.Application.Resources%2A>, można zamiast tego użyć słownika zasobów niestandardowych do przechowywania tych zasobów i ustawić <xref:System.Windows.Application.Resources%2A> z nim zamiast tego. Poniżej przedstawiono, jak zadeklarować słownik zasobów niestandardowych przy użyciu kodu XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Zamiana słowniki zasobów całej przy użyciu <xref:System.Windows.Application.Resources%2A> służy do obsługi motywów zakres aplikacji, gdzie każdy motyw jest hermetyzowany za słownika pojedynczego zasobu. Poniższy przykład przedstawia sposób ustawiania <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Poniżej pokazano, jak można pobrać zasobów zakresu aplikacji ze słownika zasobów udostępnianych przez <xref:System.Windows.Application.Resources%2A> w języku XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Poniżej przedstawiono, jak również można uzyskać zasoby w kodzie.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Istnieją dwa zagadnienia dotyczące podczas korzystania z <xref:System.Windows.Application.Resources%2A>. Po pierwsze, słownik *klucza* jest obiektem, dlatego należy użyć dokładnie tego samego wystąpienia obiektu podczas zarówno ustawiania i pobierania wartości właściwości. (Należy zwrócić uwagę, czy klucz jest rozróżniana wielkość liter, korzystając z ciągu). Drugi, słownik *wartość* jest obiektem, dlatego należy przekonwertować wartości na żądany typ. podczas pobierania wartości właściwości.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [Zasoby XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Połączone słowniki zasobów](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
