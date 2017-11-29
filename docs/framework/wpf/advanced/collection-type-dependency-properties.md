---
title: "Właściwości zależności typu kolekcji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11927efee2b8375550767d119e6b4a95b3ef7bd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="collection-type-dependency-properties"></a><span data-ttu-id="4de88-102">Właściwości zależności typu kolekcji</span><span class="sxs-lookup"><span data-stu-id="4de88-102">Collection-Type Dependency Properties</span></span>
<span data-ttu-id="4de88-103">Ten temat zawiera wskazówki i sugerowane wzorce dla implementowania właściwości zależności, których typ właściwości jest typem kolekcji.</span><span class="sxs-lookup"><span data-stu-id="4de88-103">This topic provides guidance and suggested patterns for how to implement a dependency property where the type of the property is a collection type.</span></span>  
  
 
  
<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a><span data-ttu-id="4de88-104">Implementowanie właściwości zależności typ kolekcji</span><span class="sxs-lookup"><span data-stu-id="4de88-104">Implementing a Collection-Type Dependency Property</span></span>  
 <span data-ttu-id="4de88-105">Dla właściwości zależności ogólnie rzecz biorąc, można wzorzec implementacji jest zdefiniowanie [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] otoki właściwości, których tej właściwości nie jest obsługiwana przez <xref:System.Windows.DependencyProperty> identyfikator zamiast pola lub innych konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="4de88-105">For a dependency property in general, the implementation pattern that you follow is that you define a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrapper, where that property is backed by a <xref:System.Windows.DependencyProperty> identifier rather than a field or other construct.</span></span> <span data-ttu-id="4de88-106">W przypadku użycia tego samego wzorca po implementować właściwość typu kolekcji.</span><span class="sxs-lookup"><span data-stu-id="4de88-106">You follow this same pattern when you implement a collection-type property.</span></span> <span data-ttu-id="4de88-107">Jednak właściwość typu kolekcji wprowadza pewne złożoności wzorzec zawsze, gdy typ, który jest zawarty w kolekcji jest <xref:System.Windows.DependencyObject> lub <xref:System.Windows.Freezable> klasy.</span><span class="sxs-lookup"><span data-stu-id="4de88-107">However, a collection-type property introduces some complexity to the pattern whenever the type that is contained within the collection is itself a <xref:System.Windows.DependencyObject> or <xref:System.Windows.Freezable> derived class.</span></span>  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a><span data-ttu-id="4de88-108">Inicjowanie zbierania ponad wartość domyślną</span><span class="sxs-lookup"><span data-stu-id="4de88-108">Initializing the Collection Beyond the Default Value</span></span>  
 <span data-ttu-id="4de88-109">Podczas tworzenia właściwości zależności nie określisz wartości domyślnej właściwości jako wartość początkowa pola.</span><span class="sxs-lookup"><span data-stu-id="4de88-109">When you create a dependency property, you do not specify the property default value as the initial field value.</span></span> <span data-ttu-id="4de88-110">Zamiast tego można określić wartość domyślną, za pomocą metadanych właściwości zależności.</span><span class="sxs-lookup"><span data-stu-id="4de88-110">Instead, you specify the default value through the dependency property metadata.</span></span> <span data-ttu-id="4de88-111">Jeśli Twoje właściwości jest typem referencyjnym, wartość domyślna określona w metadanych właściwości zależności nie jest wartość domyślną dla każdego wystąpienia; Zamiast tego jest wartość domyślna, która ma zastosowanie do wszystkich wystąpień tego typu.</span><span class="sxs-lookup"><span data-stu-id="4de88-111">If your property is a reference type, the default value specified in dependency property metadata is not a default value per instance; instead it is a default value that applies to all instances of the type.</span></span> <span data-ttu-id="4de88-112">W związku z tym należy zachować ostrożność, aby nie korzystać z pojedynczej kolekcji statycznych zdefiniowany przez metadane właściwości kolekcji pracy wartość domyślną dla nowo utworzonego wystąpienia danego typu.</span><span class="sxs-lookup"><span data-stu-id="4de88-112">Therefore you must be careful to not use the singular static collection defined by the collection property metadata as the working default value for newly created instances of your type.</span></span> <span data-ttu-id="4de88-113">Zamiast tego należy się upewnić, celowo ustaw wartość kolekcji do kolekcji unikatowy (wystąpieniem) jako część logiki konstruktora klasy.</span><span class="sxs-lookup"><span data-stu-id="4de88-113">Instead, you must make sure that you deliberately set the collection value to a unique (instance) collection as part of your class constructor logic.</span></span> <span data-ttu-id="4de88-114">W przeciwnym razie zostanie utworzony klasa pojedyncza przypadkowe.</span><span class="sxs-lookup"><span data-stu-id="4de88-114">Otherwise you will have created an unintentional singleton class.</span></span>  
  
 <span data-ttu-id="4de88-115">Rozważmy następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="4de88-115">Consider the following example.</span></span> <span data-ttu-id="4de88-116">W poniższej sekcji przykładzie przedstawiono definicję klasy `Aquarium`.</span><span class="sxs-lookup"><span data-stu-id="4de88-116">The following section of the example shows the definition for a class `Aquarium`.</span></span> <span data-ttu-id="4de88-117">Klasa definiuje właściwość zależności typu kolekcji `AquariumObjects`, ogólnego, który używa <xref:System.Collections.Generic.List%601> to typ <xref:System.Windows.FrameworkElement> ograniczenie typu.</span><span class="sxs-lookup"><span data-stu-id="4de88-117">The class defines the collection type dependency property `AquariumObjects`, which uses the generic <xref:System.Collections.Generic.List%601> type with a <xref:System.Windows.FrameworkElement> type constraint.</span></span> <span data-ttu-id="4de88-118">W <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> wywołania dla właściwości zależności metadanych ustanawia wartość domyślna ma być nowe ogólny <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="4de88-118">In the <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> call for the dependency property, the metadata establishes the default value to be a new generic <xref:System.Collections.Generic.List%601>.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 <span data-ttu-id="4de88-119">Jednak jeśli kod pozostanie tak jak pokazano tej wartości domyślne jedną listę jest współdzielona przez wszystkie wystąpienia `Aquarium`.</span><span class="sxs-lookup"><span data-stu-id="4de88-119">However, if you just left the code as shown, that single list default value is shared for all instances of `Aquarium`.</span></span> <span data-ttu-id="4de88-120">W przypadku uruchomienia następujący kod testu, który jest przeznaczony do wyświetlenia, jak może utworzyć wystąpienia dwa oddzielne `Aquarium` wystąpień i Dodaj jeden różnych `Fish` do każdego z nich, można zobaczyć zaskakująco wyników:</span><span class="sxs-lookup"><span data-stu-id="4de88-120">If you ran the following test code, which is intended to show how you would instantiate two separate `Aquarium` instances and add a single different `Fish` to each of them, you would see a surprising result:</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 <span data-ttu-id="4de88-121">Zamiast każdej kolekcji o licznik równy jeden Każda kolekcja ma licznika dwóch!</span><span class="sxs-lookup"><span data-stu-id="4de88-121">Instead of each collection having a count of one, each collection has a count of two!</span></span> <span data-ttu-id="4de88-122">Jest to spowodowane każdego `Aquarium` dodana jego `Fish` do kolekcji wartości domyślne, wynika z jednego konstruktora wywołanie w metadanych i dlatego jest współużytkowana przez wszystkie wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="4de88-122">This is because each `Aquarium` added its `Fish` to the default value collection, which resulted from a single constructor call in the metadata and is therefore shared between all instances.</span></span> <span data-ttu-id="4de88-123">Ta sytuacja jest prawie nigdy nie chcesz.</span><span class="sxs-lookup"><span data-stu-id="4de88-123">This situation is almost never what you want.</span></span>  
  
 <span data-ttu-id="4de88-124">Aby rozwiązać ten problem, należy zresetować wartość właściwości zależności kolekcji do unikatowego wystąpienia, jako część wywołania konstruktora klasy.</span><span class="sxs-lookup"><span data-stu-id="4de88-124">To correct this problem, you must reset the collection dependency property value to a unique instance, as part of the class constructor call.</span></span> <span data-ttu-id="4de88-125">Ponieważ ta właściwość jest właściwością tylko do odczytu zależności, użyj <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> metodę, aby ustawić, za pomocą <xref:System.Windows.DependencyPropertyKey> który jest dostępny tylko w klasie.</span><span class="sxs-lookup"><span data-stu-id="4de88-125">Because the property is a read-only dependency property, you use the <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> method to set it, using the <xref:System.Windows.DependencyPropertyKey> that is only accessible within the class.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 <span data-ttu-id="4de88-126">Teraz, po przeprowadzeniu, że sama ponownie testowania kodu, można zobaczyć więcej oczekiwanych rezultatów, gdzie każdy `Aquarium` obsługiwane unikatowych pobrania.</span><span class="sxs-lookup"><span data-stu-id="4de88-126">Now, if you ran that same test code again, you could see more expected results, where each `Aquarium` supported its own unique collection.</span></span>  
  
 <span data-ttu-id="4de88-127">Byłoby niewielkich zmian w tym wzorcu Jeśli zdecydujesz się na Twoje właściwości kolekcji można odczytu i zapisu.</span><span class="sxs-lookup"><span data-stu-id="4de88-127">There would be a slight variation on this pattern if you chose to have your collection property be read-write.</span></span> <span data-ttu-id="4de88-128">W takim przypadku należy wywołać metody dostępu publicznego zestawu z konstruktora w celu inicjowania, który będzie nadal wywoływania nonkey podpis <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> w ramach Twojej otoki zestawu przy użyciu publicznego <xref:System.Windows.DependencyProperty> identyfikator.</span><span class="sxs-lookup"><span data-stu-id="4de88-128">In that case, you could call the public set accessor from the constructor to do the initialization, which would still be calling the nonkey signature of <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> within your set wrapper, using a public <xref:System.Windows.DependencyProperty> identifier.</span></span>  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a><span data-ttu-id="4de88-129">Raportowanie powiązanie zmiany wartości z właściwości kolekcji</span><span class="sxs-lookup"><span data-stu-id="4de88-129">Reporting Binding Value Changes from Collection Properties</span></span>  
 <span data-ttu-id="4de88-130">Właściwości kolekcji, która jest elementem właściwości zależności nie raportuje automatycznie zmiany do właściwości podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="4de88-130">A collection property that is itself a dependency property does not automatically report changes to its subproperties.</span></span> <span data-ttu-id="4de88-131">W przypadku tworzenia powiązania w kolekcji, może to spowodować powiązania z raportowania zmian, w związku z tym unieważnia niektóre scenariusze powiązania danych.</span><span class="sxs-lookup"><span data-stu-id="4de88-131">If you are creating bindings into a collection, this can prevent the binding from reporting changes, thus invalidating some data binding scenarios.</span></span> <span data-ttu-id="4de88-132">Jednak jeśli używany jest typ kolekcji <xref:System.Windows.FreezableCollection%601> jako typ kolekcji, następnie zmiany podrzędnych zawartych w niej elementów w kolekcji są prawidłowo raportowane i powiązanie działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="4de88-132">However, if you use the collection type <xref:System.Windows.FreezableCollection%601> as your collection type, then subproperty changes to contained elements in the collection are properly reported, and binding works as expected.</span></span>  
  
 <span data-ttu-id="4de88-133">Aby włączyć podwłaściwości powiązania w kolekcji obiektów zależności, należy utworzyć jako typ właściwości kolekcji <xref:System.Windows.FreezableCollection%601>, z ograniczeniem typu dla tej kolekcji do dowolnego <xref:System.Windows.DependencyObject> klasy.</span><span class="sxs-lookup"><span data-stu-id="4de88-133">To enable subproperty binding in a dependency object collection, create the collection property as type <xref:System.Windows.FreezableCollection%601>, with a type constraint for that collection to any <xref:System.Windows.DependencyObject> derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de88-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4de88-134">See Also</span></span>  
 <xref:System.Windows.FreezableCollection%601>  
 [<span data-ttu-id="4de88-135">XAML oraz klas niestandardowych dla WPF</span><span class="sxs-lookup"><span data-stu-id="4de88-135">XAML and Custom Classes for WPF</span></span>](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="4de88-136">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="4de88-136">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="4de88-137">Przegląd właściwości zależności</span><span class="sxs-lookup"><span data-stu-id="4de88-137">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="4de88-138">Właściwości niestandardowe zależności</span><span class="sxs-lookup"><span data-stu-id="4de88-138">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="4de88-139">Metadane właściwości zależności</span><span class="sxs-lookup"><span data-stu-id="4de88-139">Dependency Property Metadata</span></span>](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)