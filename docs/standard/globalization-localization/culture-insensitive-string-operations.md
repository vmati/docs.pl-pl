---
title: "Niezależne od kultury operacje na ciągach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dddd46dc5d825738dd9d5038ae573910122953c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="19801-102">Niezależne od kultury operacje na ciągach</span><span class="sxs-lookup"><span data-stu-id="19801-102">Culture-Insensitive String Operations</span></span>
<span data-ttu-id="19801-103">Operacje na ciągach, w których jest uwzględniana kultura, mogą okazać się przydatne w przypadku tworzenia aplikacji, które mają wyświetlać wyniki użytkownikom na podstawie kultury.</span><span class="sxs-lookup"><span data-stu-id="19801-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="19801-104">Domyślnie zależne od kultury metod uzyskania kultura używana z <xref:System.Globalization.CultureInfo.CurrentCulture%2A> właściwości bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="19801-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>  
  
 <span data-ttu-id="19801-105">Należy zauważyć, że operacje na ciągach, w których jest uwzględniana kultura, nie zawsze są pożądanym zachowaniem.</span><span class="sxs-lookup"><span data-stu-id="19801-105">Note that culture-sensitive string operations are not always the desired behavior.</span></span> <span data-ttu-id="19801-106">Używanie operacji, w których jest uwzględniana kultura, gdy wyniki powinny być niezależne od kultury, może spowodować, że kod aplikacji przestanie działać w przypadku kultur z niestandardowymi mapowaniami wielkości liter i regułami sortowania.</span><span class="sxs-lookup"><span data-stu-id="19801-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="19801-107">Na przykład, zobacz sekcję "Ciąg porównania który Użyj bieżącej kultury" w [najlepsze rozwiązania dotyczące ciągów za pomocą](../../../docs/standard/base-types/best-practices-strings.md) artykułu.</span><span class="sxs-lookup"><span data-stu-id="19801-107">For an example, see the "String Comparisons that Use the Current Culture" section in the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article.</span></span>  
  
 <span data-ttu-id="19801-108">To, czy w operacjach na ciągach powinna być uwzględniana kultura, zależy od tego, jak aplikacja używa wyników.</span><span class="sxs-lookup"><span data-stu-id="19801-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="19801-109">W operacjach na ciągach, które wyświetlają wyniki użytkownikowi, zazwyczaj powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="19801-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="19801-110">Na przykład jeśli aplikacja wyświetla posortowaną listę zlokalizowanych ciągów w polu listy, aplikacja powinna wykonać sortowanie z uwzględnieniem kultury.</span><span class="sxs-lookup"><span data-stu-id="19801-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>  
  
 <span data-ttu-id="19801-111">W wynikach operacji na ciągach, które są używane wewnętrznie, zazwyczaj nie powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="19801-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="19801-112">Ogólnie, jeśli aplikacja wykonuje operacje na nazwach plików, formatach trwałości lub informacjach symbolicznych, które nie są wyświetlane użytkownikowi, wyniki operacji na ciągach nie powinny ulegać zmianie w zależności od kultury.</span><span class="sxs-lookup"><span data-stu-id="19801-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="19801-113">Na przykład jeśli aplikacja porównuje ciąg w celu ustalenia, czy jest on rozpoznawanym tagiem XML, w porównaniu nie powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="19801-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="19801-114">Ponadto jeśli decyzja zabezpieczeń jest oparta na wynik operacji zmiany porównania lub w przypadku ciągu, operacja powinna być niezależne od kultury aby upewnić się, że wynik nie ma wpływu na wartość <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span><span class="sxs-lookup"><span data-stu-id="19801-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>  
  
 <span data-ttu-id="19801-115">Bez względu na to, czy jest tworzona aplikacja zawierająca kod służący do obsługi problemów lokalizacji i globalizacji, należy pamiętać o metodach programu .NET Framework pobierających domyślnie wyniki, w których jest uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="19801-115">Whether or not you are developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET Framework methods that retrieve culture-sensitive results by default.</span></span> <span data-ttu-id="19801-116">Celem tego tematu jest zilustrowanie prawidłowego sposobu używania tych metod w aplikacjach w celu uzyskania wyników, w których nie jest uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="19801-116">The purpose of this topic is to illustrate the correct way for your applications to use these methods to obtain culture-insensitive results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19801-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="19801-117">See Also</span></span>  
 [<span data-ttu-id="19801-118">Lokalizacja i globalizacja</span><span class="sxs-lookup"><span data-stu-id="19801-118">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)