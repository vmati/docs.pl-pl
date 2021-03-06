---
title: Funkcje matematyczne
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9b4ef03a2a517b9ce53954bc4576b655afdafc03
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="mathematical-functions"></a>Funkcje matematyczne
.NET Framework Data Provider for SQL Server (SqlClient) oferuje funkcje matematyczne, których wykonywanie obliczeń na wartości wejściowych, które są przekazywane jako argumenty i zwracać wynik będący wartością wartość liczbową. Te funkcje są w obszarze nazw SqlServer, która jest dostępna, gdy używasz SqlClient. Właściwości przestrzeni nazw dostawcy umożliwia programu Entity Framework dowiedzieć się, które prefiks jest używany przez tego dostawcę dla określonych elementów składowych, takich jak typy i funkcje. W poniższej tabeli opisano funkcje matematyczne SqlClient.  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`ABS(` `expression` `)`|Wykonuje funkcję wartość bezwzględna.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Wartość zwracana**<br /><br /> Wartość bezwzględna określone wyrażenie.<br /><br /> **Przykład**<br /><br /> `SqlServer.ABS(-2)`|  
|`ACOS(` `expression` `)`|Zwraca wartość cosinus określonego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.ACOS(.9)`|  
|`ASIN(` `expression` `)`|Zwraca wartość arcus sinus określonego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.ASIN(.9)`|  
|`ATAN(` `expression` `)`|Zwraca wartość tangens określonego wyrażenia liczbowego.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.ATAN(9)`|  
|`ATN2(` `expression`, `expression``)`|Zwraca kąt w radianach, którego tangens jest między określonym dwóch wyrażeń liczbowych.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.ATN2(9, 8)`|  
|`CEILING(` `expression` `)`|Konwertuje najmniejsza liczba całkowita, która jest większa niż lub równa jej określone wyrażenie.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Wartość zwracana**<br /><br /> `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Przykład**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]|  
|`COS(` `expression` `)`|Oblicza trygonometryczne cosinus kąta określonego w radianach.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.COS(45)`|  
|`COT(` `expression` `)`|Oblicza trygonometryczne cotangens kąta określonego w radianach.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.COT(60)`|  
|`DEGREES(` `radians` `)`|Zwraca odpowiadający mu kąt w stopniach.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Wartość zwracana**<br /><br /> `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Przykład**<br /><br /> `SqlServer.DEGREES(3.1)`|  
|`EXP(` `expression` `)`|Oblicza wartość wykładniczej określonego wyrażenia liczbowego.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.EXP(1)`|  
|`FLOOR(` `expression` `)`|Konwertuje największa liczba całkowita mniejsza lub równa do niego określone wyrażenie.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]|  
|`LOG(` `expression` `)`|Oblicza logarytm naturalny z określonym `float` wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.LOG(100)`|  
|`LOG10(` `expression` `)`|Zwraca logarytm o podstawie base 10 określonego `Double` wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.LOG10(100)`|  
|`PI()`|Zwraca stałą wartość liczby pi jako `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.PI()`|  
|`POWER(` `numeric_expression, power_expression` `)`|Oblicza wartość określonego wyrażenia do określonej potęgi.<br /><br /> **Argumenty**<br /><br /> `numeric_expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> `power_expression`: A `Double` reprezentujący zasilania, do którego zostanie wywołane `numeric_expression`.<br /><br /> **Wartość zwracana**<br /><br /> Wartość określonego `numeric_expression` do określonego `power_expression`.<br /><br /> **Przykład**<br /><br /> `SqlServer.POWER(2,7)`|  
|`RADIANS(` `expression` `)`|Konwertuje stopnie na radiany.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Wartość zwracana**<br /><br /> `Int32`, `Int64`,<br /><br /> `Double`, lub<br /><br /> `Decimal`.<br /><br /> **Przykład**<br /><br /> `SqlServer.RADIANS(360.0)`|  
|`RAND(`[inicjatora]`)`|Zwraca wartość losową z zakresu od 0 do 1.<br /><br /> **Argumenty**<br /><br /> Wartość Retruns inicjatora jako `Int32`. Inicjatora nie zostanie określony, aparatu bazy danych programu SQL Server przypisuje wartość inicjatora losowo. Wartość inicjatora określony wynik zwracany jest zawsze taki sam.<br /><br /> **Wartość zwracana**<br /><br /> Losowe `Double` wartość z zakresu od 0 do 1.<br /><br /> **Przykład**<br /><br /> `SqlServer.RAND()`|  
|`ROUND(` `numeric_expression, length` [ ,`function` ]`)`|Zwraca wartość wyrażenia liczbowego zaokrąglone do określonej długości lub dokładności.<br /><br /> **Argumenty**<br /><br /> `numeric_expression`: `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> `length`: `Int32` Reprezentujący dokładność, do którego `numeric_expression` ma zostać zaokrąglona. Gdy `length` jest liczbą dodatnią `numeric_expression` jest zaokrąglana do liczby miejsc dziesiętnych określonej przez `length`. Gdy `length` jest liczbą ujemną `numeric_expression` jest zaokrąglana lewej strony punktu dziesiętnego, określony przez `length`.<br /><br /> `function`: (opcjonalnie) `Int32` reprezentujący typ operacji do wykonania. Gdy funkcja zostanie pominięty lub ma wartość 0 (domyślnie), `numeric_expression` jest zaokrąglana. W przypadku wartości innej niż określono wartość 0, `numeric_expression` zostały obcięte.<br /><br /> **Wartość zwracana**<br /><br /> Wartość określonego `numeric_expression` do określonego `power_expression`.<br /><br /> **Przykład**<br /><br /> `SqlServer.ROUND(748.58, -3)`|  
|`SIGN(` `expression` `)`|Zwraca plus (+ 1), 0 (zero) lub znakiem minus (-1) z określonego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32`, `Int64`, `Double`, lub`Decimal`<br /><br /> **Wartość zwracana**<br /><br /> `Int32`, `Int64`, `Double`, Lub `Decimal`.<br /><br /> **Przykład**<br /><br /> `SqlServer.SIGN(-10)`|  
|`SIN(` `expression` `)`|Oblicza sinus trygonometryczne określony kąt w radianach, a następnie zwraca `Double` wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.SIN(20)`|  
|`SQRT(` `expression` `)`|Zwraca pierwiastek kwadratowy z określonego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.SQRT(3600)`|  
|`SQUARE(` `expression` `)`|Zwraca kwadrat określone wyrażenie.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Double`.<br /><br /> **Wartość zwracana**<br /><br /> A `Double`.<br /><br /> **Przykład**<br /><br /> `SqlServer.SQUARE(25)`|  
|`TAN(` `expression` `)`|Oblicza tangens określonego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: `Double`<br /><br /> **Wartość zwracana**<br /><br /> `Double`<br /><br /> **Przykład**<br /><br /> `SqlServer.TAN(45.0)`|  
  
 Aby uzyskać więcej informacji o funkcji matematycznych, które obsługuje SqlClient zobacz dokumentację dla używanej wersji programu SQL Server określona w manifeście dostawcy SqlClient:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Funkcje matematyczne (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115913)|[Funkcje matematyczne (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115911)|[Funkcje matematyczne (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115912)|  
  
## <a name="see-also"></a>Zobacz też  
 [Klient SQL dla funkcji programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
