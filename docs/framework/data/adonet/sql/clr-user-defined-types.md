---
title: "Typy danych zdefiniowane przez użytkownika CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e81cf54ed9dc516d88b8c7a97c8a5b33b8943d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="75b71-102">Typy danych zdefiniowane przez użytkownika CLR</span><span class="sxs-lookup"><span data-stu-id="75b71-102">CLR User-Defined Types</span></span>
<span data-ttu-id="75b71-103">Microsoft SQL Server zapewnia obsługę zdefiniowanych przez użytkownika typów (UDTs) zaimplementowany przy użyciu programu Microsoft .NET Framework środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="75b71-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="75b71-104">Środowisko CLR jest zintegrowany z programu SQL Server, a mechanizm ten umożliwia rozszerzanie system typu bazy danych.</span><span class="sxs-lookup"><span data-stu-id="75b71-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="75b71-105">UDTs rozszerzalność użytkownika system typów danych programu SQL Server, a także możliwość definiowania złożonych typów strukturalnych.</span><span class="sxs-lookup"><span data-stu-id="75b71-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="75b71-106">UDTs zapewnia dwie kluczowe korzyści z punktu widzenia architektury aplikacji:</span><span class="sxs-lookup"><span data-stu-id="75b71-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="75b71-107">Silne encapsulation (zarówno na kliencie i serwerze) między stan wewnętrzny i zewnętrzny zachowania.</span><span class="sxs-lookup"><span data-stu-id="75b71-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="75b71-108">Ścisła integracja z innymi powiązanych funkcji serwera.</span><span class="sxs-lookup"><span data-stu-id="75b71-108">Deep integration with other related server features.</span></span> <span data-ttu-id="75b71-109">Po zdefiniowaniu własne UDT umożliwia we wszystkich kontekstach gdzie typ systemu w programie SQL Server, w tym definicje kolumn i służy jako zmienne, parametry, funkcja wyników, kursorów, wyzwalaczy i replikacji.</span><span class="sxs-lookup"><span data-stu-id="75b71-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="75b71-110">Aby uzyskać szczegółowe informacje Zobacz wersji programu SQL Server — książki Online dla wersji programu SQL Server są przy użyciu.</span><span class="sxs-lookup"><span data-stu-id="75b71-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="75b71-111">**SQL Server — książki Online**</span><span class="sxs-lookup"><span data-stu-id="75b71-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="75b71-112">Typy danych zdefiniowane przez użytkownika CLR</span><span class="sxs-lookup"><span data-stu-id="75b71-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="75b71-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75b71-113">See Also</span></span>  
 [<span data-ttu-id="75b71-114">Tworzenie obiekty programu SQL Server 2005 w kodzie zarządzanym</span><span class="sxs-lookup"><span data-stu-id="75b71-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="75b71-115">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="75b71-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)