---
title: "Usługa AJAX korzystająca z typów złożonych — przykład"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5af5840dde2cb72ee6b39b75ece3606e3c58b32b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-using-complex-types-sample"></a>Usługa AJAX korzystająca z typów złożonych — przykład
W tym przykładzie przedstawiono sposób użycia [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Aby utworzyć usługę ASP.NET asynchronicznego JavaScript i XML (AJAX), która tworzy wystąpienia typów złożonych i wysyła je między usługą i klienta jako JavaScript Object Notation (JSON). Usługa AJAX mogą korzystać za pomocą kodu JavaScript w kliencie przeglądarki sieci Web. Ten przykład jest oparty na [podstawowa usługa AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) próbki.  
  
 Obsługa interfejsu AJAX w [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] jest zoptymalizowany do użycia z programem ASP.NET AJAX za pośrednictwem <xref:System.Web.UI.ScriptManager> formantu. Na przykład za pomocą [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] z ASP.NET AJAX, zobacz [przykłady AJAX](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.  
  
 Usługi w poniższym przykładzie jest [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi z żadnego kodu specyficzne dla interfejsu AJAX. Ponieważ <xref:System.ServiceModel.Web.WebGetAttribute> atrybut nie ma zastosowania, jest używany domyślny zlecenie HTTP ("POST"). Usługa ma jedną operację `DoMath`, która zwraca wartość typu złożonego o nazwie `MathResult`. Typ złożony jest typu kontraktu danych standardowe, które również nie zawiera określonego AJAX kodu.  
  
```  
[DataContract]  
    public class MathResult  
    {  
        [DataMember]  
        public double sum;  
        [DataMember]  
        public double difference;  
        [DataMember]  
        public double product;  
        [DataMember]  
        public double quotient;  
    }  
```  
  
 Tworzenie punktu końcowego AJAX w usłudze przy użyciu <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, po prostu tak jak na przykład podstawowa usługa AJAX.  
  
 Klient ComplexTypeClientPage.aspx strony sieci Web zawiera kod platformy ASP.NET i JavaScript do wywołania usługi, gdy użytkownik kliknie **obliczanie** przycisk na stronie. Kod, aby wywołać usługę konstruuje treść kodu JSON i wysyła je przy użyciu protokołu HTTP POST, podobnie jak [AJAX Service przy użyciu protokołu HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) próbki.  
  
 Po wywołaniu usługi zakończy się powodzeniem, można uzyskać dostępu do elementów członkowskich danych poszczególnych (`sum`, `difference`, `product` i `quotient`) na JavaScript wynikowy obiekt.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, kompilacji, a następnie uruchom próbki  
  
1.  Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Skompiluj rozwiązanie ComplexTypeAjaxService.sln zgodnie z opisem w [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Przejdź do http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (nie należy otwierać ComplexTypeClientPage.aspx w przeglądarce z katalogu projektu).  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>Zobacz też  
 [Podstawowa usługa AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
