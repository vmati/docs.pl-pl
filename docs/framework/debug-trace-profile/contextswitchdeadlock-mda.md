---
title: contextSwitchDeadlock MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 816afbae0cca18de24c11152541a509b54c119b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="contextswitchdeadlock-mda"></a>contextSwitchDeadlock MDA
`contextSwitchDeadlock` Zarządzany Asystent debugowania (MDA) została aktywowana po wykryciu zakleszczenie podczas próby przejścia kontekstu COM.  
  
## <a name="symptoms"></a>Symptomy  
 Najbardziej typowe objaw jest wywołanie niezarządzane składnika modelu COM z kodu zarządzanego nie zwraca.  Kolejnym objawem może być użycie pamięci zwiększa się w czasie.  
  
## <a name="cause"></a>Przyczyna  
 Najbardziej prawdopodobną przyczyną jest to, że wątku jednowątkowego apartamentu (STA) nie jest przekazywanie komunikatów. Wątku STA. jest albo oczekiwania bez przekazywania komunikatów lub operacji długie i nie zezwala na wiadomości w kolejce pompa.  
  
 Użycie pamięci zwiększa się w czasie jest spowodowany przez wątek finalizatora próba wywołania `Release` niezarządzane COM składnika i składnik ten nie zwraca.  Zapobiega to odzyskiwanie inne obiekty finalizatora.  
  
 Jest domyślnie pozostaje tryb komórek jednowątkowych model wątkowy wątku głównego aplikacji konsoli języka Visual Basic To zdarzenie MDA jest włączone, jeśli wątku STA. używa współdziałanie COM bezpośrednio lub pośrednio przez środowisko uruchomieniowe języka wspólnego lub formantu innych firm.  Aby uniknąć aktywowanie to zdarzenie MDA w aplikacji konsoli języka Visual Basic, zastosuj <xref:System.MTAThreadAttribute> atrybut do głównej metody lub zmodyfikować aplikację tak, by przekazywać komunikaty.  
  
 Jest to możliwe, że to zdarzenie MDA do fałszywie aktywowany, gdy są spełnione wszystkie następujące warunki:  
  
-   Aplikacja tworzy składniki modelu COM z wątki STA bezpośrednio lub pośrednio do biblioteki.  
  
-   Aplikacja została zatrzymana w debugerze, a użytkownik nadal aplikacji lub wykonać operacji kroku.  
  
-   Nie włączono debugowanie niezarządzane.  
  
 Aby ustalić, czy MDA fałszywie aktywowana, wyłącz wszystkie punkty przerwania, ponownie uruchom aplikację i zezwolenie na uruchamianie bez zatrzymania. Jeśli nie włączono MDA, prawdopodobnie początkowej aktywacji była wartość false. W takim przypadku należy wyłączyć MDA w celu uniknięcia konfliktów z sesji debugowania.  
  
> [!NOTE]
>  To zdarzenie MDA znajduje się w domyślnym zestawem dla [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] i nowszych wersjach. Podczas procesu hostingu jest włączone w [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], nie można wyłączyć mda ustawionych w domyślnym. Proces hostingu jest włączona domyślnie, więc musi być jawnie wyłączone. Aby dowiedzieć się, jak wyłączyć mda, zobacz "Włączanie i wyłączanie mda" w [diagnozowanie problemów z Asystenci zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="resolution"></a>Rozwiązanie  
 Wykonaj COM zasady dotyczące przekazywanie komunikatów STA.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 To zdarzenie MDA nie ma wpływu na środowisko CLR. Zwraca tylko dane o kontekstach COM.  
  
## <a name="output"></a>Dane wyjściowe  
 Komunikat opisujący bieżący kontekst i kontekst docelowy.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Marshaling międzyoperacyjny](../../../docs/framework/interop/interop-marshaling.md)
