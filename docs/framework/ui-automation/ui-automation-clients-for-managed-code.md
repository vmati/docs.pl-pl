---
title: "Klienci automatyzacji interfejsu użytkownika do kodu zarządzanego"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- UI Automation, clients for managed code
- managed code, UI Automation clients
ms.assetid: e1ed1197-3e9e-4e78-8845-92e82787faed
caps.latest.revision: "58"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8142ef17bdfb78226e7a65376e132bad18bc258e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-clients-for-managed-code"></a><span data-ttu-id="dab2c-102">Klienci automatyzacji interfejsu użytkownika do kodu zarządzanego</span><span class="sxs-lookup"><span data-stu-id="dab2c-102">UI Automation Clients for Managed Code</span></span>
> [!NOTE]
>  <span data-ttu-id="dab2c-103">Ta dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="dab2c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dab2c-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dab2c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dab2c-105">Ta sekcja zawiera omówienie i — tematy porad ułatwiających tworzenie klienci automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dab2c-105">This section contains overviews and how-to topics to help you develop UI Automation clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dab2c-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="dab2c-106">In This Section</span></span>  
 [<span data-ttu-id="dab2c-107">Automatyzacja interfejsu użytkownika a skalowanie ekranu</span><span class="sxs-lookup"><span data-stu-id="dab2c-107">UI Automation and Screen Scaling</span></span>](../../../docs/framework/ui-automation/ui-automation-and-screen-scaling.md)  
 [<span data-ttu-id="dab2c-108">Obsługa automatyzacji interfejsu użytkownika dla formantów standardowych</span><span class="sxs-lookup"><span data-stu-id="dab2c-108">UI Automation Support for Standard Controls</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-standard-controls.md)  
 [<span data-ttu-id="dab2c-109">Zdarzeń automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="dab2c-109">UI Automation Events for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md)  
 [<span data-ttu-id="dab2c-110">Buforowanie w klientach automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="dab2c-110">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)  
 [<span data-ttu-id="dab2c-111">Właściwości automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="dab2c-111">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="dab2c-112">Mapowanie wzorców formantów dla klientów automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="dab2c-112">Control Pattern Mapping for UI Automation Clients</span></span>](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [<span data-ttu-id="dab2c-113">Wzorce formantów automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="dab2c-113">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="dab2c-114">Uzyskiwanie elementów automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="dab2c-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [<span data-ttu-id="dab2c-115">Problemy wielowątkowości dotyczące automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="dab2c-115">UI Automation Threading Issues</span></span>](../../../docs/framework/ui-automation/ui-automation-threading-issues.md)  
 [<span data-ttu-id="dab2c-116">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="dab2c-116">How-to Topics</span></span>](../../../docs/framework/ui-automation/ui-automation-clients-for-managed-code-how-to-topics.md)  
  
## <a name="reference"></a><span data-ttu-id="dab2c-117">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="dab2c-117">Reference</span></span>  
 <xref:System.Windows.Automation>