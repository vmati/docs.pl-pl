---
title: "Opcje kompilatora Visual Basic według kategorii"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f554893858b9475b3d94a669a094206be6a5c3fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Opcje kompilatora Visual Basic według kategorii
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Kompilatora wiersza polecenia podano zamiast kompilowanie programów z poziomu [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] zintegrowane środowisko programistyczne (IDE). Poniżej przedstawiono listę [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] opcje wiersza polecenia kompilatora posortowane według kategorii funkcjonalności.  
  
## <a name="compiler-output"></a>Dane wyjściowe kompilatora  
  
|Opcja|Cel|  
|---|---|  
|[/ nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Pomija informacje transparentu kompilatora.|  
|[/ utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Wyświetla kompilatora, dane wyjściowe przy użyciu kodowania UTF-8.|  
|[/ verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Wyświetla dodatkowe informacje podczas kompilacji.|  
|`/modulename:<string>`|Określ nazwę modułu źródła|  
|[/ preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Określanie języka danych wyjściowych kompilatora.|  
  
## <a name="optimization"></a>Optymalizacja  
  
|Opcja|Cel|  
|---|---|  
|[/ filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Określa lokalizację były wyrównane w sekcjach pliku wyjściowego.|  
|[/ optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Włącza/wyłącza optymalizacje.|  
  
## <a name="output-files"></a>Pliki wyjściowe  
  
|Opcja|Cel|  
|---|---|  
|[/ doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Komentarze dokumentacji procesów do pliku XML.|  
|[/ netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Ustawia kompilatora do docelowego [!INCLUDE[Compact](~/includes/compact-md.md)].|  
|[/ out](../../../visual-basic/reference/command-line-compiler/out.md)|Określa plik wyjściowy.|  
|[/ TARGET](../../../visual-basic/reference/command-line-compiler/target.md)|Określa format danych wyjściowych.|  
  
## <a name="net-assemblies"></a>Zestawów platformy .NET  
  
|Opcja|Cel|  
|---|---|  
|[/ addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Powoduje, że kompilator wszystkie wpisz informacje z określonym dostępnych plików do projektu są obecnie kompilacji.|  
|[/ DelaySign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Określa, czy zestaw zostanie podpisany całkowicie czy częściowo.|  
|[/ Imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importuje przestrzeni nazw z określonego zestawu.|  
|[/ KeyContainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Określa nazwę kontenera kluczy parę kluczy zapewnić silnej nazwy zestawu.|  
|[/ KeyFile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Określa plik zawierający klucz lub parę kluczy, aby zapewnić silnej nazwy zestawu.|  
|[/ libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Określa lokalizację zestawów odwołuje się [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opcji.|  
|[/ Reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importuje metadane z zestawu.|  
|[/ moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Określa nazwę zestawu, który będzie należeć modułu.|  
|`/analyzer`|Uruchom analizatorów z tego zestawu (krótka wersja: /)|  
|`/additionalfile`|Nazwy dodatkowych plików bezpośrednio nie wpływają na generowanie kodu, które mogą być używane przez analizatory do produkcji błędy lub ostrzeżenia.|  
  
## <a name="debuggingerror-checking"></a>Sprawdzanie Debugowanie błędów  
  
|Opcja|Cel|  
|---|---|  
|[/ bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Tworzy plik zawierający informacje, które ułatwia zgłosić usterkę.|  
|[/ Debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Generuje informacje o debugowaniu.|  
|[/ nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Pomija możliwość generowania ostrzeżeń kompilatora.|  
|[/ quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Uniemożliwia wyświetlanie kodu dotyczące składni błędów i ostrzeżeń kompilatora.|  
|[/ removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Wyłącza sprawdzanie przepełnienia liczby całkowitej.|  
|[/ warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Zamienia ostrzeżenia błędy.|  
|`/ruleset:<file>`|Określ plik zestaw reguł, który powoduje wyłączenie diagnostyczne zależne.|  
  
## <a name="help"></a>Pomoc  
  
|Opcja|Cel|  
|---|---|  
|[/?](../../../visual-basic/reference/command-line-compiler/help.md)|Wyświetla opcje kompilatora. To polecenie jest taki sam jak określenie `/help` opcji. Kompilacja nie występuje.|  
|[/ Help](../../../visual-basic/reference/command-line-compiler/help.md)|Wyświetla opcje kompilatora. To polecenie jest taki sam jak określenie `/?` opcji. Kompilacja nie występuje.|  
  
## <a name="language"></a>Język  
  
|Opcja|Cel|  
|---|---|  
|[/ langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Określ wersję językową: 9 &#124; 9.0 &#124; 10 &#124; 10.0 &#124; 11 &#124; 11.0.|  
|[/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Wymusza jawnej deklaracji zmiennych.|  
|[/ optionstrict —](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Wymusza ścisłe zasady semantyki.|  
|[/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Określa, czy porównywanie ciągów powinna być binarnego lub korzystają bezpośrednio z semantyki tekst specyficzne dla ustawień regionalnych.|  
|[/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Umożliwia użycie wnioskowania o typie lokalnym w deklaracjach zmiennych.|  
  
## <a name="preprocessor"></a>Preprocesor  
  
|Opcja|Cel|  
|---|---|  
|[/ define](../../../visual-basic/reference/command-line-compiler/define.md)|Definiuje symbole kompilacji warunkowej.|  
  
## <a name="resources"></a>Resources  
  
|Opcja|Cel|  
|---|---|  
|[/ linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Tworzy łącze do zasobów zarządzanych.|  
|[/ Resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Osadza zarządzanego zasobu w zestawie.|  
|[/ win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Wstawia plik .ico do pliku wyjściowego.|  
|[/ win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Wstawia zasobów Win32 do pliku wyjściowego.|  
  
## <a name="miscellaneous"></a>Inne  
  
|Opcja|Cel|  
|---|---|  
|[@ (Określ plik odpowiedzi)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Określa plik odpowiedzi.|  
|[/ BaseAddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Określa adres podstawowy biblioteki dll.|  
|[/ CodePage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Określa stronę kodową do używania wszystkich plików kodu źródłowego w kompilacji.|  
|[/ errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Określa sposób [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilatora Zgłoś wewnętrzne błędy kompilatora.|  
|[/ highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Określa, że jądra systemu Windows czy określonego pliku wykonywalnego obsługuje wysokiej entropii losowe generowanie układu przestrzeni adresów (ASLR).|  
|[/ main](../../../visual-basic/reference/command-line-compiler/main.md)|Określa klasę, która zawiera `Sub``Main` procedurę do użycia podczas uruchamiania.|  
|[/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Kompiluje z Vbc.rsp|  
|[/ nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Powoduje, że kompilator nie do standardowych bibliotek.|  
|[/ nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Instruuje kompilator, aby nie osadzania manifestu żadnych aplikacji w pliku wykonywalnego.|  
|[/ platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Określa platformę procesora kompilatora docelowe pliku wyjściowego.|  
|[/ recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Podkatalogi wyszukiwania dla plików źródłowych do skompilowania.|  
|[/ rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Określa przestrzeń nazw dla wszystkich deklaracji typów.|  
|[/ sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Określa lokalizację pliku Mscorlib.dll i pliku Microsoft.VisualBasic.dll.|  
|[/ vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Określa, że kompilator powinien kompilować bez odwołanie w Visual Basic Runtime Library lub odwołanie do biblioteki środowiska uruchomieniowego określonych.|  
|[/ win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identyfikuje użytkownika aplikacji plik manifestu Win32 do osadzenia pliku przenośny plik wykonywalny (PE) projektu.|  
|`/parallel[+&#124;-]`|Określa, czy używać współbieżnych kompilacji (+).|  
|`/checksumalgorithm:<alg>`|Określ algorytm oblicza sumę kontrolną pliku źródłowego, przechowywane w pliku PDB.  Obsługiwane są następujące wartości: SHA1 (ustawienie domyślne) lub SHA256.|  
  
## <a name="see-also"></a>Zobacz też  
 [Opcje kompilatora Visual Basic w porządku alfabetycznym](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md)  
 [Wprowadzenie do projektanta projektu](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)  
 [Opcje kompilatora C# alfabetycznym](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [Opcje kompilatora C# według kategorii](../../../csharp/language-reference/compiler-options/listed-by-category.md)
