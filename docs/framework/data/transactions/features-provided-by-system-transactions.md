---
title: "Funkcje oferowane przez bibliotekę System.Transactions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1170adc2fb2ede41e9e111e9d7dd6612f06676a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="features-provided-by-systemtransactions"></a>Funkcje oferowane przez bibliotekę System.Transactions
W tej sekcji opisano sposób korzystania z funkcji udostępnianych przez <xref:System.Transactions> przestrzeni nazw, aby napisać własny transakcyjny Menedżer aplikacji i zasobów. W szczególności w tej sekcji opisano sposób tworzenia i uczestniczyć w transakcji (lokalnej lub rozproszone) z jednego lub wielu uczestników.  
  
## <a name="overview-of-systemtransactions"></a>Omówienie System.Transactions  
 Klasy w infrastrukturę <xref:System.Transactions> przestrzeń nazw powoduje transakcyjne programowania prosty i wydajny przez Obsługa transakcji w programie SQL Server, ADO.NET usługi kolejkowania komunikatów (MSMQ) i transakcji rozproszonych firmy Microsoft Koordynator (transakcji rozproszonych MSDTC). <xref:System.Transactions> Przestrzeń nazw obejmuje zarówno jawne programowania model na podstawie <xref:System.Transactions.Transaction> klasy, a także niejawne programowania modelu przy użyciu <xref:System.Transactions.TransactionScope> klasy, w którym transakcje są automatycznie zarządzane przez infrastrukturę. Aby uzyskać więcej informacji na temat tworzenia aplikacji transakcyjnej przy użyciu tych dwóch modeli, zobacz [zapisywania transakcyjnych aplikacji](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 <xref:System.Transactions> Również przestrzeń nazw zawiera typy umożliwiające wdrożenie Menedżera zasobów. Menedżer zasobów zarządza danych trwałe lub zmienne używane w transakcji, a działanie we współpracy z menedżerem transakcji, aby zapewnić aplikacji niepodzielność i izolacji. Menedżer transakcji zapewnianej przez <xref:System.Transactions> infrastruktury obsługuje transakcje obejmujące wiele zasobów volatile lub pojedynczy zasób trwały. Aby uzyskać więcej informacji dotyczących wdrażania Menedżera zasobów, zobacz [implementacji Menedżera zasobów](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Menedżer transakcji również przezroczysty Eskalowanie transakcji lokalnych transakcje rozproszone przez koordynowanie z menedżerem transakcji na dysku, takich jak usługi, gdy Menedżer dodatkowych zasobów trwałe współdziała z transakcją. Istnieją dwie metody klucza który <xref:System.Transactions> infrastruktury zapewnia lepszą wydajność.  
  
-   Eskalacja dynamiczne, które zapewnia <xref:System.Transactions> infrastruktury tylko uruchamia MSDTC, gdy transakcja zapisanych na wielu rozproszonymi zasobami. Aby uzyskać więcej informacji o eskalacji dynamicznych. zobacz [eskalacji zarządzania transakcji](../../../../docs/framework/data/transactions/transaction-management-escalation.md) tematu.  
  
-   Awansowanie rejestracji, co umożliwia zasobu, takie jak bazy danych, przejęcie na własność transakcji, jeśli jest tylko typy jednostek uczestnictwa w transakcji. Później, jeśli to konieczne, <xref:System.Transactions> infrastruktury nadal może eskalować zarządzania transakcji MSDTC. Dodatkowo zmniejsza to ryzyko przy użyciu MSDTC. Awansowanie rejestracji są przedstawione szczegółowo w temacie[Optymalizacja za pomocą pojedynczego zatwierdzić fazy i awansowanie pojedyncze powiadomienia fazy](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 <xref:System.Transactions> Nazw definiuje trzy poziomy zaufania - AllowPartiallyTrustedCallers (APTCA), DistributedTransactionPermission(DTP) i pełną zaufania - ograniczenia dla typów zasobów do niego dostęp ujawnia. Aby uzyskać więcej informacji na temat różnych poziomów zaufania, zobacz [poziomy zaufania zabezpieczeń podczas uzyskiwania dostępu do zasobów](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>W tej sekcji  
  
### <a name="writing-a-transactional-application"></a>Pisanie aplikacji transakcyjnych  
 <xref:System.Transactions> Przestrzeń nazw zawiera dwa modele do tworzenia aplikacji transakcyjnych. [Implementowanie transakcji niejawnej przy użyciu zakresu transakcji](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) w tym artykule opisano sposób <xref:System.Transactions> przestrzeń nazw obsługuje tworzenie niejawne transakcji za pomocą <xref:System.Transactions.TransactionScope> klasy.  
  
 [Implementowanie jawnych transakcji przy użyciu obiekcie CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) w tym artykule opisano sposób <xref:System.Transactions> przestrzeń nazw obsługuje tworzenie jawnych transakcji przy użyciu <xref:System.Transactions.CommittableTransaction> klasy.  
  
 Dodatkowe tematy obejmujące zapisywania transakcyjnych aplikacji, zobacz [zapisywania transakcyjnych aplikacji](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### <a name="implementing-a-resource-manager"></a>Implementowanie Menedżera zasobów  
 Aby zaimplementować Menedżera zasobów, które mogą uczestniczyć w transakcji, zobacz [implementacji Menedżera zasobów](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md). W tej sekcji opisano rejestracja zasobu, zatwierdzanie transakcji, odzyskiwania po awarii i optymalizacji najlepszych rozwiązań.
