---
title: "Zagadnienia dotyczące współdziałania Direct3D9 i WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 886ef6c8c9df9d14b5c2a805da2e3948d5e55f69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a><span data-ttu-id="f75da-102">Zagadnienia dotyczące współdziałania Direct3D9 i WPF</span><span class="sxs-lookup"><span data-stu-id="f75da-102">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>
<span data-ttu-id="f75da-103">Zawartość Direct3D9 można obsługiwać przy użyciu <xref:System.Windows.Interop.D3DImage> klasy.</span><span class="sxs-lookup"><span data-stu-id="f75da-103">You can host Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span> <span data-ttu-id="f75da-104">Hostowanie zawartości Direct3D9 mogą wpływać na wydajność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f75da-104">Hosting Direct3D9 content can affect the performance of your application.</span></span> <span data-ttu-id="f75da-105">W tym temacie opisano najlepsze rozwiązania w celu optymalizacji wydajności, odnośnie do hostowania zawartości Direct3D9 w aplikacji Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f75da-105">This topic describes best practices to optimize performance when hosting Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="f75da-106">Sposób użycia obejmują następujące najlepsze rozwiązania <xref:System.Windows.Interop.D3DImage> i najlepsze rozwiązania w przypadku, gdy używasz systemu Windows Vista, Windows XP i wielu monitor wyświetla.</span><span class="sxs-lookup"><span data-stu-id="f75da-106">These best practices include how to use <xref:System.Windows.Interop.D3DImage> and best practices when you are using Windows Vista, Windows XP, and multi-monitor displays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f75da-107">Aby uzyskać przykłady kodu, które przedstawiają następujące najlepsze rozwiązania, zobacz [WPF i współdziałanie Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f75da-107">For code examples that demonstrate these best practices, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span></span>  
  
## <a name="use-d3dimage-sparingly"></a><span data-ttu-id="f75da-108">Użyj D3DImage oszczędnie</span><span class="sxs-lookup"><span data-stu-id="f75da-108">Use D3DImage Sparingly</span></span>  
 <span data-ttu-id="f75da-109">Direct3D9 zawartości hostowanej w <xref:System.Windows.Interop.D3DImage> wystąpienia nie jest renderowana jako wysoka jak w przypadku czysty aplikacji Direct3D.</span><span class="sxs-lookup"><span data-stu-id="f75da-109">Direct3D9 content hosted in a <xref:System.Windows.Interop.D3DImage> instance does not render as fast as in a pure Direct3D application.</span></span> <span data-ttu-id="f75da-110">Kopiowanie powierzchni i opróżniania buforu polecenie może być kosztowne operacje.</span><span class="sxs-lookup"><span data-stu-id="f75da-110">Copying the surface and flushing the command buffer can be costly operations.</span></span> <span data-ttu-id="f75da-111">Jak liczba <xref:System.Windows.Interop.D3DImage> zwiększa wystąpień opróżniania więcej występuje i powoduje spadek wydajności.</span><span class="sxs-lookup"><span data-stu-id="f75da-111">As the number of <xref:System.Windows.Interop.D3DImage> instances increases, more flushing occurs, and performance degrades.</span></span> <span data-ttu-id="f75da-112">W związku z tym należy używać <xref:System.Windows.Interop.D3DImage> oszczędnie.</span><span class="sxs-lookup"><span data-stu-id="f75da-112">Therefore, you should use <xref:System.Windows.Interop.D3DImage> sparingly.</span></span>  
  
