---
title: "Przykłady Operator specyficzne dla zestawu danych (LINQ do DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dea56be6aad0e596eaf9a61fae1352474f99fb04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="940e1-102">Przykłady Operator specyficzne dla zestawu danych (LINQ do DataSet)</span><span class="sxs-lookup"><span data-stu-id="940e1-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="940e1-103">Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> — metoda i <xref:System.Data.DataRowComparer> klasy.</span><span class="sxs-lookup"><span data-stu-id="940e1-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="940e1-104">`FillDataSet` Metodę używaną w tym przykładzie jest określona w [podczas ładowania danych do zestawu danych](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="940e1-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="940e1-105">Przykłady w tym temacie można użyć kontaktu, adres produktu, SalesOrderHeader i szczegóły zamówienia sprzedaży tabel w bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="940e1-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="940e1-106">Przykłady w tym temacie należy użyć następującego `using` / `Imports` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="940e1-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="940e1-107">Aby uzyskać więcej informacji, zobacz [porady: tworzenie LINQ do DataSet projektu w programie Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="940e1-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="940e1-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="940e1-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="940e1-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="940e1-109">Example</span></span>  
 <span data-ttu-id="940e1-110">W tym przykładzie ładuje <xref:System.Data.DataTable> z wyników zapytania za pomocą <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="940e1-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="940e1-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="940e1-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="940e1-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="940e1-112">Example</span></span>  
 <span data-ttu-id="940e1-113">W tym przykładzie porównuje dwa wiersze z różnymi danymi za pomocą <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="940e1-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="940e1-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="940e1-114">See Also</span></span>  
 [<span data-ttu-id="940e1-115">Podczas ładowania danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="940e1-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="940e1-116">LINQ do DataSet przykłady</span><span class="sxs-lookup"><span data-stu-id="940e1-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)