---
title: Zasady architektury
description: Projektowania nowoczesnych aplikacji sieci Web platformy ASP.NET Core i Azure | Zasady architektury
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 20524c8aa0e64fd40a1a4a6811063557f74074d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
#<a name="architectural-principles"></a><span data-ttu-id="9ca5a-103">Zasady architektury</span><span class="sxs-lookup"><span data-stu-id="9ca5a-103">Architectural Principles</span></span>

> <span data-ttu-id="9ca5a-104">"Jeśli konstruktorów wbudowana budynków programistów sposób zapisano programy, a następnie woodpecker pierwszy, dostarczonej wraz z spowodowałoby zniszczenie cywilizacji."</span><span class="sxs-lookup"><span data-stu-id="9ca5a-104">"If builders built buildings the way programmers wrote programs, then the first woodpecker that came along would destroy civilization."</span></span>  
> <span data-ttu-id="9ca5a-105">_\-Jan Weinberg_</span><span class="sxs-lookup"><span data-stu-id="9ca5a-105">_\- Gerald Weinberg_</span></span>

## <a name="summary"></a><span data-ttu-id="9ca5a-106">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="9ca5a-106">Summary</span></span>

<span data-ttu-id="9ca5a-107">Należy zaprojektować i projektowania rozwiązań w zakresie oprogramowania z utrzymanie pamiętać.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-107">You should architect and design software solutions with maintainability in mind.</span></span> <span data-ttu-id="9ca5a-108">Zasady opisane w tej sekcji pomocne kierunku architektury decyzje, które będą powodować czystą, łatwy w obsłudze aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-108">The principles outlined in this section can help guide you toward architectural decisions that will result in clean, maintainable applications.</span></span> <span data-ttu-id="9ca5a-109">Ogólnie rzecz biorąc te zasady przeprowadzi Cię do tworzenia aplikacji poza odrębny składników, które nie są ściśle powiązane do innych części aplikacji, ale raczej komunikują się za pośrednictwem jawne interfejsy lub systemami wiadomości.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-109">Generally, these principles will guide you toward building applications out of discrete components that are not tightly coupled to other parts of your application, but rather communicate through explicit interfaces or messaging systems.</span></span>

## <a name="common-design-principles"></a><span data-ttu-id="9ca5a-110">Wspólne zasady projektowania</span><span class="sxs-lookup"><span data-stu-id="9ca5a-110">Common design principles</span></span>

### <a name="separation-of-concerns"></a><span data-ttu-id="9ca5a-111">Separacji</span><span class="sxs-lookup"><span data-stu-id="9ca5a-111">Separation of Concerns</span></span>

<span data-ttu-id="9ca5a-112">Jest wiodącą zasadę podczas opracowywania **separacji dotyczy**.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-112">A guiding principle when developing is **Separation of Concerns**.</span></span> <span data-ttu-id="9ca5a-113">Ta zasada potwierdza, powinny być oddzielone oprogramowania zależności od rodzaju pracy, którą wykonuje.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-113">This principle asserts that software should be separated based on the kinds of work it performs.</span></span> <span data-ttu-id="9ca5a-114">Załóżmy na przykład, aplikacji, która zawiera logikę do identyfikacji warte wymienienia elementów do wyświetlenia dla użytkownika, a które formatuje w określony sposób, aby były bardziej widoczne takie elementy.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-114">For instance, consider an application that includes logic for identifying noteworthy items to display to the user, and which formats such items in a particular way to make them more noticeable.</span></span> <span data-ttu-id="9ca5a-115">Zachowanie odpowiedzialny za wybierania elementów do formatu powinny być przechowywane oddzielnie od zachowania odpowiedzialny za formatowania elementów, ponieważ są one oddzielne zagadnienia są tylko przypadkowo ze sobą powiązane.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-115">The behavior responsible for choosing which items to format should be kept separate from the behavior responsible for formatting the items, since these are separate concerns that are only coincidentally related to one another.</span></span>

