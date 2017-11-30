---
title: "Instrukcje: Bezpieczne punkty końcowe metadanych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e28b4dec851cc4115c2688540ebee151c91e4cd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="46e61-102">Instrukcje: Bezpieczne punkty końcowe metadanych</span><span class="sxs-lookup"><span data-stu-id="46e61-102">How to: Secure Metadata Endpoints</span></span>
<span data-ttu-id="46e61-103">Metadane usługi mogą zawierać poufne informacje o aplikacji, która złośliwy użytkownik może wykorzystać.</span><span class="sxs-lookup"><span data-stu-id="46e61-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="46e61-104">Konsumentów usługi może wymagać mechanizm bezpiecznego uzyskiwania metadanych dotyczących usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="46e61-105">W związku z tym czasami jest niezbędne do opublikowania metadanych przy użyciu bezpiecznego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="46e61-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>  
  
 <span data-ttu-id="46e61-106">Punkty końcowe metadanych są zwykle chronione przy użyciu mechanizmów zabezpieczeń standardowe zdefiniowane w [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zabezpieczania punkty końcowe aplikacji.</span><span class="sxs-lookup"><span data-stu-id="46e61-106">Metadata endpoints are generally secured using the standard security mechanisms defined in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] for securing application endpoints.</span></span> <span data-ttu-id="46e61-107">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Omówienie zabezpieczeń](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="46e61-107">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span></span>  
  
 <span data-ttu-id="46e61-108">W tym temacie przedstawiono kroki, aby utworzyć punkt końcowy zabezpieczone przez certyfikat Secure Sockets Layer (SSL) lub innymi słowy, punkt końcowy HTTPS.</span><span class="sxs-lookup"><span data-stu-id="46e61-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="46e61-109">Aby utworzyć bezpieczny HTTPS GET końcowym metadanych w kodzie</span><span class="sxs-lookup"><span data-stu-id="46e61-109">To create a secure HTTPS GET metadata endpoint in code</span></span>  
  
1.  <span data-ttu-id="46e61-110">Konfigurowanie portu z odpowiedniego certyfikatu X.509.</span><span class="sxs-lookup"><span data-stu-id="46e61-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="46e61-111">Certyfikat musi pochodzić z zaufanego urzędu i musi mieć przeznaczenia "Autoryzacja usługi".</span><span class="sxs-lookup"><span data-stu-id="46e61-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="46e61-112">Należy użyć narzędzia HttpCfg.exe do dołączenia certyfikatu do portu.</span><span class="sxs-lookup"><span data-stu-id="46e61-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="46e61-113">Zobacz [porady: Konfigurowanie portu z certyfikatem SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="46e61-113">See [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="46e61-114">Podmiot certyfikatu lub jego systemu nazw domen (DNS) musi odpowiadać nazwie komputera.</span><span class="sxs-lookup"><span data-stu-id="46e61-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="46e61-115">Jest to konieczne, ponieważ jeden z pierwszego czynności, które wykonuje mechanizmu HTTPS jest do sprawdzenia, czy certyfikat został wystawiony do tego samego identyfikatora URI (Uniform Resource) jako adres, na którym jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="46e61-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>  
  
2.  <span data-ttu-id="46e61-116">Utwórz nowe wystąpienie klasy <xref:System.ServiceModel.Description.ServiceMetadataBehavior> klasy.</span><span class="sxs-lookup"><span data-stu-id="46e61-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>  
  
3.  <span data-ttu-id="46e61-117">Ustaw <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> właściwość <xref:System.ServiceModel.Description.ServiceMetadataBehavior> klasy do `true`.</span><span class="sxs-lookup"><span data-stu-id="46e61-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>  
  
4.  <span data-ttu-id="46e61-118">Ustaw <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> odpowiedni adres URL dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="46e61-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="46e61-119">Należy pamiętać, że jeśli określono adres bezwzględny adres URL musi rozpoczynać się od schemat "https://".</span><span class="sxs-lookup"><span data-stu-id="46e61-119">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="46e61-120">Jeśli określisz adresem względnym, musi dostarczyć podstawowy adres HTTPS dla hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="46e61-121">Jeśli ta właściwość nie jest ustawiona, domyślnym adresem jest "", lub bezpośrednio w podstawowy adres HTTPS dla usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
5.  <span data-ttu-id="46e61-122">Dodaj je do kolekcji zachowań który <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> właściwość <xref:System.ServiceModel.Description.ServiceDescription> klasy zwraca, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="46e61-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="46e61-123">Aby utworzyć bezpieczny HTTPS GET końcowym metadanych w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="46e61-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>  
  
1.  <span data-ttu-id="46e61-124">Dodaj [ \<zachowania >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementu [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elementem pliku konfiguracji dla usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-124">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>  
  
2.  <span data-ttu-id="46e61-125">Dodaj [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) elementu [ \<zachowania >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="46e61-125">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="46e61-126">Dodaj [ \<zachowanie >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elementu `<serviceBehaviors>` elementu.</span><span class="sxs-lookup"><span data-stu-id="46e61-126">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>  
  
4.  <span data-ttu-id="46e61-127">Ustaw `name` atrybutu `<behavior>` element odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="46e61-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="46e61-128">`name` Atrybut jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="46e61-128">The `name` attribute is required.</span></span> <span data-ttu-id="46e61-129">W poniższym przykładzie użyto wartości `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="46e61-129">The example below uses the value `mySvcBehavior`.</span></span>  
  
5.  <span data-ttu-id="46e61-130">Dodaj [ \<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) do `<behavior>` elementu.</span><span class="sxs-lookup"><span data-stu-id="46e61-130">Add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>  
  
6.  <span data-ttu-id="46e61-131">Ustaw atrybut `httpsGetEnabled` elementu `<serviceMetadata>` na `true`.</span><span class="sxs-lookup"><span data-stu-id="46e61-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>  
  
7.  <span data-ttu-id="46e61-132">Ustaw `httpsGetUrl` atrybutu `<serviceMetadata>` element odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="46e61-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="46e61-133">Należy pamiętać, że jeśli określono adres bezwzględny adres URL musi rozpoczynać się od schemat "https://".</span><span class="sxs-lookup"><span data-stu-id="46e61-133">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="46e61-134">Jeśli określisz adresem względnym, musi dostarczyć podstawowy adres HTTPS dla hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="46e61-135">Jeśli ta właściwość nie jest ustawiona, domyślnym adresem jest "", lub bezpośrednio w podstawowy adres HTTPS dla usługi.</span><span class="sxs-lookup"><span data-stu-id="46e61-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
8.  <span data-ttu-id="46e61-136">Aby zachowanie używane z usługą, należy ustawić `behaviorConfiguration` atrybutu [ \<usługi >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) elementu na wartość atrybutu nazwy elementu zachowanie.</span><span class="sxs-lookup"><span data-stu-id="46e61-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="46e61-137">Poniższy kod konfiguracji przedstawia pełny przykład.</span><span class="sxs-lookup"><span data-stu-id="46e61-137">The following configuration code shows a complete example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="46e61-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="46e61-138">Example</span></span>  
 <span data-ttu-id="46e61-139">Poniższy przykład tworzy wystąpienie <xref:System.ServiceModel.ServiceHost> i dodaje punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="46e61-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="46e61-140">Następnie tworzony wystąpienia <xref:System.ServiceModel.Description.ServiceMetadataBehavior> klasy i ustawia właściwości w celu utworzenia punktu wymiany metadanych bezpieczne.</span><span class="sxs-lookup"><span data-stu-id="46e61-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46e61-141">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="46e61-141">Compiling the Code</span></span>  
 <span data-ttu-id="46e61-142">Przykładowy kod używa następujących nazw:</span><span class="sxs-lookup"><span data-stu-id="46e61-142">The code example uses the following namespaces:</span></span>  
  
-   <xref:System.ServiceModel?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Description?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="46e61-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="46e61-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>  
 [<span data-ttu-id="46e61-144">Porady: Konfigurowanie portu z certyfikatem SSL</span><span class="sxs-lookup"><span data-stu-id="46e61-144">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="46e61-145">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="46e61-145">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="46e61-146">Zagadnienia dotyczące zabezpieczeń obejmujące metadane</span><span class="sxs-lookup"><span data-stu-id="46e61-146">Security Considerations with Metadata</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [<span data-ttu-id="46e61-147">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="46e61-147">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)