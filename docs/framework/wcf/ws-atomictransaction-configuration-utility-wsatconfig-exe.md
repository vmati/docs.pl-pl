---
title: "Narzędzie do konfiguracji elementu WS-AtomicTransaction (wsatConfig.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c84a0ddd05de3a28a6c38bc63151c8cec35bdd2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a><span data-ttu-id="5a3ac-102">Narzędzie do konfiguracji elementu WS-AtomicTransaction (wsatConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="5a3ac-102">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span></span>
<span data-ttu-id="5a3ac-103">Narzędzia konfiguracji WS-AtomicTransaction służy do konfigurowania podstawowych ustawień obsługi protokołu WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-103">The WS-AtomicTransaction Configuration Utility is used to configure basic WS-AtomicTransaction support settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5a3ac-104">Syntax</span></span>  
  
```  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a3ac-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5a3ac-105">Remarks</span></span>  
 <span data-ttu-id="5a3ac-106">To narzędzie wiersza polecenia może służyć do konfigurowania podstawowych ustawień protokołu WS-AT w tylko komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-106">This command line tool can be used to configure basic WS-AT settings in a local machine only.</span></span> <span data-ttu-id="5a3ac-107">Jeśli należy skonfigurować ustawienia na komputerach lokalnych i zdalnych, możesz użyć przystawki programu MMC zgodnie z opisem w [Konfigurowanie obsługi protokołu WS-AT transakcji](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="5a3ac-107">If you have to configure settings on both local and remote machines, you should use the MMC snap-in as described in [Configuring WS-Atomic Transaction Support](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).</span></span>  
  
 <span data-ttu-id="5a3ac-108">Narzędzia wiersza polecenia znajduje się w lokalizacji instalacji zestawu Windows SDK, w szczególności</span><span class="sxs-lookup"><span data-stu-id="5a3ac-108">The command line tool can be found in the Windows SDK installation location, specifically,</span></span>  
  
 <span data-ttu-id="5a3ac-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Foundation\wsatConfig.exe komunikacji</span><span class="sxs-lookup"><span data-stu-id="5a3ac-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe</span></span>  
  
 <span data-ttu-id="5a3ac-110">Jeśli używasz [!INCLUDE[wxp](../../../includes/wxp-md.md)] lub [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], należy pobrać aktualizacji przed uruchomieniem WsatConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-110">If you are running [!INCLUDE[wxp](../../../includes/wxp-md.md)] or [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], you must download an update before running WsatConfig.exe.</span></span> <span data-ttu-id="5a3ac-111">Aby uzyskać więcej informacji na temat tej aktualizacji, zobacz [aktualizacji dla Commerce Server 2007 (KB912817)](http://go.microsoft.com/fwlink/?LinkId=95340) i [dostępności z systemu Windows XP COM + poprawki pakietu zbiorczego pakietu 13](http://go.microsoft.com/fwlink/?LinkId=95341).</span><span class="sxs-lookup"><span data-stu-id="5a3ac-111">For more information about this update, see [Update for Commerce Server 2007 (KB912817)](http://go.microsoft.com/fwlink/?LinkId=95340) and [Availability of Windows XP COM+ Hotfix Rollup Package 13](http://go.microsoft.com/fwlink/?LinkId=95341).</span></span>  
  
 <span data-ttu-id="5a3ac-112">W poniższej tabeli przedstawiono opcje, które mogą być używane z narzędzia konfiguracji WS-AtomicTransaction (wsatConfig.exe).</span><span class="sxs-lookup"><span data-stu-id="5a3ac-112">The following table shows the options that can be used with WS-AtomicTransaction Configuration Utility (wsatConfig.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a3ac-113">Po ustawieniu certyfikatu SSL dla wybranego portu możesz zastąpić oryginalny certyfikat SSL skojarzony z tego portu, jeśli taka istnieje.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-113">When you set an SSL certificate for a selected port, you overwrite the original SSL certificate associated with that port if one exists.</span></span>  
  
|<span data-ttu-id="5a3ac-114">Opcje</span><span class="sxs-lookup"><span data-stu-id="5a3ac-114">Options</span></span>|<span data-ttu-id="5a3ac-115">Opis</span><span class="sxs-lookup"><span data-stu-id="5a3ac-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a3ac-116">-kont:\<konta ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-116">-accounts:\<account,></span></span>|<span data-ttu-id="5a3ac-117">Określa rozdzielaną przecinkami listę kont, które mogą uczestniczyć w WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-117">Specifies a comma-separated list of accounts that can participate in WS-AtomicTransaction.</span></span> <span data-ttu-id="5a3ac-118">Ważność tych kont nie jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-118">The validity of these accounts is not checked.</span></span>|  
|<span data-ttu-id="5a3ac-119">-accountsCerts:\<thumb > &#124; " Issuer\SubjectName"></span><span class="sxs-lookup"><span data-stu-id="5a3ac-119">-accountsCerts:\<thumb>&#124;"Issuer\SubjectName",></span></span>|<span data-ttu-id="5a3ac-120">Określa rozdzielaną przecinkami listę certyfikatów, które mogą uczestniczyć w WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-120">Specifies a comma-separated list of certificates that can participate in WS-AtomicTransaction.</span></span> <span data-ttu-id="5a3ac-121">Certyfikaty są wskazane przez odcisk palca lub parę Issuer\SubjectName.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-121">The certificates are indicated by thumbprint or by the Issuer\SubjectName pair.</span></span> <span data-ttu-id="5a3ac-122">Użyj wartości {EMPTY} dla nazwy podmiotu, jeśli jest pusty.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-122">Use {EMPTY} for subject name if it is empty.</span></span>|  
|<span data-ttu-id="5a3ac-123">-endpointCert: < maszynę &#124; \<thumb > &#124; " Issuer\SubjectName"></span><span class="sxs-lookup"><span data-stu-id="5a3ac-123">-endpointCert:<machine&#124;\<thumb>&#124;"Issuer\SubjectName"></span></span>|<span data-ttu-id="5a3ac-124">Używa certyfikatu komputera lub innego lokalnego certyfikatu punktu końcowego określonego przez odcisk palca lub parę Issuer\SubjectName.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-124">Uses the machine certificate or another local endpoint certificate specified by thumbprint or Issuer\SubjectName pair.</span></span> <span data-ttu-id="5a3ac-125">Używa {EMPTY} jako nazwę podmiotu, jeśli jest pusty.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-125">Uses {EMPTY} for the subject name if it is empty.</span></span>|  
|<span data-ttu-id="5a3ac-126">-maxTimeout:\<s ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-126">-maxTimeout:\<sec></span></span>|<span data-ttu-id="5a3ac-127">Określa maksymalny limit czasu w sekundach.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-127">Specifies the maximum timeout in seconds.</span></span> <span data-ttu-id="5a3ac-128">Prawidłowe wartości to od 0 do 3600.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-128">Valid values are from 0 to 3600.</span></span>|  
|<span data-ttu-id="5a3ac-129">— sieć:\<Włącz &#124; Wyłącz ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-129">-network:\<enable&#124;disable></span></span>|<span data-ttu-id="5a3ac-130">Włącza lub wyłącza obsługę sieci WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-130">Enables or disables the WS-AtomicTransaction network support.</span></span>|  
|<span data-ttu-id="5a3ac-131">— port:\<portNum ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-131">-port:\<portNum></span></span>|<span data-ttu-id="5a3ac-132">Ustawia HTTPS port dla protokołu WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-132">Sets the HTTPS port for WS-AtomicTransaction.</span></span><br /><br /> <span data-ttu-id="5a3ac-133">Jeśli została już włączona zapora, przed uruchomieniem tego narzędzia, numer portu jest automatycznie rejestrowane na liście wyjątków.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-133">If you have already enabled firewall before running this tool, the port is automatically registered in the exception list.</span></span> <span data-ttu-id="5a3ac-134">Jeśli Zapora jest wyłączone przed uruchomieniem tego narzędzia, żadne dodatkowe skonfigurowano dotyczące zapory.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-134">If firewall is disabled before running this tool, nothing additional is configured regarding the firewall.</span></span><br /><br /> <span data-ttu-id="5a3ac-135">Po skonfigurowaniu usługi WS-AT zostanie włączona zapora, należy ponownie uruchomić to narzędzie i podaj numer portu, za pomocą tego parametru.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-135">If you enable firewall after configuring WS-AT, you have to run this tool again and supply the port number using this parameter.</span></span> <span data-ttu-id="5a3ac-136">Wyłączenie zapory po skonfigurowaniu, WS-AT w dalszym ciągu działać bez dodatkowych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-136">If you disable firewall after configuring, WS-AT continues to work without additional input.</span></span>|  
|<span data-ttu-id="5a3ac-137">-timeout:\<s ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-137">-timeout:\<sec></span></span>|<span data-ttu-id="5a3ac-138">Określa domyślny limit czasu w sekundach.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-138">Specifies the default timeout in seconds.</span></span> <span data-ttu-id="5a3ac-139">Prawidłowe są wartości z zakresu od 1 do 3600.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-139">Valid values are from 1 to 3600.</span></span>|  
|<span data-ttu-id="5a3ac-140">-traceActivity:\<Włącz &#124; Wyłącz ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-140">-traceActivity:\<enable&#124;disable></span></span>|<span data-ttu-id="5a3ac-141">Włącza lub wyłącza śledzenie zdarzeń aktywności.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-141">Enables or disables the tracing of activity events.</span></span>|  
|<span data-ttu-id="5a3ac-142">-traceLevel:\<poza &#124; Błąd &#124; Krytyczne &#124; Ostrzeżenie &#124; informacje o &#124; Pełne &#124; Wszystkie >}</span><span class="sxs-lookup"><span data-stu-id="5a3ac-142">-traceLevel:\<Off&#124;Error&#124;Critical&#124;Warning&#124;Information&#124; Verbose&#124;All>}</span></span>|<span data-ttu-id="5a3ac-143">Określa poziom śledzenia.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-143">Specifies the trace level.</span></span>|  
|<span data-ttu-id="5a3ac-144">-tracePII:\<Włącz &#124; Wyłącz ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-144">-tracePII:\<enable&#124;disable></span></span>|<span data-ttu-id="5a3ac-145">Włącza lub wyłącza śledzenie informacji umożliwiających identyfikację użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-145">Enables or disables the tracing of personally identifiable information.</span></span>|  
|<span data-ttu-id="5a3ac-146">-traceProp:\<Włącz &#124; Wyłącz ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-146">-traceProp:\<enable&#124;disable></span></span>|<span data-ttu-id="5a3ac-147">Włącza lub wyłącza śledzenie zdarzeń propagacji.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-147">Enables or disables the tracing of propagation events.</span></span>|  
|<span data-ttu-id="5a3ac-148">— ponowne uruchomienie</span><span class="sxs-lookup"><span data-stu-id="5a3ac-148">-restart</span></span>|<span data-ttu-id="5a3ac-149">Ponownie uruchamia usługę MSDTC w celu aktywowania zmian natychmiast.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-149">Restarts MSDTC to activate changes immediately.</span></span> <span data-ttu-id="5a3ac-150">Jeśli nie zostanie określony, zmiany zaczynają obowiązywać po ponownym uruchomieniu usługi MSDTC.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-150">If this is not specified, the changes take effect when MSDTC is restarted.</span></span>|  
|<span data-ttu-id="5a3ac-151">— Pokaż</span><span class="sxs-lookup"><span data-stu-id="5a3ac-151">-show</span></span>|<span data-ttu-id="5a3ac-152">Wyświetla bieżące ustawienia protokołu WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-152">Displays the current WS-AtomicTransaction protocol settings.</span></span>|  
|<span data-ttu-id="5a3ac-153">-SerwerWirtualny:\<SerwerWirtualny ></span><span class="sxs-lookup"><span data-stu-id="5a3ac-153">-virtualServer:\<virtualServer></span></span>|<span data-ttu-id="5a3ac-154">Określa nazwę klastra zasobu DTC.</span><span class="sxs-lookup"><span data-stu-id="5a3ac-154">Specifies the DTC resource cluster name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a3ac-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a3ac-155">See Also</span></span>  
 [<span data-ttu-id="5a3ac-156">Za pomocą protokołu WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="5a3ac-156">Using WS-AtomicTransaction</span></span>](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)  
 [<span data-ttu-id="5a3ac-157">Konfigurowanie obsługi protokołu WS-Atomic Transaction</span><span class="sxs-lookup"><span data-stu-id="5a3ac-157">Configuring WS-Atomic Transaction Support</span></span>](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)