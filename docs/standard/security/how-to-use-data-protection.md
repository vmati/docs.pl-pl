---
title: 'Porady: stosowanie ochrony danych'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 92e792f554ef3007e7a13efdbb995560375a9efa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-data-protection"></a>Porady: stosowanie ochrony danych
.NET Framework zapewnia dostęp do ochrony danych interfejsu API (DPAPI), który służy do szyfrowania danych przy użyciu informacji z bieżącego konta użytkownika lub komputera.  Gdy używasz DPAPI można rozwiązać problem trudne jawnie generowania i przechowywania kluczy kryptograficznych.  
  
 Użyj <xref:System.Security.Cryptography.ProtectedMemory> klasy do szyfrowania tablicy bajtów w pamięci.  Ta funkcja jest dostępna w systemie Microsoft Windows XP i nowszych systemów operacyjnych.  Można określić pamięci, szyfrowane przez bieżący proces odszyfrować je mogą tylko przez wszystkie procesy lub z tego samego kontekstu użytkownika bieżącego procesu.  Zobacz <xref:System.Security.Cryptography.MemoryProtectionScope> wyliczenie szczegółowy opis <xref:System.Security.Cryptography.ProtectedMemory> opcje.  
  
 Użyj <xref:System.Security.Cryptography.ProtectedData> klasy do szyfrowania kopii tablicy bajtów. Ta funkcja jest dostępna w systemie Microsoft Windows 2000 i nowszych systemów operacyjnych.  Można określić, czy dane zaszyfrowane przy bieżącego konta użytkownika mogły być odszyfrowane tylko przez tego samego konta użytkownika, lub można określić, że wszystkie konta na komputerze można odszyfrować dane zaszyfrowane przy bieżącego konta użytkownika.  Zobacz <xref:System.Security.Cryptography.DataProtectionScope> wyliczenie szczegółowy opis <xref:System.Security.Cryptography.ProtectedData> opcje.  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a>Do szyfrowania danych w pamięci przy użyciu ochrony danych  
  
1.  Wywołaj statycznych <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> metoda podczas przekazanie tablicy bajtów do szyfrowania, entropii i zakres ochrony pamięci.  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a>Do odszyfrowywania danych w pamięci przy użyciu ochrony danych  
  
1.  Wywołaj statycznych <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> metoda podczas przekazywania tablicę bajtów do odszyfrowania i zakresu ochrony pamięci.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Do szyfrowania danych do pliku lub strumienia za pomocą ochrony danych  
  
1.  Utwórz losowe entropii.  
  
2.  Wywołaj statycznych <xref:System.Security.Cryptography.ProtectedData.Protect%2A> metoda podczas przekazanie tablicy bajtów do szyfrowania, entropii i zakresu ochrony danych.  
  
3.  Zaszyfrowane dane zapisać do pliku lub strumienia.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Aby odszyfrować dane z pliku lub strumienia za pomocą ochrony danych  
  
1.  Zaszyfrowane dane do odczytu z pliku lub strumienia.  
  
2.  Wywołaj statycznych <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> metoda podczas przekazywania tablicę bajtów do odszyfrowania i zakresu ochrony danych.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje dwie formy szyfrowania i odszyfrowywania.  Najpierw przykładowy kod szyfruje i odszyfrowuje tablicę bajtów w pamięci.  Następnie przykładowy kod szyfruje kopiowania tablicy bajtów, zapisuje go w pliku ładuje dane z kopii pliku i odszyfrowuje dane.  W przykładzie przedstawiono oryginalne dane zaszyfrowane dane i odszyfrowane dane.  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
-   Odwołanie do `System.Security.dll`.  
  
-   Obejmują <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, i <xref:System.Text> przestrzeni nazw.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Security.Cryptography.ProtectedMemory>  
 <xref:System.Security.Cryptography.ProtectedData>
