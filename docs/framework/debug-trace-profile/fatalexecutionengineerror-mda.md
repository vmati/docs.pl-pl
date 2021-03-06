---
title: fatalExecutionEngineError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6eb091883f59302e195d1b49b84693815196a4b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="fatalexecutionengineerror-mda"></a>fatalExecutionEngineError MDA
`fatalExecutionEngine``Error` Zarządzany Asystent debugowania (MDA) jest aktywowany, gdy wykryto błąd krytyczny w środowisku uruchomieniowym języka (wspólnego CLR). Proces zostanie zakończony.  
  
## <a name="symptoms"></a>Symptomy  
 Kończenie procesu nieoczekiwany. Nie można określić inne objawy, ponieważ błąd CLR może wystąpić z różnych przyczyn.  
  
## <a name="cause"></a>Przyczyna  
 Środowisko CLR śmiertelnie została uszkodzona. W większości przypadków jest to spowodowane uszkodzeniem danych, która może być spowodowana przez liczbę problemów, takie jak wywołania platformy źle sformułowane wywołania funkcji i przekazywanie nieprawidłowe dane do środowiska CLR.  
  
## <a name="resolution"></a>Rozwiązanie  
 Włączanie dodatkowych MDA może zidentyfikować problem. Następujące MDA może być szczególnie przydatne w zdiagnozowaniu problemu:  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 To zdarzenie MDA nie ma wpływu na zachowanie środowiska uruchomieniowego.  
  
## <a name="output"></a>Dane wyjściowe  
 Adres funkcji CLR, która spowodowała błąd krytyczny, identyfikator wątku, w którym wystąpił błąd i kod błędu.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