## <a name="best-practices-on-windows-vista"></a><span data-ttu-id="f75da-113">Najlepsze rozwiązania w systemie Windows Vista</span><span class="sxs-lookup"><span data-stu-id="f75da-113">Best Practices on Windows Vista</span></span>  
 <span data-ttu-id="f75da-114">Aby uzyskać najlepszą wydajność w systemie Windows Vista z wyświetlania, która jest skonfigurowana do używania modelu wyświetlić sterowników systemu Windows (WDDM), należy utworzyć obszar Direct3D9 na `IDirect3DDevice9Ex` urządzenia.</span><span class="sxs-lookup"><span data-stu-id="f75da-114">For best performance on Windows Vista with a display that is configured to use the Windows Display Driver Model (WDDM), create your Direct3D9 surface on an `IDirect3DDevice9Ex` device.</span></span> <span data-ttu-id="f75da-115">Dzięki temu udostępnianie powierzchni.</span><span class="sxs-lookup"><span data-stu-id="f75da-115">This enables surface sharing.</span></span> <span data-ttu-id="f75da-116">Karta wideo musi obsługiwać `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` i `D3DCAPS2_CANSHARERESOURCE` możliwości sterownika w systemie Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f75da-116">The video card must support the `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` and `D3DCAPS2_CANSHARERESOURCE` driver capabilities on Windows Vista.</span></span> <span data-ttu-id="f75da-117">Inne ustawienia powodują powierzchni do skopiowania przez oprogramowanie, które znacząco zmniejsza wydajność.</span><span class="sxs-lookup"><span data-stu-id="f75da-117">Any other settings cause the surface to be copied through software, which reduces performance significantly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f75da-118">Jeśli system Windows Vista wyświetlania, która jest skonfigurowana do używania systemu Windows XP wyświetlić sterownik modelu (XDDM), powierzchni zawsze jest kopiowana za pośrednictwem oprogramowania, niezależnie od ustawień.</span><span class="sxs-lookup"><span data-stu-id="f75da-118">If Windows Vista has a display that is configured to use the Windows XP Display Driver Model (XDDM), the surface is always copied through software, regardless of settings.</span></span> <span data-ttu-id="f75da-119">Odpowiednie ustawienia i karty wideo zobaczysz lepszą wydajność w systemie Windows Vista używania WDDM, ponieważ powierzchni kopie są wykonywane w sprzęcie.</span><span class="sxs-lookup"><span data-stu-id="f75da-119">With the proper settings and video card, you will see better performance on Windows Vista when you use the WDDM because surface copies are performed in hardware.</span></span>  
  
## <a name="best-practices-on-windows-xp"></a><span data-ttu-id="f75da-120">Najlepsze rozwiązania w systemie Windows XP</span><span class="sxs-lookup"><span data-stu-id="f75da-120">Best Practices on Windows XP</span></span>  
 <span data-ttu-id="f75da-121">Aby uzyskać najlepszą wydajność w systemie Windows XP, który korzysta z systemu Windows XP wyświetlania sterownik modelu (XDDM), tworzenie zamykane powierzchni, która działa prawidłowo po `IDirect3DSurface9::GetDC` metoda jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="f75da-121">For best performance on Windows XP, which uses the Windows XP Display Driver Model (XDDM), create a lockable surface that behaves correctly when the `IDirect3DSurface9::GetDC` method is called.</span></span> <span data-ttu-id="f75da-122">Wewnętrznie `BitBlt` metody przesyła powierzchni na urządzeniach sprzętowych.</span><span class="sxs-lookup"><span data-stu-id="f75da-122">Internally, the `BitBlt` method transfers the surface across devices in hardware.</span></span> <span data-ttu-id="f75da-123">`GetDC` Metoda zawsze działa na powierzchni XRGB.</span><span class="sxs-lookup"><span data-stu-id="f75da-123">The `GetDC` method always works on XRGB surfaces.</span></span> <span data-ttu-id="f75da-124">Jednak jeśli na komputerze klienckim jest zainstalowany system Windows XP z dodatkiem SP3 lub SP2, a klient ma również poprawka dla funkcji warstwie okno, ta metoda działa tylko na powierzchni ARGB.</span><span class="sxs-lookup"><span data-stu-id="f75da-124">However, if the client computer is running Windows XP with SP3 or SP2, and if the client also has the hotfix for the layered-window feature, this method only works on ARGB surfaces.</span></span> <span data-ttu-id="f75da-125">Karta wideo musi obsługiwać `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` możliwości sterownika.</span><span class="sxs-lookup"><span data-stu-id="f75da-125">The video card must support the `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` driver capability.</span></span>  
  
 <span data-ttu-id="f75da-126">Głębokość ekranu 16-bitowych może znacznie zmniejszyć wydajność.</span><span class="sxs-lookup"><span data-stu-id="f75da-126">A 16-bit desktop display depth can significantly reduce performance.</span></span> <span data-ttu-id="f75da-127">Zaleca się pulpitu 32-bitowych.</span><span class="sxs-lookup"><span data-stu-id="f75da-127">A 32-bit desktop is recommended.</span></span>  
  
 <span data-ttu-id="f75da-128">Jeśli tworzysz dla systemu Windows Vista i Windows XP, należy przetestować wydajność w systemie Windows XP.</span><span class="sxs-lookup"><span data-stu-id="f75da-128">If you are developing for Windows Vista and Windows XP, test the performance on Windows XP.</span></span> <span data-ttu-id="f75da-129">Wyczerpaniu pamięci wideo w systemie Windows XP jest problemem.</span><span class="sxs-lookup"><span data-stu-id="f75da-129">Running out of video memory on Windows XP is a concern.</span></span> <span data-ttu-id="f75da-130">Ponadto <xref:System.Windows.Interop.D3DImage> w systemie Windows XP używa więcej pamięci wideo i przepustowość niż Windows Vista WDDM ze względu na potrzeby kopiowania pamięci bardzo wideo.</span><span class="sxs-lookup"><span data-stu-id="f75da-130">In addition, <xref:System.Windows.Interop.D3DImage> on Windows XP uses more video memory and bandwidth than Windows Vista WDDM, due to a necessary extra video memory copy.</span></span> <span data-ttu-id="f75da-131">W związku z tym można spodziewać się wydajności być gorsza w systemie Windows XP niż w systemie Windows Vista dla tego samego sprzętu wideo.</span><span class="sxs-lookup"><span data-stu-id="f75da-131">Therefore, you can expect performance to be worse on Windows XP than on Windows Vista for the same video hardware.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f75da-132">XDDM jest dostępna na systemie Windows XP i Windows Vista; jednak WDDM jest dostępna tylko w systemie Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f75da-132">XDDM is available on both Windows XP and Windows Vista; however, WDDM is available only on Windows Vista.</span></span>  
  
