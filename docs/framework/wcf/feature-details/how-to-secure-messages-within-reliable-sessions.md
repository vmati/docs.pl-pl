---
title: "Instrukcje: Zabezpieczanie komunikatów w sesjach niezawodnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3f27b1a4de2019660e0facb081300a79eae65b99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="08558-102">Instrukcje: Zabezpieczanie komunikatów w sesjach niezawodnych</span><span class="sxs-lookup"><span data-stu-id="08558-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="08558-103">W tym temacie opisano kroki wymagane do włączenia zabezpieczenia na poziomie komunikatu dla komunikatów wymieniane w niezawodnej sesji przy użyciu jednej powiązań dostarczane przez system, które obsługują sesji programu, ale nie domyślnie.</span><span class="sxs-lookup"><span data-stu-id="08558-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="08558-104">Włącz sesji bezpieczne, niezawodne imperatively przy użyciu kodu lub deklaratywnie w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="08558-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="08558-105">Ta procedura wykorzystuje pliki konfiguracji klienta i usługi umożliwia bezpieczne, niezawodne sesji.</span><span class="sxs-lookup"><span data-stu-id="08558-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="08558-106">Ta procedura składa się z trzech poniższych zadań głównych:</span><span class="sxs-lookup"><span data-stu-id="08558-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="08558-107">Określ, czy klient i usługa wymiana komunikatów w ramach niezawodnej sesji.</span><span class="sxs-lookup"><span data-stu-id="08558-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="08558-108">Wymagaj zabezpieczenia na poziomie komunikatu niezawodnej sesji.</span><span class="sxs-lookup"><span data-stu-id="08558-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="08558-109">Określ typ poświadczeń klienta, które klient musi używać uwierzytelniania za pomocą usługi.</span><span class="sxs-lookup"><span data-stu-id="08558-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="08558-110">Jest ważne w pierwszym zadaniu, który zawiera element konfiguracji punktu końcowego `bindingConfiguration` atrybut, który odwołuje się do konfiguracji powiązania o nazwie (w tym przykładzie) `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="08558-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="08558-111">[  **\<Powiązania >** ](../../../../docs/framework/misc/binding.md) element konfiguracji odwołuje się następnie tę nazwę, aby włączyć niezawodnej sesji przez ustawienie `enabled` atrybutu [  **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elementu `true`.</span><span class="sxs-lookup"><span data-stu-id="08558-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="08558-112">Można wymagać, aby gwarancje uporządkowanego dostarczenia są dostępne w ramach niezawodnej sesji przez ustawienie `ordered` atrybutu `true`.</span><span class="sxs-lookup"><span data-stu-id="08558-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="08558-113">Źródło kopii przykładu, na której oparto tej procedury konfiguracji, zobacz [sesja niezawodna WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="08558-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="08558-114">Podstawowych elementów drugiego zadania są realizowane przez ustawienie `mode` atrybutu  **\<zabezpieczeń >** element zawarty w  **\<powiązania >** Element klienta i usługi `Message`.</span><span class="sxs-lookup"><span data-stu-id="08558-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="08558-115">Podstawowych elementów trzeci zadań są realizowane przez ustawienie `clientCredentialType` atrybutu  **\<wiadomości >** element zawarty w  **\<zabezpieczeń >** Element klienta i usługi `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="08558-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="08558-116">Jeśli zabezpieczenia komunikatów z sesji niezawodnych, niezawodna obsługa komunikatów podejmuje próbę uwierzytelnienia klienta nieuwierzytelnione, dopóki nie zostanie przekroczony limit czasu zamiast generowania wyjątku przy pierwszym niepowodzeniu.</span><span class="sxs-lookup"><span data-stu-id="08558-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="08558-117">Skonfiguruj usługę z WSHttpBinding do użycia niezawodnej sesji</span><span class="sxs-lookup"><span data-stu-id="08558-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="08558-118">Ta procedura jest opisana w [porady: wymiana komunikatów w ramach niezawodnej sesji](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="08558-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="08558-119">Konfigurowanie klienta z WSHttpBinding do użycia niezawodnej sesji</span><span class="sxs-lookup"><span data-stu-id="08558-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="08558-120">Ta procedura jest opisana w [porady: wymiana komunikatów w ramach niezawodnej sesji](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="08558-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="08558-121">Ustaw tryb i ClientCredentialType w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="08558-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="08558-122">Dodaj odpowiednie powiązanie elementu [  **\<powiązania >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elementu w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="08558-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="08558-123">W poniższym przykładzie dodano [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="08558-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="08558-124">Dodaj  **\<powiązania >** element i ustaw jej `name` atrybutu odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="08558-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="08558-125">W przykładzie użyto nazwy `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="08558-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="08558-126">Dodaj  **\<zabezpieczeń >** element i ustaw `mode` atrybutu `Message`.</span><span class="sxs-lookup"><span data-stu-id="08558-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="08558-127">W ramach  **\<zabezpieczeń >** elementu, Dodaj  **\<wiadomości >** element i ustaw `clientCredentialType` atrybutu `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="08558-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```