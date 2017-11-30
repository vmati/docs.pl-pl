---
title: Semafor i klasa SemaphoreSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- counting semaphores
- semaphores
- threading [.NET Framework], cross-process synchronization
- Semaphore class, about Semaphore class
- SemaphoreSlim class, about SemaphoreSlim class
- threading [.NET Framework], Semaphore class
ms.assetid: 7722a333-b974-47a2-a7c0-f09097fb644e
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 039dee4df1a6d06fa1833eae077817ff5eca3ea3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="semaphore-and-semaphoreslim"></a><span data-ttu-id="bdfff-102">Semafor i klasa SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="bdfff-102">Semaphore and SemaphoreSlim</span></span>
<span data-ttu-id="bdfff-103"><xref:System.Threading.Semaphore?displayProperty=nameWithType> Klasa reprezentuje nazwanych (ogólnosystemowe) lub semafora lokalnego.</span><span class="sxs-lookup"><span data-stu-id="bdfff-103">The <xref:System.Threading.Semaphore?displayProperty=nameWithType> class represents a named (systemwide) or local semaphore.</span></span> <span data-ttu-id="bdfff-104">Jest cienką otoką wokół obiektu semafora Win32.</span><span class="sxs-lookup"><span data-stu-id="bdfff-104">It is a thin wrapper around the Win32 semaphore object.</span></span> <span data-ttu-id="bdfff-105">Semaforów Win32 są liczenie semaforów, które mogą być używane do kontrolowania dostępu do puli zasobów.</span><span class="sxs-lookup"><span data-stu-id="bdfff-105">Win32 semaphores are counting semaphores, which can be used to control access to a pool of resources.</span></span>  
  
 <span data-ttu-id="bdfff-106"><xref:System.Threading.SemaphoreSlim> Klasa reprezentuje semafora niewielka, szybkie, który może służyć do oczekujących w ramach jednego procesu, gdy powinny być bardzo krótki czas oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="bdfff-106">The <xref:System.Threading.SemaphoreSlim> class represents a lightweight, fast semaphore that can be used for waiting within a single process when wait times are expected to be very short.</span></span> <span data-ttu-id="bdfff-107"><xref:System.Threading.SemaphoreSlim>opiera się możliwie często na elementy podstawowe synchronizacji udostępniane przez środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="bdfff-107"><xref:System.Threading.SemaphoreSlim> relies as much as possible on synchronization primitives provided by the common language runtime (CLR).</span></span> <span data-ttu-id="bdfff-108">Jednak także uchwyty oczekiwania opóźnieniem zainicjowane, na podstawie jądra niezbędnych do obsługi oczekiwanie na wielu semaforów.</span><span class="sxs-lookup"><span data-stu-id="bdfff-108">However, it also provides lazily initialized, kernel-based wait handles as necessary to support waiting on multiple semaphores.</span></span> <span data-ttu-id="bdfff-109"><xref:System.Threading.SemaphoreSlim>również obsługuje używanie anulowanie tokenów, ale nie obsługuje nazwane semaforów lub użycie dojście oczekiwania synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="bdfff-109"><xref:System.Threading.SemaphoreSlim> also supports the use of cancellation tokens, but it does not support named semaphores or the use of a wait handle for synchronization.</span></span>  
  