## <a name="general-best-practices"></a><span data-ttu-id="f75da-133">Najlepsze praktyki ogólne</span><span class="sxs-lookup"><span data-stu-id="f75da-133">General Best Practices</span></span>  
 <span data-ttu-id="f75da-134">Podczas tworzenia urządzenia, użyj `D3DCREATE_MULTITHREADED` flagi tworzenia.</span><span class="sxs-lookup"><span data-stu-id="f75da-134">When you create the device, use the `D3DCREATE_MULTITHREADED` creation flag.</span></span> <span data-ttu-id="f75da-135">Pozwala to zmniejszyć wydajność, ale system renderowania WPF wywołuje metody dla tego urządzenia z innego wątku.</span><span class="sxs-lookup"><span data-stu-id="f75da-135">This reduces performance, but the WPF rendering system calls methods on this device from another thread.</span></span> <span data-ttu-id="f75da-136">Należy postępować zgodnie protokołu blokowania poprawnie, dzięki czemu nie ma dwa wątków dostępu do urządzenia, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="f75da-136">Be sure to follow the locking protocol correctly, so that no two threads access the device at the same time.</span></span>  
  
 <span data-ttu-id="f75da-137">Jeśli Twoje renderowania jest wykonywana w wątku WPF zarządzane, zdecydowanie zaleca się utworzenie urządzenia w usłudze `D3DCREATE_FPU_PRESERVE` flagi tworzenia.</span><span class="sxs-lookup"><span data-stu-id="f75da-137">If your rendering is performed on a WPF managed thread, it is strongly recommended that you create the device with the `D3DCREATE_FPU_PRESERVE` creation flag.</span></span> <span data-ttu-id="f75da-138">Bez tego ustawienia renderowania D3D można zmniejszyć dokładność operacji podwójnej precyzji WPF i powodować problemy związane z renderowaniem.</span><span class="sxs-lookup"><span data-stu-id="f75da-138">Without this setting, the D3D rendering can reduce the accuracy of WPF double-precision operations and introduce rendering issues.</span></span>  
  
 <span data-ttu-id="f75da-139">Ustawianie widoku kafelków <xref:System.Windows.Interop.D3DImage> jest szybkie, chyba, że Kafelek powierzchni z systemem innym niż pow2 bez obsługi sprzętu lub jeśli użytkownik kafelka <xref:System.Windows.Media.DrawingBrush> lub <xref:System.Windows.Media.VisualBrush> zawierający <xref:System.Windows.Interop.D3DImage>.</span><span class="sxs-lookup"><span data-stu-id="f75da-139">Tiling a <xref:System.Windows.Interop.D3DImage> is fast, unless you tile a non-pow2 surface without hardware support, or if you tile a <xref:System.Windows.Media.DrawingBrush> or <xref:System.Windows.Media.VisualBrush> that contains a <xref:System.Windows.Interop.D3DImage>.</span></span>  
  
