---
title: "Procedury składowane CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aebc681482482c364f762b12065cf041f4976be9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="clr-stored-procedures"></a>Procedury składowane CLR
Procedury składowane są procedury, których nie można używać w wyrażeniach skalarne. Mogą zwracać wyniki tabelaryczne i komunikaty do klienta, wywołania języka definicji danych (DDL) i instrukcji języka manipulacji danych oraz zwraca parametry wyjściowe.  
  
> [!NOTE]
>  Microsoft Visual Basic nie obsługuje parametrów wyjściowych w taki sam sposób, który wykonuje Microsoft Visual C#. Należy określić parametr jest przekazywany za pomocą odwołania i stosowanie \<Out() > atrybut do reprezentowania parametru wyjściowego, co przedstawiono poniżej:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Aby uzyskać szczegółowe informacje Zobacz wersji programu SQL Server — książki Online dla wersji programu SQL Server są przy użyciu.  
  
 **SQL Server — książki Online**  
  
1.  [Procedury składowane CLR](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie obiekty programu SQL Server 2005 w kodzie zarządzanym](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
