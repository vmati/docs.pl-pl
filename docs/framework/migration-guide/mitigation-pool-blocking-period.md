---
title: "Środki zaradcze: Okres blokuje puli"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42eaddeb2714a8c294f45d24eb7e6d9cf216fecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-pool-blocking-period"></a>Środki zaradcze: Okres blokuje puli
Blokowanie czasu puli połączeń zostało usunięte dla połączeń z bazami danych Azure SQL.  
  
## <a name="additional-description"></a>Dodatkowy opis  
 W [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] i starszych wersjach, gdy aplikacja napotka błąd przejściowy połączenia podczas nawiązywania połączenia z bazą danych, próba połączenia nie może zostać powtórzone szybko, ponieważ puli połączeń buforuje błędu i ponownie zgłasza wyjątek 5 sekund na 1 min. Aby uzyskać więcej informacji, zobacz [programu SQL Server połączenia buforowanie (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). To zachowanie jest powodować problemy dla połączeń z bazami danych Azure SQL, które często nie przejściowych błędów, które są zazwyczaj odzyskała sprawność działania po w ciągu kilku sekund. Funkcja blokowania puli połączeń oznacza, że aplikacji nie można połączyć z bazą danych na okres szeroką gamę nawet, jeśli baza danych jest dostępne. To zachowanie jest szczególnie powodować problemy dla aplikacji sieci web, który nawiązać połączenie bazy danych Azure SQL i który należy do renderowania w ciągu kilku sekund.  
  
 Począwszy od [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]dla połączenie jest otwarte żądania do znanego baz danych Azure SQL (*. database.windows.net, \*. database.chinacloudapi.cn, \*. database.usgovcloudapi.net, \*. database.cloudapi.de), Otwórz błędów połączenia nie są buforowane. Dla wszystkich innych prób połączenia połączenia czasu blokowania puli nadal mają być egzekwowane.  
  
## <a name="impact"></a>Wpływ  
 Ta zmiana umożliwia Otwórz próba ponowienia natychmiast baz danych Azure SQL, zwiększając wydajność aplikacji z włączoną obsługą chmury.  
  
## <a name="mitigation"></a>Ograniczenie  
 Połączenia czasu blokowania puli aplikacji, które niekorzystny wpływ na tę zmianę, można skonfigurować przez ustawienie nowego <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> właściwości.  Wartość właściwości jest elementem członkowskim <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> wyliczenia, który może przybrać jedną z trzech wartości:  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 Poprzednie mogą zostać przywrócone przez ustawienie <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> właściwości `PoolBlockingPeriod.AlwaysBlock`.  
  
## <a name="see-also"></a>Zobacz też  
 [Zmiany środowiska uruchomieniowego](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