<span data-ttu-id="9ca5a-116">Pod względem architektury aplikacje mogą być logicznie wbudowane do wykonania tej zasady oddzielając zachowanie firm core z infrastruktury i użytkownika logikę interfejsu.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-116">Architecturally, applications can be logically built to follow this principle by separating core business behavior from infrastructure and user interface logic.</span></span> <span data-ttu-id="9ca5a-117">W idealnym przypadku reguł biznesowych i logiki powinien znajdować się w oddzielnych projektu, który nie należy uwzględniać inne projekty w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-117">Ideally, business rules and logic should reside in a separate project, which should not depend on other projects in the application.</span></span> <span data-ttu-id="9ca5a-118">Pomaga to zapewnić, że modelu biznesowego jest prosty do testowania i można rozwijać bez są ściśle powiązane szczegóły implementacji niskiego poziomu.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-118">This helps ensure that the business model is easy to test and can evolve without being tightly coupled to low-level implementation details.</span></span> <span data-ttu-id="9ca5a-119">Separacji kluczowa jest za korzystanie z warstw w architekturach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-119">Separation of concerns is a key consideration behind the use of layers in application architectures.</span></span>

### <a name="encapsulation"></a><span data-ttu-id="9ca5a-120">Hermetyzacja protokołu</span><span class="sxs-lookup"><span data-stu-id="9ca5a-120">Encapsulation</span></span>

<span data-ttu-id="9ca5a-121">Różne części aplikacji należy używać **hermetyzacji** aby ochronić ich z innymi częściami aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-121">Different parts of an application should use **encapsulation** to insulate them from other parts of the application.</span></span> <span data-ttu-id="9ca5a-122">Składniki aplikacji i warstwach powinno być możliwe dostosowanie ich wewnętrznej implementacji bez przerywania ich współpracownicy, dopóki nie naruszenia zamówień zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-122">Application components and layers should be able to adjust their internal implementation without breaking their collaborators as long as external contracts are not violated.</span></span> <span data-ttu-id="9ca5a-123">Właściwe korzystanie z hermetyzacji pomaga osiągnąć luźne powiązanie i Modułowość projektów aplikacji, ponieważ obiekty i pakietów można zastąpić alternatywnych implementacji tak długo, jak ten sam interfejs jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-123">Proper use of encapsulation helps achieve loose coupling and modularity in application designs, since objects and packages can be replaced with alternative implementations so long as the same interface is maintained.</span></span>

<span data-ttu-id="9ca5a-124">W klasach hermetyzacji uzyskuje się poprzez ograniczenie poza dostęp do wewnętrzny stan klasy.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-124">In classes, encapsulation is achieved by limiting outside access to the class's internal state.</span></span> <span data-ttu-id="9ca5a-125">Jeśli poza aktora chce manipulowania stan obiektu, go należy to zrobić za pośrednictwem funkcji dobrze zdefiniowany (lub metoda ustawiająca właściwości), zamiast bezpośredniego dostępu do prywatnego stan obiektu.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-125">If an outside actor wants to manipulate the state of the object, it should do so through a well-defined function (or property setter), rather than having direct access to the private state of the object.</span></span> <span data-ttu-id="9ca5a-126">Podobnie składniki aplikacji i same aplikacje powinny ujawniać dobrze zdefiniowanych interfejsów dla swoich współpracowników do użycia zamiast stosowanie ich stanie można zmodyfikować bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-126">Likewise, application components and applications themselves should expose well-defined interfaces for their collaborators to use, rather than allowing their state to be modified directly.</span></span> <span data-ttu-id="9ca5a-127">Dzięki temu aplikacja — projekt wewnętrzny podlegać ewolucji w czasie, nie martwiąc się, że to tak spowoduje przerwanie współpracownikom, tak długo, jak zamówień publicznych, które są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-127">This frees the application's internal design to evolve over time without worrying that doing so will break collaborators, so long as the public contracts are maintained.</span></span>

### <a name="dependency-inversion"></a><span data-ttu-id="9ca5a-128">Odwracanie zależności</span><span class="sxs-lookup"><span data-stu-id="9ca5a-128">Dependency Inversion</span></span>

