---
title: "Wyjątki: raise — Funkcja (F#)"
description: "Dowiedz się, jak F # \"raise\" funkcja służy do wskazują, że wystąpił błąd lub wyjątkowych warunku."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a>Wyjątki: raise — Funkcja

`raise` Funkcja służy do wskazują, że wystąpił błąd lub wyjątkowych warunku. Obiekt wyjątku jest przechwytywane informacje o tym błędzie.


## <a name="syntax"></a>Składnia

```fsharp
raise (expression)
```

## <a name="remarks"></a>Uwagi
`raise` Funkcji generuje obiekt wyjątku i inicjuje proces odwijanie stosu. Proces odwijaniem stosu jest zarządzana przez środowisko uruchomieniowe języka wspólnego (CLR), dlatego działanie tego procesu jest taka sama jak w dowolnym języku .NET. Proces odwijaniem stosu jest wyszukiwania dla obsługi wyjątków odpowiadający wygenerowany wyjątek. Wyszukiwanie rozpoczyna się w bieżącym `try...with` wyrażenia, jeśli istnieje. W każdym wzorca `with` bloku zaznaczono w kolejności. W przypadku odnalezienia pasującego obsługi wyjątków wyjątek jest uznawany za obsługiwany; w przeciwnym razie stos jest oddzielić i `with` bloki zapasowej łańcuch wywołań są zaznaczone, aż do znalezienia zgodnego programu obsługi. Wszelkie `finally` bloków, które występują w łańcuchu wywołań także są wykonywane w kolejności jako cofa stosu.

`raise` Funkcji jest odpowiednikiem `throw` w języku C# lub języka C++. Użyj `reraise` w procedurze obsługi catch propagację ten sam wyjątek zapasowej łańcuch wywołań.

Następujący przykładowy kod, przedstawiający zastosowanie `raise` funkcji do generowania wyjątku.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

`raise` Funkcji można również zgłaszać wyjątki .NET, jak pokazano w poniższym przykładzie.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a>Zobacz też
[Obsługa wyjątków](index.md)

[Typy wyjątków](exception-types.md)

[Wyjątki: `try...with` wyrażenia](the-try-with-expression.md)

[Wyjątki: `try...finally` wyrażenia](the-try-finally-expression.md)

[Wyjątki: `failwith` — funkcja](the-failwith-function.md)

[Wyjątki: `invalidArg` — funkcja](the-invalidArg-function.md)
