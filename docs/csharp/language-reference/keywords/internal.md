---
title: "internal (odwołanie w C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords: internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a3b115022ed2b38dfcfbbfad3c5fc00e0203b255
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="internal-c-reference"></a><span data-ttu-id="6f768-102">internal (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="6f768-102">internal (C# Reference)</span></span>
<span data-ttu-id="6f768-103">`internal` — Słowo kluczowe jest [modyfikator dostępu](../../../csharp/language-reference/keywords/access-modifiers.md) typy i elementy członkowskie typu.</span><span class="sxs-lookup"><span data-stu-id="6f768-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="6f768-104">Ta strona zawiera `internal` dostępu.</span><span class="sxs-lookup"><span data-stu-id="6f768-104">This page covers `internal` access.</span></span> <span data-ttu-id="6f768-105">`internal` — Słowo kluczowe jest również częścią [ `protected internal` ](./protected-internal.md) modyfikator dostępu.</span><span class="sxs-lookup"><span data-stu-id="6f768-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="6f768-106">Wewnętrzne typy i elementy członkowskie są dostępne tylko w plikach w tym samym zestawie, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="6f768-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="6f768-107">Porównanie `internal` z innych modyfikatorów dostępu, zobacz [poziomów ułatwień dostępu](../../../csharp/language-reference/keywords/accessibility-levels.md) i [modyfikatory dostępu](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="6f768-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="6f768-108">Aby uzyskać więcej informacji na temat zestawów, zobacz [zestawy i Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f768-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="6f768-109">Zazwyczaj wewnętrznego dostępu jest używane w programowania opartego na składnik ponieważ dzięki grupy składników do współpracy w sposób prywatnej bez narażania z resztą kodu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6f768-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="6f768-110">Na przykład można podać struktura umożliwiająca tworzenie graficznych interfejsów użytkownika `Control` i `Form` klasy, które współpracują przy użyciu elementów członkowskich z dostępem do wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="6f768-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="6f768-111">Ponieważ te elementy członkowskie są wewnętrzne, ich nie są widoczne dla kodu, który używa programu framework.</span><span class="sxs-lookup"><span data-stu-id="6f768-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="6f768-112">Jest błąd, aby odwoływać się do typu lub elementu członkowskiego o wewnętrznej dostęp spoza zestawu, w którym został zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="6f768-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f768-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="6f768-113">Example</span></span>  
 <span data-ttu-id="6f768-114">Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="6f768-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="6f768-115">Wewnętrzna klasa podstawowa zawiera pierwszy plik `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="6f768-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="6f768-116">W drugim pliku, próba utworzenia wystąpienia `BaseClass` spowoduje błąd.</span><span class="sxs-lookup"><span data-stu-id="6f768-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="6f768-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="6f768-117">Example</span></span>  
 <span data-ttu-id="6f768-118">W tym przykładzie należy używać tych samych plików, które są używane w przykładzie 1 i zmienić poziom dostępności `BaseClass` do `public`.</span><span class="sxs-lookup"><span data-stu-id="6f768-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="6f768-119">Również zmienić poziom dostępności elementu członkowskiego `IntM` do `internal`.</span><span class="sxs-lookup"><span data-stu-id="6f768-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="6f768-120">W takim przypadku można utworzyć wystąpienia klasy, ale nie masz dostępu do wewnętrznego elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="6f768-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f768-121">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="6f768-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f768-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f768-122">See Also</span></span>  
 [<span data-ttu-id="6f768-123">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="6f768-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6f768-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="6f768-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6f768-125">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="6f768-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6f768-126">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="6f768-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="6f768-127">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="6f768-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="6f768-128">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="6f768-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="6f768-129">publiczny</span><span class="sxs-lookup"><span data-stu-id="6f768-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="6f768-130">prywatne</span><span class="sxs-lookup"><span data-stu-id="6f768-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="6f768-131">chronione</span><span class="sxs-lookup"><span data-stu-id="6f768-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)