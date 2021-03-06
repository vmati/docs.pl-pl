---
title: "Ciąg interpolacji - C#"
description: "Dowiedz się, jak działa interpolacji ciągu w języku C# 6"
keywords: ".NET i .NET core C#, ciąg"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: ac19d4208da4f8ee6dd3e071ab70dbc41a0cd065
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="string-interpolation-in-c"></a>Ciąg interpolacji w języku C# #

Ciąg interpolacji jest sposób symbole zastępcze w ciągu zastępuje wartość zmiennej ciągu. Przed C# 6, jest sposób, w tym celu `System.String.Format`. To działanie jest zgoda, ale ponieważ używa numeru symbole zastępcze, może być trudniejsze do odczytu i pełniejsze.

Inne języki programowania miały interpolacji ciąg wbudowanych w języku jakiś czas. Na przykład w kodzie PHP:

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

W języku C# 6 koniec zostały tego stylu interpolacji ciągu. Można użyć `$` przed ciąg, aby wskazać, że należy zastąpić zmienne/wyrażenia ich wartości.

## <a name="prerequisites"></a>Wymagania wstępne
Należy skonfigurować komputer z usługami .NET core. Instrukcje instalacji można znaleźć na [.NET Core](https://www.microsoft.com/net/core) strony.
Można uruchomić tej aplikacji, w systemie Windows, Ubuntu Linux, macOS lub w kontenerze Docker. Należy zainstalować w edytorze kodu dotyczącego elementów ulubionych. Opisy poniżej użyj [Visual Studio Code](https://code.visualstudio.com/) czyli typu open source cross platform edytora. Można jednak użyć dowolnego narzędzia potrafisz.

## <a name="create-the-application"></a>Tworzenie aplikacji

Teraz, po zainstalowaniu wszystkich narzędzi, należy utworzyć nową aplikację platformy .NET Core. Aby użyć generatora wiersza polecenia, Utwórz katalog projektu, takie jak `interpolated`i uruchom następujące polecenie w ulubionych powłoki:

```
dotnet new console
```

To polecenie spowoduje utworzenie projektu podstawowe .NET core z pliku projektu *interpolated.csproj*i pliku kodu źródłowego, *Program.cs*. Konieczne będzie wykonanie `dotnet restore` do przywrócenia zależności niezbędne do skompilowania tego projektu.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Do wykonania programu, należy użyć `dotnet run`. Powinien zostać wyświetlony "tekst Hello, World" dane wyjściowe do konsoli.



## <a name="intro-to-string-interpolation"></a>Wprowadzenie do ciągu interpolacji

Z `System.String.Format`, określ "symbole zastępcze" w ciągu, który zastępuje parametrów po ciągu. Przykład:

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

Który dane wyjściowe obejmują "mojej nazwy jest gajów Matt".

W języku C# 6, zamiast `String.Format`, zdefiniuj ciągu interpolowanym dołączając ją z `$` symboli, a następnie za pomocą zmiennych bezpośrednio w ciągu. Przykład:

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

Nie trzeba używać tylko zmienne. Można użyć dowolnego wyrażenia w nawiasach. Przykład:

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

Czy wyjściowy, który:

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a>Jak działa interpolacji ciągu

W tle tej składni interpolacji ciągu jest przetłumaczyć String.Format przez kompilator. Tak, możesz zrobić [tego samego typu rzeczy wykonaniu przed z String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).

Na przykład można dodać uzupełniania i formatowania liczbowa:

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

Powyższe czy dane wyjściowe wyglądać mniej więcej tak:

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Jeśli nazwa zmiennej nie zostanie znaleziony, błąd w czasie kompilacji zostanie wygenerowany.

Przykład:

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

Kompilacja to spowoduje wyświetlenie błędów:
 
* `Cannot use local variable 'adj' before it is declared`- `adj` nie została zadeklarowana zmienna, do *po* ciągu interpolowanym.
* `The name 'otheranimal' does not exist in the current context`-zmiennej o nazwie `otheranimal` nawet nigdy nie został zadeklarowany.

## <a name="localization-and-internationalization"></a>Lokalizacja i internacjonalizacji

Obsługuje ciągu interpolowanym `IFormattable` i `FormattableString`, które mogą być przydatne w przypadku internacjonalizacji.

Domyślnie w ciągu interpolowanym używa bieżącej kultury. Aby korzystać z inną kulturę, można rzutować go jako`IFormattable`

Przykład:

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a>Wniosek 

W tym samouczku przedstawiono sposób korzystania z funkcji interpolacji ciągu języka C# 6. Zasadniczo jest bardziej zwięzły sposób zapisywania prosty `String.Format` instrukcji z niektórych ostrzeżenia dla bardziej zaawansowanych stosowania.
