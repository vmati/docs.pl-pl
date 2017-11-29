---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e24d340364f126d9cf33295d6d36d1b686065a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="e265a-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e265a-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="e265a-103">Ten element konfiguracji definiuje standardowy punkt końcowy, który zawiera informacje, aby umożliwić aplikacji funkcjonowanie jako program kliencki, który można znaleźć adres punktu końcowego dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="e265a-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="e265a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e265a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e265a-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e265a-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e265a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="e265a-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
      <discoveryClientSettings discoveryEndpoint="String">
        <findCriteria duration="TimeSpan" 
                      maxResults="Integer" 
                      scopeMatchBy="Uri">
          <contractTypeNames>
            <add name="String" namespace="String" />
          <contractTypeNames>
          <extensions />
          <scopes>
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e265a-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e265a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e265a-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e265a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e265a-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e265a-109">Attributes</span></span>  
 <span data-ttu-id="e265a-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="e265a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e265a-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e265a-111">Child Elements</span></span>  
  
|<span data-ttu-id="e265a-112">Element</span><span class="sxs-lookup"><span data-stu-id="e265a-112">Element</span></span>|<span data-ttu-id="e265a-113">Opis</span><span class="sxs-lookup"><span data-stu-id="e265a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e265a-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="e265a-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="e265a-115">Zawiera ustawienia wymagane przez aplikację do uczestnictwa w procesie odnajdowania usług jako klient.</span><span class="sxs-lookup"><span data-stu-id="e265a-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e265a-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e265a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e265a-117">Element</span><span class="sxs-lookup"><span data-stu-id="e265a-117">Element</span></span>|<span data-ttu-id="e265a-118">Opis</span><span class="sxs-lookup"><span data-stu-id="e265a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e265a-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e265a-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e265a-120">Zbiór standardowych punktów końcowych, które są wstępnie zdefiniowanych punktów końcowych z jedną lub więcej z ich właściwości (adres, powiązanie, kontrakt) stałe.</span><span class="sxs-lookup"><span data-stu-id="e265a-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e265a-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e265a-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>