## <a name="managing-a-limited-resource"></a><span data-ttu-id="bdfff-110">Zarządzanie zasobem ograniczone</span><span class="sxs-lookup"><span data-stu-id="bdfff-110">Managing a Limited Resource</span></span>  
 <span data-ttu-id="bdfff-111">Wątki wprowadź semafora przez wywołanie metody <xref:System.Threading.WaitHandle.WaitOne%2A> metodę, która jest dziedziczona z <xref:System.Threading.WaitHandle> klasy, w przypadku <xref:System.Threading.Semaphore?displayProperty=nameWithType> obiektu, lub <xref:System.Threading.SemaphoreSlim.Wait%2A?displayProperty=nameWithType> lub <xref:System.Threading.SemaphoreSlim.WaitAsync%2A?displayProperty=nameWithType> metody, w przypadku <xref:System.Threading.SemaphoreSlim> obiektu...</span><span class="sxs-lookup"><span data-stu-id="bdfff-111">Threads enter the semaphore by calling the <xref:System.Threading.WaitHandle.WaitOne%2A> method, which is inherited from the <xref:System.Threading.WaitHandle> class, in the case of a <xref:System.Threading.Semaphore?displayProperty=nameWithType> object, or the <xref:System.Threading.SemaphoreSlim.Wait%2A?displayProperty=nameWithType> or <xref:System.Threading.SemaphoreSlim.WaitAsync%2A?displayProperty=nameWithType> method, in the case of a <xref:System.Threading.SemaphoreSlim> object..</span></span> <span data-ttu-id="bdfff-112">Po powrocie z wywołania licznik na semafora zostanie zmniejszona.</span><span class="sxs-lookup"><span data-stu-id="bdfff-112">When the call returns, the count on the semaphore is decremented.</span></span> <span data-ttu-id="bdfff-113">Gdy wątek żąda wpis oraz liczbę wynosi zero, bloki wątku.</span><span class="sxs-lookup"><span data-stu-id="bdfff-113">When a thread requests entry and the count is zero, the thread blocks.</span></span> <span data-ttu-id="bdfff-114">Jak wątków wersji semafora przez wywołanie metody <xref:System.Threading.Semaphore.Release%2A?displayProperty=nameWithType> lub <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType> metody zablokowanych wątków mogą wprowadzać.</span><span class="sxs-lookup"><span data-stu-id="bdfff-114">As threads release the semaphore by calling the <xref:System.Threading.Semaphore.Release%2A?displayProperty=nameWithType> or <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType> method, blocked threads are allowed to enter.</span></span> <span data-ttu-id="bdfff-115">Brak nie gwarantuje kolejność, takich jak pierwszy, FIFO (FIFO) lub ostatni na, wytworzenia, dla zablokowanych wątków na wejście do semafora.</span><span class="sxs-lookup"><span data-stu-id="bdfff-115">There is no guaranteed order, such as first-in, first-out (FIFO) or last-in, first-out (LIFO), for blocked threads to enter the semaphore.</span></span>  
  
 <span data-ttu-id="bdfff-116">Wątek można wprowadzić semafora wielokrotnie przez wywołanie metody <xref:System.Threading.Semaphore?displayProperty=nameWithType> obiektu <xref:System.Threading.WaitHandle.WaitOne%2A> metody lub <xref:System.Threading.SemaphoreSlim> obiektu <xref:System.Threading.SemaphoreSlim.Wait%2A> metody wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="bdfff-116">A thread can enter the semaphore multiple times by calling the <xref:System.Threading.Semaphore?displayProperty=nameWithType> object's <xref:System.Threading.WaitHandle.WaitOne%2A> method or the  <xref:System.Threading.SemaphoreSlim> object's <xref:System.Threading.SemaphoreSlim.Wait%2A> method repeatedly.</span></span> <span data-ttu-id="bdfff-117">Aby zwolnić semafora, Wątek można albo wywołanie <xref:System.Threading.Semaphore.Release?displayProperty=nameWithType> lub <xref:System.Threading.SemaphoreSlim.Release?displayProperty=nameWithType> metoda przeciążenia taką samą liczbę razy, lub zadzwoń <xref:System.Threading.Semaphore.Release%28System.Int32%29?displayProperty=nameWithType> lub <xref:System.Threading.SemaphoreSlim.Release%28System.Int32%29?displayProperty=nameWithType> metoda przeciążenia i określ liczbę wpisów do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="bdfff-117">To release the semaphore, the thread can either call the <xref:System.Threading.Semaphore.Release?displayProperty=nameWithType> or <xref:System.Threading.SemaphoreSlim.Release?displayProperty=nameWithType> method overload the same number of times, or call the <xref:System.Threading.Semaphore.Release%28System.Int32%29?displayProperty=nameWithType> or <xref:System.Threading.SemaphoreSlim.Release%28System.Int32%29?displayProperty=nameWithType> method overload and specify the number of entries to be released.</span></span>  
  
