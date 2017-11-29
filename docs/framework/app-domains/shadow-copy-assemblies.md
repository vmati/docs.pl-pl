---
title: "Kopiowanie zestawów w tle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], shadow copying
- application domains, shadow copying assemblies
- shadow copying assemblies
ms.assetid: de8b8759-fca7-4260-896b-5a4973157672
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2eb71e1d03da16581ee25bf972be51ee2f63f585
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="shadow-copying-assemblies"></a><span data-ttu-id="bf499-102">Kopiowanie zestawów w tle</span><span class="sxs-lookup"><span data-stu-id="bf499-102">Shadow Copying Assemblies</span></span>
<span data-ttu-id="bf499-103">Włącza zestawy, które są używane w domenie aplikacji do zaktualizowania bez zwalniania domeny aplikacji kopiowania w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-103">Shadow copying enables assemblies that are used in an application domain to be updated without unloading the application domain.</span></span> <span data-ttu-id="bf499-104">Jest to szczególnie przydatne w przypadku aplikacji, które muszą być dostępne w sposób ciągły, takie jak lokacje programu ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bf499-104">This is particularly useful for applications that must be available continuously, such as ASP.NET sites.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf499-105">Kopiowanie w tle nie jest obsługiwany w [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bf499-105">Shadow copying is not supported in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 <span data-ttu-id="bf499-106">Środowisko uruchomieniowe języka wspólnego blokuje pliku zestawu, gdy zestaw jest załadowany, więc nie można zaktualizować pliku, dopóki nie zostanie zwolniony zestawu.</span><span class="sxs-lookup"><span data-stu-id="bf499-106">The common language runtime locks an assembly file when the assembly is loaded, so the file cannot be updated until the assembly is unloaded.</span></span> <span data-ttu-id="bf499-107">Zwalnianie domen aplikacji jest jedynym sposobem, aby zwolnić zestaw z domeny aplikacji, więc w normalnych okolicznościach zestawu nie można zaktualizować na dysku do wszystkich domen aplikacji, które korzystają z zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="bf499-107">The only way to unload an assembly from an application domain is by unloading the application domain, so under normal circumstances, an assembly cannot be updated on disk until all the application domains that are using it have been unloaded.</span></span>  
  
 <span data-ttu-id="bf499-108">Domeny aplikacji skonfigurowano do plików kopii w tle, zestawy w ścieżce aplikacji są skopiowany do innej lokalizacji i załadować z tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bf499-108">When an application domain is configured to shadow copy files, assemblies from the application path are copied to another location and loaded from that location.</span></span> <span data-ttu-id="bf499-109">Kopia jest zablokowany, ale oryginalny plik zestawu jest odblokowany i można go zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="bf499-109">The copy is locked, but the original assembly file is unlocked and can be updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf499-110">Tylko zestawy, które mogą być kopie w tle są te są przechowywane w katalogu aplikacji lub jego podkatalogach, określony przez <xref:System.AppDomainSetup.ApplicationBase%2A> i <xref:System.AppDomainSetup.PrivateBinPath%2A> właściwości po skonfigurowaniu domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bf499-110">The only assemblies that can be shadow copied are those stored in the application directory or its subdirectories, specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties when the application domain is configured.</span></span> <span data-ttu-id="bf499-111">Zestawy przechowywanych w pamięci podręcznej GAC nie są kopie w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-111">Assemblies stored in the global assembly cache are not shadow copied.</span></span>  
  
 <span data-ttu-id="bf499-112">Ten artykuł zawiera następujące sekcje:</span><span class="sxs-lookup"><span data-stu-id="bf499-112">This article contains the following sections:</span></span>  
  
