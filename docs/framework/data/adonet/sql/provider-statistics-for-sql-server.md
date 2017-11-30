---
title: Statystyki dostawcy dla programu SQL Server
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
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 54e9a3b6f72eee2246d2c76b10e01fe011435b3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="62594-102">Statystyki dostawcy dla programu SQL Server</span><span class="sxs-lookup"><span data-stu-id="62594-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="62594-103">W programie .NET Framework w wersji 2.0, .NET Framework Data Provider for SQL Server obsługuje statystyk czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="62594-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="62594-104">Należy włączyć statystyki przez ustawienie <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> właściwość <xref:System.Data.SqlClient.SqlConnection> do obiektu `True` po poprawnego obiektu połączenia utworzone.</span><span class="sxs-lookup"><span data-stu-id="62594-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="62594-105">Po włączeniu statystyki można przeglądać je jako "migawka w czasie" pobierając <xref:System.Collections.IDictionary> odwoływać się za pośrednictwem <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> metody <xref:System.Data.SqlClient.SqlConnection> obiektu.</span><span class="sxs-lookup"><span data-stu-id="62594-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="62594-106">Wyliczanie za pośrednictwem listy jako zbiór wpisy słownika pary nazwa/wartość.</span><span class="sxs-lookup"><span data-stu-id="62594-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="62594-107">Tych par nazwa/wartość są nieuporządkowane.</span><span class="sxs-lookup"><span data-stu-id="62594-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="62594-108">W dowolnym momencie można wywołać <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> metody <xref:System.Data.SqlClient.SqlConnection> obiektu do resetowania liczników.</span><span class="sxs-lookup"><span data-stu-id="62594-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="62594-109">Jeśli nie włączono zbieranie statystyk, wyjątek nie zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="62594-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="62594-110">Ponadto jeśli <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> jest wywoływana bez <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> o najpierw wywołuje, wartości pobierane są wartości początkowe dla każdego wpisu.</span><span class="sxs-lookup"><span data-stu-id="62594-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="62594-111">Po włączeniu statystyki uruchomienie aplikacji przez pewien czas i Wyłącz statystyk, wartości pobierane odpowiada wartości zebranych do punktu wyłączonym statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="62594-112">Wszystkie wartości statystyczne zebrane znajdują się na poszczególnych połączeń.</span><span class="sxs-lookup"><span data-stu-id="62594-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="62594-113">Dostępne wartości statystycznych</span><span class="sxs-lookup"><span data-stu-id="62594-113">Statistical Values Available</span></span>  
 <span data-ttu-id="62594-114">Aktualnie brak dostępnych 18 różnych elementów od dostawcy programu Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62594-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="62594-115">Liczba dostępnych elementów jest możliwy za pośrednictwem **liczba** właściwość <xref:System.Collections.IDictionary> interfejsu Odwołanie zwrócone przez <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span><span class="sxs-lookup"><span data-stu-id="62594-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="62594-116">Wszystkie liczniki dla dostawcy statystyk użycia środowisko uruchomieniowe języka wspólnego <xref:System.Int64> typu (**długi** w języku C# i Visual Basic), która jest 64 bity.</span><span class="sxs-lookup"><span data-stu-id="62594-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="62594-117">Maksymalna wartość **int64** typu danych, zgodnie z definicją **int64. MaxValue** pola, ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="62594-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="62594-118">Gdy ta wartość maksymalna, wartości liczników one już nie należy traktować jako dokładne.</span><span class="sxs-lookup"><span data-stu-id="62594-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="62594-119">Oznacza to, że **int64. MaxValue**-1((2^63)-2) skutecznie jest największy poprawną wartością wszystkie statystyki.</span><span class="sxs-lookup"><span data-stu-id="62594-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62594-120">Słownik służy do zwracania statystyki dostawcy, ponieważ numer, nazwy i kolejność zwracane statystyki mogą ulec zmianie w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="62594-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="62594-121">Aplikacje nie należy polegać na określoną wartość zostanie znaleziony w słowniku, ale zamiast tego należy sprawdzić, czy wartość jest istnieje i odpowiednio gałęzi.</span><span class="sxs-lookup"><span data-stu-id="62594-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="62594-122">W poniższej tabeli opisano bieżące wartości statystyczne dostępne.</span><span class="sxs-lookup"><span data-stu-id="62594-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="62594-123">Należy pamiętać, że nazwy kluczy dla poszczególnych wartości nie są zlokalizowane w regionalnych wersji programu Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62594-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="62594-124">Nazwa klucza</span><span class="sxs-lookup"><span data-stu-id="62594-124">Key Name</span></span>|<span data-ttu-id="62594-125">Opis</span><span class="sxs-lookup"><span data-stu-id="62594-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="62594-126">Zwraca liczbę strumienia danych tabelarycznych (TDS) pakietów odebranych przez dostawcę z programu SQL Server po aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="62594-127">Zwraca liczbę pakietów TDS wysyłanych do serwera SQL przez dostawcę po włączeniu statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="62594-128">Duże polecenia może wymagać wielu buforów.</span><span class="sxs-lookup"><span data-stu-id="62594-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="62594-129">Na przykład, jeśli dużych polecenia są wysyłane do serwera i wymaga sześciu pakietów `ServerRoundtrips` jest zwiększany o jeden i `BuffersSent` jest zwiększany o sześciu.</span><span class="sxs-lookup"><span data-stu-id="62594-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="62594-130">Zwraca liczbę bajtów danych odebranych przez dostawcę z programu SQL Server, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyki pakietów TDS.</span><span class="sxs-lookup"><span data-stu-id="62594-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="62594-131">Zwraca liczbę bajtów danych wysłanych do programu SQL Server w pakietach TDS po aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyki.</span><span class="sxs-lookup"><span data-stu-id="62594-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="62594-132">Czas (w milisekundach), że połączenie zostało otwarte po włączeniu statystyki (całkowity czas połączenia, jeśli umożliwiono statystyki przed otwarciem połączenie).</span><span class="sxs-lookup"><span data-stu-id="62594-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="62594-133">Zwraca liczbę powtórzeń kursora był otwarty przez połączenie, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="62594-134">Należy pamiętać, że tylko/do przodu — tylko do odczytu wyniki zwrócone przez instrukcje SELECT nie są uznawane za kursory i w związku z tym nie wpływają na wartość tego licznika.</span><span class="sxs-lookup"><span data-stu-id="62594-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="62594-135">Zwraca zbiorczą ilość czasu (w milisekundach), czy dostawca jest poświęcony na przetwarzanie włączenie statystyk, tym czas oczekiwania na odpowiedzi z serwera, a także czas poświęcony na wykonywanie kodu w samej dostawcy.</span><span class="sxs-lookup"><span data-stu-id="62594-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="62594-136">Klasy, które zawierają kod chronometrażu są:</span><span class="sxs-lookup"><span data-stu-id="62594-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="62594-137">Element SqlConnection</span><span class="sxs-lookup"><span data-stu-id="62594-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="62594-138">Klasy SqlCommand</span><span class="sxs-lookup"><span data-stu-id="62594-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="62594-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="62594-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="62594-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="62594-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="62594-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="62594-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="62594-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="62594-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="62594-143">Aby zachować możliwie najmniejsze członków wydajności o znaczeniu krytycznym, nie jest mierzony następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="62594-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="62594-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="62594-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="62594-145">Ten operator [] (wszystkie przeciążenia)</span><span class="sxs-lookup"><span data-stu-id="62594-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="62594-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="62594-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="62594-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="62594-147">GetChar</span></span><br /><br /> <span data-ttu-id="62594-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="62594-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="62594-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="62594-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="62594-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="62594-150">GetDouble</span></span><br /><br /> <span data-ttu-id="62594-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="62594-151">GetFloat</span></span><br /><br /> <span data-ttu-id="62594-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="62594-152">GetGuid</span></span><br /><br /> <span data-ttu-id="62594-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="62594-153">GetInt16</span></span><br /><br /> <span data-ttu-id="62594-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="62594-154">GetInt32</span></span><br /><br /> <span data-ttu-id="62594-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="62594-155">GetInt64</span></span><br /><br /> <span data-ttu-id="62594-156">GetName</span><span class="sxs-lookup"><span data-stu-id="62594-156">GetName</span></span><br /><br /> <span data-ttu-id="62594-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="62594-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="62594-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="62594-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="62594-159">GetSqlBoolean</span><span class="sxs-lookup"><span data-stu-id="62594-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="62594-160">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="62594-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="62594-161">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="62594-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="62594-162">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="62594-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="62594-163">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="62594-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="62594-164">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="62594-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="62594-165">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="62594-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="62594-166">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="62594-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="62594-167">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="62594-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="62594-168">GetSqlMoney</span><span class="sxs-lookup"><span data-stu-id="62594-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="62594-169">GetSqlSingle</span><span class="sxs-lookup"><span data-stu-id="62594-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="62594-170">GetSqlString</span><span class="sxs-lookup"><span data-stu-id="62594-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="62594-171">GetString</span><span class="sxs-lookup"><span data-stu-id="62594-171">GetString</span></span><br /><br /> <span data-ttu-id="62594-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="62594-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="62594-173">Zwraca sumę instrukcje INSERT, usuwania i aktualizacji, które są wykonywane za pośrednictwem połączenia, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="62594-174">Zwraca całkowitą liczbę wierszy, wpływ instrukcje INSERT, usuwania i aktualizacji, które są wykonywane za pośrednictwem połączenia, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="62594-175">Zwraca zbiorczą ilość czasu (w milisekundach) dostawcy oczekujących na odpowiedzi z serwera po aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="62594-176">Zwraca liczbę przygotowanego polecenia wykonywane za pośrednictwem połączenia, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="62594-177">Zwraca liczbę instrukcji przygotowane przez połączenie, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="62594-178">Zwraca liczbę instrukcji "SELECT" wykonywane za pośrednictwem połączenia, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="62594-179">Zawiera instrukcje pobierania, aby pobierać wiersze z kursorami oraz liczbę elementów w instrukcji "SELECT" jest aktualizowany po zakończeniu <xref:System.Data.SqlClient.SqlDataReader> zostanie osiągnięty.</span><span class="sxs-lookup"><span data-stu-id="62594-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="62594-180">Zwraca liczbę wierszy zaznaczone, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="62594-181">Ten licznik wskazuje wszystkie wiersze, które są generowane przez instrukcje SQL, nawet te, które nie zostały faktycznie używane przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="62594-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="62594-182">Na przykład zamknięcia czytnika danych przed odczytaniem cały zestaw wyników nie wpłynie na wartość licznika.</span><span class="sxs-lookup"><span data-stu-id="62594-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="62594-183">W tym wiersze, pobierane z kursorami za pomocą instrukcji pobierania.</span><span class="sxs-lookup"><span data-stu-id="62594-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="62594-184">Zwraca liczbę razy połączenia wysłane do serwera poleceń i otrzymano odpowiedzi, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="62594-185">Zwraca liczbę wyników zestawów, które były używane po aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyk.</span><span class="sxs-lookup"><span data-stu-id="62594-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="62594-186">Na przykład obejmuje to każdego zestawu wyników zwróconego do klienta.</span><span class="sxs-lookup"><span data-stu-id="62594-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="62594-187">Kursory każdej operacji pobierania lub fetch bloku jest traktowany jako zestaw wyników niezależne.</span><span class="sxs-lookup"><span data-stu-id="62594-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="62594-188">Zwraca liczbę uruchomione po aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyki, w tym wycofywania transakcji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="62594-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="62594-189">Jeśli połączenie jest uruchamiana za pomocą automatycznego zatwierdzania na, każde polecenie jest uważany za transakcji.</span><span class="sxs-lookup"><span data-stu-id="62594-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="62594-190">Ten licznik zwiększa liczbę transakcji, jak najszybciej po wykonaniu instrukcji BEGIN TRAN, niezależnie od tego, czy transakcja jest zatwierdzenia lub wycofania później.</span><span class="sxs-lookup"><span data-stu-id="62594-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="62594-191">Zwraca liczbę nieprzygotowany instrukcje wykonywane za pośrednictwem połączenia, gdy aplikacja została uruchomiona przy użyciu dostawcy i włączył statystyki.</span><span class="sxs-lookup"><span data-stu-id="62594-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="62594-192">Pobieranie wartości</span><span class="sxs-lookup"><span data-stu-id="62594-192">Retrieving a Value</span></span>  
 <span data-ttu-id="62594-193">Następującej aplikacji konsoli pokazano, jak włączyć statystyki dotyczące połączenia, pobrać cztery wartości poszczególnych statystyk i zapisać je w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="62594-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62594-194">W poniższym przykładzie użyto przykładowej **AdventureWorks** baza danych dołączona [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62594-194">The following example uses the sample **AdventureWorks** database included with [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62594-195">W przykładowym kodzie w podanym ciągu połączenia przyjęto założenie, że baza danych jest zainstalowany i dostępny na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="62594-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="62594-196">Zmodyfikuj parametry połączenia w razie potrzeby dla danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="62594-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="62594-197">Pobieranie wszystkich wartości</span><span class="sxs-lookup"><span data-stu-id="62594-197">Retrieving All Values</span></span>  
 <span data-ttu-id="62594-198">Następującej aplikacji konsoli Pokazuje, jak włączyć statystyki dotyczące połączenia, pobrać wszystkich wartości dostępne statystyki przy użyciu modułu wyliczającego i zapisywać je w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="62594-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62594-199">W poniższym przykładzie użyto przykładowej **AdventureWorks** baza danych dołączona [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62594-199">The following example uses the sample **AdventureWorks** database included with [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62594-200">W przykładowym kodzie w podanym ciągu połączenia przyjęto założenie, że baza danych jest zainstalowany i dostępny na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="62594-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="62594-201">Zmodyfikuj parametry połączenia w razie potrzeby dla danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="62594-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="62594-202">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62594-202">See Also</span></span>  
 [<span data-ttu-id="62594-203">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="62594-203">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="62594-204">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="62594-204">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)