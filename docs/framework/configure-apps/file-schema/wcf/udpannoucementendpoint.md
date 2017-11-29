---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 85fcd6b81cca9f9b7a71ebdda96ef75e1dc1405a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="7c233-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="7c233-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="7c233-103">Ten element konfiguracji definiuje standardowy punkt końcowy jest używany przez usługi do wysłania komunikatów Anons powiązania protokołu UDP.</span><span class="sxs-lookup"><span data-stu-id="7c233-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="7c233-104">Ma stały kontraktu i obsługuje dwie wersje odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="7c233-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="7c233-105">Ponadto ma stałym powiązaniem UDP oraz domyślną wartość adresu zgodnie ze specyfikacją WS-Discovery (WS-Discovery kwietnia 2005 lub WS-Discovery w wersji 1.1).</span><span class="sxs-lookup"><span data-stu-id="7c233-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="7c233-106">Można określić adres multiemisji do użycia na potrzeby wysyłania i odbierania wiadomości powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="7c233-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="7c233-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7c233-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="7c233-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7c233-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c233-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="7c233-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c233-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="7c233-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7c233-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="7c233-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c233-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="7c233-112">Attributes</span></span>  
  
|<span data-ttu-id="7c233-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="7c233-113">Attribute</span></span>|<span data-ttu-id="7c233-114">Opis</span><span class="sxs-lookup"><span data-stu-id="7c233-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c233-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="7c233-115">discoveryVersion</span></span>|<span data-ttu-id="7c233-116">Ciąg, który określa jeden z dwóch wersji protokołu WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="7c233-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="7c233-117">Prawidłowe wartości to WSDiscovery11 i WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="7c233-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="7c233-118">Ta wartość jest typu <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="7c233-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="7c233-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="7c233-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="7c233-120">Wartość Timespan określający maksymalną wartość opóźnienia protokołu Discovery będzie czekać przed wysłaniem wiadomości powitania.</span><span class="sxs-lookup"><span data-stu-id="7c233-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="7c233-121">Przed wysłaniem wiadomości będą oczekiwać losowo wartość z zakresu od 0 i wartość tego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="7c233-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="7c233-122">Ten atrybut służy do ustawiania małe, losowe opóźnienie do uniknięcia sieci "burz", gdy sieć trafia i wszystkich usług powróci w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="7c233-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="7c233-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="7c233-123">multicastAddress</span></span>|<span data-ttu-id="7c233-124">Identyfikator URI, który określa adres multiemisji do użycia na potrzeby wysyłania i odbierania wiadomości odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="7c233-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="7c233-125">Wartość domyślna to adres multiemisji jako zgodna ze specyfikacją protokołu.</span><span class="sxs-lookup"><span data-stu-id="7c233-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="7c233-126">nazwa</span><span class="sxs-lookup"><span data-stu-id="7c233-126">name</span></span>|<span data-ttu-id="7c233-127">Ciąg określający nazwę Konfiguracja standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="7c233-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="7c233-128">Nazwa jest używana w `endpointConfiguration` atrybutu punktu końcowego usługi, aby połączyć standardowy punkt końcowy do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7c233-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c233-129">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="7c233-129">Child Elements</span></span>  
  
|<span data-ttu-id="7c233-130">Element</span><span class="sxs-lookup"><span data-stu-id="7c233-130">Element</span></span>|<span data-ttu-id="7c233-131">Opis</span><span class="sxs-lookup"><span data-stu-id="7c233-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c233-132">\<udpTransportSettings ></span><span class="sxs-lookup"><span data-stu-id="7c233-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="7c233-133">Kolekcja ustawień, które pozwalają na skonfigurowanie transportu UDP dla punktu końcowego protokołu UDP.</span><span class="sxs-lookup"><span data-stu-id="7c233-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c233-134">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="7c233-134">Parent Elements</span></span>  
  
|<span data-ttu-id="7c233-135">Element</span><span class="sxs-lookup"><span data-stu-id="7c233-135">Element</span></span>|<span data-ttu-id="7c233-136">Opis</span><span class="sxs-lookup"><span data-stu-id="7c233-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c233-137">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7c233-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7c233-138">Zbiór standardowych punktów końcowych, które są wstępnie zdefiniowanych punktów końcowych z jedną lub więcej z ich właściwości (adres, powiązanie, kontrakt) stałe.</span><span class="sxs-lookup"><span data-stu-id="7c233-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c233-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c233-139">Example</span></span>  
 <span data-ttu-id="7c233-140">W poniższym przykładzie pokazano klienta nasłuchiwanie powiadomienia za pośrednictwem protokołu UDP multiemisji transportu z domyślny adres multiemisji i UDP multiemisji transportu z określonym adresem multiemisji.</span><span class="sxs-lookup"><span data-stu-id="7c233-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
      <endpoint name="udpAnnouncementEndpointStandard"  
                kind="udpAnnouncementEndpoint"  
                bindingConfiguration="..." />  
      <endpoint name="udpAnnouncementEndpoint2"  
                kind="udpAnnouncementEndpoint"  
                endpointConfiguration="AnnouncementConfiguration3702"  
                bindingConfiguration="..." />  
...  
  </service>  
</services>  
<standardEndpoints>  
  <udpAnnouncementEndpoint>  
     <standardEndpoint name="AnnouncementConfiguration2"   
          version="WSDiscoveryApril2005"   
          multicastAddress="soap.udp://239.255.255.250:3703"/>          
  </udpAnnouncementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c233-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7c233-141">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>