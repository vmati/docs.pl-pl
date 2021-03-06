---
title: "Programowanie na poziomie kanału usługi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a1a6ef03b3ee0cc68809ec6ba80a7eadbc44cb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="service-channel-level-programming"></a>Programowanie na poziomie kanału usługi
W tym temacie opisano sposób zapisania [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplikacji usługi bez użycia <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> i jego skojarzony obiekt modelu.  
  
## <a name="receiving-messages"></a>Odbieranie komunikatów  
 Będzie gotowa do odbierania i przetwarzania wiadomości, wymagane są następujące kroki:  
  
1.  Utwórz powiązanie.  
  
2.  Tworzenie odbiornika kanałów.  
  
3.  Otworzyć odbiornika kanałów.  
  
4.  Żądania odczytu i wysyłać odpowiedzi.  
  
5.  Zamknij wszystkie obiekty kanału.  
  
#### <a name="creating-a-binding"></a>Tworzenie powiązania  
 Pierwszym etapem nasłuchiwania i odbierania wiadomości jest utworzenie powiązania. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]jest dostarczany z powiązaniami kilka wbudowanych lub dostarczane przez system, które mogą być używane bezpośrednio przez utworzenie wystąpienia jednego z nich. Ponadto można również utworzyć własne niestandardowe powiązanie przez utworzenie wystąpienia klasy CustomBinding, czyli, co oznacza kod w wyświetlania 1.  
  
 Poniższy przykład kodu tworzy wystąpienie <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> i dodaje <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> do jego kolekcję elementów, który jest kolekcją elementów, które są używane do tworzenia kanału stosu wiązania. W tym przykładzie ponieważ kolekcja elementów zawiera tylko <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, wynikowy stosu kanału ma kanał transportu HTTP.  
  
#### <a name="building-a-channellistener"></a>Tworzenie ChannelListener  
 Po utworzeniu powiązanie, nazywamy <!--zz<xref:System.ServiceModel.Channels.Binding.BuildChannelListener%601%2A?displayProperty=nameWithType>--> `System.ServiceModel.Channels.Binding.BuildChannelListener` do utworzenia odbiornika kanałów, gdzie parametr typu jest kształtu kanału do utworzenia. W tym przykładzie używamy <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> ponieważ chcemy nasłuchiwać komunikatów przychodzących w wymiany komunikatów żądania/odpowiedzi.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel>jest używany do odbierania komunikatów i odsyła odpowiedź komunikatów żądania. Wywoływanie <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=nameWithType> zwraca <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>, które mogą służyć do komunikatu żądania i przesyła komunikat odpowiedzi z powrotem.  
  
 Podczas tworzenia odbiornika, jest przekazywana adresu sieciowego, na którym ją nasłuchuje, w tym przypadku `http://localhost:8080/channelapp`. Ogólnie rzecz biorąc, każdy kanał transportu obsługuje co najmniej prawdopodobnie kilka Schematy adresów, na przykład transportu HTTP obsługuje schematy http i https.  
  
 Możemy również przekazać pustą <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=nameWithType> podczas tworzenia odbiornika. Parametr wiązania jest mechanizm do przekazania parametrów, które kontrolują sposób odbiornika powinny zostać skompilowane. W naszym przykładzie nie używamy tych parametrów, jest przekazywana pustej kolekcji.  
  
#### <a name="listening-for-incoming-messages"></a>Nasłuchiwanie przychodzących komunikatów  
 Następnie wywołaj <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> na początek akceptowanie kanałów i odbiornika. Zachowanie <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType> zależy od tego, czy transport jest zorientowany na połączenie lub bez połączenia. Dla transportu z nawiązaniem połączenia <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> blokuje dopóki nowego żądania połączenia efektem punktu, który zwraca nowy kanał, reprezentujący tego nowego połączenia. Dla transportu bez połączenia, takich jak HTTP <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> zwraca bezpośrednio z jednym i tylko kanału, który tworzy odbiornik transportu.  
  
 W tym przykładzie odbiornika zwraca kanału implementującego interfejs <xref:System.ServiceModel.Channels.IReplyChannel>. Do odbierania wiadomości dla tego kanału, możemy pierwsze wywołanie <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> on umieszczony w stanie gotowy do komunikacji. Następnie wywołaj <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> które bloki aż do nadejścia wiadomości.  
  
#### <a name="reading-the-request-and-sending-a-reply"></a>Odczytywanie żądania i wysyłania odpowiedzi  
 Gdy <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> zwraca <xref:System.ServiceModel.Channels.RequestContext>, uzyskujemy odebranej wiadomości przy użyciu jego <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A> właściwości. Możemy zapisać zawartości komunikatu akcji i treści, (który jest ciągiem założono).  
  
 Aby wysłać odpowiedzi, utworzymy nowy komunikat odpowiedzi w tym przypadku ponownie przekazywanie danych ciągu będziemy odebrana w żądaniu. Następnie wywołaj <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> do wysłania komunikatu odpowiedzi.  
  
#### <a name="closing-objects"></a>Zamykanie obiektów  
 Aby uniknąć przeciek zasobów, jest bardzo ważne, aby zamknąć obiekty używane podczas komunikacji, gdy nie są już wymagane. W tym przykładzie możemy zamknąć komunikat żądania, kontekst żądania, kanału i odbiornika.  
  
 Poniższy przykładowy kod przedstawia podstawowe usługi, w którym odbiornika kanałów odbiera tylko jeden komunikat. Rzeczywiste usługi temu akceptowanie kanałów i odbieranie wiadomości do momentu kończy działanie usługi.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]
