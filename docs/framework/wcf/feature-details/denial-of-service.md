---
title: "Odmowa usługi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: denial of service [WCF]
ms.assetid: dfb150f3-d598-4697-a5e6-6779e4f9b600
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d5f67790abad5dcf6311de1817b4ea093e703d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="denial-of-service"></a>Odmowa usługi
Odmowa usługi występuje, gdy system jest przeciążony w taki sposób, że nie można przetworzyć wiadomości, lub są przetwarzane bardzo wolno.  
  
## <a name="excess-memory-consumption"></a>Zużycie pamięci nadmiarowe  
 Problem może wystąpić, gdy odczytywanie dokumentu XML z dużą liczbą unikatowe nazwy lokalnej, przestrzenie nazw i prefiksy. Jeśli korzystasz z klasą pochodzącą z <xref:System.Xml.XmlReader>, i należy wywołać <xref:System.Xml.XmlReader.LocalName%2A>, <xref:System.Xml.XmlReader.Prefix%2A> lub <xref:System.Xml.XmlReader.NamespaceURI%2A> zwracany ciąg właściwości dla każdego elementu, jest dodawany do <xref:System.Xml.NameTable>. Kolekcja posiadaniu <xref:System.Xml.NameTable> nigdy nie zmniejsza rozmiar tworzenia wirtualnej "przeciek pamięci" dojść ciągu.  
  
 Następujące czynniki:  
  
-   Pochodzić od <xref:System.Xml.NameTable> klasy i wymuszać maksymalną wielkość limitu przydziału. (Nie może uniemożliwić korzystanie z <xref:System.Xml.NameTable> lub Przełącz <xref:System.Xml.NameTable> gdy jest pełny.)  
  
-   Unikaj używania właściwości wymienionych — zamiast tego użyj <xref:System.Xml.XmlReader.MoveToAttribute%2A> metody z <xref:System.Xml.XmlReader.IsStartElement%2A> metody w miarę możliwości; tych metod nie zwracać ciągi i w związku z tym uniknąć problemów z przepełnienie <xref:System.Xml.NameTable> kolekcji.  
  
## <a name="malicious-client-sends-excessive-license-requests-to-service"></a>Złośliwe klient wysyła żądania nadmiernego licencji usługi  
 Złośliwego klienta bombards usługi za pomocą żądania nadmiernego licencji, może spowodować server do używania pamięci nadmierne.  
  
 Ograniczenie: Użyj następujących właściwości <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> klasy:  
  
-   <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxCachedCookies%2A>: Określa maksymalną liczbę ograniczonego czasu `SecurityContextToken`s, który serwer buforuje po `SPNego` lub `SSL` negocjacji.  
  
-   <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.IssuedCookieLifetime%2A>: Określa okres istnienia `SecurityContextTokens` który problemów serwera po `SPNego` lub `SSL` negocjacji. Pamięć podręczna serwera `SecurityContextToken`s dla tego okresu czasu.  
  
-   <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxPendingSessions%2A>: steruje maksymalną liczbą bezpiecznych konwersacji, które są ustalane na serwerze, ale które zostały przetworzone żadnych komunikatów aplikacji. Ten limit przydziału uniemożliwia klientom ustanawiania bezpiecznych konwersacji w usłudze, co powoduje usługi do zarządzania stanem na klienta, ale nigdy nie za ich pomocą.  
  
-   <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.InactivityTimeout%2A>: Określa maksymalny czas, Usługa przechowuje bezpiecznej konwersacji podtrzymania bez otrzymania wiadomości aplikacji od klienta do konwersacji. Ten limit przydziału uniemożliwia klientom ustanawiania bezpiecznych konwersacji w usłudze, co powoduje usługi do zarządzania stanem na klienta, ale nigdy nie za ich pomocą.  
  
