---
title: "Przykład technologii serializacji typów ogólnych usług sieci Web"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e9d5ed7a1bb55803cd1df8c6c6c740e8facb306e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="web-services-generics-serialization-technology-sample"></a>Przykład technologii serializacji typów ogólnych usług sieci Web
[Pobieranie próbki](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 W tym przykładzie pokazano, jak i kontrolowanie serializacji typów ogólnych w usługach sieci Web ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Aby samodzielnie tworzyć przykładowy przy użyciu programu Visual Studio  
  
1.  Otwórz program Visual Studio i wybierz **nowej witryny sieci Web** z **pliku** menu.  
  
2.  W **nowej witryny sieci Web** okno dialogowe, wybierz w okienku po lewej stronie odpowiedni język programowania, a następnie w okienku po prawej stronie wybierz **usługi sieci Web ASP.NET**.  
  
3.  Kliknij przycisk **Przeglądaj** i przejdź do podkatalogu \CS\GenericsService.  
  
4.  Wybierz Service.asmx do otwierania tego PLiku w programie Visual Studio.  
  
5.  Na **kompilacji** menu, kliknij przycisk **Kompiluj rozwiązanie**.  
  
> [!NOTE]
>  Pierwszych pięć kroków na tej liście są opcjonalne. Środowisko uruchomieniowe programu .NET Framework automatycznie generuje razem usługi pierwszy sieci Web, gdy wymagane są usługi.  
  
> [!NOTE]
>  Poniższe kroki są wymagane do utworzenia próbki.  
  
1.  Otwórz [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] i przejdź do podkatalogu \CS.  
  
2.  Kliknij prawym przyciskiem myszy ikonę podkatalogu GenericsService, a następnie wybierz **udostępnianie i zabezpieczenia**.  
  
3.  W **udostępnianie w sieci Web** wybierz opcję **Udostępnij ten Folder**.  
  
> [!IMPORTANT]
>  Zanotuj nazwę katalogu wirtualnego, który znajduje się w **aliasy** okienka, ponieważ będą potrzebne do uruchomienia przykładu.  
  
### <a name="to-build-the-sample-using-internet-information-services"></a>Aby samodzielnie tworzyć przykładowy przy użyciu Internetowych usług informacyjnych  
  
1.  Otwórz **Internetowe usługi informacyjne** zarządzania przystawka i rozwiń **witryn sieci Web**.  
  
2.  Kliknięcie lewym przyciskiem myszy **domyślna witryna sieci Web**, wybierz pozycję **nowy**, a następnie wybierz **katalog wirtualny?** do utworzenia **Kreatora tworzenia katalogów wirtualnych**.  
  
3.  Kliknij przycisk **dalej**, wprowadź publicznym aliasem katalogu wirtualnego i kliknij przycisk **dalej**.  
  
4.  Wprowadź ścieżkę do katalogu, w którym zapisano próbki (zwykle w podkatalogu \CS\GenericsService), a następnie kliknij przycisk **dalej**. Kliknij przycisk **dalej** aby zakończyć pracę kreatora.  
  
> [!IMPORTANT]
>  Zanotuj nazwę katalogu wirtualnego, który znajduje się w **Alias** okienka, ponieważ będą potrzebne do uruchomienia przykładu.  
  
### <a name="to-run-the-sample"></a>Aby uruchomić przykładowy  
  
1.  Otwórz okno przeglądarki, a następnie wybierz jego paskiem adresu.  
  
2.  Typ **http://localhost/ [wirtualnego directory]/Service.asmx**, gdzie [katalog wirtualny] reprezentuje katalog wirtualny utworzony podczas tworzenia przykładowej.  
  
## <a name="remarks"></a>Uwagi  
 Przykład przedstawia domyślnej strony ASP.NET, która zawiera łącza do definicji usługi sieci Web. Można dostosować wyświetlanie oprócz zmodyfikowanie kodu źródłowego dla usługi sieci Web. Aby uzyskać więcej informacji, zobacz [klientami usługi sieci Web XML budynku](http://msdn.microsoft.com/en-us/c606f3cb-4111-45b4-ae42-9300420fa16c).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Collections.Generic>  
 <xref:System.Web.Services>  
 <xref:System.Xml.Serialization>  
 [Serializacja](../../../docs/standard/serialization/index.md)  
 [Utworzone za pomocą programu ASP.NET i klientami usługi XML sieci Web usług XML sieci Web](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)
