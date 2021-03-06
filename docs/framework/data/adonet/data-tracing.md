---
title: "Dane śledzenia w ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: "9"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: df958982739c7ab2fd7aba42918b919c25d86829
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="data-tracing-in-adonet"></a>Dane śledzenia w ADO.NET
Funkcja śledzenia danych wbudowanych obsługiwaną przez dostawców danych .NET dla funkcji ADO.NET [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB i ODBC, a także ADO.NET <xref:System.Data.DataSet>i [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] protokołów sieciowych.  
  
 Śledzenie danych interfejsu API dostępu może pomóc w diagnozowaniu następujące problemy:  
  
-   Niezgodność schematu między program kliencki a bazą danych.  
  
-   Baza danych niedostępności lub biblioteka problemów z siecią.  
  
-   Niepoprawne SQL twardego kodowanych lub generowanych przez aplikację.  
  
-   Niepoprawne logiki programowania.  
  
-   Problemy wynikające z interakcji między wiele składników ADO.NET lub między ADO.NET i własnych składników.  
  
 Do obsługi śledzenia różnych technologii, śledzenie jest otwarty, więc deweloperzy mogą śledzenia problemu na dowolnym poziomie stosu aplikacji. Chociaż śledzenia nie jest funkcją tylko ADO.NET, dostawcy Microsoft korzystać z Instrumentacji interfejsów API i śledzenie uogólniony.  
  
 Aby uzyskać więcej informacji na temat i konfigurowanie zarządzanych śledzenia w ADO.NET, zobacz [dostęp do danych śledzenia](http://msdn.microsoft.com/library/hh880086.aspx).  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Uzyskiwanie dostępu do informacji diagnostycznych w dzienniku zdarzeń rozszerzonych  
 W [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], śledzenie dostępu do danych ([śledzenie dostępu do danych](http://msdn.microsoft.com/library/hh880086.aspx)) została zaktualizowana, aby ułatwić łatwiej skorelować zdarzenia klienta z informacje diagnostyczne, takie jak błędy połączeń z serwera łączności pierścień buforu i aplikacji informacje o wydajności w dzienniku zdarzeń rozszerzonych. Aby uzyskać informacje dotyczące odczytywania dziennika zdarzeń rozszerzonych, zobacz [danych sesji zdarzeń widoku](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 W operacjach połączenia ADO.NET wyśle klientowi identyfikator połączenia. Jeśli połączenie nie powiedzie się, możesz uzyskać dostęp bufor pierścień łączności ([rozwiązywania problemów z łącznością programu SQL Server 2008 buforem pierścienia łączności](http://go.microsoft.com/fwlink/?LinkId=207752)) i Znajdź `ClientConnectionID` pola i uzyskać informacje diagnostyczne Błąd połączenia. Identyfikatory połączeń klienta są rejestrowane w buforze pierścień tylko wtedy, gdy wystąpi błąd. (Jeśli połączenie nie powiedzie się przed wysłaniem pakiet wstępnego logowania, identyfikator połączenia klienta nie zostanie wygenerowany.) Identyfikator połączenia klienta jest identyfikatorem GUID 16 bajtów. Możesz również znaleźć połączenie klienta IDENTYFIKATORA w danych wyjściowych zdarzeń rozszerzonych docelowych, jeśli `client_connection_id` akcji jest dodawany do zdarzeń w sesji zdarzeń rozszerzonych. Można włączyć śledzenie dostępu do danych i ponownie uruchom polecenie połączenia i obserwować `ClientConnectionID` pola w śledzeniu dostępu do danych, jeśli potrzebujesz dodatkowej pomocy diagnostycznych sterownika klienta.  
  
 Klienta można uzyskać Identyfikatora połączenia programowo przy użyciu `SqlConnection.ClientConnectionID` właściwości.  
  
 `ClientConnectionID` Jest dostępna dla <xref:System.Data.SqlClient.SqlConnection> obiekt, który pomyślnie nawiąże połączenie. Jeśli próba połączenia nie powiedzie się, `ClientConnectionID` mogą być dostępne za pośrednictwem `SqlException.ToString`.  
  
 ADO.NET wysyła również identyfikator działania właściwe dla wątków. Identyfikator działania są przechwytywane w sesji zdarzeń rozszerzonych, jeśli sesje są uruchamiane z włączoną opcją TRACK_CAUSAILITY. Problemy z wydajnością z aktywnego połączenia, możesz pobrać identyfikator działania ze śledzenia dostępu do danych klienta (`ActivityID` pola), a następnie zlokalizuj identyfikator działania w danych wyjściowych zdarzeń rozszerzonych. Identyfikator działania w zdarzeń rozszerzonych jest identyfikatorem GUID 16-bajtowych, (nie to samo identyfikatora GUID dla Identyfikatora połączenia klienta) dołączony numer kolejny 4 bajtowych. Numer sekwencyjny reprezentuje kolejność żądania w wątku i określa względne uporządkowanie partii i instrukcje RPC dla wątku. `ActivityID` Jest obecnie opcjonalnie wysyłane żądania RPC i instrukcje SQL partii, gdy jest włączone śledzenie dostępu do danych i 18 bit dostępu do danych śledzenia word konfiguracji jest włączona.  
  
 Poniżej przedstawiono przykład, który używa [!INCLUDE[tsql](../../../../includes/tsql-md.md)] można uruchomić sesji zdarzeń rozszerzonych, które będą przechowywane w buforze pierścień i zarejestruje identyfikator działania wysłanych z klienta na operacje RPC i partii.  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Śledzenie sieci w programie .NET Framework](../../../../docs/framework/network-programming/network-tracing.md)  
 [Śledzenie i instrumentacja aplikacji](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