<span data-ttu-id="9ca5a-129">Kierunek zależności aplikacji powinna być w kierunku abstrakcji, nie szczegóły implementacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-129">The direction of dependency within the application should be in the direction of abstraction, not implementation details.</span></span> <span data-ttu-id="9ca5a-130">Większość aplikacji są zapisywane w taki sposób, że zależności kompilacji przepływów w kierunku wykonywania środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-130">Most applications are written such that compile-time dependency flows in the direction of runtime execution.</span></span> <span data-ttu-id="9ca5a-131">To tworzy wykres zależności bezpośrednich.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-131">This produces a direct dependency graph.</span></span> <span data-ttu-id="9ca5a-132">Oznacza to jeśli moduł A wywołań w funkcji w module B, które wywołuje funkcję w module C, a następnie w momencie czasu A kompilacji są zależne od B, który będzie zależeć od C, jak pokazano w rysunek 4-1.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-132">That is, if module A calls a function in module B, which calls a function in module C, then at compile time A will depend on B which will depend on C, as shown in Figure 4-1.</span></span>

![](./media/image4-1.png)

<span data-ttu-id="9ca5a-133">**Rysunek 4-1.**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-133">**Figure 4-1.**</span></span> <span data-ttu-id="9ca5a-134">Wykres zależności bezpośrednich.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-134">Direct dependency graph.</span></span>

<span data-ttu-id="9ca5a-135">Zastosowanie zasady odwracanie zależności umożliwia A może wywołać metody abstrakcji, która implementuje B, umożliwiając a wywołania B w czasie wykonywania, ale b zależeć interfejs sterowane przez A w czasie kompilacji (w związku z tym *odwracanie* Typowy kompilacji zależności).</span><span class="sxs-lookup"><span data-stu-id="9ca5a-135">Applying the dependency inversion principle allows A to call methods on an abstraction that B implements, making it possible for A to call B at runtime, but for B to depend on an interface controlled by A at compile time (thus, *inverting* the typical compile-time dependency).</span></span> <span data-ttu-id="9ca5a-136">W czasie wykonywania przepływ wykonania programu nie zostanie zmienione, ale wprowadzenie interfejsy oznacza, że łatwo można podłączyć różnych implementacji tych interfejsów.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-136">At run time, the flow of program execution remains unchanged, but the introduction of interfaces means that different implementations of these interfaces can easily be plugged in.</span></span>

![](./media/image4-2.png)

<span data-ttu-id="9ca5a-137">**Rysunek 4-2.**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-137">**Figure 4-2.**</span></span> <span data-ttu-id="9ca5a-138">Wykres zależności odwrócony.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-138">Inverted dependency graph.</span></span>

<span data-ttu-id="9ca5a-139">**Odwracanie zależności** jest kluczowym elementem tworzenia luźno połączonych aplikacji, ponieważ szczegóły implementacji mogą być zapisywane są zależne od i wdrożenie nowszej abstrakcje poziomu, a nie odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-139">**Dependency inversion** is a key part of building loosely-coupled applications, since implementation details can be written to depend on and implement higher level abstractions, rather than the other way around.</span></span> <span data-ttu-id="9ca5a-140">Wynikowa aplikacje są w związku z tym testować, moduły i łatwy w obsłudze.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-140">The resulting applications are more testable, modular, and maintainable as a result.</span></span> <span data-ttu-id="9ca5a-141">Rozwiązanie polegające na *iniekcji zależności* jest możliwe dzięki zgodnie z zasadą odwracanie zależności.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-141">The practice of *dependency injection* is made possible by following the dependency inversion principle.</span></span>

### <a name="explicit-dependencies"></a><span data-ttu-id="9ca5a-142">Jawne zależności</span><span class="sxs-lookup"><span data-stu-id="9ca5a-142">Explicit Dependencies</span></span>

<span data-ttu-id="9ca5a-143">**Klasy i metody jawnie należy włączyć wszystkie brać obiekty, które są im niezbędne do poprawnego działania.**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-143">**Methods and classes should explicitly require any collaborating objects they need in order to function correctly.**</span></span> <span data-ttu-id="9ca5a-144">Konstruktory klas możliwość klas zidentyfikować elementy, które są im potrzebne, aby mogła być w nieprawidłowym stanie i działać prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-144">Class constructors provide an opportunity for classes to identify the things they need in order to be in a valid state and to function properly.</span></span> <span data-ttu-id="9ca5a-145">Po zdefiniowaniu klasy, która konstruowane i o nazwie, ale który będzie działać tylko prawidłowo w przypadku niektórych składników infrastruktury lub globalnych w miejscu tych klas są *nieuczciwych* z klientów.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-145">If you define classes that can be constructed and called, but which will only function properly if certain global or infrastructure components are in place, these classes are being *dishonest* with their clients.</span></span> <span data-ttu-id="9ca5a-146">Kontrakt konstruktora informuje klienta, który wymaga tylko określone czynności (prawdopodobnie pusta, jeśli klasa jest tylko za pomocą konstruktora domyślnego), ale, a następnie w czasie wykonywania, który okaże się obiekt naprawdę prawdopodobnie potrzebował coś innego.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-146">The constructor contract is telling the client that it only needs the things specified (possibly nothing if the class is just using a default constructor), but then at runtime it turns out the object really did need something else.</span></span>

