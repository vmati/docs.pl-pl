---
title: "Podsumowanie typu śledzenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe4222ac124174341a28035c955a2a9bef4a167c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="trace-type-summary"></a>Podsumowanie typu śledzenia
[Źródło poziomy](http://go.microsoft.com/fwlink/?LinkID=94943) definiuje różne poziomy śledzenia: krytyczny, błąd, ostrzeżenie, informacje i pełne, jak również tak jak opisano w `ActivityTracing` flagi, które włącza dane wyjściowe śledzenia zdarzeń transfer granic i działania.  
  
 Można również przejrzeć [element TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) dla typów danych śledzenia, które może być wysyłany z <xref:System.Diagnostics>.  
  
 W poniższej tabeli wymieniono najważniejsze alerty.  
  
|Typ śledzenia|Opis|  
|----------------|-----------------|  
|Krytyczny|Błąd krytyczny lub aplikacji awarii.|  
|Błąd|Nieodwracalny błąd.|  
|Ostrzeżenie|Komunikat informacyjny.|  
|Informacje|Niekrytyczny problem.|  
|Pełny|Śledzenie debugowania.|  
|Uruchamianie|Rozpoczynanie przetwarzania jednostki logicznej.|  
|Wstrzymaj|Zawieszenie jednostki logicznej przetwarzania.|  
|Wznawianie|Wznowienie przetwarzania jednostki logicznej.|  
|Zatrzymywanie|Zatrzymywanie jednostki logicznej przetwarzania.|  
|Transfer|Zmiana tożsamości korelacji.|  
  
 Działanie jest zdefiniowany jako kombinacji typów śledzenia powyżej.  
  
 Poniżej znajduje się wyrażenie regularne definiuje idealne działania w zakresie lokalnego (źródła)  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Oznacza to, że działanie muszą spełniać następujące warunki.  
  
-   Musi zaczynać się i odpowiednio Zatrzymaj śledzenie rozpoczęcia i zakończenia  
  
-   Musi mieć śledzenia Transfer poprzedzającego śledzenia wstrzymania lub wznowienia  
  
-   Nie może mieć śladów między śladów wstrzymywanie i wznawianie, jeśli istnieją takie dane śledzenia  
  
-   Tak długo, jak poprzednie warunki są spełnione może mieć żadnych i ślady krytyczne/błędu/ostrzeżenia/informacji/Verbose/Transfer  
  
 Poniżej znajduje się wyrażenie regularne definiuje działania idealne rozwiązanie w zakresie globalnym  
  
```  
R+   
```  
  
 z języka R są wyrażenia regularnego do działania w zakresie lokalnym. Przekłada się to,  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
