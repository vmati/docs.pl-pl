---
title: "Nazw zestawów i bibliotek DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76584e0d22b6e651dfd851675a72d1f0cb70feb1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-assemblies-and-dlls"></a>Nazw zestawów i bibliotek DLL
Zestaw jest jednostką wdrożenia i tożsamości dla programów kodu zarządzanego. Mimo że zestawy mogą znajdować się co najmniej jednego pliku, zwykle zestawu mapuje jeden do jednego z biblioteki DLL. W związku z tym w tej sekcji opisano tylko DLL konwencji nazewnictwa, które następnie mogą być mapowane na zestawie konwencji nazewnictwa.  
  
 **CZY ✓** wybierz nazw dla Twojego zestawu bibliotek DLL, które sugeruje duże zestawy funkcji, takich jak dane systemowe.  
  
 Nazwa pliku zestawu i biblioteki DLL nie musi odpowiadać nazwy przestrzeni nazw, ale można wykonać nazwę przestrzeni nazw w nazwach zestawów. Regułą jest nazwa biblioteki DLL, na podstawie prefiksu wspólnej zestawów zawartych w zestawie. Na przykład zestaw o dwie przestrzenie nazw, `MyCompany.MyTechnology.FirstFeature` i `MyCompany.MyTechnology.SecondFeature`, może być wywoływana `MyCompany.MyTechnology.dll`.  
  
 **ROZWAŻ ✓** nazewnictwa bibliotek DLL według następującego wzorca:  
  
 `<Company>.<Component>.dll`  
  
 gdzie `<Component>` zawiera co najmniej jedną klauzulę oddzielona kropkami. Na przykład:  
  
 `Litware.Controls.dll`.,  
  
 *Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*  
  
 *Drukowane uprawnieniami wariancji x edukacji, Inc. z [Framework zaleceń dotyczących projektowania: konwencje, Idioms i wzorce dla bibliotek .NET wielokrotnego użytku, wydanie 2](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina i Abrams Brada opublikowane 22 Oct 2008 przez Professional Addison-Wesley jako część serii rozwoju systemu Windows firmy Microsoft.*  
  
## <a name="see-also"></a>Zobacz też  
 [Struktura — zalecenia dotyczące projektowania](../../../docs/standard/design-guidelines/index.md)  
 [Wskazówki dotyczące nazewnictwa](../../../docs/standard/design-guidelines/naming-guidelines.md)
