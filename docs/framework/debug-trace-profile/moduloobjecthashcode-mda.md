---
title: moduloObjectHashcode MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 618196473e8e947e84b0506771bce84ee71a1c2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="moduloobjecthashcode-mda"></a>moduloObjectHashcode MDA
`moduloObjectHashcode` Zarządzany Asystent debugowania (MDA) zmiany zachowania <xref:System.Object> klasy do wykonania modulo operacja skrótu zwrócony przez <xref:System.Object.GetHashCode%2A> metody. Modulo domyślnego dla tego MDA wynosi 1, co powoduje, że <xref:System.Object.GetHashCode%2A> do zwrócenia 0 dla wszystkich obiektów.  
  
## <a name="symptoms"></a>Symptomy  
 Po przeniesieniu do nowej wersji środowisko uruchomieniowe języka wspólnego (CLR), program nie działa prawidłowo:  
  
-   Program otrzymuje z niewłaściwym obiektem <xref:System.Collections.Hashtable>.  
  
-   Kolejność wyliczenie z <xref:System.Collections.Hashtable> zawiera zmiany, która dzieli program.  
  
-   Dwa obiekty używane równe nie są takie same.  
  
-   Dwa obiekty używane różnej teraz są takie same.  
  
## <a name="cause"></a>Przyczyna  
 Program może występować z niewłaściwym obiektem <xref:System.Collections.Hashtable> ponieważ wykonania <xref:System.Object.Equals%2A> metody w klasie klucza do <xref:System.Collections.Hashtable> testy równości obiektów przez porównanie wyników wywołanie <xref:System.Object.GetHashCode%2A> — metoda . Skrótu nie powinien służyć do testowania równość obiektu, ponieważ dwa obiekty może mieć taki sam skrót, nawet jeśli ich odpowiednich pól mają różne wartości. Te kolizji kod skrótu, wystąpić sporadycznych w praktyce. Wpływ ma na <xref:System.Collections.Hashtable> wyszukiwanie jest równe wyświetlane są dwa klucze, które nie są takie same, czy nieprawidłowy obiekt jest zwracany z <xref:System.Collections.Hashtable>. Ze względu na wydajność, implementacja <xref:System.Object.GetHashCode%2A> można przełączać się między wersji środowiska uruchomieniowego, więc konflikty, które nie mogą wystąpić w jednej wersji może wystąpić w kolejnych wersjach. Włącz to zdarzenie MDA sprawdzić, czy używany kod ma usterki podczas kolizji skrótu. Włączenie tej opcji, to zdarzenie MDA powoduje, że <xref:System.Object.GetHashCode%2A> metoda zwraca 0, co kolizji wszystkie kody skrótów. Tylko efekt Włączanie przez to zdarzenie MDA powinny mieć programu jest wolniej uruchomieniu programu.  
  
 Kolejność wyliczenie z <xref:System.Collections.Hashtable> może zmienić z jednej wersji środowiska uruchomieniowego, jeśli inny algorytm używany do obliczania skrótu dla zmian klucza. Aby sprawdzić, czy program trwało zależności rzędu wyliczenie kluczy lub wartości spoza tablicy skrótów, można włączyć to zdarzenie MDA.  
  
## <a name="resolution"></a>Rozwiązanie  
 Nigdy nie używaj skrótu zastępuje tożsamość obiektu. Implementowanie zastąpienie z <xref:System.Object.Equals%2A?displayProperty=nameWithType> metody do porównania nie skrótu.  
  
 Nie należy tworzyć zależności rzędu wyliczenia kluczy lub wartości w tabelach skrótów.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 Aplikacje działać wolniej, gdy to zdarzenie MDA jest włączona. To zdarzenie MDA po prostu przyjmuje wartość skrótu, które mogłyby być zwracane i zamiast tego zwraca resztę po podzielona przez moduł.  
  
## <a name="output"></a>Dane wyjściowe  
 Nie ma żadnych danych wyjściowych dla tego MDA.  
  
## <a name="configuration"></a>Konfiguracja  
 `modulus` Atrybut określa modulo używane na wartość skrótu. Wartość domyślna to 1.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.Equals%2A?displayProperty=nameWithType>  
 [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
