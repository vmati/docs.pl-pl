---
title: JSONP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02332e04f729abd125f43acdbe0883851004537e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="jsonp"></a>JSONP
W tym przykładzie przedstawiono sposób obsługi formatu JSON z dopełnienie (JSONP) w usługach WCF REST. Format JSONP jest Konwencji, używany do innej domeny skrypty wywołania przez generowanie tagi skryptu w bieżącym dokumencie. Wynik zostanie zwrócony w funkcji określonej wywołania zwrotnego. JSONP opiera się na założeniu, że tagi, takie jak \<skryptu src = "http:/ /..." > można ocenić skryptów z dowolnej domeny i pobierane przez tagi skryptu jest obliczane w zakresie, w którym mogą już zdefiniowany innych funkcji.  
  
## <a name="demonstrates"></a>Demonstracje  
 Między domenami skryptów JSONP.  
  
## <a name="discussion"></a>Omówienie  
 Przykład obejmuje strony sieci Web, które są dodawane dynamicznie bloku skryptu po wyrenderowaniu strony w przeglądarce. Ten blok skryptu wywołuje usługa REST usługi WCF, która zawiera jedną operację `GetCustomer`. Usługa WCF REST zwraca nazwę i adres otoczona nazwę funkcji wywołania zwrotnego klienta. Gdy usługa WCF REST odpowiada, funkcja wywołania zwrotnego na stronie sieci Web została wywołana z danych klienta i funkcja wywołania zwrotnego wyświetla dane na stronie sieci Web. Iniekcji tagu i wykonywania funkcji wywołania zwrotnego jest realizowane automatycznie przez formant ASP.NET AJAX ScriptManager. Wzorca użycia jest taka sama jak z wszystkich serwerów proxy ASP.NET AJAX, z uwzględnieniem jeden wiersz, aby włączyć JSONP, jak pokazano w poniższym kodzie:  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
```  
  
 Strony sieci Web można wywołać usługi REST usługi WCF, ponieważ usługa używa <xref:System.ServiceModel.Description.WebScriptEndpoint> z `crossDomainScriptAccessEnabled` ustawioną `true`. Obie te konfiguracje są wykonywane w pliku Web.config w obszarze \<system.serviceModel > elementu.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 ScriptManager zarządza interakcji z usługą i ukrywa optymalizacji złożoności ręcznie wdrażania dostępu JSONP. Gdy `crossDomainScriptAccessEnabled` ma ustawioną wartość `true` i odpowiedzi format dla formatu JSON, jest operacja [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastruktury sprawdza identyfikator URI żądania dla wywołania zwrotnego parametr ciągu zapytania i opakowuje JSON odpowiedzi o wartości zapytania wywołania zwrotnego Parametr typu String. W przykładzie strony sieci Web wywołuje usługę WCF REST z następujący identyfikator URI.  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
```  
  
 Ponieważ parametru ciągu zapytania wywołanie zwrotne ma wartość `JsonPCallback`, usługi WCF zwraca odpowiedź JSONP pokazano w poniższym przykładzie.  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
```  
  
 Tej odpowiedzi JSONP zawiera dane klienta w formacie JSON, opakowana z nazwą funkcji wywołania zwrotnego, która żądanej strony sieci Web. ScriptManager wykonanie tego wywołania zwrotnego przy użyciu tagu skryptu do wykonania żądania między domenami, a następnie przekazać wynik do obsługi onSuccess, który został przekazany do operacji GetCustomer proxy ASP.NET AJAX.  
  
 Próbka składa się z dwóch aplikacji sieci web platformy ASP.NET: jeden zawiera po prostu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi, a inny zawiera sieci Web .aspx, który wywołuje usługę. Podczas uruchamiania rozwiązania, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] będzie obsługiwać dwie witryny sieci Web na inne porty, które tworzy środowisko, w którym usługa i klient na żywo w różnych domenach.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>Aby uruchomić przykładowy  
  
1.  Otwórz rozwiązanie przykładowej JSONP.  
  
2.  Naciśnij klawisz F5, aby uruchomić HYPERLINK "http://localhost:26648/JSONPClientPage.aspx" http://localhost:26648/JSONPClientPage.aspx w przeglądarce.  
  
3.  Należy zauważyć, że po załadowaniu strony wejść tekst "Name" i "Address" są wypełniane przy wartości.  Wartości te zostały podane po wywołaniu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi po zakończeniu przeglądarki renderowania strony.
