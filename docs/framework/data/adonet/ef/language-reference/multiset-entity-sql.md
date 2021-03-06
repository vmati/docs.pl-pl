---
title: Zestaw WIELOKROTNY (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6389051ae1244a2a38699704c67217d9807fe7e4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="multiset-entity-sql"></a>Zestaw WIELOKROTNY (jednostka SQL)
Tworzy wystąpienie zestaw wielokrotny na podstawie listy wartości. Wszystkie wartości w Konstruktorze multiset — muszą być zgodne z typem `T`. Pusty konstruktorów zestawów wielokrotnych są niedozwolone.  
  
## <a name="syntax"></a>Składnia  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argumenty  
 `expression`  
 Wszelkie prawidłową listę wartości.  
  
## <a name="return-value"></a>Wartość zwracana  
 Kolekcja typu MULTISET\<T >.  
  
## <a name="remarks"></a>Uwagi  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]udostępnia trzy rodzaje konstruktory: wiersz konstruktorów, obiekt konstruktorów i konstruktorów multiset (lub kolekcji). Aby uzyskać więcej informacji, zobacz [konstruowania typy](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 Multiset — Konstruktor tworzy wystąpienie zestaw wielokrotny na podstawie listy wartości. Wszystkie wartości w Konstruktorze musi być zgodne z typem.  
  
 Na przykład poniższe wyrażenie tworzy zestaw wielokrotny liczb całkowitych.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Zagnieżdżone literały zestawów wielokrotnych są obsługiwane tylko podczas mutiset zawijania ma jeden elementów zestawów wielokrotnych; na przykład `{{1, 2, 3}}`. Gdy multiset zawijania ma wiele elementów zestawów wielokrotnych (na przykład `{{1, 2}, {3, 4}}`), zagnieżdżonych zestawów wielokrotnych literały nie są obsługiwane.  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora MULTISET do utworzenia wystąpienia zestaw wielokrotny z listy wartości. Kwerenda jest oparta na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Zobacz też  
 [Konstruowanie typów](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