## <a name="best-practices-for-multi-monitor-displays"></a><span data-ttu-id="f75da-140">Najlepsze rozwiązania dotyczące wielu monitorów</span><span class="sxs-lookup"><span data-stu-id="f75da-140">Best Practices for Multi-Monitor Displays</span></span>  
 <span data-ttu-id="f75da-141">Jeśli używasz komputera, który ma wiele monitorów, należy wykonać opisane wcześniej najlepszych rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="f75da-141">If you are using a computer that has multiple monitors, you should follow the previously described best practices.</span></span> <span data-ttu-id="f75da-142">Dostępne są także niektóre dodatkowe zagadnienia dotyczące wydajności związane wiele monitorów.</span><span class="sxs-lookup"><span data-stu-id="f75da-142">There are also some additional performance considerations for a multi-monitor configuration.</span></span>  
  
 <span data-ttu-id="f75da-143">Podczas tworzenia buforu zapasowego jest tworzona na określonym urządzeniu i karty, ale WPF mogą być wyświetlane front buforu na wszystkich kart.</span><span class="sxs-lookup"><span data-stu-id="f75da-143">When you create the back buffer, it is created on a specific device and adapter, but WPF may display the front buffer on any adapter.</span></span> <span data-ttu-id="f75da-144">Kopiowanie między kart, aby zaktualizować front buforu może być bardzo kosztowna.</span><span class="sxs-lookup"><span data-stu-id="f75da-144">Copying across adapters to update the front buffer can be very expensive.</span></span> <span data-ttu-id="f75da-145">W systemie Windows Vista, który jest skonfigurowany do używania WDDM z wielu kart wideo i `IDirect3DDevice9Ex` urządzenia, jeśli bufor front jest na inną kartę, ale nadal tej samej karty wideo, nie ma wpływ na wydajność.</span><span class="sxs-lookup"><span data-stu-id="f75da-145">On Windows Vista that is configured to use the WDDM with multiple video cards and with an `IDirect3DDevice9Ex` device, if the front buffer is on a different adapter but still the same video card, there is no performance penalty.</span></span> <span data-ttu-id="f75da-146">W systemach Windows XP i XDDM z wielu kart wideo, istnieje jednak zmniejszenie wydajności znaczące po front bufor jest wyświetlany na inną kartę niż buforu zapasowego.</span><span class="sxs-lookup"><span data-stu-id="f75da-146">However, on Windows XP and the XDDM with multiple video cards, there is a significant performance penalty when the front buffer is displayed on a different adapter than the back buffer.</span></span> <span data-ttu-id="f75da-147">Aby uzyskać więcej informacji, zobacz [WPF i współdziałanie Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f75da-147">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span></span>  
  
## <a name="performance-summary"></a><span data-ttu-id="f75da-148">Podsumowanie wydajności</span><span class="sxs-lookup"><span data-stu-id="f75da-148">Performance Summary</span></span>  
 <span data-ttu-id="f75da-149">W poniższej tabeli przedstawiono wydajności aktualizacji front buforu w zależności od systemu operacyjnego, format pikseli i lockability powierzchni.</span><span class="sxs-lookup"><span data-stu-id="f75da-149">The following table shows performance of the front buffer update as a function of operating system, pixel format, and surface lockability.</span></span> <span data-ttu-id="f75da-150">Front buforu i buforu zapasowego muszą być w tej samej karty.</span><span class="sxs-lookup"><span data-stu-id="f75da-150">The front buffer and back buffer are assumed to be on the same adapter.</span></span> <span data-ttu-id="f75da-151">W zależności od konfiguracji karty aktualizacje sprzętu są zwykle dużo szybsze niż aktualizacji oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="f75da-151">Depending on the adapter configuration, hardware updates are generally much faster than software updates.</span></span>  
  
|<span data-ttu-id="f75da-152">Format pikseli powierzchni</span><span class="sxs-lookup"><span data-stu-id="f75da-152">Surface pixel format</span></span>|<span data-ttu-id="f75da-153">Windows Vista, WDDM i 9Ex</span><span class="sxs-lookup"><span data-stu-id="f75da-153">Windows Vista, WDDM and 9Ex</span></span>|<span data-ttu-id="f75da-154">Inne konfiguracje systemu Windows Vista</span><span class="sxs-lookup"><span data-stu-id="f75da-154">Other Windows Vista configurations</span></span>|<span data-ttu-id="f75da-155">Windows XP z dodatkiem SP3 lub SP2 z poprawek</span><span class="sxs-lookup"><span data-stu-id="f75da-155">Windows XP SP3 or SP2 w/ hotfix</span></span>|<span data-ttu-id="f75da-156">Windows XP z dodatkiem SP2</span><span class="sxs-lookup"><span data-stu-id="f75da-156">Windows XP SP2</span></span>|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|<span data-ttu-id="f75da-157">D3DFMT_X8R8G8B8 (nie zamykane)</span><span class="sxs-lookup"><span data-stu-id="f75da-157">D3DFMT_X8R8G8B8 (not lockable)</span></span>|<span data-ttu-id="f75da-158">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-158">**Hardware Update**</span></span>|<span data-ttu-id="f75da-159">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-159">Software Update</span></span>|<span data-ttu-id="f75da-160">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-160">Software Update</span></span>|<span data-ttu-id="f75da-161">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-161">Software Update</span></span>|  
|<span data-ttu-id="f75da-162">D3DFMT_X8R8G8B8 (zamykane)</span><span class="sxs-lookup"><span data-stu-id="f75da-162">D3DFMT_X8R8G8B8 (lockable)</span></span>|<span data-ttu-id="f75da-163">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-163">**Hardware Update**</span></span>|<span data-ttu-id="f75da-164">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-164">Software Update</span></span>|<span data-ttu-id="f75da-165">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-165">**Hardware Update**</span></span>|<span data-ttu-id="f75da-166">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-166">**Hardware Update**</span></span>|  
|<span data-ttu-id="f75da-167">D3DFMT_A8R8G8B8 (nie zamykane)</span><span class="sxs-lookup"><span data-stu-id="f75da-167">D3DFMT_A8R8G8B8 (not lockable)</span></span>|<span data-ttu-id="f75da-168">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-168">**Hardware Update**</span></span>|<span data-ttu-id="f75da-169">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-169">Software Update</span></span>|<span data-ttu-id="f75da-170">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-170">Software Update</span></span>|<span data-ttu-id="f75da-171">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-171">Software Update</span></span>|  
|<span data-ttu-id="f75da-172">D3DFMT_A8R8G8B8 (zamykane)</span><span class="sxs-lookup"><span data-stu-id="f75da-172">D3DFMT_A8R8G8B8 (lockable)</span></span>|<span data-ttu-id="f75da-173">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-173">**Hardware Update**</span></span>|<span data-ttu-id="f75da-174">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-174">Software Update</span></span>|<span data-ttu-id="f75da-175">**Aktualizacja sprzętu**</span><span class="sxs-lookup"><span data-stu-id="f75da-175">**Hardware Update**</span></span>|<span data-ttu-id="f75da-176">Aktualizacja oprogramowania</span><span class="sxs-lookup"><span data-stu-id="f75da-176">Software Update</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f75da-177">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f75da-177">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="f75da-178">WPF i współdziałanie Direct3D9</span><span class="sxs-lookup"><span data-stu-id="f75da-178">WPF and Direct3D9 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
 [<span data-ttu-id="f75da-179">Wskazówki: Tworzenie zawartości Direct3D9 hostingu na platformie WPF</span><span class="sxs-lookup"><span data-stu-id="f75da-179">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [<span data-ttu-id="f75da-180">Wskazówki: Obsługa Direct3D9 zawartości na platformie WPF</span><span class="sxs-lookup"><span data-stu-id="f75da-180">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)