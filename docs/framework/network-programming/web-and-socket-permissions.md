---
title: "Sieć Web i uprawnienia gniazda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b426b5e7e6a9b617311db05670f526fc415d591d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="web-and-socket-permissions"></a>Sieć Web i uprawnienia gniazda
Zabezpieczenia internetowe dla aplikacji za pomocą <xref:System.Net> przestrzeni nazw jest zapewniana przez <xref:System.Net.WebPermission> i <xref:System.Net.SocketPermission> klasy. **WebPermission** klasa steruje aplikacji prawo do dane żądania z identyfikatora URI lub do obsługi identyfikatora URI z Internetem. **SocketPermission** klasy formantów aplikacji przez prawo, aby użyć <xref:System.Net.Sockets.Socket> akceptować dane na port lokalny lub skontaktuj się z urządzeń zdalnych przy użyciu protokołu transportu na inny adres, oparta na hoście, a numer portu i protokół Transport gniazda.  
  
 Klasy uprawnień, których można użyć zależy od typu aplikacji. Aplikacje używające <xref:System.Net.WebRequest> i jego elementy podrzędne powinny używać **WebPermission** klasy do zarządzania uprawnieniami. Aplikacje używające dostęp na poziomie gniazda powinny używać **SocketPermission** klasy do zarządzania uprawnieniami.  
  
 **WebPermission** i **SocketPermission** zdefiniować dwa uprawnienia: Zaakceptuj i nawiąż połączenie. Zaakceptuj przyznaje prawa do odpowiedzi połączenia przychodzącego z innej strony aplikacji. Połącz przyznaje uprawnienia do nawiązania połączenia do innej strony aplikacji.  
  
 Dla **SocketPermission** wystąpienia, akceptować oznacza, że aplikacja może akceptować połączeń przychodzących na komputerze lokalnym transportu adres; połączyć oznacza, że aplikacja może nawiązać połączenie niektórych adres transportu (lokalnej lub zdalnej).  
  
 Dla **WebPermission** wystąpienia, akceptować oznacza, że aplikację można wyeksportować kontrolowane przez identyfikator URI **WebPermission** World; połączyć oznacza, że aplikacja może uzyskiwać dostęp do tego identyfikatora URI (czy jest lokalnych lub zdalnych).  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczenia](../../../docs/standard/security/index.md)  
 [Zabezpieczenia w programowaniu sieciowym](../../../docs/framework/network-programming/security-in-network-programming.md)
