---
title: "Delegaty (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6649537238af38e073eeb8747487822d058b7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="delegates-c-programming-guide"></a>Delegaty (Przewodnik programowania w języku C#)
A [delegować](../../../csharp/language-reference/keywords/delegate.md) jest typem, który reprezentuje odwołania do metody z listą określonego parametru i typ zwracany. Podczas tworzenia wystąpienia delegata można skojarzyć jego wystąpienie z dowolną metodą mającą zgodny podpis i zwracany typ. Za pośrednictwem wystąpienia delegata można wywołać metodę.  
  
 Delegaty służą do przekazywania metod jako argumentów do innych metod. Programy obsługi zdarzeń to po prostu metody, które są wywoływane za pośrednictwem delegatów. Użytkownik tworzy metodę niestandardową, a klasa, taka jak formant systemu Windows, może wywołać tę metodę, gdy wystąpi określone zdarzenie. W poniższym przykładzie pokazano deklarację delegata:  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 Do delegata można przypisać każdą metodę z dowolnej dostępnej klasy lub struktury, która pasuje do typu delegata. Może to być metoda statyczna lub metoda wystąpienia. Umożliwia to programowe zmienianie wywołań metod, a także podłączanie nowego kodu do istniejących klas.  
  
> [!NOTE]
>  W kontekście przeciążania metod podpis metody nie zawiera wartości zwracanej. Jednak w kontekście delegatów podpis zawiera wartość zwracaną. Innymi słowy metoda musi mieć taki sam zwracany typ jak delegat.  
  
 Ta możliwość odwoływania się do metody jak do parametru sprawia, że delegaty idealnie nadają się do definiowania metod wywoływania zwrotnego. Na przykład odwołanie do metody, która porównuje dwa obiekty można przekazać jako argument do algorytmu sortowania. Kod porównania znajduje się w osobnej procedurze, więc algorytm sortowania można napisać w bardziej ogólny sposób.  
  
## <a name="delegates-overview"></a>Omówienie delegatów  
 Delegaty mają następujące właściwości:  
  
-   Delegaty są podobne do wskaźników funkcji w języku C++, ale są bezpieczne dla typów.  
  
-   Delegaty zezwalają na przekazywanie metod jako parametrów.  
  
-   Delegatów można używać do definiowania metod wywoływania zwrotnego.  
  
-   Delegaty można łączyć w łańcuch; na przykład w jednym zdarzeniu można wywołać wiele metod.  
  
-   Metody nie muszą dokładnie pasować do typu delegata. Aby uzyskać więcej informacji, zobacz [przy użyciu wariancji w Delegatach](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
-   C# w wersji 2.0 wprowadzono koncepcję [metod anonimowych](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), które umożliwiają bloki kodu, które mają być przekazywane jako parametry zamiast oddzielnie zdefiniowanych — metoda. W języku C# 3.0 wprowadzono wyrażenia lambda, które stanową wygodniejszy sposób pisania bloków kodu w tekście. Zarówno metody anonimowe, jak i wyrażenia lambda (w pewnych kontekstach) są kompilowane na typy delegatów. Te funkcje są obecnie nazywane łącznie funkcjami anonimowymi. Aby uzyskać więcej informacji na temat wyrażeń lambda, zobacz [funkcje anonimowe](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="in-this-section"></a>W tej sekcji  
  
-   [Używanie delegatów](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [Kiedy należy używać delegatów zamiast interfejsów (C# przewodnik programowania w języku)](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [Obiekty delegowane z nazwanego vs. Metody anonimowe](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [Metody anonimowe](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [Korzystanie z wariancji w Delegatach](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [Porady: łączenie obiektów delegowanych (obiekty delegowane multiemisji)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [Porady: deklarowanie, wystąpienia i użycie delegowania](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a>Polecane rozdziały książki  
 [Obiekty delegowane, zdarzeń i wyrażenia Lambda](http://go.microsoft.com/fwlink/?LinkId=195395) w [C# 3.0 Cookbook, trzecia edycja: ponad 250 rozwiązań dla programistów języka C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Delegaci i zdarzenia](http://go.microsoft.com/fwlink/?LinkId=195418) w [Learning C# 3.0: wzorca podstawy języka C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Delegate>  
 [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
 [Zdarzenia](../../../csharp/programming-guide/events/index.md)
