---
title: "&lt;System.Diagnostics&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d336a0f733451cb28d8fe57af20585515b71ca4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; — Element
Określa obiektów nasłuchujących śledzenia zbierania, przechowywania i kierowania wiadomości i poziom, gdy jest ustawiona przełącznik śledzenia.  
  
 \<Konfiguracja >  
\<System.Diagnostics >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Assert >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Określa, czy wyświetlać okno komunikatu po wywołaniu <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metody; określa także nazwę pliku do zapisania komunikatów.|  
|[\<liczniki wydajności >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Określa rozmiar pamięci globalnej współużytkowane przez liczniki wydajności.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Zawiera nasłuchujących może odwoływać się wszystkie źródła lub element śledzenia. Obiekty nasłuchujące zidentyfikowane jako udostępnione obiekty nasłuchujące można dodać do źródła lub śledzenie według nazwy.|  
|[\<źródeł >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Określa źródła śledzenia, które inicjują śledzenia wiadomości.|  
|[\<przełączniki >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Zawiera przełączniki śledzenia i poziomy, gdzie są ustawione przełączniki śledzenia.|  
|[\<śledzenia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Zawiera nasłuchujących zbierania, przechowywania i trasy śledzenia wiadomości.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób osadzenia przełącznika śledzenia i odbiornik śledzenia wewnątrz  **\<system.diagnostics >** elementu. `General` Przełącznik śledzenia jest ustawiony na <xref:System.Diagnostics.TraceLevel> poziom. Odbiornik śledzenia `myListener` tworzy plik o nazwie `MyListener.log` i zapisuje dane wyjściowe do pliku.  
  
> [!NOTE]
>  W programie .NET Framework w wersji 2.0 tekst można użyć do określenia wartości dla przełącznika. Na przykład można określić `true` dla <xref:System.Diagnostics.BooleanSwitch> lub użyj tekst reprezentujący wartości wyliczenia, takich jak `Error` dla <xref:System.Diagnostics.TraceSwitch>. Wiersz `<add name="myTraceSwitch" value="Error" />` jest odpowiednikiem `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [Schemat ustawień debugowania i śledzenia](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)