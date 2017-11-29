---
title: "DateTime — Składnia XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e261018e6c7b9fea9ad449c5e92a131df40807
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="65119-102">DateTime — Składnia XAML</span><span class="sxs-lookup"><span data-stu-id="65119-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="65119-103">Niektóre formanty, takie jak <xref:System.Windows.Controls.Calendar> i <xref:System.Windows.Controls.DatePicker>, właściwości, które używają <xref:System.DateTime> typu.</span><span class="sxs-lookup"><span data-stu-id="65119-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="65119-104">Mimo że początkowej daty lub godziny dla tych kontrolek zazwyczaj określić w kodem w czasie wykonywania, można określić początkowej daty lub godziny w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="65119-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="65119-105">WPF XAML parser obsługuje analizowania <xref:System.DateTime> wartości przy użyciu składni wbudowanego tekstu XAML.</span><span class="sxs-lookup"><span data-stu-id="65119-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="65119-106">W tym temacie opisano specyfice <xref:System.DateTime> składni tekstu XAML.</span><span class="sxs-lookup"><span data-stu-id="65119-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="65119-107">Kiedy należy używać składni języka XAML daty i godziny</span><span class="sxs-lookup"><span data-stu-id="65119-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="65119-108">Ustawienie daty w języku XAML nie zawsze jest konieczne i może nawet być niepożądane.</span><span class="sxs-lookup"><span data-stu-id="65119-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="65119-109">Na przykład można użyć <xref:System.DateTime.Now%2A?displayProperty=nameWithType> właściwość w celu zainicjowania datę w czasie wykonywania, lub wykonaj wszystkie zmiany daty kalendarza w kodem oparte na danych wejściowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="65119-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="65119-110">Istnieją jednak scenariusze, w których warto dat kodowane w <xref:System.Windows.Controls.Calendar> i <xref:System.Windows.Controls.DatePicker> w szablonie formantu.</span><span class="sxs-lookup"><span data-stu-id="65119-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="65119-111"><xref:System.DateTime> Do tych scenariuszy należy użyć składni języka XAML.</span><span class="sxs-lookup"><span data-stu-id="65119-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="65119-112">Składnia XAML DateTime jest zachowanie natywnego</span><span class="sxs-lookup"><span data-stu-id="65119-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="65119-113"><xref:System.DateTime>jest klasa, która jest zdefiniowana w klasie podstawowej bibliotekach środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="65119-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="65119-114">Z powodu jak biblioteki klasy podstawowej są powiązane z resztą środowiska CLR, nie jest możliwa do stosowania <xref:System.ComponentModel.TypeConverterAttribute> klasy i użycia konwertera typu, aby przetworzyć ciągów z XAML i przekonwertować je na <xref:System.DateTime> w modelu obiektów czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="65119-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="65119-115">Brak nie `DateTimeConverter` klasy zapewnia zachowanie konwersji; macierzysty analizator WPF XAML zachowanie konwersji opisanych w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="65119-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="65119-116">Ciągi formatujące składnię daty/godziny XAML</span><span class="sxs-lookup"><span data-stu-id="65119-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="65119-117">Można określić format <xref:System.DateTime> zawierające ciąg formatu.</span><span class="sxs-lookup"><span data-stu-id="65119-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="65119-118">Ciągi formatujące formalnego składni tekst, który może służyć do tworzenia wartości.</span><span class="sxs-lookup"><span data-stu-id="65119-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="65119-119"><xref:System.DateTime>wartości dla istniejącego WPF steruje użyciem zwykle tylko składniki daty <xref:System.DateTime> i nie składniki czasu.</span><span class="sxs-lookup"><span data-stu-id="65119-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="65119-120">Podczas określania <xref:System.DateTime> w języku XAML, będzie można użyć dowolnego z ciągi formatujące zamiennie.</span><span class="sxs-lookup"><span data-stu-id="65119-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="65119-121">Można również użyć formaty i ciągi formatów, które nie są pokazywane w szczególności w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="65119-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="65119-122">Z technicznego punktu widzenia XAML dla każdego <xref:System.DateTime> wartość, która jest określona, a następnie przeanalizować przez parser WPF XAML używa wewnętrznego wywołanie <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, w związku z tym można użyć dowolnego ciągu zaakceptowane przez <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> dla XAML z danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="65119-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="65119-123">Aby uzyskać więcej informacji, zobacz <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65119-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65119-124">Zawsze używa składni języka XAML DateTime `en-us` jako <xref:System.Globalization.CultureInfo> jego natywnego konwersji.</span><span class="sxs-lookup"><span data-stu-id="65119-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="65119-125">Nie jest to wpływu na <xref:System.Windows.FrameworkElement.Language%2A> wartość lub `xml:lang` wartość w języku XAML, ponieważ konwersja poziom atrybutu typu XAML działa bez tego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="65119-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="65119-126">Nie należy próbować interpolować ciągi formatujące pokazane z powodu zmian kultury, takie jak kolejność dnia i miesiąca.</span><span class="sxs-lookup"><span data-stu-id="65119-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="65119-127">Ciągi formatujące pokazane są ciągami dokładnego formatu, używany podczas analizowania kodu w języku XAML, niezależnie od innych ustawień kultury.</span><span class="sxs-lookup"><span data-stu-id="65119-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="65119-128">W poniższych sekcjach opisano niektóre typowe <xref:System.DateTime> ciągi formatujące.</span><span class="sxs-lookup"><span data-stu-id="65119-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="65119-129">Wzorzec krótkiej daty ("d")</span><span class="sxs-lookup"><span data-stu-id="65119-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="65119-130">Poniżej pokazano format daty krótkiej <xref:System.DateTime> w języku XAML:</span><span class="sxs-lookup"><span data-stu-id="65119-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="65119-131">Jest to najprostsza forma, który określa wszystkie informacje niezbędne dla typowego użycia za pomocą formantów WPF i nie może zależeć od przesunięcia przypadkowemu strefy czasowej, a składnik czasu i dlatego zaleca się w innych formatach.</span><span class="sxs-lookup"><span data-stu-id="65119-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="65119-132">Na przykład aby określić datę 1 czerwca 2010, należy użyć następujący ciąg:</span><span class="sxs-lookup"><span data-stu-id="65119-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="65119-133">Aby uzyskać więcej informacji, zobacz <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65119-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="65119-134">Sortowanie wzorzec DateTime ("s")</span><span class="sxs-lookup"><span data-stu-id="65119-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="65119-135">Poniżej pokazano umożliwiający sortowanie <xref:System.DateTime> wzorca w języku XAML:</span><span class="sxs-lookup"><span data-stu-id="65119-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="65119-136">Na przykład aby określić datę 1 czerwca 2010, należy użyć następującego ciągu (czas, które składniki są wprowadzane jako 0):</span><span class="sxs-lookup"><span data-stu-id="65119-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="65119-137">Wzorzec RFC1123 ("r")</span><span class="sxs-lookup"><span data-stu-id="65119-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="65119-138">Wzorzec RFC1123 jest przydatne, ponieważ może to być ciąg na wejściu z innych generatory date, również korzystających ze wzorca RFC1123 przyczyn Niezmienna kultura.</span><span class="sxs-lookup"><span data-stu-id="65119-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="65119-139">Poniżej pokazano RFC1123 <xref:System.DateTime> wzorca w języku XAML:</span><span class="sxs-lookup"><span data-stu-id="65119-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="65119-140">Na przykład aby określić datę 1 czerwca 2010, należy użyć następującego ciągu (czas, które składniki są wprowadzane jako 0):</span><span class="sxs-lookup"><span data-stu-id="65119-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="65119-141">Inne formaty i wzorce</span><span class="sxs-lookup"><span data-stu-id="65119-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="65119-142">Jak wspomniano wcześniej, <xref:System.DateTime> w języku XAML może być określona jako dowolny ciąg, który jest dopuszczalna jako wejściowe dla <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65119-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65119-143">Dotyczy to również inne formaty formalny (na przykład <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) i formatów, które nie są sformalizowane jako określonego <xref:System.Globalization.DateTimeFormatInfo> formularza.</span><span class="sxs-lookup"><span data-stu-id="65119-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="65119-144">Na przykład formularz `YYYY/mm/dd` jest dopuszczalna jako wejściowe dla <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65119-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65119-145">W tym temacie podjęto próby opisania wszystkich możliwych formatów, które będzie działać, a zamiast tego zaleca wzorzec krótkiej daty jako standardowe rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="65119-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65119-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65119-146">See Also</span></span>  
 [<span data-ttu-id="65119-147">Omówienie XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="65119-147">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)