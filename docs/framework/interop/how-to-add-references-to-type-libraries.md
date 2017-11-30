---
title: "Porady: dodawanie odwołań do bibliotek typów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e5bbc99c3c40b0864a7c1c25cb79a3d7c26e3a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="51319-102">Porady: dodawanie odwołań do bibliotek typów</span><span class="sxs-lookup"><span data-stu-id="51319-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="51319-103">Program Visual Studio generuje zestawu międzyoperacyjnego zawierający metadane, podczas dodawania odwołania do biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="51319-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="51319-104">Jeśli podstawowy zestaw międzyoperacyjny jest dostępny, Visual Studio korzysta z istniejącego zestawu przed wygenerowaniem nowego zestawu międzyoperacyjnego.</span><span class="sxs-lookup"><span data-stu-id="51319-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="51319-105">Aby dodać odwołanie do biblioteki typów w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51319-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="51319-106">Zainstaluj plik COM DLL lub EXE na komputerze, chyba, że plik Windows Setup.exe przeprowadza instalację.</span><span class="sxs-lookup"><span data-stu-id="51319-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="51319-107">Wybierz **projektu**, **Dodaj odwołanie**.</span><span class="sxs-lookup"><span data-stu-id="51319-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="51319-108">W Menedżerze odwołania, zaznacz opcję **COM**.</span><span class="sxs-lookup"><span data-stu-id="51319-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="51319-109">Wybierz bibliotekę typów, z listy lub Przeglądaj w poszukiwaniu pliku .tlb.</span><span class="sxs-lookup"><span data-stu-id="51319-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="51319-110">Wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="51319-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="51319-111">W Eksploratorze rozwiązań Otwórz menu skrótów dla odwołania został właśnie dodany, a następnie wybierz pozycję **właściwości**.</span><span class="sxs-lookup"><span data-stu-id="51319-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="51319-112">W **właściwości** okna, upewnij się, że **Osadź typy międzyoperacyjne** właściwość jest ustawiona na **True**.</span><span class="sxs-lookup"><span data-stu-id="51319-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="51319-113">Powoduje osadzanie informacji o typie dla typów COM w plikach wykonywalnych, eliminując konieczność wdrożenia podstawowe zestawy międzyoperacyjne z aplikacją programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="51319-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51319-114">Menu i opcje okna dialogowego może się różnić w zależności od wersji programu Visual Studio używasz.</span><span class="sxs-lookup"><span data-stu-id="51319-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="51319-115">Aby dodać odwołanie do biblioteki typów dla kompilacji wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="51319-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="51319-116">Generowanie zestawu międzyoperacyjnego, zgodnie z opisem w [porady: generowanie zestawy międzyoperacyjne z bibliotek typów](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="51319-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="51319-117">Użyj [/Link (opcje kompilatora C#)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) lub [/Link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) typy — opcja kompilatora o nazwie zestawu międzyoperacyjnego osadzanie informacji o typie dla modelu COM w Twoje pliki wykonywalne.</span><span class="sxs-lookup"><span data-stu-id="51319-117">Use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51319-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="51319-118">See Also</span></span>  
 [<span data-ttu-id="51319-119">Importowanie biblioteki typów jako zestawu</span><span class="sxs-lookup"><span data-stu-id="51319-119">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="51319-120">Udostępnianie składników modelu COM aplikacji .NET Framework</span><span class="sxs-lookup"><span data-stu-id="51319-120">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="51319-121">Wskazówki: Osadzanie informacji o typie z zestawów Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="51319-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="51319-122">Wskazówki: Osadzanie typów z zarządzanych zestawów</span><span class="sxs-lookup"><span data-stu-id="51319-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="51319-123">/ Link (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="51319-123">/link (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="51319-124">/ Link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51319-124">/link (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/link.md)