### <a name="semaphores-and-thread-identity"></a><span data-ttu-id="bdfff-118">Semaforów i tożsamości wątku</span><span class="sxs-lookup"><span data-stu-id="bdfff-118">Semaphores and Thread Identity</span></span>  
 <span data-ttu-id="bdfff-119">Typy dwóch semafora nie Wymuszaj tożsamość wątku na wywołania <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.SemaphoreSlim.Wait%2A>, <xref:System.Threading.Semaphore.Release%2A>, i <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="bdfff-119">The two semaphore types do not enforce thread identity on calls to the <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.SemaphoreSlim.Wait%2A>, <xref:System.Threading.Semaphore.Release%2A>, and <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="bdfff-120">Na przykład typowy scenariusz użycia dla semaforów obejmuje wątku producentów i konsumentów wątków, z jednego wątku zawsze zwiększanie Licznik semafora, a drugi zawsze zmniejszanie go.</span><span class="sxs-lookup"><span data-stu-id="bdfff-120">For example, a common usage scenario for semaphores involves a producer thread and a consumer thread, with one thread always incrementing the semaphore count and the other always decrementing it.</span></span>  
  
 <span data-ttu-id="bdfff-121">Odpowiada programisty upewnij się, że wątek nie zwalnia semafora zbyt wiele razy.</span><span class="sxs-lookup"><span data-stu-id="bdfff-121">It is the programmer's responsibility to ensure that a thread does not release the semaphore too many times.</span></span> <span data-ttu-id="bdfff-122">Na przykład załóżmy, że maksymalna liczba dwóch i który wątku A i B wątku ma semafora zarówno wprowadź semafora.</span><span class="sxs-lookup"><span data-stu-id="bdfff-122">For example, suppose a semaphore has a maximum count of two, and that thread A and thread B both enter the semaphore.</span></span> <span data-ttu-id="bdfff-123">Jeśli to błąd programistyczny w wątku B powoduje go do wywołania `Release` dwa razy, zarówno wywołania powiodło się.</span><span class="sxs-lookup"><span data-stu-id="bdfff-123">If a programming error in thread B causes it to call  `Release` twice, both calls succeed.</span></span> <span data-ttu-id="bdfff-124">Licznik na semafora jest pełny i gdy wątku A ostatecznie wywołuje `Release`, <xref:System.Threading.SemaphoreFullException> jest generowany.</span><span class="sxs-lookup"><span data-stu-id="bdfff-124">The count on the semaphore is full, and when thread A eventually calls `Release`, a <xref:System.Threading.SemaphoreFullException> is thrown.</span></span>  
  
