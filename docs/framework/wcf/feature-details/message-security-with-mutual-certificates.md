---
title: "Zabezpieczenia komunikatów ze wzajemnymi certyfikatami"
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
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3d5e598fea118eb340b965d605f5fdeb9c479a4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="14ff2-102">Zabezpieczenia komunikatów ze wzajemnymi certyfikatami</span><span class="sxs-lookup"><span data-stu-id="14ff2-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="14ff2-103">Poniżej przedstawiono scenariusz [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usługi i klienta zabezpieczony używających trybu zabezpieczenia wiadomości.</span><span class="sxs-lookup"><span data-stu-id="14ff2-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message security mode.</span></span> <span data-ttu-id="14ff2-104">Klient i usługa są uwierzytelniane za pomocą certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="14ff2-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="14ff2-105">Ten scenariusz jest współdziałanie, ponieważ używa WS-Security z profilem tokenu certyfikatu X.509.</span><span class="sxs-lookup"><span data-stu-id="14ff2-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14ff2-106">W tym scenariuszu nie przeprowadza negocjowanie certyfikatu usługi.</span><span class="sxs-lookup"><span data-stu-id="14ff2-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="14ff2-107">Należy podać certyfikat usługi do klienta z wyprzedzeniem wszelkie komunikacji klienta.</span><span class="sxs-lookup"><span data-stu-id="14ff2-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="14ff2-108">Certyfikat serwera można rozpowszechnianej za pomocą aplikacji lub podane w komunikacie poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="14ff2-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="14ff2-109">![Zabezpieczenia ze wzajemnymi certyfikatami wiadomości](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="14ff2-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="14ff2-110">Cechy</span><span class="sxs-lookup"><span data-stu-id="14ff2-110">Characteristic</span></span>|<span data-ttu-id="14ff2-111">Opis</span><span class="sxs-lookup"><span data-stu-id="14ff2-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="14ff2-112">Tryb zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="14ff2-112">Security Mode</span></span>|<span data-ttu-id="14ff2-113">Komunikat</span><span class="sxs-lookup"><span data-stu-id="14ff2-113">Message</span></span>|  
|<span data-ttu-id="14ff2-114">Współdziałanie</span><span class="sxs-lookup"><span data-stu-id="14ff2-114">Interoperability</span></span>|<span data-ttu-id="14ff2-115">Tak, z WS-Security i klientów zgodne tokenu profilu certyfikatu X.509 i usług.</span><span class="sxs-lookup"><span data-stu-id="14ff2-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="14ff2-116">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="14ff2-116">Authentication</span></span>|<span data-ttu-id="14ff2-117">Wzajemne uwierzytelnianie serwera i klienta.</span><span class="sxs-lookup"><span data-stu-id="14ff2-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="14ff2-118">Integralność</span><span class="sxs-lookup"><span data-stu-id="14ff2-118">Integrity</span></span>|<span data-ttu-id="14ff2-119">Tak</span><span class="sxs-lookup"><span data-stu-id="14ff2-119">Yes</span></span>|  
|<span data-ttu-id="14ff2-120">Poufność</span><span class="sxs-lookup"><span data-stu-id="14ff2-120">Confidentiality</span></span>|<span data-ttu-id="14ff2-121">Tak</span><span class="sxs-lookup"><span data-stu-id="14ff2-121">Yes</span></span>|  
|<span data-ttu-id="14ff2-122">Transportu</span><span class="sxs-lookup"><span data-stu-id="14ff2-122">Transport</span></span>|<span data-ttu-id="14ff2-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="14ff2-123">HTTP</span></span>|  
|<span data-ttu-id="14ff2-124">Powiązanie</span><span class="sxs-lookup"><span data-stu-id="14ff2-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="14ff2-125">Usługa</span><span class="sxs-lookup"><span data-stu-id="14ff2-125">Service</span></span>  
 <span data-ttu-id="14ff2-126">Następujący kod i konfiguracja są przeznaczone do uruchamiania niezależnie.</span><span class="sxs-lookup"><span data-stu-id="14ff2-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="14ff2-127">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="14ff2-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="14ff2-128">Tworzenie przy użyciu kodu z konfiguracji autonomicznej usługi.</span><span class="sxs-lookup"><span data-stu-id="14ff2-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="14ff2-129">Tworzenie usługi przy użyciu wprowadzonej konfiguracji, ale nie definiują żadnych punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="14ff2-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="14ff2-130">Kod</span><span class="sxs-lookup"><span data-stu-id="14ff2-130">Code</span></span>  
 <span data-ttu-id="14ff2-131">W poniższym kodzie tworzy punkt końcowy usługi, który korzysta z zabezpieczeń wiadomości.</span><span class="sxs-lookup"><span data-stu-id="14ff2-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="14ff2-132">Usługa wymaga certyfikatu do samodzielnego uwierzytelnienia.</span><span class="sxs-lookup"><span data-stu-id="14ff2-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="14ff2-133">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="14ff2-133">Configuration</span></span>  
 <span data-ttu-id="14ff2-134">Następującej konfiguracji można zamiast kodu do utworzenia tej samej usługi.</span><span class="sxs-lookup"><span data-stu-id="14ff2-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"   
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="14ff2-135">Klient</span><span class="sxs-lookup"><span data-stu-id="14ff2-135">Client</span></span>  
 <span data-ttu-id="14ff2-136">Następujący kod i konfiguracja są przeznaczone do uruchamiania niezależnie.</span><span class="sxs-lookup"><span data-stu-id="14ff2-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="14ff2-137">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="14ff2-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="14ff2-138">Utwórz autonomiczny klienta przy użyciu kodu (i kod klienta).</span><span class="sxs-lookup"><span data-stu-id="14ff2-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="14ff2-139">Tworzenie klienta, który nie definiuje żadnych adresy punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="14ff2-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="14ff2-140">W zamian użyj Konstruktora klienta, który przyjmuje nazwę konfiguracji jako argument.</span><span class="sxs-lookup"><span data-stu-id="14ff2-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="14ff2-141">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="14ff2-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="14ff2-142">Kod</span><span class="sxs-lookup"><span data-stu-id="14ff2-142">Code</span></span>  
 <span data-ttu-id="14ff2-143">Poniższy kod tworzy klienta.</span><span class="sxs-lookup"><span data-stu-id="14ff2-143">The following code creates the client.</span></span> <span data-ttu-id="14ff2-144">Tryb zabezpieczeń jest ustawiony na komunikat, a typ poświadczeń klienta ma wartość Certificate.</span><span class="sxs-lookup"><span data-stu-id="14ff2-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="14ff2-145">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="14ff2-145">Configuration</span></span>  
 <span data-ttu-id="14ff2-146">Poniższa konfiguracja klienta.</span><span class="sxs-lookup"><span data-stu-id="14ff2-146">The following configures the client.</span></span> <span data-ttu-id="14ff2-147">Certyfikat klienta musi być podana przy użyciu [ \<clientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="14ff2-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="14ff2-148">Ponadto certyfikat usługi zostanie określona przy użyciu [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="14ff2-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"   
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ff2-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="14ff2-149">See Also</span></span>  
 [<span data-ttu-id="14ff2-150">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="14ff2-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="14ff2-151">Model zabezpieczeń systemu Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="14ff2-151">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)  
 [<span data-ttu-id="14ff2-152">Porady: tworzenie i zainstalować certyfikaty tymczasowe w programie WCF dla zabezpieczeń transportu podczas tworzenia</span><span class="sxs-lookup"><span data-stu-id="14ff2-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=244264)