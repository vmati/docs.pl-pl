---
title: '-docelowych: module (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b54ea9085ecc23d4a535d440d0634c997f22615
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="targetmodule-c-compiler-options"></a>/target:module (opcje kompilatora C#)
Ta opcja powoduje, że kompilator nie Generuj manifest zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie plik danych wyjściowych, utworzone przez kompilowania przy użyciu tej opcji będzie miał rozszerzenie modułu .netmodule.  
  
 Nie można załadować pliku, który nie ma manifestu zestawu przez .NET Framework środowisko uruchomieniowe języka wspólnego. Jednak taki plik można uwzględnić w manifeście zestawu zestawu za pomocą klasy [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Jeśli więcej niż jeden moduł jest tworzony w jednej kompilacji, [wewnętrzny](../../../csharp/language-reference/keywords/internal.md) typów w jeden moduł będzie dostępna dla innych modułów w kompilacji. Gdy kod w odwołaniach do modułów `internal` typów w innym module, a następnie obu modułów musi być włączona do manifestu zestawu za pomocą klasy **/addmodule**.  
  
 Tworzenie modułu nie jest obsługiwane w środowisku projektowym Visual Studio.  
  
 Aby uzyskać informacje dotyczące ustawiania tej opcji kompilatora programowo, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Przykład  
 Kompiluj `in.cs`, tworzenie `in.netmodule`:  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a>Zobacz też  
 [/ TARGET (opcje kompilatora C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)