## <a name="named-semaphores"></a><span data-ttu-id="bdfff-125">Nazwane semaforów</span><span class="sxs-lookup"><span data-stu-id="bdfff-125">Named Semaphores</span></span>  
 <span data-ttu-id="bdfff-126">System operacyjny Windows umożliwia semaforów mieć nazwy.</span><span class="sxs-lookup"><span data-stu-id="bdfff-126">The Windows operating system allows semaphores to have names.</span></span> <span data-ttu-id="bdfff-127">Semafor o nazwie jest całym systemie.</span><span class="sxs-lookup"><span data-stu-id="bdfff-127">A named semaphore is system wide.</span></span> <span data-ttu-id="bdfff-128">Oznacza to, że po utworzeniu semafor o nazwie jest widoczne dla wszystkich wątków w wszystkich procesów.</span><span class="sxs-lookup"><span data-stu-id="bdfff-128">That is, once the named semaphore is created, it is visible to all threads in all processes.</span></span> <span data-ttu-id="bdfff-129">W związku z tym semafor o nazwie może służyć do synchronizowania działania procesów, a także wątków.</span><span class="sxs-lookup"><span data-stu-id="bdfff-129">Thus, named semaphore can be used to synchronize the activities of processes as well as threads.</span></span>  
  
 <span data-ttu-id="bdfff-130">Można utworzyć <xref:System.Threading.Semaphore> obiekt, który reprezentuje semafor o nazwie systemu za pomocą jednego z konstruktorów, które określa nazwę.</span><span class="sxs-lookup"><span data-stu-id="bdfff-130">You can create a <xref:System.Threading.Semaphore> object that represents a named system semaphore by using one of the constructors that specifies a name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdfff-131">Ponieważ nazwanego semaforów całym systemie, istnieje możliwość wielu <xref:System.Threading.Semaphore> semafor o nazwie obiekty reprezentujące takie same.</span><span class="sxs-lookup"><span data-stu-id="bdfff-131">Because named semaphores are system wide, it is possible to have multiple <xref:System.Threading.Semaphore> objects that represent the same named semaphore.</span></span> <span data-ttu-id="bdfff-132">Zawsze należy wywołać konstruktora lub <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType> metoda, nowy <xref:System.Threading.Semaphore> tworzony jest obiekt.</span><span class="sxs-lookup"><span data-stu-id="bdfff-132">Each time you call a constructor or the <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType> method, a new <xref:System.Threading.Semaphore> object is created.</span></span> <span data-ttu-id="bdfff-133">Określenie tej samej nazwie wielokrotnie tworzy wiele obiektów, które reprezentują tego samego semafor o nazwie.</span><span class="sxs-lookup"><span data-stu-id="bdfff-133">Specifying the same name repeatedly creates multiple objects that represent the same named semaphore.</span></span>  
  
 <span data-ttu-id="bdfff-134">Użyj semaforów nazwanego, należy zachować ostrożność.</span><span class="sxs-lookup"><span data-stu-id="bdfff-134">Be careful when you use named semaphores.</span></span> <span data-ttu-id="bdfff-135">Ponieważ są one całym systemie, inny proces, który używa tej samej nazwie można wprowadzić Twojej semafora nieoczekiwanie.</span><span class="sxs-lookup"><span data-stu-id="bdfff-135">Because they are system wide, another process that uses the same name can enter your semaphore unexpectedly.</span></span> <span data-ttu-id="bdfff-136">Złośliwy kod na tym samym komputerze może wykorzystać tę podstawę ataku typu "odmowa usługi".</span><span class="sxs-lookup"><span data-stu-id="bdfff-136">Malicious code executing on the same computer could use this as the basis of a denial-of-service attack.</span></span>  
  
 <span data-ttu-id="bdfff-137">Umożliwia kontrolę dostępu, aby chronić <xref:System.Threading.Semaphore> obiekt, który reprezentuje semafora nazwanego, najlepiej przy użyciu konstruktora, który określa <xref:System.Security.AccessControl.SemaphoreSecurity?displayProperty=nameWithType> obiektu.</span><span class="sxs-lookup"><span data-stu-id="bdfff-137">Use access control security to protect a <xref:System.Threading.Semaphore> object that represents a named semaphore, preferably by using a constructor that specifies a <xref:System.Security.AccessControl.SemaphoreSecurity?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="bdfff-138">Można także zastosować dla zabezpieczeń kontroli dostępu przy użyciu opcji <xref:System.Threading.Semaphore.SetAccessControl%2A?displayProperty=nameWithType> metody, ale pozostawia okno luki w zabezpieczeniach między semafora została utworzona, a czas jest chroniony.</span><span class="sxs-lookup"><span data-stu-id="bdfff-138">You can also apply access control security using the <xref:System.Threading.Semaphore.SetAccessControl%2A?displayProperty=nameWithType> method, but this leaves a window of vulnerability between the time the semaphore is created and the time it is protected.</span></span> <span data-ttu-id="bdfff-139">Ochrona semaforów za pomocą kontrolę dostępu pomaga zapobiegać złośliwe ataki, ale nie rozwiązuje problemu konflikty nazw przypadkowe.</span><span class="sxs-lookup"><span data-stu-id="bdfff-139">Protecting semaphores with access control security helps prevent malicious attacks, but does not solve the problem of unintentional name collisions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfff-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bdfff-140">See Also</span></span>  
 <xref:System.Threading.Semaphore>  
 <xref:System.Threading.SemaphoreSlim>  
 [<span data-ttu-id="bdfff-141">Wątkowość obiektów i funkcji</span><span class="sxs-lookup"><span data-stu-id="bdfff-141">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)