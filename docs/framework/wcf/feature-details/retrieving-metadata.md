---
title: Pobieranie metadanych
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc96c585ba55fbf63283d7cb23fae5b364b0465
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-metadata"></a>Pobieranie metadanych
Pobieranie metadanych to proces żądania i pobierania metadanych z punktu końcowego metadanych, takich jak punkt końcowy metadanych WS-MetadataExchange (MEX) lub punkt końcowy metadanych HTTP/GET.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Podczas pobierania metadanych z wiersza polecenia, używając Svcutil.exe  
 Można pobrać metadanych usługi przy użyciu żądania WS-MetadataExchange lub HTTP/GET [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) narzędzie i przekazywanie `/target:metadata` przełącznika i adresu. Svcutil.exe pobiera metadane pod określonym adresem i zapisuje plik na dysku. Używa svcutil.exe <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienie wewnętrznie i ładuje z konfiguracji <xref:System.ServiceModel.Description.IMetadataExchange> konfiguracji punktu końcowego, którego nazwa odpowiada schemat adresu przekazany do Svcutil.exe jako dane wejściowe.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Pobieranie metadanych programowo przy użyciu obiekt klasy MetadataExchangeClient  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]można pobrać metadanych usługi za pomocą standardowych protokołów, takich jak usługi WS-MetadataExchange i żądania HTTP/GET. Oba te protokoły są obsługiwane przez <xref:System.ServiceModel.Description.MetadataExchangeClient> typu. Możesz pobrać metadanych usługi przy użyciu <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> typu, podając adres punktu końcowego metadanych i opcjonalnie powiązanie. Powiązanie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienie może być jednym z powiązań domyślne z <xref:System.ServiceModel.Description.MetadataExchangeBindings> klasy statycznej, powiązanie dostarczone przez użytkownika lub powiązanie ładowane z konfiguracji punktu końcowego dla `IMetadataExchange` kontraktu. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Również może rozpoznać adres HTTP URL odwołania do metadanych za pomocą <xref:System.Net.HttpWebRequest> typu.  
  
 Domyślnie <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienia jest powiązany z pojedynczym <xref:System.ServiceModel.ChannelFactory> wystąpienia. Możesz zmienić lub Zastąp <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> wystąpienie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> przez zastąpienie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A> metoda wirtualna. Analogicznie, można zmienić lub Zastąp <xref:System.Net.HttpWebRequest> wystąpienie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> na wysyłanie żądań HTTP/GET przez zastąpienie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType> metoda wirtualna.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Instrukcje: używanie programu Svcutil.exe do pobierania dokumentów metadanych](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Pokazuje, jak używać Svcutil.exe do pobierania dokumentów metadanych.  
  
 [Instrukcje: dynamiczne uzyskiwanie metadanych powiązania przy użyciu klasy MetadataResolver](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Pokazuje, jak używać <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> można uzyskać metadanych powiązania dynamicznie w czasie wykonywania.  
  
 [Instrukcje: używanie elementu MetadataExchangeClient do pobierania metadanych](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Pokazuje, jak używać <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> klasę, aby pobrać pliki metadanych do <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> obiekt, który zawiera <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> obiektów do zapisu do plików lub do innych celów.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>
