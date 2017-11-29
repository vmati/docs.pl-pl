---
title: Wprowadzenie do LINQ (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6fd14840cfffb1a59949251b26c168aada336de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="c0b68-102">Wprowadzenie do LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c0b68-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="c0b68-103">Zapytanie języku zintegrowanym (LINQ) jest innowacje wprowadzone w programie .NET Framework w wersji 3.5 który zawiera odstęp między world obiektów i world danych.</span><span class="sxs-lookup"><span data-stu-id="c0b68-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="c0b68-104">Tradycyjnym zapytań dotyczących danych są wyrażane jako skompilować prostego parametry bez typu sprawdzania w czasie lub obsługę funkcji IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c0b68-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="c0b68-105">Ponadto należy dowiedzieć się język kwerendy różne dla każdego typu źródła danych: SQL bazy danych, dokumentów XML, różnych usług sieci Web i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="c0b68-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="c0b68-106">LINQ sprawia, że *zapytania* konstrukcję najwyższej jakości języka w języku C#.</span><span class="sxs-lookup"><span data-stu-id="c0b68-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="c0b68-107">Możesz pisać zapytania względem kolekcje silnie typizowanych obiektów przy użyciu operatorów znanych i słowa kluczowe języka.</span><span class="sxs-lookup"><span data-stu-id="c0b68-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="c0b68-108">Można zapisywać zapytania LINQ w C# dla programu SQL Server baz danych, XML dokumentów danych ADO.NET i kolekcji obiektów, która obsługuje <xref:System.Collections.IEnumerable> lub ogólnego <xref:System.Collections.Generic.IEnumerable%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c0b68-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="c0b68-109">Obsługa LINQ jest również udostępniany przez osoby trzecie dla wielu usług sieci Web oraz inne implementacje bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c0b68-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="c0b68-110">W nowych projektach lub obok kwerend LINQ z systemem innym niż w istniejących projektów, można użyć zapytań LINQ.</span><span class="sxs-lookup"><span data-stu-id="c0b68-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="c0b68-111">Jedynym wymaganiem jest, że projekt docelowy .NET Framework w wersji 3.5 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="c0b68-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="c0b68-112">Na poniższej ilustracji, z programu Visual Studio przedstawiono zapytania LINQ częściowo ukończone w bazie danych programu SQL Server w języku C# i Visual Basic z sprawdzanie pełny typ oraz obsługę funkcji IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c0b68-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="c0b68-113">![Zapytania LINQ z Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="c0b68-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c0b68-114">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="c0b68-114">Next Steps</span></span>  
 <span data-ttu-id="c0b68-115">Aby uzyskać więcej informacji na temat LINQ, Rozpocznij od staje się poznać niektóre podstawowe założenia w sekcji wprowadzenie [wprowadzenie do LINQ w C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), a następnie zapoznaj się z dokumentacją w technologii LINQ, w której jesteś zainteresowany:</span><span class="sxs-lookup"><span data-stu-id="c0b68-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="c0b68-116">Bazy danych programu SQL Server: [LINQ do SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="c0b68-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="c0b68-117">Dokumenty XML: [LINQ do XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="c0b68-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="c0b68-118">Zestawy danych ADO.NET: [LINQ do DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="c0b68-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="c0b68-119">Kolekcje .NET, plików, ciągi i tak dalej: [LINQ do obiektów (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="c0b68-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b68-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c0b68-120">See Also</span></span>  
 [<span data-ttu-id="c0b68-121">Zapytanie o języku zintegrowanym (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c0b68-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)