## <a name="wsdualhttpbinding-or-dual-custom-bindings-require-client-authentication"></a>WSDualHttpBinding lub dwa powiązania niestandardowe wymagają uwierzytelniania klienta  
 Domyślnie <xref:System.ServiceModel.WSDualHttpBinding> ma włączoną obsługą zabezpieczeń. Jest to możliwe, jednak, że jeśli uwierzytelnianie klienta została wyłączona przez ustawienie <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> właściwości <xref:System.ServiceModel.MessageCredentialType.None>, złośliwy użytkownik może prowadzić do odmowy usługi ataków na trzeci usługi. Może to wystąpić, ponieważ złośliwego klienta może bezpośrednia usługi do wysyłania strumienia komunikatów do innej usługi.  
  
 Aby temu zaradzić, nie należy ustawiać właściwości `None`. Wziąć pod uwagę możliwość ta podczas tworzenia niestandardowego powiązania, które ma podwójną komunikatów.  
  
## <a name="auditing-event-log-can-be-filled"></a>Dziennik zdarzeń inspekcji mogą być wypełnione  
 Jeśli złośliwy użytkownik rozumie, że inspekcja jest włączona, niepowołana może wysyłać nieprawidłowe komunikaty, powodujących wpisy inspekcji do zapisania. Dziennik inspekcji jest wypełniony w ten sposób, inspekcji systemu nie powiedzie się.  
  
 Aby temu zaradzić, ustaw <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> właściwości `true` i użyj właściwości podglądu zdarzeń w celu kontrolowania zachowania inspekcji. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Wyświetlanie i zarządzanie dziennikami zdarzeń za pomocą Podglądu zdarzeń zobacz [Podgląd zdarzeń](http://go.microsoft.com/fwlink/?LinkId=186123). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Inspekcji](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="invalid-implementations-of-iauthorizationpolicy-can-cause-service-hangs"></a>Nieprawidłowy implementacje zawiesza się usługa Przyczyna może IAuthorizationPolicy  
 Wywoływanie <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> metody na błędną implementację elementu <xref:System.IdentityModel.Policy.IAuthorizationPolicy> interfejs może spowodować, że usługa zawieszenie.  
  
 Ograniczenie: Użyj tylko zaufanego kodu. Oznacza to, używają tylko kod, który został zapisany i przetestowane lub która pochodzi z zaufanego dostawcę. Nie zezwalaj na niezaufane rozszerzenia <xref:System.IdentityModel.Policy.IAuthorizationPolicy> być podłączony do kodu bez ukończenia brany pod uwagę. Dotyczy to wszystkich rozszerzeń zastosowany w implementacji usługi. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]nie daje żadnej różnicy między kodem aplikacji i obcego kodu, który jest podłączony za pomocą punkty rozszerzeń.  
  
## <a name="kerberos-maximum-token-size-may-need-resizing"></a>Może być konieczne Kerberos maksymalny rozmiar tokenu zmiana rozmiaru  
 Jeśli klient należy do dużej liczby grup (około 900, mimo że rzeczywista liczba może być różna w zależności od grup), problem może wystąpić, gdy blok Nagłówek wiadomości przekroczy 64 kilobajtów. W takim przypadku można zwiększyć maksymalny rozmiar tokenu protokołu Kerberos, zgodnie z opisem w artykule firmy Microsoft Support "[uwierzytelniania protokołu Kerberos programu Internet Explorer nie działa z powodu Niewystarczający bufor łączący się z IIS](http://go.microsoft.com/fwlink/?LinkId=89176)." Może również należy zwiększyć maksymalną [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] komunikatu rozmiar, aby obsłużyć większą token protokołu Kerberos.  
  