-   <span data-ttu-id="bf499-113">[Włączanie i przy użyciu kopiowanie w tle](#EnablingAndUsing) opisano podstawowe wykorzystanie i opcje, które są dostępne do kopiowania w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-113">[Enabling and Using Shadow Copying](#EnablingAndUsing) describes the basic use and the options that are available for shadow copying.</span></span>  
  
-   <span data-ttu-id="bf499-114">[Wydajność uruchamiania](#StartupPerformance) opisano zmiany wprowadzone do kopiowania w tle [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] w celu zwiększenia wydajności uruchamiania i jak przywrócić zachowanie starszych wersji.</span><span class="sxs-lookup"><span data-stu-id="bf499-114">[Startup Performance](#StartupPerformance) describes the changes that are made to shadow copying in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] to improve startup performance, and how to revert to the behavior of earlier versions.</span></span>  
  
-   <span data-ttu-id="bf499-115">[Przestarzałe metody](#ObsoleteMethods) opisano zmiany, które zostały wprowadzone do właściwości i metod tego formantu kopiowanie w tle w [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf499-115">[Obsolete Methods](#ObsoleteMethods) describes the changes that were made to the properties and methods that control shadow copying in the [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)].</span></span>  
  
<a name="EnablingAndUsing"></a>   
## <a name="enabling-and-using-shadow-copying"></a><span data-ttu-id="bf499-116">Włączanie i korzystanie z kopiowania w tle</span><span class="sxs-lookup"><span data-stu-id="bf499-116">Enabling and Using Shadow Copying</span></span>  
 <span data-ttu-id="bf499-117">Można użyć właściwości <xref:System.AppDomainSetup> klasy w następujący sposób, aby skonfigurować domenę aplikacji do kopiowania w tle:</span><span class="sxs-lookup"><span data-stu-id="bf499-117">You can use the properties of the <xref:System.AppDomainSetup> class as follows to configure an application domain for shadow copying:</span></span>  
  
-   <span data-ttu-id="bf499-118">Kopiowanie przez ustawienie w tle Włącz <xref:System.AppDomainSetup.ShadowCopyFiles%2A> wartość ciągu dla właściwości `"true"`.</span><span class="sxs-lookup"><span data-stu-id="bf499-118">Enable shadow copying by setting the <xref:System.AppDomainSetup.ShadowCopyFiles%2A> property to the string value `"true"`.</span></span>  
  
     <span data-ttu-id="bf499-119">Domyślnie to ustawienie powoduje wszystkie zestawy w ścieżce aplikacji ma zostać skopiowany do pamięci podręcznej pobierania przed załadowaniem.</span><span class="sxs-lookup"><span data-stu-id="bf499-119">By default, this setting causes all assemblies in the application path to be copied to a download cache before they are loaded.</span></span> <span data-ttu-id="bf499-120">To jest tej samej pamięci podręcznej obsługiwanego przez środowisko uruchomieniowe języka wspólnego do przechowywania plików pobranych z innych komputerów, a środowisko uruchomieniowe języka wspólnego automatycznie usuwa pliki, gdy nie są już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="bf499-120">This is the same cache maintained by the common language runtime to store files downloaded from other computers, and the common language runtime automatically deletes the files when they are no longer needed.</span></span>  
  
-   <span data-ttu-id="bf499-121">Opcjonalnie ustawić niestandardową lokalizację plików w tle przy użyciu <xref:System.AppDomainSetup.CachePath%2A> właściwości i <xref:System.AppDomainSetup.ApplicationName%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="bf499-121">Optionally set a custom location for shadow copied files by using the <xref:System.AppDomainSetup.CachePath%2A> property and the <xref:System.AppDomainSetup.ApplicationName%2A> property.</span></span>  
  
     <span data-ttu-id="bf499-122">Podstawowa ścieżka lokalizacji jest tworzony przez łączenie <xref:System.AppDomainSetup.ApplicationName%2A> właściwości <xref:System.AppDomainSetup.CachePath%2A> właściwość jako podkatalogu.</span><span class="sxs-lookup"><span data-stu-id="bf499-122">The base path for the location is formed by concatenating the <xref:System.AppDomainSetup.ApplicationName%2A> property to the <xref:System.AppDomainSetup.CachePath%2A> property as a subdirectory.</span></span> <span data-ttu-id="bf499-123">Zestawy są kopiowane do podkatalogów tej ścieżki nie do podstawowej sama ścieżka cień.</span><span class="sxs-lookup"><span data-stu-id="bf499-123">Assemblies are shadow copied to subdirectories of this path, not to the base path itself.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf499-124">Jeśli <xref:System.AppDomainSetup.ApplicationName%2A> nie ustawiono właściwości <xref:System.AppDomainSetup.CachePath%2A> właściwości jest ignorowany i jest używany przez pamięć podręczną pobierania.</span><span class="sxs-lookup"><span data-stu-id="bf499-124">If the <xref:System.AppDomainSetup.ApplicationName%2A> property is not set, the <xref:System.AppDomainSetup.CachePath%2A> property is ignored and the download cache is used.</span></span> <span data-ttu-id="bf499-125">Nie wyjątek.</span><span class="sxs-lookup"><span data-stu-id="bf499-125">No exception is thrown.</span></span>  
  
     <span data-ttu-id="bf499-126">Jeśli określisz lokalizacji niestandardowej, są zobowiązani do czyszczenia katalogów i skopiować pliki, kiedy nie są już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="bf499-126">If you specify a custom location, you are responsible for cleaning up the directories and copied files when they are no longer needed.</span></span> <span data-ttu-id="bf499-127">Nie są automatycznie usuwane.</span><span class="sxs-lookup"><span data-stu-id="bf499-127">They are not deleted automatically.</span></span>  
  
     <span data-ttu-id="bf499-128">Istnieje kilka przyczyn, dlaczego warto ustawić niestandardową lokalizację plików w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-128">There are a few reasons why you might want to set a custom location for shadow copied files.</span></span> <span data-ttu-id="bf499-129">Można ustawić niestandardową lokalizację plików w tle, jeśli aplikacja generuje dużą liczbę kopii.</span><span class="sxs-lookup"><span data-stu-id="bf499-129">You might want to set a custom location for shadow copied files if your application generates a large number of copies.</span></span> <span data-ttu-id="bf499-130">Pamięć podręczną pobierania jest ograniczona przez rozmiar, a nie przez okres istnienia, więc jest to możliwe, że środowisko uruchomieniowe języka wspólnego będzie próbował usunąć plik, który jest używany.</span><span class="sxs-lookup"><span data-stu-id="bf499-130">The download cache is limited by size, not by lifetime, so it is possible that the common language runtime will attempt to delete a file that is still in use.</span></span> <span data-ttu-id="bf499-131">Kolejny powód, aby ustawić niestandardową lokalizację jest w przypadku korzystania z aplikacji nie ma prawa do zapisu na lokalizację katalogu, środowisko uruchomieniowe języka wspólnego używanych przez pamięć podręczną pobierania.</span><span class="sxs-lookup"><span data-stu-id="bf499-131">Another reason to set a custom location is when users running your application do not have write access to the directory location the common language runtime uses for the download cache.</span></span>  
  
-   <span data-ttu-id="bf499-132">Opcjonalnie ograniczyć zestawy, które są w tle przy użyciu <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="bf499-132">Optionally limit the assemblies that are shadow copied by using the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property.</span></span>  
  
     <span data-ttu-id="bf499-133">Po włączeniu kopiowanie w tle dla domeny aplikacji, wartość domyślna to można skopiować wszystkie zestawy w ścieżce aplikacji — to znaczy w katalogach określony przez <xref:System.AppDomainSetup.ApplicationBase%2A> i <xref:System.AppDomainSetup.PrivateBinPath%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="bf499-133">When you enable shadow copying for an application domain, the default is to copy all assemblies in the application path — that is, in the directories specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties.</span></span> <span data-ttu-id="bf499-134">Można ograniczyć kopiowanie do wybranych katalogów, tworząc ciąg, który zawiera tylko katalogi chcesz kopii w tle i przypisywanie ciąg do <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="bf499-134">You can limit the copying to selected directories by creating a string that contains only those directories you want to shadow copy, and assigning the string to the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property.</span></span> <span data-ttu-id="bf499-135">Katalogi należy rozdzielić średnikami.</span><span class="sxs-lookup"><span data-stu-id="bf499-135">Separate the directories with semicolons.</span></span> <span data-ttu-id="bf499-136">Tylko zestawy, które są kopie w tle są pokazane w wybranych katalogów.</span><span class="sxs-lookup"><span data-stu-id="bf499-136">The only assemblies that are shadow copied are the ones in the selected directories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf499-137">Jeśli nie przypisuj ciąg <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> właściwości, lub jeśli ta właściwość jest ustawiona na `null`, wszystkie zestawy w katalogach określonych przez <xref:System.AppDomainSetup.ApplicationBase%2A> i <xref:System.AppDomainSetup.PrivateBinPath%2A> właściwości są kopie w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-137">If you don’t assign a string to the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property, or if you set this property to `null`, all assemblies in the directories specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties are shadow copied.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bf499-138">Ponieważ średnik jest znak ogranicznika średnikami, nie może zawierać ścieżki katalogu.</span><span class="sxs-lookup"><span data-stu-id="bf499-138">Directory paths must not contain semicolons, because the semicolon is the delimiter character.</span></span> <span data-ttu-id="bf499-139">Brak nie znak ucieczki dla średnikami.</span><span class="sxs-lookup"><span data-stu-id="bf499-139">There is no escape character for semicolons.</span></span>  
  
<a name="StartupPerformance"></a>   
## <a name="startup-performance"></a><span data-ttu-id="bf499-140">Startowa wydajność</span><span class="sxs-lookup"><span data-stu-id="bf499-140">Startup Performance</span></span>  
 <span data-ttu-id="bf499-141">Po uruchomieniu domeny aplikacji, która używa kopiowanie w tle, istnieje opóźnienie podczas zestawy w katalogu aplikacji są kopiowane do katalogu kopii w tle lub sprawdzić, czy są już w tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bf499-141">When an application domain that uses shadow copying starts, there is a delay while assemblies in the application directory are copied to the shadow copy directory, or verified if they are already in that location.</span></span> <span data-ttu-id="bf499-142">Przed [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], wszystkie zestawy zostały skopiowane do katalogu tymczasowego.</span><span class="sxs-lookup"><span data-stu-id="bf499-142">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], all assemblies were copied to a temporary directory.</span></span> <span data-ttu-id="bf499-143">Otwarto każdego zestawu, aby zweryfikować nazwę zestawu, a silnej nazwy zostało zweryfikowane.</span><span class="sxs-lookup"><span data-stu-id="bf499-143">Each assembly was opened to verify the assembly name, and the strong name was validated.</span></span> <span data-ttu-id="bf499-144">Każdy zestaw zaznaczono czy miał został zaktualizowany niedawno niż kopia w tle kopii katalogu.</span><span class="sxs-lookup"><span data-stu-id="bf499-144">Each assembly was checked to see whether it had been updated more recently than the copy in the shadow copy directory.</span></span> <span data-ttu-id="bf499-145">Jeśli tak, został skopiowany do katalogu kopii w tle.</span><span class="sxs-lookup"><span data-stu-id="bf499-145">If so, it was copied to the shadow copy directory.</span></span> <span data-ttu-id="bf499-146">Na koniec tymczasowe kopie zostały odrzucone.</span><span class="sxs-lookup"><span data-stu-id="bf499-146">Finally, the temporary copies were discarded.</span></span>  
  
 <span data-ttu-id="bf499-147">Począwszy od [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], domyślne zachowanie uruchamiania jest bezpośrednie porównanie pliku Data i godzina każdego zestawu w katalogu aplikacji przy użyciu pliku daty i czasu kopii w tle katalogu kopii.</span><span class="sxs-lookup"><span data-stu-id="bf499-147">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the default startup behavior is to directly compare the file date and time of each assembly in the application directory with the file date and time of the copy in the shadow copy directory.</span></span> <span data-ttu-id="bf499-148">Jeśli zestaw został zaktualizowany, jest kopiowana za pomocą tej samej procedury, jak w starszych wersjach programu .NET Framework; w przeciwnym razie kopia w tle kopii katalogu została załadowana.</span><span class="sxs-lookup"><span data-stu-id="bf499-148">If the assembly has been updated, it is copied by using the same procedure as in earlier versions of the .NET Framework; otherwise, the copy in the shadow copy directory is loaded.</span></span>  
  
 <span data-ttu-id="bf499-149">Wynikowa zwiększenie wydajności jest największy dla aplikacji, w których zestawy nie zmieniają się często i zmiany zwykle występują w małego podzbioru zestawów.</span><span class="sxs-lookup"><span data-stu-id="bf499-149">The resulting performance improvement is largest for applications in which assemblies do not change frequently and changes usually occur in a small subset of assemblies.</span></span> <span data-ttu-id="bf499-150">Większość zestawów w przypadku zmiany aplikacji są często używane nowe zachowanie domyślne może spowodować regresji wydajności.</span><span class="sxs-lookup"><span data-stu-id="bf499-150">If a majority of assemblies in an application change frequently, the new default behavior might cause a performance regression.</span></span> <span data-ttu-id="bf499-151">Można przywrócić zachowanie uruchamiania poprzednich wersji programu .NET Framework, dodając [ \<shadowCopyVerifyByTimestamp > element](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) do pliku konfiguracji z `enabled="false"`.</span><span class="sxs-lookup"><span data-stu-id="bf499-151">You can restore the startup behavior of previous versions of the .NET Framework by adding the [\<shadowCopyVerifyByTimestamp> element](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) to the configuration file, with `enabled="false"`.</span></span>  
  
<a name="ObsoleteMethods"></a>   
## <a name="obsolete-methods"></a><span data-ttu-id="bf499-152">Metody przestarzałe</span><span class="sxs-lookup"><span data-stu-id="bf499-152">Obsolete Methods</span></span>  
 <span data-ttu-id="bf499-153"><xref:System.AppDomain> Klasa ma kilka metod, takich jak <xref:System.AppDomain.SetShadowCopyFiles%2A> i <xref:System.AppDomain.ClearShadowCopyPath%2A>, który może służyć do kontrolowania kopiowanie w tle w domenie aplikacji, ale te zostały oznaczone jako przestarzałe w programie .NET Framework w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="bf499-153">The <xref:System.AppDomain> class has several methods, such as <xref:System.AppDomain.SetShadowCopyFiles%2A> and <xref:System.AppDomain.ClearShadowCopyPath%2A>, that can be used to control shadow copying on an application domain, but these have been marked obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="bf499-154">Zalecanym sposobem konfigurowania domeny aplikacji dla kopiowanie w tle jest użycie właściwości <xref:System.AppDomainSetup> klasy.</span><span class="sxs-lookup"><span data-stu-id="bf499-154">The recommended way to configure an application domain for shadow copying is to use the properties of the <xref:System.AppDomainSetup> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf499-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bf499-155">See Also</span></span>  
 <xref:System.AppDomainSetup.ShadowCopyFiles%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.CachePath%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.ApplicationName%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bf499-156">\<shadowCopyVerifyByTimestamp > — Element</span><span class="sxs-lookup"><span data-stu-id="bf499-156">\<shadowCopyVerifyByTimestamp> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)