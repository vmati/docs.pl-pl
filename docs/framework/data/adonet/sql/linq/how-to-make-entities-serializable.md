---
title: "Porady: należy do serializacji jednostek"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8f6121b8548c1909f4680419a1fee8f9848ebc1d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-make-entities-serializable"></a>Porady: należy do serializacji jednostek
Możesz wprowadzić jednostek serializacji, podczas generowania kodu. Klasy jednostki są oznaczone <xref:System.Runtime.Serialization.DataContractAttribute> atrybutu i kolumny z <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu.  
  
 Deweloperzy przy użyciu [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] można użyć [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] w tym celu.  
  
 Jeśli używasz narzędzia wiersza polecenia SQLMetal, użyj **/serialization** opcję z `unidirectional` argumentu. Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (narzędzie generowania kodu)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Przykład  
 Następujące wiersze polecenia SQLMetal tworzy pliki, których podmioty możliwy do serializacji.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Serializacja](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [Tworzenie modelu obiektu](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
