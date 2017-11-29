---
title: "LINQ do obiektów (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bb2a6593b02125478f2221a6822dec447921c4f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="8be73-102">LINQ do obiektów (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="8be73-103">Termin "LINQ do obiektów" odwołuje się do korzystania z LINQ zapytania ze wszystkimi <xref:System.Collections.IEnumerable> lub <xref:System.Collections.Generic.IEnumerable%601> kolekcji bezpośrednio, bez użycia pośredniego dostawcy LINQ lub interfejsu API, takich jak [LINQ do SQL](https://msdn.microsoft.com/library/bb386976) lub [LINQ do XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="8be73-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="8be73-104">Użyj rozszerzenia LINQ, takich jak zbadać wszystkie kolekcje wyliczalny <xref:System.Collections.Generic.List%601>, <xref:System.Array>, lub <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="8be73-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="8be73-105">Kolekcja może być zdefiniowana przez użytkownika lub mogą być zwrócone przez interfejs API programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8be73-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="8be73-106">W tym sensie podstawowe LINQ do obiektów reprezentuje nowe podejście do kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8be73-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="8be73-107">W ten sposób stare, trzeba było zapisać złożonych `foreach` pętle określonych sposobu pobierania danych z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8be73-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="8be73-108">W ujęciu LINQ pisania deklaratywne kod, który opisuje ma zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="8be73-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="8be73-109">Ponadto zapytań LINQ oferuje trzy główne zalet w porównaniu z tradycyjnym `foreach` pętle:</span><span class="sxs-lookup"><span data-stu-id="8be73-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1.  <span data-ttu-id="8be73-110">Są one bardziej zwięzłe i do odczytu, szczególnie, gdy wiele warunków filtrowania.</span><span class="sxs-lookup"><span data-stu-id="8be73-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="8be73-111">Udostępniają zaawansowane filtrowanie, kolejność i grupowanie możliwości z co najmniej kodu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8be73-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="8be73-112">Mogą one być przenoszone do innych źródeł danych z żadnych modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="8be73-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="8be73-113">W ogólności, tym bardziej złożone operację należy wykonać na danych, więcej korzyści będzie realizować za pomocą LINQ zamiast metod tradycyjnych iteracji.</span><span class="sxs-lookup"><span data-stu-id="8be73-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="8be73-114">Ta sekcja ma na celu pokazują podejście LINQ z przykładami select.</span><span class="sxs-lookup"><span data-stu-id="8be73-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="8be73-115">Nie ma niepełna.</span><span class="sxs-lookup"><span data-stu-id="8be73-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8be73-116">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="8be73-116">In This Section</span></span>  
 [<span data-ttu-id="8be73-117">LINQ i ciągi (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-117">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="8be73-118">Wyjaśniono, jak LINQ może służyć do wykonywania zapytań i przekształcanie ciągów i kolekcji ciągów.</span><span class="sxs-lookup"><span data-stu-id="8be73-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="8be73-119">Zawiera również linki do tematów, które przedstawiają tych zasad.</span><span class="sxs-lookup"><span data-stu-id="8be73-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="8be73-120">LINQ i odbicie (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-120">LINQ and Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="8be73-121">Łącza na przykład, który demonstruje sposób LINQ używa odbicia.</span><span class="sxs-lookup"><span data-stu-id="8be73-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="8be73-122">LINQ i katalogi plików (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-122">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="8be73-123">Wyjaśniono, jak LINQ może służyć do interakcji z systemów plików.</span><span class="sxs-lookup"><span data-stu-id="8be73-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="8be73-124">Zawiera również linki do tematów, które przedstawiają te pojęcia.</span><span class="sxs-lookup"><span data-stu-id="8be73-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="8be73-125">Porady: zapytanie w ArrayList za pomocą LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-125">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="8be73-126">Demonstracja zapytanie w ArrayList w języku C#.</span><span class="sxs-lookup"><span data-stu-id="8be73-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="8be73-127">Porady: dodawanie metod niestandardowych do kwerend LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-127">How to: Add Custom Methods for LINQ Queries (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="8be73-128">Wyjaśniono, jak rozszerzyć zestaw metod, których można używać do kwerend LINQ przez dodanie metody rozszerzenia umożliwiające <xref:System.Collections.Generic.IEnumerable%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="8be73-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="8be73-129">Zapytanie o języku zintegrowanym (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="8be73-129">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="8be73-130">Zawiera łącza do tematów, w których opisano LINQ i zawierają przykłady kodu, które wykonywania zapytań.</span><span class="sxs-lookup"><span data-stu-id="8be73-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>