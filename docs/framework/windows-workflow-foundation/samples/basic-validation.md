---
title: "Podstawowe sprawdzanie poprawności"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2712ca923d8608fe9e26dba380476993d35b6a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="basic-validation"></a>Podstawowe sprawdzanie poprawności
W tym przykładzie składa się z działania `CreateProduct`, która sprawdza, czy jego `Cost` argument jest mniejszy niż lub równy jego `Price` argumentu.  
  
## <a name="sample-details"></a>Szczegóły próbki  
 Istnieją dwa autorów, korzystających z weryfikacji, określony przez autora działania (tworzy logikę weryfikacji dla działania) i autor przepływu pracy, który wywołuje usługi weryfikacji dla określonego przepływu pracy. W tym scenariuszu określony przez autora działania chce wymusić, że każde wystąpienie jego działania musi mieć mniejszy lub równy koszt niż cena.  
  
 Określony przez autora działania (wewnątrz działania), musi:  
  
-   Tworzenie ograniczenia (`PriceGreaterThanCost`). Jest to, gdzie znajduje się całą logikę sprawdzania poprawności.  
  
-   Zastąpienie `System.Activities.CodeActivity.OnGetConstraints()` i Dodaj ograniczenie (`PriceGreaterThanCost`) do ograniczenia <xref:System.Collections.IList>.  
  
 Autor przepływu pracy (główny program), musi:  
  
-   Tworzenie przepływów pracy przy użyciu wystąpienia działania do sprawdzania poprawności (`CreateProduct`).  
  
-   Wywołanie <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, która zwraca <xref:System.Activities.Validation.ValidationResults> kolekcji <xref:System.Activities.Validation.ValidationError>.  
  
-   (Opcjonalnie) Drukuj <xref:System.Activities.Validation.ValidationError> obiektów.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, kompilacji, a następnie uruchom próbki  
  
1.  Otwórz rozwiązanie próbki BasicValidation.sln w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Tworzenie i uruchamianie rozwiązania.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`