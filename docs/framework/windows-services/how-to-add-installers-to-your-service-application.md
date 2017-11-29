---
title: "Porady: dodawanie instalatorów od aplikacji usług"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 8137e41f92335849916dfc9e9ce72afeb186e73c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="02e95-102">Porady: dodawanie instalatorów od aplikacji usług</span><span class="sxs-lookup"><span data-stu-id="02e95-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="02e95-103">Program Visual Studio jest dostarczany instalacji składników, które można zainstalować zasoby skojarzone z usługi aplikacji.</span><span class="sxs-lookup"><span data-stu-id="02e95-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="02e95-104">Instalacja składników zarejestrować poszczególnych usług w systemie, do której jest instalowany i umożliwić Menedżera sterowania usługami wiedzieć, czy Usługa istnieje.</span><span class="sxs-lookup"><span data-stu-id="02e95-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="02e95-105">Podczas pracy z aplikacją usługi, możesz wybrać link w oknie właściwości można automatycznie dodać odpowiednie pliki instalacyjne do projektu.</span><span class="sxs-lookup"><span data-stu-id="02e95-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02e95-106">Wartości właściwości dla usługi są kopiowane z klasy usługi do klasy Instalatora.</span><span class="sxs-lookup"><span data-stu-id="02e95-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="02e95-107">Po aktualizacji wartości właściwości w klasie usługi, nie są one automatycznie aktualizowane w Instalatorze.</span><span class="sxs-lookup"><span data-stu-id="02e95-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="02e95-108">Po dodaniu Instalatora do projektu, nową klasę (, która domyślnie nosi nazwę `ProjectInstaller`) jest tworzony w projekcie i wystąpień instalacji odpowiednie składniki są tworzone w niej.</span><span class="sxs-lookup"><span data-stu-id="02e95-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="02e95-109">Ta klasa działa jako centralny punkt dla wszystkich składników instalacji musi projektu.</span><span class="sxs-lookup"><span data-stu-id="02e95-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="02e95-110">Na przykład jeśli dodać drugi usług do aplikacji i kliknij link Dodaj Instalatora, drugi klasa Instalatora nie jest tworzona; Zamiast tego składnika niezbędne dodatkowe instalacji drugiego usługi jest dodawany do istniejącej klasy.</span><span class="sxs-lookup"><span data-stu-id="02e95-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="02e95-111">Nie trzeba wykonać specjalne pisania kodu w ramach programów instalacyjnych, aby poprawnie zainstalować usługi.</span><span class="sxs-lookup"><span data-stu-id="02e95-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="02e95-112">Jednak czasami konieczne może być modyfikować zawartość pliki instalacyjne, jeśli konieczne jest dodanie specjalne funkcje do procesu instalacji.</span><span class="sxs-lookup"><span data-stu-id="02e95-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02e95-113">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="02e95-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="02e95-114">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="02e95-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="02e95-115">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="02e95-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="02e95-116">Aby dodać instalatorów od aplikacji usług</span><span class="sxs-lookup"><span data-stu-id="02e95-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="02e95-117">W **Eksploratora rozwiązań**, dostępu **projekt** widoku dla usługi, dla której chcesz dodać składnik instalacji.</span><span class="sxs-lookup"><span data-stu-id="02e95-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="02e95-118">Kliknij przycisk tła projektanta, aby wybrać usługi, a nie wszystkich jego zawartość.</span><span class="sxs-lookup"><span data-stu-id="02e95-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="02e95-119">Przy użyciu projektanta fokus, kliknij prawym przyciskiem myszy, a następnie kliknij polecenie **dodać Instalatora**.</span><span class="sxs-lookup"><span data-stu-id="02e95-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="02e95-120">Nowa klasa `ProjectInstaller`i dwa składniki instalacji <xref:System.ServiceProcess.ServiceProcessInstaller> i <xref:System.ServiceProcess.ServiceInstaller>, zostaną dodane do projektu i wartości właściwości dla usługi są kopiowane do składników.</span><span class="sxs-lookup"><span data-stu-id="02e95-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="02e95-121">Kliknij przycisk <xref:System.ServiceProcess.ServiceInstaller> składnika i sprawdź, czy wartość <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> właściwość ma ustawioną taką samą wartość jak <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> właściwości na samą usługę.</span><span class="sxs-lookup"><span data-stu-id="02e95-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="02e95-122">Aby określić, jak można uruchomić usługi, kliknij przycisk <xref:System.ServiceProcess.ServiceInstaller> składnika i ustaw <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> na odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="02e95-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="02e95-123">Wartość</span><span class="sxs-lookup"><span data-stu-id="02e95-123">Value</span></span>|<span data-ttu-id="02e95-124">Wynik</span><span class="sxs-lookup"><span data-stu-id="02e95-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="02e95-125">Usługa musi być uruchomiona ręcznie po zakończeniu instalacji.</span><span class="sxs-lookup"><span data-stu-id="02e95-125">The service must be manually started after installation.</span></span> <span data-ttu-id="02e95-126">Aby uzyskać więcej informacji, zobacz [porady: Uruchom usługi](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="02e95-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="02e95-127">Przy każdym ponownym uruchomieniu komputera, usługa zostanie uruchomiona przez samego siebie.</span><span class="sxs-lookup"><span data-stu-id="02e95-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="02e95-128">Nie można uruchomić usługi.</span><span class="sxs-lookup"><span data-stu-id="02e95-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="02e95-129">Aby ustalić kontekst zabezpieczeń, w którym będzie uruchamiany usługi, kliknij przycisk <xref:System.ServiceProcess.ServiceProcessInstaller> składnika i ustawianie wartości odpowiednich właściwości.</span><span class="sxs-lookup"><span data-stu-id="02e95-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="02e95-130">Aby uzyskać więcej informacji, zobacz [porady: Określanie kontekstu zabezpieczeń dla usług](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="02e95-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="02e95-131">Zastąp wszystkie metody, dla których należy wykonać czynności niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="02e95-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="02e95-132">Wykonaj kroki od 1 do 7 dla każdej dodatkowej usługi w projekcie.</span><span class="sxs-lookup"><span data-stu-id="02e95-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02e95-133">Dla każdej dodatkowej usługi w projekcie, należy dodać dodatkowe <xref:System.ServiceProcess.ServiceInstaller> składnika w projekcie `ProjectInstaller` klasy.</span><span class="sxs-lookup"><span data-stu-id="02e95-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="02e95-134"><xref:System.ServiceProcess.ServiceProcessInstaller> Element został dodany w kroku 3 współdziała z wszystkich instalatorów poszczególnych usług w projekcie.</span><span class="sxs-lookup"><span data-stu-id="02e95-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e95-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02e95-135">See Also</span></span>  
 [<span data-ttu-id="02e95-136">Wprowadzenie do aplikacji usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="02e95-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="02e95-137">Porady: Instalowanie i odinstalowywanie usług</span><span class="sxs-lookup"><span data-stu-id="02e95-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="02e95-138">Porady: uruchamianie usług</span><span class="sxs-lookup"><span data-stu-id="02e95-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="02e95-139">Porady: Określanie kontekstu zabezpieczeń dla usług</span><span class="sxs-lookup"><span data-stu-id="02e95-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)