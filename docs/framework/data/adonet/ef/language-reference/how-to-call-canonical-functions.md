---
title: "Porady: wywoływać funkcje kanoniczny"
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
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 02cbcee218db310fdddc7f42d9b6f01a16a8314d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-call-canonical-functions"></a>Porady: wywoływać funkcje kanoniczny
<xref:System.Data.Objects.EntityFunctions> Klasa zawiera metody, które udostępniają kanonicznej funkcji do użycia w składniku LINQ do jednostek zapytań. Aby uzyskać informacje na temat funkcji kanonicznej Zobacz [kanonicznej funkcji](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
> [!NOTE]
>  <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> i <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> metod w <xref:System.Data.Objects.EntityFunctions> klasy nie mają funkcji kanonicznej odpowiedniki.  
  
 Canonical funkcje, których wykonywanie obliczeń na zestaw wartości i zwraca pojedynczą wartość (znanej także jako kanonicznej funkcji agregujących) może być wywoływany bezpośrednio. Inne funkcje canonical można wywołać tylko w ramach zapytania składnika LINQ to Entities. Aby wywołać funkcję agregującą bezpośrednio, należy podać <xref:System.Data.Objects.ObjectQuery%601> funkcji. Aby uzyskać więcej informacji zobacz drugi przykład poniżej.  
  
 Niektóre funkcje canonical można wywołać za pomocą wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) metod w składniku LINQ do jednostek zapytań. Aby uzyskać listę metodach CLR, które mapują kanonicznej funkcji, zobacz [metodę CLR mapowania funkcji kanonicznej](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto [modelu sprzedaży AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832). Przykład wykonuje zapytania składnika LINQ to Entities używającej <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> metodę, aby zwrócić wszystkie produkty, dla której to różnica między `SellEndDate` i `SellStartDate` jest mniejsza niż 365 dni:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto [modelu sprzedaży AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832). Przykład wywołuje agregacji <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> metody bezpośrednio do Zwróć odchylenie standardowe `SalesOrderHeader` sum częściowych. Należy pamiętać, że <xref:System.Data.Objects.ObjectQuery%601> została przekazana do funkcji, co umożliwia można wywołać bez części zapytania składnika LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też  
 [Wywoływanie funkcji w zapytaniach składnika LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Zapytania w składniku LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
