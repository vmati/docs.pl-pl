---
title: 'Ograniczenie: Serializacja znaki kontrolne z elementu DataContractJsonSerializer'
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e92bc1ab55674a39331cef5d0450cd8e28ef55f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Ograniczenie: Serializacja znaki kontrolne z elementu DataContractJsonSerializer

W programie .NET Framework 4.7, sposób, w których kontroli znaki są serializowane z <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> została zmieniona z wersja języka ECMAScript 6 i V8. 
 
## <a name="impact"></a>Wpływ

.NET framework 4.6.2 i wcześniejszych wersjach <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> nie serializować niektóre znaki kontrolne specjalnych, takich jak `\b`, `\f`, i `\t`, w sposób zgodny ze standardami wersja języka ECMAScript 6 i V8.

W przypadku aplikacji przeznaczonych dla wersji programu .NET Framework w programie .NET Framework 4.7 serializacji te znaki kontrolne jest zgodny z wersja języka ECMAScript 6 i V8. Uwzględnione są następujące:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Ograniczenie

W przypadku aplikacji przeznaczonych dla wersji programu .NET Framework w programie .NET Framework 4.7 to zachowanie jest domyślnie włączona.

Jeśli to zachowanie nie jest pożądane, można zrezygnować z tej funkcji, dodając następujący wiersz do `<runtime>` sekcji w pliku app.config lub web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Zobacz także
[Zmiany w przekierowywaniu w programie .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
