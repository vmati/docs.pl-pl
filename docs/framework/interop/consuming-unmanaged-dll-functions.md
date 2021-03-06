---
title: "Wykorzystywanie niezarządzanych funkcji DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6276f2dc2bd57dc3eaf81eb2949e3c1ea3727e69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="consuming-unmanaged-dll-functions"></a>Wykorzystywanie niezarządzanych funkcji DLL
Wywołanie platformy to usługa, że umożliwia zarządzanego kodu wywoływanie niezarządzanych funkcji zaimplementowana w biblioteki dołączanej dynamicznie (dll), takich jak w interfejsie API Win32. Lokalizuje i wywołuje wyeksportowanej funkcji i marshals granicy współdziałanie argumenty (liczby całkowite, ciągi, tablic, struktur i tak dalej), zgodnie z potrzebami. Aby uzyskać więcej informacji na temat tej usługi, zobacz [A bliżej przyjrzeć się wywołanie platformy](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).  
  
 W tej sekcji przedstawiono kilka zadań związanych z wykorzystywanie niezarządzanych funkcji DLL. Oprócz następujące zadania są ogólne zagadnienia i łącza, co zapewnia dodatkowe informacje i przykłady.  
  
#### <a name="to-consume-exported-dll-functions"></a>Aby korzystać z wyeksportowanych funkcji DLL  
  
1.  [Identyfikowanie funkcji w bibliotekach DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).  
  
     Minimalny należy określić nazwę funkcji i nazwy biblioteki dll, która go zawiera.  
  
2.  [Tworzenie klasy utrzymującej funkcje DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).  
  
     Można użyć istniejącej klasy, Utwórz poszczególnych klas dla każdej funkcji niezarządzanej lub utworzyć jedną klasę, która zawiera zestaw powiązanych funkcji niezarządzanej.  
  
3.  [Tworzenie prototypów w kodzie zarządzanym](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
     [Visual Basic] Użyj **Declare** instrukcji z **funkcja** i **Lib** słów kluczowych. W rzadkich przypadkach można użyć **elementu DllImportAttribute** z **funkcji udostępnionych** słów kluczowych. Te przypadki są objaśnione później w tej sekcji.  
  
     [C#] Użyj **elementu DllImportAttribute** do identyfikowania biblioteki DLL i funkcji. Oznacz metodę z **statycznych** i **extern** modyfikatorów.  
  
     [C++] Użyj **elementu DllImportAttribute** do identyfikowania biblioteki DLL i funkcji. Oznacz metodę otoki lub funkcji z **zewnętrzne "C"**.  
  
4.  [Wywoływanie funkcji DLL](../../../docs/framework/interop/calling-a-dll-function.md).  
  
     Wywołaj metodę w klasie zarządzanej, jak w przypadku innych metod zarządzanych. [Przekazywanie struktur](../../../docs/framework/interop/passing-structures.md) i [Implementowanie funkcji wywołania zwrotnego](../../../docs/framework/interop/callback-functions.md) przypadków specjalnych.  
  
 Aby uzyskać przykłady pokazujące, które pokazują, jak utworzyć. Deklaracje opartych na potrzeby używania z platformy invoke, zobacz [organizowanie danych za pomocą wywołania platformy](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="a-closer-look-at-platform-invoke"></a>Bliższe spojrzenie na platformie wywołania  
 Wywołanie platformy opiera się na metadanych, aby zlokalizować eksportowane funkcje i kierować ich argumentów w czasie wykonywania. Na poniższej ilustracji przedstawiono ten proces.  
  
 ![Wywołanie platformy](../../../docs/framework/interop/media/pinvoke.gif "funkcji pinvoke")  
Wywołanie funkcji niezarządzanej DLL wywołanie platformy  
  
 Gdy wywołanie platformy wywołania funkcji niezarządzanej wykonywania następującej akcji:  
  
1.  Lokalizuje pliku DLL zawierającego funkcję.  
  
2.  Ładuje bibliotekę DLL do pamięci.  
  
3.  Lokalizuje adres funkcji w pamięci i wypchnięcia jej argumentów na stosie, organizowanie danych zgodnie z potrzebami.  
  
    > [!NOTE]
    >  Lokalizowania i ładowania biblioteki DLL i znajdowanie adresu funkcji w pamięci występuje tylko w pierwszym wywołaniu funkcji.  
  
4.  Formant transferu do funkcji niezarządzanej.  
  
 Wywołanie platformy zgłasza wyjątki generowane przez funkcję niezarządzane do zarządzanego obiektu wywołującego.  
  
## <a name="see-also"></a>Zobacz też  
 [Współdziałanie z kodem niezarządzanym](../../../docs/framework/interop/index.md)  
 [Przykłady wywołań platformy](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Marshaling międzyoperacyjny](../../../docs/framework/interop/interop-marshaling.md)  
 [Wykorzystywanie niezarządzanych funkcji DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
