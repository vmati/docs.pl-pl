---
title: "Wdrażanie aplikacji międzyoperacyjnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying applications [.NET Framework], interop
- strong-named assemblies, interop applications
- unsigned assemblies
- private assemblies
- exposing COM components to .NET Framework
- interoperation with unmanaged code, deploying applications
- shared assemblies
- COM interop, deploying applications
- interoperation with unmanaged code, exposing COM components
- signed assemblies
- COM interop, exposing COM components
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0682fd149134531781346d21245a0b1fd3fc4d43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-an-interop-application"></a>Wdrażanie aplikacji międzyoperacyjnych
Międzyoperacyjne aplikacji zwykle obejmuje zestaw klienta .NET, co najmniej jeden zestawy międzyoperacyjne reprezentujących różne COM biblioteki typów i co najmniej jeden zarejestrowany składników COM. Visual Studio i [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] zapewniają narzędzia do importowania i skonwertować biblioteki typów na zestaw międzyoperacyjny zgodnie z opisem w [Importowanie biblioteki typów jako zestawu](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md). Istnieją dwa sposoby wdrażania aplikacji międzyoperacyjnych:  
  
-   Za pomocą osadzone typy międzyoperacyjne: począwszy od [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], można nakazać kompilatorowi osadzanie informacji o typie z zestawu międzyoperacyjnego do pliku wykonywalnego. Kompilator osadza informacje typu, używanych przez aplikację. Nie trzeba wdrażać zestawu międzyoperacyjnego z aplikacją. Jest to zalecana technika.  
  
-   Wdrażając zestawy międzyoperacyjne: można utworzyć standardowe odwołanie do zestawu międzyoperacyjnego. W takim przypadku należy wdrożyć zestawu międzyoperacyjnego z aplikacją. Jeśli zostanie zastosowana ta technika, a nie jest używany prywatny składnika modelu COM, zawsze odwoływać się do podstawowego zestawu międzyoperacyjnego (PIA) opublikowane przez autora składnika modelu COM, który chcesz uwzględnić w kodzie zarządzanym. Aby uzyskać więcej informacji na temat Tworzenie i używanie podstawowe zestawy międzyoperacyjne zobacz [podstawowe zestawy międzyoperacyjne](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
 Jeśli używasz osadzone typy międzyoperacyjne, wdrożenie jest proste i bezpośrednie. Nie ma specjalnych, należy wykonać. Dalszej części tego artykułu opisano scenariusze wdrażania zestawy międzyoperacyjne z aplikacją.  
  
## <a name="deploying-interop-assemblies"></a>Wdrażanie zestawy międzyoperacyjne  
 Zestawy mogą mieć silnej nazwy. Zestaw o silnej nazwie zawiera klucz publiczny wydawcy, który zapewnia unikatową tożsamość. Zestawy, które są tworzone przez [Importer biblioteki typów (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) mogą być podpisane przez wydawcę za pomocą **/KeyFile** opcji. Należy zainstalować podpisanych zestawów w globalnej pamięci podręcznej zestawów. Zestawy nieoznaczone musi być zainstalowany na komputerze użytkownika jako zestawy prywatne.  
  
### <a name="private-assemblies"></a>Zestawy prywatne  
 Aby zainstalować zestaw do użycia przez użytkowników, zarówno plik wykonywalny aplikacji i zestawu międzyoperacyjnego, który zawiera importowanych typów COM musi być zainstalowany w tej samej struktury katalogów. Na poniższej ilustracji przedstawiono niepodpisanego zestawu międzyoperacyjnego na użytek prywatnie Client1.exe i Client2.exe, które znajdują się w innej aplikacji, katalogów. Zestawu międzyoperacyjnego, która jest wywoływana LOANLib.dll w tym przykładzie, zainstalowano dwa razy.  
  
 ![Struktura katalogów i rejestru systemu Windows](../../../docs/framework/interop/media/comdeployprivate.gif "comdeployprivate")  
Katalog struktury i wpisy rejestru prywatnego wdrożenia  
  
 Wszystkie składniki COM skojarzone z aplikacją, musi być zainstalowany w rejestrze systemu Windows. Jeśli Client1.exe i Client2.exe na ilustracji są zainstalowane na różnych komputerach, należy zarejestrować składników COM na obu komputerach.  
  
### <a name="shared-assemblies"></a>Zestawy udostępnione  
 Zestawy, które są współużytkowane przez wiele aplikacji należy zainstalować w scentralizowane repozytorium o nazwie globalnej pamięci podręcznej zestawów. Klientów platformy .NET można uzyskać dostępu do tej samej kopii zestawu międzyoperacyjnego, który jest podpisany i zainstalowane w globalnej pamięci podręcznej zestawów. Aby uzyskać więcej informacji na temat Tworzenie i używanie podstawowe zestawy międzyoperacyjne zobacz [podstawowe zestawy międzyoperacyjne](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
## <a name="see-also"></a>Zobacz też  
 [Udostępnianie składników COM programowi .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 [Importowanie biblioteki typów jako zestawu](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Używanie typów COM w kodzie zarządzanym](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [Kompilowanie projektu międzyoperacyjnego](../../../docs/framework/interop/compiling-an-interop-project.md)
