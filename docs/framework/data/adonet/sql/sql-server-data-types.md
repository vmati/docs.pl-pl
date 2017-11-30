---
title: Danych programu SQL Server typy i ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="4df04-102">Danych programu SQL Server typy i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4df04-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="4df04-103">SQL Server i programu .NET Framework są oparte na systemach innego typu, które mogą spowodować utratę danych.</span><span class="sxs-lookup"><span data-stu-id="4df04-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="4df04-104">Aby zachować spójność danych, .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) udostępnia metody typizowane metody dostępu do pracy z danymi programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4df04-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="4df04-105">Korzystając z wyliczeń w <xref:System.Data.SqlDbType> klas, aby określić <xref:System.Data.SqlClient.SqlParameter> typów danych.</span><span class="sxs-lookup"><span data-stu-id="4df04-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="4df04-106">Aby uzyskać więcej informacji oraz tabelę, która opisuje dane typu mapowań między typy danych .NET Framework i programu SQL Server, zobacz [mapowanie typu danych serwera SQL](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="4df04-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="4df04-107">SQL Server 2008 wprowadzono nowe typy danych, które są przeznaczone do potrzeb firmy do pracy z datą i godziną, struktury, częściową strukturą i bez struktury danych.</span><span class="sxs-lookup"><span data-stu-id="4df04-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="4df04-108">Te opisano w dokumentacji SQL Server 2008 — książki Online.</span><span class="sxs-lookup"><span data-stu-id="4df04-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="4df04-109">Typy danych programu SQL Server, które są dostępne do użycia w aplikacji zależy od wersji programu SQL Server, którego używasz.</span><span class="sxs-lookup"><span data-stu-id="4df04-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="4df04-110">Aby uzyskać więcej informacji zobacz odpowiednich wersji programu SQL Server — książki Online w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="4df04-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="4df04-111">**SQL Server — książki Online**</span><span class="sxs-lookup"><span data-stu-id="4df04-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="4df04-112">Typy danych (aparat bazy danych)</span><span class="sxs-lookup"><span data-stu-id="4df04-112">Data Types (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="4df04-113">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="4df04-113">In This Section</span></span>  
 [<span data-ttu-id="4df04-114">Właściwości SqlTypes i zestawie danych</span><span class="sxs-lookup"><span data-stu-id="4df04-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="4df04-115">W tym artykule opisano obsługę typu `SqlTypes` w `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="4df04-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="4df04-116">Obsługa wartości Null</span><span class="sxs-lookup"><span data-stu-id="4df04-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="4df04-117">Pokazuje, jak pracować z wartości null i przechowywanymi na trzy logiczne.</span><span class="sxs-lookup"><span data-stu-id="4df04-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="4df04-118">Porównanie identyfikator GUID i uniqueidentifier wartości</span><span class="sxs-lookup"><span data-stu-id="4df04-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="4df04-119">Pokazuje, jak pracować z wartości identyfikatora GUID i unikatowy identyfikator programu SQL Server i programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4df04-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="4df04-120">Daty i godziny</span><span class="sxs-lookup"><span data-stu-id="4df04-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="4df04-121">Opis sposobu użycia nowego Data i godzina typy danych wprowadzonych w programie SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4df04-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4df04-122">Duże typów</span><span class="sxs-lookup"><span data-stu-id="4df04-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="4df04-123">Pokazuje, jak można pobrać danych z dużą wartość UDTs wprowadzone w programie SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4df04-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4df04-124">Dane XML w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="4df04-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="4df04-125">Opisuje sposób pracy z danymi XML pobrane z programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4df04-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4df04-126">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="4df04-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="4df04-127">W tym artykule opisano `DataSet` klasy i wszystkich jego elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="4df04-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="4df04-128">W tym artykule opisano `SqlTypes` przestrzeni nazw i wszystkich jego elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="4df04-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="4df04-129">W tym artykule opisano `SqlDbType` wyliczenie i wszystkich jego elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="4df04-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="4df04-130">W tym artykule opisano `DbType` wyliczenie i wszystkich jego elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="4df04-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df04-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4df04-131">See Also</span></span>  
 [<span data-ttu-id="4df04-132">Mapowanie typu danych serwera SQL</span><span class="sxs-lookup"><span data-stu-id="4df04-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="4df04-133">Konfigurowanie parametrów i typów danych parametrów</span><span class="sxs-lookup"><span data-stu-id="4df04-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="4df04-134">Parametry przechowywanymi w tabeli</span><span class="sxs-lookup"><span data-stu-id="4df04-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="4df04-135">Dane binarne i duża wartość serwera SQL</span><span class="sxs-lookup"><span data-stu-id="4df04-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="4df04-136">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="4df04-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)