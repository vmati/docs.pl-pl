---
title: "Marshaling międzyoperacyjny"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5bfd5ca9d42c654882c77efafed82aec7e4f0c9b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="interop-marshaling"></a>Marshaling międzyoperacyjny
<a name="top"></a>Przekazywanie międzyoperacyjne decyduje o tym, jak dane są przekazywane w metody argumentów i zwracanych wartości między zarządzanymi i niezarządzanymi pamięci podczas wywołania. Przekazywanie międzyoperacyjne jest wykonywane przez usługę kierowania środowisko uruchomieniowe języka wspólnego firmy działalnością czasu wykonywania.  
  
 Większość typów danych mają wspólne reprezentacje w pamięci zarządzane i niezarządzane. Organizator międzyoperacyjnego obsługuje te typy dla Ciebie. Inne typy może być niejednoznaczna lub nie jest reprezentowana przez cały w pamięci zarządzanej.  
  
 Niejednoznaczne typ może mieć wielu reprezentacje niezarządzane, mapowane na jeden typ zarządzany lub Brak informacji o typie, takich jak rozmiar tablicy. Niejednoznacznych typów organizatora udostępnia reprezentację domyślne i Reprezentacje alternatywne, w których istnieje wiele oświadczeń. Możesz podać jawne instrukcje organizatora, w jaki jest do organizowania niejednoznaczne typu.  
  
 Ten przegląd zawiera następujące sekcje:  
  
