---
title: Schemat konfiguracji programu WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e006cf94e9ec048617856e997271cd450725b94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-configuration-schema"></a>Schemat konfiguracji programu WCF
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]elementy konfiguracji umożliwiają skonfigurowanie [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] usługi i aplikacje klienckie. Można użyć [narzędzie edytora konfiguracji (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) pozwala tworzyć i modyfikować pliki konfiguracyjne dla klientów i usług. Ponieważ pliki konfiguracji są w formacie XML, należy zapoznać się z XML, jeśli chcesz ręcznie edytować za pomocą edytora tekstu. W przeciwnym razie może wystąpić problemy, takie jak unfound tagu elementu XML lub atrybut. Wynika to z tagów elementu XML i atrybutów jest rozróżniana wielkość liter.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Konfiguracji system jest oparty na <xref:System.Configuration> przestrzeni nazw. W takim przypadku używane standardowe funkcje oferowane przez <xref:System.Configuration> przestrzeni nazw, takie jak konfiguracja, blokowanie, szyfrowania i scalanie, aby zwiększyć bezpieczeństwo aplikacji i jej konfiguracji. Aby uzyskać więcej informacji dotyczących tych pojęć zobacz następujące tematy.  
  
 [Szyfrowanie informacji o konfiguracji](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Ustawienia konfiguracji blokowania](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 W tej sekcji opisano wszystkie możliwe wartości poszczególnych elementów konfiguracji i jak współdziała z innymi elementami konfiguracji usługi WCF. Następujące mapy przedstawiono schemat konfiguracji usługi WCF.  
  
 ![Schemat konfiguracji programu WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  Należy chronić [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] sekcji konfiguracyjnych w plikach konfiguracji aplikacji (app.config) z odpowiednią kontroli dostępu zawiera listę (ACL) aby uniemożliwić wszystkie potencjalne zagrożenia bezpieczeństwa.  Należy na przykład upewnij się, że odpowiednie osoby mogą uzyskać dostęp lub zmodyfikować ustawienia zabezpieczeń na powiązania aplikacji lub modelu usługi części pliku konfiguracji dla usługi.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [\<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Opisuje `ServiceModel` elementu.  
  
 [\<system.serviceModel.activation >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 Konfiguruje narzędzia SMSvcHost.exe.  
  
 [\<System.Runtime.serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 Element najwyższego poziomu do ustawiania opcji, gdy przy użyciu serializatorów, takich jak <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Konfigurowanie systemu Windows Communication Foundation aplikacji](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 Opisuje sposób konfigurowania [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] usług i klientów.
