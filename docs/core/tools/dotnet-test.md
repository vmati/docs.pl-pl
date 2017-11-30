---
title: polecenie test DotNet - .NET Core interfejsu wiersza polecenia
description: "Polecenie test dotnet służy do wykonywania testów jednostkowych w danym projekcie."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 9eb5be38549711717c11767332bfc84920ea927a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="dotnet-test"></a><span data-ttu-id="b17e2-103">DotNet test</span><span class="sxs-lookup"><span data-stu-id="b17e2-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b17e2-104">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b17e2-104">Name</span></span>

<span data-ttu-id="b17e2-105">`dotnet test`— .NET testowanie sterowników używane do wykonywania testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="b17e2-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b17e2-106">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="b17e2-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b17e2-107">.NET core 2.x</span><span class="sxs-lookup"><span data-stu-id="b17e2-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b17e2-108">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="b17e2-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="b17e2-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b17e2-109">Description</span></span>

<span data-ttu-id="b17e2-110">`dotnet test` Polecenie służy do wykonywania testów jednostkowych w danym projekcie.</span><span class="sxs-lookup"><span data-stu-id="b17e2-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="b17e2-111">Testy jednostkowe są projektów aplikacji konsoli, które mają zależności w jednostce testowania framework (na przykład MSTest, NUnit lub xUnit) i uruchamiający dotnet framework testowania jednostki.</span><span class="sxs-lookup"><span data-stu-id="b17e2-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="b17e2-112">Te są dostarczane w pakietach NuGet i zostaną przywrócone jako zwykłej zależności projektu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="b17e2-113">Projekty testowe należy również określić uruchamiający.</span><span class="sxs-lookup"><span data-stu-id="b17e2-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="b17e2-114">To jest określany przy użyciu zwykłego `<PackageReference>` element, taki jak pokazano w poniższym przykładowym pliku projektu:</span><span class="sxs-lookup"><span data-stu-id="b17e2-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="b17e2-115">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b17e2-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b17e2-116">Określa ścieżkę do projektu testowego.</span><span class="sxs-lookup"><span data-stu-id="b17e2-116">Specifies a path to the test project.</span></span> <span data-ttu-id="b17e2-117">W przypadku jego pominięcia domyślnie bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b17e2-118">Opcje</span><span class="sxs-lookup"><span data-stu-id="b17e2-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b17e2-119">.NET core 2.x</span><span class="sxs-lookup"><span data-stu-id="b17e2-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b17e2-120">Używa niestandardowych adapterów testowych z określonej ścieżki w uruchomieniu testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b17e2-121">Definiuje konfigurację kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b17e2-121">Defines the build configuration.</span></span> <span data-ttu-id="b17e2-122">Wartość domyślna to `Debug`, ale konfiguracja projektu można zastąpić to ustawienie domyślne zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="b17e2-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="b17e2-123">Włącza moduł zbierający dane dla uruchomienia testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-123">Enables data collector for the test run.</span></span> <span data-ttu-id="b17e2-124">Aby uzyskać więcej informacji, zobacz [monitora i analizować uruchomienia testu](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="b17e2-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b17e2-125">Włącza tryb diagnostycznych dla testu platformy i zapisu komunikaty diagnostyczne do określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="b17e2-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b17e2-126">Wyszukuje pliki binarne testów dla określonego [framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b17e2-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b17e2-127">Odfiltrowuje testy w bieżącym projekcie przy użyciu danego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b17e2-128">Aby uzyskać więcej informacji, zobacz [opcję Szczegóły filtru](#filter-option-details) sekcji.</span><span class="sxs-lookup"><span data-stu-id="b17e2-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b17e2-129">Aby uzyskać dodatkowe informacje i przykłady dotyczące sposobu używania filtrowanie testów selektywnego jednostki, zobacz [przeprowadzanie testów jednostkowych selektywne](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b17e2-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b17e2-130">Drukuje krótkich pomocy dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b17e2-131">Określa Rejestrator dla wyników testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b17e2-132">Nie kompilacji projektu testowego przed jego uruchomieniem.</span><span class="sxs-lookup"><span data-stu-id="b17e2-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="b17e2-133">Nie wykonać przywracanie niejawne, podczas uruchamiania polecenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b17e2-134">Katalog, w którym można znaleźć plików binarnych do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="b17e2-135">Katalog, w której będzie można umieścić wyników testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="b17e2-136">Określony katalog zostanie utworzony, jeśli nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="b17e2-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b17e2-137">Ustawienia używane podczas uruchamiania testów.</span><span class="sxs-lookup"><span data-stu-id="b17e2-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b17e2-138">Lista wszystkich odnalezionych testów w bieżącym projekcie.</span><span class="sxs-lookup"><span data-stu-id="b17e2-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b17e2-139">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b17e2-140">Dozwolone wartości to `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, i `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b17e2-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b17e2-141">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="b17e2-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b17e2-142">Używa niestandardowych adapterów testowych z określonej ścieżki w uruchomieniu testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b17e2-143">Definiuje konfigurację kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b17e2-143">Defines the build configuration.</span></span> <span data-ttu-id="b17e2-144">Wartość domyślna to `Debug`, ale konfiguracja projektu można zastąpić to ustawienie domyślne zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="b17e2-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b17e2-145">Włącza tryb diagnostycznych dla testu platformy i zapisu komunikaty diagnostyczne do określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="b17e2-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b17e2-146">Wyszukuje pliki binarne testów dla określonego [framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b17e2-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b17e2-147">Odfiltrowuje testy w bieżącym projekcie przy użyciu danego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b17e2-148">Aby uzyskać więcej informacji, zobacz [opcję Szczegóły filtru](#filter-option-details) sekcji.</span><span class="sxs-lookup"><span data-stu-id="b17e2-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b17e2-149">Aby uzyskać dodatkowe informacje i przykłady dotyczące sposobu używania filtrowanie testów selektywnego jednostki, zobacz [przeprowadzanie testów jednostkowych selektywne](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b17e2-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b17e2-150">Drukuje krótkich pomocy dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b17e2-151">Określa Rejestrator dla wyników testu.</span><span class="sxs-lookup"><span data-stu-id="b17e2-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b17e2-152">Nie kompilacji projektu testowego przed jego uruchomieniem.</span><span class="sxs-lookup"><span data-stu-id="b17e2-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b17e2-153">Katalog, w którym można znaleźć plików binarnych do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b17e2-154">Ustawienia używane podczas uruchamiania testów.</span><span class="sxs-lookup"><span data-stu-id="b17e2-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b17e2-155">Lista wszystkich odnalezionych testów w bieżącym projekcie.</span><span class="sxs-lookup"><span data-stu-id="b17e2-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b17e2-156">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="b17e2-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b17e2-157">Dozwolone wartości to `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, i `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b17e2-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b17e2-158">Przykłady</span><span class="sxs-lookup"><span data-stu-id="b17e2-158">Examples</span></span>

<span data-ttu-id="b17e2-159">Uruchom testy w projekcie w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="b17e2-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="b17e2-160">Uruchom testy `test1` projektu:</span><span class="sxs-lookup"><span data-stu-id="b17e2-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="b17e2-161">Szczegóły opcji filtru</span><span class="sxs-lookup"><span data-stu-id="b17e2-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b17e2-162">`<Expression>`ma format `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="b17e2-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="b17e2-163">`<property>`atrybut `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="b17e2-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="b17e2-164">Właściwości obsługiwanych przez platform testów jednostkowych popularnych są następujące:</span><span class="sxs-lookup"><span data-stu-id="b17e2-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="b17e2-165">Struktury testowej</span><span class="sxs-lookup"><span data-stu-id="b17e2-165">Test Framework</span></span> | <span data-ttu-id="b17e2-166">Obsługiwanych właściwości</span><span class="sxs-lookup"><span data-stu-id="b17e2-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b17e2-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="b17e2-167">MSTest</span></span>         | <ul><li><span data-ttu-id="b17e2-168">Element FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b17e2-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="b17e2-169">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b17e2-169">Name</span></span></li><li><span data-ttu-id="b17e2-170">className</span><span class="sxs-lookup"><span data-stu-id="b17e2-170">ClassName</span></span></li><li><span data-ttu-id="b17e2-171">Priorytet</span><span class="sxs-lookup"><span data-stu-id="b17e2-171">Priority</span></span></li><li><span data-ttu-id="b17e2-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="b17e2-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="b17e2-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="b17e2-173">Xunit</span></span>          | <ul><li><span data-ttu-id="b17e2-174">Element FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b17e2-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="b17e2-175">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="b17e2-175">DisplayName</span></span></li><li><span data-ttu-id="b17e2-176">Cechy</span><span class="sxs-lookup"><span data-stu-id="b17e2-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="b17e2-177">`<operator>` Opisuje relację między właściwości i wartość:</span><span class="sxs-lookup"><span data-stu-id="b17e2-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="b17e2-178">Operator</span><span class="sxs-lookup"><span data-stu-id="b17e2-178">Operator</span></span> | <span data-ttu-id="b17e2-179">Funkcja</span><span class="sxs-lookup"><span data-stu-id="b17e2-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="b17e2-180">Dokładnego dopasowania</span><span class="sxs-lookup"><span data-stu-id="b17e2-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="b17e2-181">Nie dokładnego dopasowania</span><span class="sxs-lookup"><span data-stu-id="b17e2-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="b17e2-182">Zawiera</span><span class="sxs-lookup"><span data-stu-id="b17e2-182">Contains</span></span>        |

<span data-ttu-id="b17e2-183">`<value>`jest to ciąg.</span><span class="sxs-lookup"><span data-stu-id="b17e2-183">`<value>` is a string.</span></span> <span data-ttu-id="b17e2-184">Wszystkie wyszukiwania są bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="b17e2-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="b17e2-185">Wyrażenia bez `<operator>` jest automatycznie traktowane jako `contains` na `FullyQualifiedName` właściwości (na przykład `dotnet test --filter xyz` jest taka sama jak `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="b17e2-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="b17e2-186">Może być częścią wyrażenia z operatorami warunkowego:</span><span class="sxs-lookup"><span data-stu-id="b17e2-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="b17e2-187">Operator</span><span class="sxs-lookup"><span data-stu-id="b17e2-187">Operator</span></span> | <span data-ttu-id="b17e2-188">Funkcja</span><span class="sxs-lookup"><span data-stu-id="b17e2-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="b17e2-189">LUB</span><span class="sxs-lookup"><span data-stu-id="b17e2-189">OR</span></span>       |
| `&`      | <span data-ttu-id="b17e2-190">AND</span><span class="sxs-lookup"><span data-stu-id="b17e2-190">AND</span></span>      |

<span data-ttu-id="b17e2-191">Może być częścią wyrażenia w nawiasach przy użyciu operatorów warunkowych (na przykład `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="b17e2-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="b17e2-192">Aby uzyskać dodatkowe informacje i przykłady dotyczące sposobu używania filtrowanie testów selektywnego jednostki, zobacz [przeprowadzanie testów jednostkowych selektywne](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b17e2-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b17e2-193">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b17e2-193">See also</span></span>

 [<span data-ttu-id="b17e2-194">Struktury i cele</span><span class="sxs-lookup"><span data-stu-id="b17e2-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="b17e2-195">Katalogu .NET core środowiska uruchomieniowego identyfikator (RID)</span><span class="sxs-lookup"><span data-stu-id="b17e2-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)