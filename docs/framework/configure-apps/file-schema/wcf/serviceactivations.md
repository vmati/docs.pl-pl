---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4f05b8164c0920893ea5b379017b1eb91f1b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="56447-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="56447-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="56447-103">Element konfiguracji, który pozwala Tobie dodać ustawienia, które definiują ustawienia aktywacji usług wirtualnych mapowane na Twojej [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] typów usług.</span><span class="sxs-lookup"><span data-stu-id="56447-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="56447-104">Dzięki temu można aktywować usługi hostowane w WAS / usług IIS bez pliku svc.</span><span class="sxs-lookup"><span data-stu-id="56447-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="56447-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56447-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="56447-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="56447-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="56447-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="56447-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56447-108">Składnia</span><span class="sxs-lookup"><span data-stu-id="56447-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56447-109">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="56447-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56447-110">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="56447-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56447-111">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="56447-111">Attributes</span></span>  
 <span data-ttu-id="56447-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="56447-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56447-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="56447-113">Child Elements</span></span>  
  
|<span data-ttu-id="56447-114">Element</span><span class="sxs-lookup"><span data-stu-id="56447-114">Element</span></span>|<span data-ttu-id="56447-115">Opis</span><span class="sxs-lookup"><span data-stu-id="56447-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56447-116">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="56447-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="56447-117">Dodaje element konfiguracji, który określa aktywacji aplikacji usługi.</span><span class="sxs-lookup"><span data-stu-id="56447-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56447-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="56447-118">Parent Elements</span></span>  
  
|<span data-ttu-id="56447-119">Element</span><span class="sxs-lookup"><span data-stu-id="56447-119">Element</span></span>|<span data-ttu-id="56447-120">Opis</span><span class="sxs-lookup"><span data-stu-id="56447-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56447-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="56447-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="56447-122">Definiuje typ, który usługę hostingu środowiskowego dla danego transportu.</span><span class="sxs-lookup"><span data-stu-id="56447-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56447-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="56447-123">Remarks</span></span>  
 <span data-ttu-id="56447-124">Poniższy przykład przedstawia sposób konfigurowania ustawień aktywacji w pliku web.config.</span><span class="sxs-lookup"><span data-stu-id="56447-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="56447-125">Za pomocą tej konfiguracji, można uaktywnić GreetingService bez użycia pliku svc.</span><span class="sxs-lookup"><span data-stu-id="56447-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="56447-126">Należy pamiętać, że `<serviceHostingEnvironment>` jest konfiguracji na poziomie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="56447-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="56447-127">Należy umieścić `web.config` zawierający konfigurację w katalogu głównym aplikacji wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="56447-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="56447-128">Ponadto `serviceHostingEnvironment` jest sekcją dziedziczne machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="56447-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="56447-129">Jeśli zarejestrujesz pojedynczą usługę w katalogu głównym komputera każdej usługi w aplikacji będzie dziedziczyć tej usługi.</span><span class="sxs-lookup"><span data-stu-id="56447-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="56447-130">Aktywacja oparta na konfiguracji obsługuje aktywacji za pośrednictwem protokołu http i innych niż http.</span><span class="sxs-lookup"><span data-stu-id="56447-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="56447-131">Wymaga to rozszerzenia w relatativeAddress, tj. SVC, xoml lub .xamlx.</span><span class="sxs-lookup"><span data-stu-id="56447-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="56447-132">Należy mapować własne rozszerzenia buildProviders wiedzieć, który następnie umożliwi aktywowania usługi przez dowolnego rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="56447-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="56447-133">Po konflikt `<serviceActivations>` sekcji zastępuje .svc rejestracji.</span><span class="sxs-lookup"><span data-stu-id="56447-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56447-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56447-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>