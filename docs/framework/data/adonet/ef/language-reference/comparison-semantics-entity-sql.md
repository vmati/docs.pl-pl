---
title: "Semantykę porównania (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c6d22b72e05e6293a7fd3bcf7ddfba6e116e441f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="comparison-semantics-entity-sql"></a>Semantykę porównania (jednostka SQL)
Wykonywanie następujących [!INCLUDE[esql](../../../../../../includes/esql-md.md)] porównania wystąpienia typu obejmuje operatory:  
  
## <a name="explicit-comparison"></a>Jawne porównanie  
 Operacje równości:  
  
-   =  
  
-   !=  
  
 Kolejność operacji:  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 Operacje dopuszczania wartości null:  
  
-   MA WARTOŚĆ NULL  
  
-   NIE MA WARTOŚCI NULL  
  
## <a name="explicit-distinction"></a>Jawne różnicy  
 Równość różnicy:  
  
-   RÓŻNE  
  
-   GRUPUJ WEDŁUG  
  
 Porządkowanie różnicy:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Niejawne różnicy  
 Ustaw operacje i predykatów (równości):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   POKRYWA SIĘ  
  
 Predykaty elementu (równości):  
  
-   W  
  
## <a name="supported-combinations"></a>Obsługiwane kombinacje  
 W poniższej tabeli przedstawiono obsługiwane kombinacje operatory porównania dla każdego rodzaju:  
  
|**Typ**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **RÓŻNE**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**MA WARTOŚĆ NULL**<br /><br /> **NIE MA WARTOŚCI NULL**|  
|-|-|-|-|-|-|-|-|  
|Typ jednostki|Ref<sup>1</sup>|Wszystkie właściwości<sup>2</sup>|Wszystkie właściwości<sup>2</sup>|Wszystkie właściwości<sup>2</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Ref<sup>1</sup>|  
|Typ złożony|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Wiersz|Wszystkie właściwości<sup>4</sup>|Wszystkie właściwości<sup>4</sup>|Wszystkie właściwości<sup>4</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Wszystkie właściwości<sup>4</sup>|Throw<sup>3</sup>|  
|Typ pierwotny|Provider-specific|Provider-specific|Provider-specific|Provider-specific|Provider-specific|Provider-specific|Provider-specific|  
|Zestaw wielokrotny|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|REF|Tak<sup>5</sup>|Tak<sup>5</sup>|Tak<sup>5</sup>|Tak<sup>5</sup>|Throw|Throw|Tak<sup>5</sup>|  
|Skojarzenie<br /><br /> — typ|Throw<sup>3</sup>|Throw|Throw|Throw|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
  
 <sup>1</sup>odwołania do danej jednostki wystąpień typu są porównywane niejawnie, jak pokazano w poniższym przykładzie:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Wystąpienie jednostki nie można porównać do jawnego odwołania. Jeśli ta próba zostanie podjęta, jest zwracany wyjątek. Na przykład poniższe zapytanie spowoduje zgłoszenie wyjątku:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>właściwości złożonych typów są spłaszczane przed wysłaniem do magazynu, więc stają się one porównywalne (o ile ich właściwości mogą być porównywane). Zobacz też <sup>4.</sup>  
  
 <sup>3</sup>środowiska uruchomieniowego programu Entity Framework wykrywa nieobsługiwane przypadku i zgłasza wyjątek znaczące bez zaangażowania dostawcy/magazynu.  
  
 <sup>4</sup>próby porównania wszystkich właściwości. Jeśli istnieje we właściwości nie można porównywać pod względem typu, takie jak text, ntext lub image, może być zgłoszony wyjątek serwera.  
  
 <sup>5</sup>wszystkie poszczególne elementy odwołań są porównywane (dotyczy to również nazwa zestawu jednostek i wszystkich właściwości klucza typu jednostek).  
  
## <a name="see-also"></a>Zobacz też  
 [Omówienie jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