## <a name="autoenrollment-results-in-multiple-certificates-with-same-subject-name-for-machine"></a>Powoduje autorejestrowania kilka certyfikatów o tej samej nazwie podmiotu maszyny  
 *Autorejestrowania* to możliwość [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] do automatycznego rejestrowania użytkowników i komputerów dla certyfikatów. Gdy komputer znajduje się w domenie z włączoną funkcją, certyfikat X.509 z przeznaczeniem uwierzytelniania klienta jest automatycznie tworzone i wstawione do magazynu certyfikatów osobistych komputera lokalnego, zawsze, gdy nowy komputer jest dołączony do sieć. Jednak autorejestrowania korzysta z taką samą nazwę podmiotu dla wszystkich certyfikatów, które tworzy się w pamięci podręcznej.  
  
 Wpływ jest to, że [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Otwórz w domenach z automatycznego rejestrowania usługi może być niemożliwe. Dzieje się tak, ponieważ domyślne kryteria wyszukiwania poświadczeń X.509 usługi może być niejednoznaczna, ponieważ istnieje wiele certyfikatów w pełni kwalifikowaną nazwą systemu nazw domen (DNS, Domain Name System) na komputerze. Jeden certyfikat pochodzi z autorejestrowania; drugi może być własnym wystawiony certyfikat.  
  
 Aby temu zaradzić, odwoływać się dokładnie certyfikat do użycia przy użyciu kryterium wyszukiwania dokładniejsze na [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md). Na przykład użyć <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> opcji, a następnie określ certyfikat przez jego unikatowy odcisk palca (skrót).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Funkcja automatycznego rejestrowania, zobacz [autorejestrowanie certyfikatów w systemie Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=95166).  
  
## <a name="last-of-multiple-alternative-subject-names-used-for-authorization"></a>Ostatnie wielu nazwy alternatywnej podmiotu używane na potrzeby autoryzacji  
 W rzadkich przypadkach, kiedy certyfikat X.509 zawiera wiele nazwy alternatywnej podmiotu i autoryzacji, przy użyciu ustawienia alternatywnej nazwy podmiotu, autoryzacji może zakończyć się niepowodzeniem.  
  
## <a name="protect-configuration-files-with-acls"></a>Chroń pliki konfiguracji za pomocą listy kontroli dostępu  
 Można określić wymaganych i opcjonalnych oświadczeń w plikach kod i konfiguracja dla [!INCLUDE[infocard](../../../../includes/infocard-md.md)] wystawionych tokenów. Powoduje to odpowiednie elementy, które są emitowane w `RequestSecurityToken` wiadomości, które są wysyłane do zabezpieczenia tokenu usługi. Osoba atakująca można zmodyfikować kod lub konfigurację, aby usunąć wymaganego lub opcjonalnego roszczenia, potencjalnie pobierania usługi tokenu zabezpieczeń można wystawić tokenu, który nie zezwala na dostęp do usługi docelowej.  
  
 Aby ograniczyć: wymagają dostępu do komputera, aby zmodyfikować pliku konfiguracji. Korzystanie z pliku kontroli dostępu zawiera listę (kontroli dostępu ACL) do zabezpieczania plików konfiguracyjnych. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]wymaga, aby kod w katalogu aplikacji lub w globalnej pamięci podręcznej zestawów, zanim umożliwi taki kod, aby być ładowane z konfiguracji. Użyj listy ACL w katalogu, aby zabezpieczyć katalogi.  
  
## <a name="maximum-number-of-secure-sessions-for-a-service-is-reached"></a>Osiągnięto maksymalną liczbę bezpiecznej sesji dla usługi  
 Gdy klient zostanie pomyślnie uwierzytelniony przez usługę i bezpieczne ustanowiono połączenie z usługą, Usługa przechowuje informacje o sesji, dopóki klient anuluje go lub wygaśnięcia sesji. Każdy ustanowienie sesji jest za mała limit maksymalnej liczby aktywnych sesji jednoczesnych z usługą. Po osiągnięciu tego limitu klientów, które próbują utworzyć nowej sesji z tą usługą są odrzucane, dopóki jedna lub więcej aktywnych sesji wygaśnięcia lub anulowania przez klienta. Klient może mieć wiele sesji z usługą, a limit liczony w każdej z nich tymi sesjami.  
  
> [!NOTE]
>  Korzystając z sesji stanowe, powyżej nie ma zastosowania. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]stanowe sesje, zobacz [porady: Tworzenie tokenu kontekstu zabezpieczeń dla bezpieczną sesję](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
 Aby temu zaradzić, Ustaw limit maksymalnej liczby aktywnych sesji i maksymalny okres istnienia sesji przez ustawienie <xref:System.ServiceModel.Channels.SecurityBindingElement> właściwość <xref:System.ServiceModel.Channels.SecurityBindingElement> klasy.  
  
## <a name="see-also"></a>Zobacz też  
 [Zagadnienia dotyczące bezpieczeństwa](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Ujawnianie informacji](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Podniesienie uprawnień](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Odmowa usługi](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Ataki oparte na metodzie powtórzeń](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Manipulowanie](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [Nieobsługiwane scenariusze](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