<span data-ttu-id="9ca5a-147">Wykonując zasady jawne zależności z klasy i metody są uczciwymi z klientów o to, czego szukają prawidłowego działania.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-147">By following the explicit dependencies principle, your classes and methods are being honest with their clients about what they need in order to function.</span></span> <span data-ttu-id="9ca5a-148">Dzięki temu kodu więcej pomocniczy i kodowania umów bardziej przyjazny dla użytkownika, ponieważ użytkownicy będą zaufania, który tak długo, jak udostępniają one, co jest wymagane w formularzu metodę lub parametrami konstruktora, obiekty, które pracują z będą zachowywać się poprawnie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-148">This makes your code more self-documenting and your coding contracts more user-friendly, since users will come to trust that as long as they provide what's required in the form of method or constructor parameters, the objects they're working with will behave correctly at runtime.</span></span>

### <a name="single-responsibility"></a><span data-ttu-id="9ca5a-149">Pojedynczy odpowiedzialności</span><span class="sxs-lookup"><span data-stu-id="9ca5a-149">Single Responsibility</span></span>

<span data-ttu-id="9ca5a-150">Zasady odpowiedzialności pojedynczego dotyczy obiektowego, ale również mogą być uważane za podobne do separacji zasady architektury.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-150">The single responsibility principle applies to object-oriented design, but can also be considered as an architectural principle similar to separation of concerns.</span></span> <span data-ttu-id="9ca5a-151">Stany go, że obiekty muszą mieć tylko jeden odpowiedzialność i powinny mieć tylko jedną z przyczyn można zmienić.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-151">It states that objects should have only one responsibility and that they should have only one reason to change.</span></span> <span data-ttu-id="9ca5a-152">Tylko sytuacji, w której należy zmienić obiekt jest w szczególności jeśli musisz zaktualizować sposób, w której wykonuje jej odpowiedzialność jeden.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-152">Specifically, the only situation in which the object should change is if the manner in which it performs its one responsibility must be updated.</span></span> <span data-ttu-id="9ca5a-153">Po tej zasady pozwala tworzyć więcej luźno połączonych i moduły systemów, ponieważ wiele rodzajów nowe zachowanie może być zaimplementowany jako nowe klasy, a nie przez dodanie dodatkowych odpowiedzialność na istniejących klas.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-153">Following this principle helps to produce more loosely-coupled and modular systems, since many kinds of new behavior can be implemented as new classes, rather than by adding additional responsibility to existing classes.</span></span> <span data-ttu-id="9ca5a-154">Dodanie nowych klas jest bezpieczniejsze niż zmiana istniejących klas, ponieważ żaden kod jeszcze zależy od nowych klas.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-154">Adding new classes is always safer than changing existing classes, since no code yet depends on the new classes.</span></span>

<span data-ttu-id="9ca5a-155">W aplikacji wbudowanymi firma Microsoft może dotyczyć zasady pojedynczego odpowiedzialność na wysokim poziomie warstw w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-155">In a monolithic application, we can apply the single responsibility principle at a high level to the layers in the application.</span></span> <span data-ttu-id="9ca5a-156">Odpowiedzialność prezentacji może pozostawać w projekcie interfejsu użytkownika, podczas dostępu do danych odpowiedzialność powinny być przechowywane w ramach projektu infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-156">Presentation responsibility should remain in the UI project, while data access responsibility should be kept within an infrastructure project.</span></span> <span data-ttu-id="9ca5a-157">Logika biznesowa powinna być przechowywana w core projekt aplikacji, których można łatwo przetestować i można rozwijać, niezależnie od innych obowiązków.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-157">Business logic should be kept in the application core project, where it can be easily tested and can evolve independently from other responsibilities.</span></span>