-   [Wywołanie platformy i modele międzyoperacyjnego modelu COM](#platform_invoke_and_com_interop_models)  
  
-   [Kierowanie parametrów i Apartamentach COM](#marshaling_and_com_apartments)  
  
-   [Kierowanie wywołań zdalnych](#marshaling_remote_calls)  
  
-   [Tematy pokrewne](#related_topics)  
  
-   [Dokumentacja](#reference)  
  
<a name="platform_invoke_and_com_interop_models"></a>   
## <a name="platform-invoke-and-com-interop-models"></a>Wywołanie platformy i modele międzyoperacyjnego modelu COM  
 Środowisko uruchomieniowe języka wspólnego udostępnia dwa mechanizmy współdziałanie z kodem niezarządzanym:  
  
-   Wywołanie platformy, co pozwala kodu zarządzanego do wywołania funkcji wyeksportowanych z biblioteki niezarządzane.  
  
-   Współdziałanie z COM, który umożliwia kodu zarządzanego do interakcji z obiektami składnika modelu COM (Object) za pośrednictwem interfejsów.  
  
 Wywołanie zarówno platformy i COM interop Użyj przekazywanie międzyoperacyjne dokładnie zmieniać argumenty metody wywołującego i wywoływany i z powrotem, jeśli to konieczne. Jak pokazano na poniższej ilustracji, wywołanie platformy przepływy wywołanie metody z kodu zarządzanego do kodu niezarządzanego i nigdy nie inny sposób, chyba że [funkcje wywołania zwrotnego](../../../docs/framework/interop/callback-functions.md) obejmuje. Mimo że wywołanie platformy wywołania mogą przepływać tylko z kodu zarządzanego do kodu niezarządzanego, dane mogą przepływać w obu kierunkach jako parametrów wejściowych lub wyjściowych. Wywołania metody międzyoperacyjnego COM może przepływać w obu kierunkach.  
  
 ![Wywołanie platformy](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")  
Wywołanie platformy i przepływu wywołania międzyoperacyjnego modelu COM  
  
 Na najniższym poziomie zarówno mechanizmów używać tego samego interop, organizowanie usługi; Jednak niektóre typy danych są obsługiwane wyłącznie przez współdziałanie z COM lub wywołanie platformy. Aby uzyskać więcej informacji, zobacz [domyślne zachowanie Marshalingu](../../../docs/framework/interop/default-marshaling-behavior.md).  
  
 [Powrót do początku](#top)  
  
<a name="marshaling_and_com_apartments"></a>   
## <a name="marshaling-and-com-apartments"></a>Kierowanie parametrów i Apartamentach COM  
 Organizator międzyoperacyjnego marshals danych między stercie środowiska uruchomieniowego języka wspólnego i niezarządzane stosu. Przekazywanie występuje, gdy obiekt wywołujący i wywoływanego nie może działać na tym samym wystąpieniu danych. Organizator międzyoperacyjnego umożliwia dla obiekt wywołujący i wywoływany wydaje się działających na tych samych danych, nawet jeśli ma swoje własne kopię danych.  
  
 COM ma również organizatora, który marshals danych między apartamentach COM lub różnych procesów COM. Podczas wywoływania metody między zarządzanymi i niezarządzanymi kodu w tej samej apartamentu COM, organizator międzyoperacyjny jest tylko organizatora, związane. Podczas wywoływania metody między kodu zarządzanego i kodu niezarządzanego innego apartamentu COM lub innego procesu, zarówno międzyoperacyjne organizatora i Organizator COM są wykorzystywane.  
  
### <a name="com-clients-and-managed-servers"></a>Klienci COM i serwerów zarządzanych  
 Wyeksportowane serwera zarządzanego z biblioteki typów zarejestrowany przez [Regasm.exe (narzędzie rejestracji zestawów)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) ma `ThreadingModel` wpis rejestru ustawioną `Both`. Ta wartość wskazuje, że serwer można aktywować jednowątkowego apartamentu (STA) lub wielowątkowe apartamentu (MTA). Obiekt serwera jest tworzony w tym samym apartamencie jako swojego obiektu wywołującego, jak pokazano w poniższej tabeli.  
  
|Klient modelu COM|Serwer .NET|Organizowanie wymagania|  
|----------------|-----------------|-----------------------------|  
|STA.|`Both`staje się pozostaje tryb komórek jednowątkowych|Przekazywanie tego samego typu apartment.|  
|MTA|`Both`staje się MTA.|Przekazywanie tego samego typu apartment.|  
  
 Ponieważ klienta i serwera znajdują się w tym samym apartamencie, interop automatycznie przekazywanie usługi obsługuje przekazywanie wszystkich danych. Na poniższej ilustracji przedstawiono funkcjonowania między zarządzanymi i niezarządzanymi stosów w ramach tego samego typu apartment styl modelu COM interop usług kierowania.  
  
 ![Przekazywanie międzyoperacyjne](../../../docs/framework/interop/media/interopheap.gif "interopheap")  
Proces kierowania tego samego typu apartment  
  
 Jeśli planujesz zarządzany serwer eksportu, należy pamiętać, określa, czy klient modelu COM typu apartment serwera. Serwer zarządzany wywoływane przez klient modelu COM w MTA zainicjować musi zapewniać bezpieczeństwo wątków.  
  
### <a name="managed-clients-and-com-servers"></a>Zarządzanych klientów i serwerów COM  
 Ustawieniem domyślnym dla apartamentach zarządzanego klienta jest MTA; Typ aplikacji klienta .NET można jednak zmienić ustawienie domyślne. Na przykład [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] ustawienia komórkowy klienta jest pozostaje tryb komórek jednowątkowych Można użyć <xref:System.STAThreadAttribute?displayProperty=nameWithType>, <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> właściwości, lub <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> właściwość, aby sprawdzić i zmienić ustawienia typu apartment klient zarządzany.  
  
 Autor składnika ustawia koligacji wątku serwera COM. W poniższej tabeli przedstawiono kombinacje ustawienia komórkowy .NET klientów i serwerów COM. Pokazuje też, powstałe w ten sposób organizowanie wymagania dla kombinacji.  
  
|Klient .NET|Serwer COM|Organizowanie wymagania|  
|-----------------|----------------|-----------------------------|  
|MTA (ustawienie domyślne)|MTA<br /><br /> STA.|Przekazywanie międzyoperacyjne.<br /><br /> I organizowanie COM Interop.|  
|STA.|MTA<br /><br /> STA.|I organizowanie COM Interop.<br /><br /> Przekazywanie międzyoperacyjne.|  
  
 Gdy klientów zarządzanych i niezarządzanych serwera są tego samego typu apartment, interop organizowanie usługi obsługuje przekazywanie wszystkich danych. Jednak jeśli klienta i serwera są inicjowane w różnych apartamentach, kierowanie modelu COM wymagany jest również. Na poniższej ilustracji przedstawiono elementy rozmowę między apartamentu.  
  
 ![Organizowanie COM](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")  
Wywołanie typu apartment między między klientem .NET a obiektu modelu COM  
  
 Dla typu apartment między przekazywanie, należy wykonać następujące:  
  
-   Zaakceptuj obciążenie organizowanie między apartamentu, który jest widoczny tylko wtedy, gdy istnieje wiele wywołań granicy. Należy zarejestrować biblioteki typów dla wywołań pomyślnie przekroczenia granic apartamentu składnika modelu COM.  
  
-   Zmiany głównego wątku przez ustawienie klienta wątku STA i MTA. Na przykład jeśli klient C# wywołuje wiele składników STA COM, można uniknąć apartamentu między przekazywanie przez ustawienie pozostaje tryb komórek jednowątkowych wątku głównego  
  
    > [!NOTE]
    >  Po ustawieniu wątek klienta C# STA wywołania składników MTA COM będzie wymagać przekazywanie typu apartment między.  
  
 Aby uzyskać instrukcje dotyczące wybierania jawnie z modelem typu apartment, zobacz [zarządzane i niezarządzane wątkowość](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5).  
  
 [Powrót do początku](#top)  
  
<a name="marshaling_remote_calls"></a>   
## <a name="marshaling-remote-calls"></a>Kierowanie wywołań zdalnych  
 Podobnie jak w przypadku typu apartment między przekazywanie, organizowanie COM uczestniczy w każdym wywołaniu między zarządzanymi i niezarządzanymi kod zawsze, gdy obiekty znajdują się w osobnych procesach. Na przykład:  
  
-   Klient modelu COM, który wywołuje serwer zarządzany na zdalnym hoście używa rozproszonych (DCOM).  
  
-   Klient zarządzany wywołująca serwera COM na zdalnym hoście używa modelu DCOM.  
  
 Na poniższej ilustracji pokazano, jak międzyoperacyjnego organizowanie i organizowanie COM Podaj kanały komunikacyjne bariery procesu i hosta.  
  
 ![Organizowanie COM](../../../docs/framework/interop/media/interophost.gif "interophost")  
Organizowanie międzyprocesowa  
  
### <a name="preserving-identity"></a>Zachowywanie tożsamości  
 Środowisko uruchomieniowe języka wspólnego zachowuje tożsamość odwołania zarządzane i niezarządzane. Na poniższej ilustracji przedstawiono przepływ bezpośrednie odwołania niezarządzane (górnym wierszu) i bezpośredniego odwołania zarządzane (wiersz w dół) poza granicami procesu i hosta.  
  
 ![Wywoływana otoka COM i wywoływana otoka środowiska uruchomieniowego](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")  
Odwołanie za pośrednictwem procesu i hosta  
  
 Na tej ilustracji:  
  
-   Klient niezarządzany pobiera odwołanie do obiektu modelu COM z obiektu zarządzanego, który pobiera to odwołanie z hosta zdalnego. Mechanizm komunikacji zdalnej jest modelu DCOM.  
  
-   Klient zarządzany pobiera odwołanie do zarządzanego obiektu z obiektu COM, który pobiera to odwołanie z hosta zdalnego. Mechanizm komunikacji zdalnej jest modelu DCOM.  
  
    > [!NOTE]
    >  Musi być zarejestrowana wyeksportowanej biblioteki typów serwera zarządzanego.  
  
 Liczba granic procesów między wywołującego i wywoływany nie ma znaczenia; tym samym bezpośrednie odwołanie do występuje wywołań w trakcie i poza procesem.  
  
### <a name="managed-remoting"></a>Zarządzane usługi zdalne  
 Środowisko uruchomieniowe są także zarządzane remoting, którym można ustanowić kanał komunikacji między obiektami zarządzanymi granicami procesu i hosta. Zarządzanych usług zdalnych może obsłużyć zapory między składnikami komunikacji, jak przedstawiono na poniższej ilustracji.  
  
 ![Protokół SOAP lub TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")  
Zdalne wywołania przez zapory przy użyciu protokołu SOAP lub klasy TcpChannel  
  
 Niektóre połączenia niezarządzane można channeled za pośrednictwem protokołu SOAP, takie jak wywołania między [obsługiwanych składników](http://msdn.microsoft.com/en-us/f109ee24-81ad-4d99-9892-51ac6f34978c) i modelu COM.  
  
 [Powrót do początku](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Tematy pokrewne  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Domyślne zachowanie marshalingu](../../../docs/framework/interop/default-marshaling-behavior.md)|Opisuje reguły, które usługa kierowania międzyoperacyjnego używa do organizowania danych.|  
|[Marshaling danych w wywołaniu platformy](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)|Opisuje sposób deklarowanie parametrów metod i przekazywanie argumentów do funkcji wyeksportowane przez niezarządzanych bibliotek.|  
|[Marshaling danych za pomocą modelu COM](../../../docs/framework/interop/marshaling-data-with-com-interop.md)|Opisuje sposób dostosowywania otoki COM, aby zmienić zachowanie marshalingu.|  
|[Instrukcje: Migrowanie zarządzanego kodu DCOM do WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)|W tym artykule opisano sposób migracji z modelu DCOM do WCF.|  
|[Instrukcje: Mapowanie wyników HRESULT i wyjątków](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|Opisuje sposób odwzorowywania niestandardowymi wyjątkami wyników HRESULT i zapewnia pełną mapowania z każdego HRESULT do jej klasy można porównywać pod względem wyjątek w programie .NET Framework.|  
|[Współdziałanie za pomocą typów ogólnych](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)|Opisuje akcje, które są obsługiwane w przypadku współdziałania COM za pomocą typów ogólnych.|  
|[Współdziałanie z kodem niezarządzanym](../../../docs/framework/interop/index.md)|Opisuje współdziałanie usług świadczonych przez środowisko uruchomieniowe języka wspólnego.|  
|[Współdziałanie COM zaawansowane](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|Zawiera łącza do dodatkowych informacji o włączenie składniki modelu COM aplikacji .NET Framework.|  
|[Zagadnienia dotyczące projektowania dla współdziałanie](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)|Porady dotyczące pisania zintegrowane składników COM.|  
  
 [Powrót do początku](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Tematy pomocy  
 <xref:System.Runtime.InteropServices?displayProperty=nameWithType>  
  
 [Powrót do początku](#top)
