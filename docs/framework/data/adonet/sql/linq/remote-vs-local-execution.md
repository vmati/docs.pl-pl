---
title: Zdalne vs. Wykonanie lokalne
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
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c402fad49526729ba09d8f4b86a5b022ca4a12cb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="remote-vs-local-execution"></a>Zdalne vs. Wykonanie lokalne
Można wykonać zapytania albo zdalnie (to znaczy aparatu bazy danych wykonuje zapytanie w bazie danych) lub lokalnie ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wykonuje zapytanie lokalnej pamięci podręcznej).  
  
## <a name="remote-execution"></a>Zdalne wykonywanie kodu  
 Należy wziąć pod uwagę następujące zapytanie:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Jeśli Twoja baza danych zawiera tysiące wierszy zleceń, czy chcesz pobrać je wszystkie do przetwarzania małych podzbioru. W [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Data.Linq.EntitySet%601> klasa implementuje <xref:System.Linq.IQueryable> interfejsu. Takie podejście upewnia się, czy takie zapytania mogą być wykonywane zdalnie. Dwie główne korzyści przepływać z tej techniki:  
  
-   Zbędne dane nie została pobrana.  
  
-   Zapytanie wykonywane przez aparat bazy danych jest często bardziej wydajne, ponieważ indeksy bazy danych.  
  
## <a name="local-execution"></a>Wykonanie lokalne  
 W innych sytuacjach możesz chcieć ma kompletnego zestawu powiązanych jednostek w lokalnej pamięci podręcznej. W tym celu <xref:System.Data.Linq.EntitySet%601> zapewnia <xref:System.Data.Linq.EntitySet%601.Load%2A> metodę, aby wszystkie elementy członkowskie w sposób jawny załadować <xref:System.Data.Linq.EntitySet%601>.  
  
 Jeśli <xref:System.Data.Linq.EntitySet%601> jest już załadowany, kolejne zapytania są wykonywane lokalnie. Takie podejście pozwala na dwa sposoby:  
  
-   Jeśli pełny zestaw musi być używane lokalnie lub wiele razy, można uniknąć zapytań zdalnych i skojarzone opóźnienia.  
  
-   Może być Zserializowany obiekt jako całą jednostkę.  
  
 Poniższy fragment kodu przedstawia sposób lokalne wykonanie można uzyskać:  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>Porównanie  
 Te dwie funkcje Podaj kombinację opcji zaawansowanych: zdalne wykonywanie kodu w dużych kolekcjach i wykonanie lokalne dla małych kolekcji lub gdy potrzebne jest pełną kolekcję. Wdrożenie zdalne wykonywanie kodu za pomocą <xref:System.Linq.IQueryable>oraz lokalnego miało zostać wykonane w pamięci <xref:System.Collections.Generic.IEnumerable%601> kolekcji. Aby wymusić wykonanie lokalne (to znaczy <xref:System.Collections.Generic.IEnumerable%601>), zobacz [przekonwertować typem rodzajowym interfejsem IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).  
  
### <a name="queries-against-unordered-sets"></a>Zapytania względem nieuporządkowaną zestawów  
 Należy zwrócić uwagę istotną różnicą między kolekcji lokalnej, która implementuje <xref:System.Collections.Generic.List%601> i kolekcja, która zapewnia zdalnego zapytania wykonywane *nieuporządkowane zestawy* relacyjnej bazy danych. <xref:System.Collections.Generic.List%601>metody takich jak implementacje używające wartości indeksu wymagają semantyki listy, które zwykle nie można uzyskać za pośrednictwem zdalnego zapytanie nieuporządkowaną zestawu. Z tego powodu niejawnie obciążenia tych metod <xref:System.Data.Linq.EntitySet%601> umożliwia wykonanie lokalne.  
  
## <a name="see-also"></a>Zobacz też  
 [Pojęcia dotyczące zapytań](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