<span data-ttu-id="9ca5a-158">Podczas tej zasady jest stosowany do architektury aplikacji i Przekierowanie do punktu końcowego logiczne, otrzymasz mikrousług.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-158">When this principle is applied to application architecture, and taken to its logical endpoint, you get microservices.</span></span> <span data-ttu-id="9ca5a-159">Danego mikrousługi powinien mieć pojedynczy odpowiedzialności.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-159">A given microservice should have a single responsibility.</span></span> <span data-ttu-id="9ca5a-160">Jeśli chcesz rozszerzyć zachowanie systemu, zazwyczaj lepiej jest to zrobić przez dodanie dodatkowych mikrousług, a nie przez dodanie odpowiedzialność do istniejącego.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-160">If you need to extend the behavior of a system, it's usually better to do it by adding additional microservices, rather than by adding responsibility to an existing one.</span></span>

[<span data-ttu-id="9ca5a-161">Dowiedz się więcej o architekturze mikrousług</span><span class="sxs-lookup"><span data-stu-id="9ca5a-161">Learn more about microservices architecture</span></span>](http://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a><span data-ttu-id="9ca5a-162">Nie powtarzaj samodzielnie (suchej)</span><span class="sxs-lookup"><span data-stu-id="9ca5a-162">Don't Repeat Yourself (DRY)</span></span>

<span data-ttu-id="9ca5a-163">Aplikacji należy unikać, określając zachowanie związane z określonym koncepcji w kilku miejscach, jak jest to często źródła błędów.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-163">The application should avoid specifying behavior related to a particular concept in multiple places as this is a frequent source of errors.</span></span> <span data-ttu-id="9ca5a-164">W pewnym momencie zmiany wymagań dotyczących wymaga zmiany tego zachowania oraz prawdopodobieństwo, że co najmniej jedno wystąpienie zachowania zakończy się niepowodzeniem, należy zaktualizować spowoduje niespójne działanie systemu.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-164">At some point, a change in requirements will require changing this behavior and the likelihood that at least one instance of the behavior will fail to be updated will result in inconsistent behavior of the system.</span></span>

<span data-ttu-id="9ca5a-165">Zamiast duplikowania logiki, hermetyzować go w konstrukcji programowania.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-165">Rather than duplicating logic, encapsulate it in a programming construct.</span></span> <span data-ttu-id="9ca5a-166">Uczyń tę konstruowania pojedynczego urzędu za pośrednictwem tego zachowania, i mieć dowolną część aplikacji, która wymaga użycia tego zachowania nową konstrukcję.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-166">Make this construct the single authority over this behavior, and have any other part of the application that requires this behavior use the new construct.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca5a-167">Unikaj powiązanie ze sobą zachowanie tylko przypadkowo powtarzających się.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-167">Avoid binding together behavior that is only coincidentally repetitive.</span></span> <span data-ttu-id="9ca5a-168">Na przykład wyłącznie z powodu dwóch różnych stałe zarówno mają taką samą wartość, która nie oznacza powinien mieć tylko jedną stałą, jeśli koncepcyjnie odnoszą się różne.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-168">For example, just because two different constants both have the same value, that doesn't mean you should have only one constant, if conceptually they're referring to different things.</span></span>

### <a name="persistence-ignorance"></a><span data-ttu-id="9ca5a-169">Nieznajomości trwałości</span><span class="sxs-lookup"><span data-stu-id="9ca5a-169">Persistence Ignorance</span></span>

<span data-ttu-id="9ca5a-170">**Trwałość nieznajomości** (PI) odwołuje się do typów, które mają zostać utrwalony, którego kod jest poza zasięgiem Wybór technologii trwałości.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-170">**Persistence ignorance** (PI) refers to types that need to be persisted, but whose code is unaffected by the choice of persistence technology.</span></span> <span data-ttu-id="9ca5a-171">Takie typy w programie .NET są czasami określane jako zwykły stare obiekty CLR (POCOs), ponieważ nie muszą dziedziczyć konkretnej klasy podstawowej ani nie implementuje danego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-171">Such types in .NET are sometimes referred to as Plain Old CLR Objects (POCOs), because they do not need to inherit from a particular base class or implement a particular interface.</span></span> <span data-ttu-id="9ca5a-172">Nieznajomości trwałości jest przydatne, ponieważ zezwala ona na ten sam model firm utrwalenia na wiele sposobów, oferty dodatkowa elastyczność w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-172">Persistence ignorance is valuable because it allows the same business model to be persisted in multiple ways, offering additional flexibility to the application.</span></span> <span data-ttu-id="9ca5a-173">Opcji trwałości mogą ulec zmianie w czasie z technologii jedną bazę danych do innego, lub dodatkowych metod trwałości mogą być wymagane, oprócz niezależnie od uruchomienia z aplikacji (na przykład przy użyciu pamięci podręcznej Redis lub usługi Azure DocumentDb oprócz relacyjna baza danych).</span><span class="sxs-lookup"><span data-stu-id="9ca5a-173">Persistence choices might change over time, from one database technology to another, or additional forms of persistence might be required in addition to whatever the application started with (for example, using a Redis cache or Azure DocumentDb in addition to a relational database).</span></span>

<span data-ttu-id="9ca5a-174">Przykładem naruszenia tej zasady obejmują:</span><span class="sxs-lookup"><span data-stu-id="9ca5a-174">Some examples of violations of this principle include:</span></span>

-   <span data-ttu-id="9ca5a-175">Wymagane klasy podstawowej</span><span class="sxs-lookup"><span data-stu-id="9ca5a-175">A required base class</span></span>

-   <span data-ttu-id="9ca5a-176">Implementacji wymaganego interfejsu</span><span class="sxs-lookup"><span data-stu-id="9ca5a-176">A required interface implementation</span></span>

-   <span data-ttu-id="9ca5a-177">Klasy odpowiedzialne za zapisywanie się (na przykład wzorzec aktywnym rekordzie)</span><span class="sxs-lookup"><span data-stu-id="9ca5a-177">Classes responsible for saving themselves (such as the Active Record pattern)</span></span>

-   <span data-ttu-id="9ca5a-178">Wymagane domyślnego konstruktora</span><span class="sxs-lookup"><span data-stu-id="9ca5a-178">Required default constructor</span></span>

-   <span data-ttu-id="9ca5a-179">Właściwości wymagających virtual — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="9ca5a-179">Properties requiring virtual keyword</span></span>

-   <span data-ttu-id="9ca5a-180">Specyficzne dla trwałości wymaganych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-180">Persistence-specific required attributes</span></span>

<span data-ttu-id="9ca5a-181">To wymaganie, że klasy nie ma żadnej z powyższych funkcji lub zachowania dodaje sprzężenia między typami utrwalenia i wybór technologii trwałości, co utrudnia przyjęcie nowych strategii dostępu do danych w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-181">The requirement that classes have any of the above features or behaviors adds coupling between the types to be persisted and the choice of persistence technology, making it more difficult to adopt new data access strategies in the future.</span></span>

### <a name="bounded-contexts"></a><span data-ttu-id="9ca5a-182">Konteksty ograniczonego</span><span class="sxs-lookup"><span data-stu-id="9ca5a-182">Bounded Contexts</span></span>

<span data-ttu-id="9ca5a-183">**Ograniczone kontekstów** są centralnej wzorzec projektowania Domain-Driven.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-183">**Bounded contexts** are a central pattern in Domain-Driven Design.</span></span> <span data-ttu-id="9ca5a-184">Umożliwiają realizowanie złożoności w dużych aplikacji lub organizacje przez podzielenie go na oddzielnych modułów koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-184">They provide a way of tackling complexity in large applications or organizations by breaking it up into separate conceptual modules.</span></span> <span data-ttu-id="9ca5a-185">Każdy moduł koncepcyjnej następnie reprezentuje kontekst, który jest oddzielona od innych kontekstach (w związku z tym ograniczone) i można rozwijać niezależnie.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-185">Each conceptual module then represents a context which is separated from other contexts (hence, bounded), and can evolve independently.</span></span> <span data-ttu-id="9ca5a-186">Każdy kontekst ograniczonego w idealnym przypadku należy wybrać własne nazwy dla pojęcia znajdujące się w nim, a powinien mieć wyłącznego dostępu do magazynu trwałości.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-186">Each bounded context should ideally be free to choose its own names for concepts within it, and should have exclusive access to its own persistence store.</span></span>

<span data-ttu-id="9ca5a-187">Co najmniej aplikacji sieci web poszczególnych powinien starań, aby mieć własne ograniczonego kontekstu, za pomocą ich własnych magazynu trwałości dla swojego modelu biznesowego, a nie z innych aplikacji do udostępniania bazy danych.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-187">At a minimum, individual web applications should strive to be their own bounded context, with their own persistence store for their business model, rather than sharing a database with other applications.</span></span> <span data-ttu-id="9ca5a-188">Komunikacja między kontekstami ograniczonego następuje za pośrednictwem interfejsów programistycznych, a nie za pomocą udostępnionej bazy danych, dzięki czemu do obsługi logiki biznesowej i zdarzenia podjęcie umieścić w odpowiedzi na zmiany, które mają miejsce.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-188">Communication between bounded contexts occurs through programmatic interfaces, rather than through a shared database, which allows for business logic and events to take place in response to changes that take place.</span></span> <span data-ttu-id="9ca5a-189">Ściśle ograniczone kontekstów mapy do mikrousług, który również w idealnym przypadku są zaimplementowane jako własne poszczególnych kontekstów ograniczone.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-189">Bounded contexts map closely to microservices, which also are ideally implemented as their own individual bounded contexts.</span></span>

> ### <a name="references--modern-web-applications"></a><span data-ttu-id="9ca5a-190">Odwołania — nowoczesnych aplikacji sieci Web</span><span class="sxs-lookup"><span data-stu-id="9ca5a-190">References – Modern Web Applications</span></span>
> - <span data-ttu-id="9ca5a-191">**Separacji**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-191">**Separation of Concerns**</span></span>  
> <span data-ttu-id="9ca5a-192"><http://deviq.com/separation-of-concerns/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-192"><http://deviq.com/separation-of-concerns/></span></span>
> - <span data-ttu-id="9ca5a-193">**Hermetyzacja** <http://deviq.com/encapsulation/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-193">**Encapsulation** <http://deviq.com/encapsulation/></span></span>
> - <span data-ttu-id="9ca5a-194">**Zasada odwracanie zależności**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-194">**Dependency Inversion Principle**</span></span>  
> <span data-ttu-id="9ca5a-195"><http://deviq.com/Dependency-Inversion-principle/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-195"><http://deviq.com/dependency-inversion-principle/></span></span>
> - <span data-ttu-id="9ca5a-196">**Zasada jawne zależności**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-196">**Explicit Dependencies Principle**</span></span>  
> <span data-ttu-id="9ca5a-197"><http://deviq.com/Explicit-Dependencies-principle/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-197"><http://deviq.com/explicit-dependencies-principle/></span></span>
> - <span data-ttu-id="9ca5a-198">**Nie powtarzaj samodzielnie**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-198">**Don't Repeat Yourself**</span></span>  
> <span data-ttu-id="9ca5a-199"><http://deviq.com/Don-t-REPEAT-yourself/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-199"><http://deviq.com/don-t-repeat-yourself/></span></span>
> - <span data-ttu-id="9ca5a-200">**Nieznajomości trwałości**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-200">**Persistence Ignorance**</span></span>  
> <span data-ttu-id="9ca5a-201"><http://deviq.com/persistence-ignorance/></span><span class="sxs-lookup"><span data-stu-id="9ca5a-201"><http://deviq.com/persistence-ignorance/></span></span>
> - <span data-ttu-id="9ca5a-202">**Kontekst ograniczonego**</span><span class="sxs-lookup"><span data-stu-id="9ca5a-202">**Bounded Context**</span></span>  
> <span data-ttu-id="9ca5a-203"><https://martinfowler.com/bliki/BoundedContext.HTML></span><span class="sxs-lookup"><span data-stu-id="9ca5a-203"><https://martinfowler.com/bliki/BoundedContext.html></span></span>

> [!div class="step-by-step"]
<span data-ttu-id="9ca5a-204">[Poprzednie] (choose-between-traditional-web-and-single-page-apps.md) [dalej] (typowe web aplikacji architectures.md)</span><span class="sxs-lookup"><span data-stu-id="9ca5a-204">[Previous] (choose-between-traditional-web-and-single-page-apps.md) [Next] (common-web-application-architectures.md)</span></span>