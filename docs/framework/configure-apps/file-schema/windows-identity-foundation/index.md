---
title: Schemat konfiguracji programu Windows Identity Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b2ac7e97627eba85013e1effdc4f856f3df79089
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="7a9c3-102">Schemat konfiguracji programu Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7a9c3-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="7a9c3-103">Tematy w tej sekcji zawierają informacje o schemacie konfiguracji systemu Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="7a9c3-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="7a9c3-104">Można również skonfigurować aplikację do korzystania z programu WIF za pośrednictwem klas udostępniany przez platformę.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-104">You can also configure an application to use WIF through classes exposed by the framework,.</span></span> <span data-ttu-id="7a9c3-105">Te klasy są wymienione w poniższych sekcjach Traktuj odpowiednie elementy w schemacie.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="7a9c3-106">Poniżej przedstawiono podstawowe XML tagu udostępnianych przez schemat konfiguracji WIF struktury.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="7a9c3-107">Atrybuty zostały pominięte.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-107">Attributes are omitted.</span></span> <span data-ttu-id="7a9c3-108">Komentarze wyróżnione wskazują główne składniki schematu.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<system.identityModel>  
    <!-- Service Configuration -->  
    <identityConfiguration>  
        <caches>  
            <sessionSecurityTokenCache />  
            <tokenReplayCache />  
        </caches>  
  
        <certificateValidation>  
            <certificateValidator />   
        </certificateValidation>  
  
        <claimsAuthenticationManager />  
  
        <claimsAuthorizationManager>  
            <optionalConfigurationElement>  
        </claimsAuthorizationManager>  
  
        <claimTypeRequired>  
            <claimType />   
        </claimTypeRequired>  
  
        <tokenReplayDetection />  
  
        <!-- Security Token Handler Collection Configuration -->  
        <securityTokenHandlers>  
            <add>  
                <!-- Can take an optional configuration element which can be one of  
                     the following or a custom element -->  
                <samlSecurityTokenHandlerRequirement>  
                    <nameClaimType>  
                    <roleClaimType>   
                </samlSecurityTokenHandlerRequirement>  
  
                <sessionSecurityTokenHandlerRequirement />  
                <x509SecurityTokenHandlerRequirement />  
                <userNameSecurityTokenHandlerRequirement />  
            </add>  
            <clear />  
            <remove />  
            <securityTokenHandlerConfiguration>  
                <audienceUris>  
                    <add>  
                    <clear>  
                    <remove>  
                </audienceUris>  
  
                <caches>  
                    <sessionSecurityTokenCache />  
                    <tokenReplayCache />  
                </caches>  
  
                <certificateValidation>  
                    <certificateValidator>   
                </certificateValidation>  
  
                <issuerNameRegistry>  
                    <!-- Can take an optional configuration element which can be   
                         the <trustedIssuers> element to configure a configuration-based  
                         issuer name registry or can be a custom element -->  
                    <trustedIssuers>  
                        <add>  
                        <clear>  
                        <remove>  
                    </trustedIssuers>  
                </issuerNameRegistry>  
  
                <issuerTokenResolver />  
                <serviceTokenResolver />  
                <tokenReplayDetection />  
            </securityTokenHandlerConfiguration>  
        </securityTokenHandlers>  
    </identityConfiguration>  
</system.identityModel>  
  
<system.identityModel.services>  
    <!-- Federation Authentication Configuration -->  
    <federatedAuthentication>  
        <cookieHandler>  
            <chunkedCookieHandler />  
            <customCookieHandler />  
        </cookieHandler>  
  
        <serviceCertificate>  
            <certificateReference>  
        </serviceCertificate>  
  
        <wsFederation />  
    </federatedAuthentication>  
</system.identityModel.services>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="7a9c3-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="7a9c3-109">In This Section</span></span>  
 <span data-ttu-id="7a9c3-110">[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Włączanie programu WIF konfiguracja zapewnia opcje w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="7a9c3-111">[\<system.identityModel.services >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) zapewnia konfiguracji dla pasywnych Federacji przy użyciu WIF.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="7a9c3-112">Konfiguruje moduł uwierzytelniania sesji (zabezpieczeń SAM) i moduł uwierzytelniania federacyjnego (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="7a9c3-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a9c3-113">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="7a9c3-113">Related Sections</span></span>  
 <span data-ttu-id="7a9c3-114">[Konfiguracja administracji, zarządzania i](http://msdn.microsoft.com/en-us/1e03c389-de2c-4096-aaff-86b087e1bea0) opisano sposób konfigurowania i zarządzania nimi WIF aplikacji i usług.</span><span class="sxs-lookup"><span data-stu-id="7a9c3-114">[Configuration, Administration, And Management](http://msdn.microsoft.com/en-us/1e03c389-de2c-4096-aaff-86b087e1bea0) Describes how to configure and manage WIF applications and services.</span></span>