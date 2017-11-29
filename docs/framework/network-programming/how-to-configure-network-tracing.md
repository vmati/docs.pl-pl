---
title: "Porady: Konfigurowanie śledzenia sieci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
caps.latest.revision: "23"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 12f328d58ef568c78d1e2c8a8ff564839cba9f3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="8b28e-102">Porady: Konfigurowanie śledzenia sieci</span><span class="sxs-lookup"><span data-stu-id="8b28e-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="8b28e-103">Plik konfiguracyjny aplikacji lub komputera zawiera ustawienia, które określają format i zawartość danych ze śledzenia sieci.</span><span class="sxs-lookup"><span data-stu-id="8b28e-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="8b28e-104">Przed rozpoczęciem procedury należy się upewnić, że śledzenie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="8b28e-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="8b28e-105">Aby uzyskać informacje na temat włączania śledzenia, zobacz [umożliwiające śledzenie sieci](../../../docs/framework/network-programming/enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="8b28e-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="8b28e-106">Plik konfiguracji komputera — machine.config — znajduje się w folderze %Windir%\Microsoft.NET\Framework w katalogu, w którym zainstalowano system Windows.</span><span class="sxs-lookup"><span data-stu-id="8b28e-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="8b28e-107">Plik jest dostępny oddzielny machine.config w folderach w obszarze %Windir%\Microsoft.NET\Framework dla każdej wersji platformy .NET zainstalowany na komputerze (na przykład C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config lub C:\Windows\ Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span><span class="sxs-lookup"><span data-stu-id="8b28e-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="8b28e-108">Ustawienia te można również wprowadzić w pliku konfiguracyjnym aplikacji. Ma on priorytet nad plikiem konfiguracyjnym komputera.</span><span class="sxs-lookup"><span data-stu-id="8b28e-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="8b28e-109">Aby skonfigurować funkcję śledzenia sieci</span><span class="sxs-lookup"><span data-stu-id="8b28e-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="8b28e-110">Dodaj następujące wiersze do odpowiedniego pliku konfiguracyjnego.</span><span class="sxs-lookup"><span data-stu-id="8b28e-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="8b28e-111">Wartości i opcje ustawień opisano w tabelach poniżej.</span><span class="sxs-lookup"><span data-stu-id="8b28e-111">The values and options for these settings are described in the tables below.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"  
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="8b28e-112">Po dodaniu nazwę `<switches>` bloku, dane wyjściowe śledzenia zawiera informacje z niektórych metod, powiązane z nazwą.</span><span class="sxs-lookup"><span data-stu-id="8b28e-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="8b28e-113">W tabeli poniżej opisano dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="8b28e-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="8b28e-114">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8b28e-114">Name</span></span>|<span data-ttu-id="8b28e-115">Skąd dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="8b28e-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="8b28e-116">Niektóre metody publiczne <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, i <xref:System.Net.Dns> klas</span><span class="sxs-lookup"><span data-stu-id="8b28e-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="8b28e-117">Niektóre metody publiczne <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, i <xref:System.Net.FtpWebResponse> klasy i SSL debugowania informacji (nieprawidłowe certyfikaty, Brak listy wystawców i błędy certyfikatu klienta.)</span><span class="sxs-lookup"><span data-stu-id="8b28e-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="8b28e-118">Niektóre metody publiczne <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, i <xref:System.Net.HttpListenerResponse> klasy.</span><span class="sxs-lookup"><span data-stu-id="8b28e-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="8b28e-119">Niektóre metody prywatne i wewnętrzne w `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="8b28e-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="8b28e-120">Niektóre metody publiczne <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler>, i <xref:System.Net.Http.WebRequestHandler> klasy.</span><span class="sxs-lookup"><span data-stu-id="8b28e-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="8b28e-121">Niektóre metody publiczne <xref:System.Net.WebSockets.ClientWebSocket> i <xref:System.Net.WebSockets.WebSocket> klasy.</span><span class="sxs-lookup"><span data-stu-id="8b28e-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="8b28e-122">W tabeli poniżej wymieniono atrybuty konfiguracyjne danych wyjściowych śledzenia.</span><span class="sxs-lookup"><span data-stu-id="8b28e-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="8b28e-123">Nazwa atrybutu</span><span class="sxs-lookup"><span data-stu-id="8b28e-123">Attribute name</span></span>|<span data-ttu-id="8b28e-124">Wartość atrybutu</span><span class="sxs-lookup"><span data-stu-id="8b28e-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="8b28e-125">Wymagane <xref:System.String> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="8b28e-126">Ustawia poziom szczegółowości danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="8b28e-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="8b28e-127">Wartości uzasadnionych `Critical`, `Error`, `Verbose`, `Warning`, i `Information`.</span><span class="sxs-lookup"><span data-stu-id="8b28e-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="8b28e-128">Ten atrybut musi być ustawiony na \<Dodaj nazwę > elementu \<przełączniki > element, jak pokazano w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8b28e-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="8b28e-129">Jest zwracany wyjątek, jeśli ten atrybut zostanie ustawiony na \<źródło > elementu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="8b28e-130">Opcjonalne <xref:System.Int32> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="8b28e-131">Ustawia maksymalną liczbę bajtów danych sieciowych w każdym zapisie ze śledzenia linii.</span><span class="sxs-lookup"><span data-stu-id="8b28e-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="8b28e-132">Wartość domyślna to 1024.</span><span class="sxs-lookup"><span data-stu-id="8b28e-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="8b28e-133">Ten atrybut musi być ustawiony na \<źródło > element, jak pokazano w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8b28e-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="8b28e-134">Jest zwracany wyjątek, jeśli ten atrybut zostanie ustawiony na elemencie w obszarze \<przełączniki > elementu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="8b28e-135">Opcjonalne <xref:System.String> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="8b28e-136">Ustaw `includehex` pokazanie śladów protokołu w formacie szesnastkowym i tekst.</span><span class="sxs-lookup"><span data-stu-id="8b28e-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="8b28e-137">Ustaw `protocolonly` do wyświetlenia tylko tekst.</span><span class="sxs-lookup"><span data-stu-id="8b28e-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="8b28e-138">Wartość domyślna to `includehex`.</span><span class="sxs-lookup"><span data-stu-id="8b28e-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="8b28e-139">Ten atrybut musi być ustawiony na \<przełączniki > element, jak pokazano w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8b28e-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="8b28e-140">Jest zwracany wyjątek, jeśli ten atrybut zostanie ustawiony na elemencie w obszarze \<źródło > elementu.</span><span class="sxs-lookup"><span data-stu-id="8b28e-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b28e-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b28e-141">See Also</span></span>  
 [<span data-ttu-id="8b28e-142">Interpretowanie Śledzenie sieci</span><span class="sxs-lookup"><span data-stu-id="8b28e-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="8b28e-143">Śledzenie sieci w programie .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b28e-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="8b28e-144">Włączanie śledzenia sieci</span><span class="sxs-lookup"><span data-stu-id="8b28e-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="8b28e-145">Wprowadzenie do Instrumentacji i śledzenie</span><span class="sxs-lookup"><span data-stu-id="8b28e-145">Introduction to Instrumentation and Tracing</span></span>](http://msdn.microsoft.com/en-us/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)