---
title: "&lt;zobacz&gt; (C# przewodnik programowania w języku)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 065c85ba411794858c8c4d70de0ac1467da1fe56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="818df-102">&lt;zobacz&gt; (C# przewodnik programowania w języku)</span><span class="sxs-lookup"><span data-stu-id="818df-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="818df-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="818df-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="818df-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="818df-104">Parameters</span></span>  
 <span data-ttu-id="818df-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="818df-105">cref = " `member`"</span></span>  
 <span data-ttu-id="818df-106">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywoływania z bieżącym środowisku kompilacji.</span><span class="sxs-lookup"><span data-stu-id="818df-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="818df-107">Kompilator sprawdza, czy element podanego kodu istnieje i przekazuje `member` do nazwy elementu w danych wyjściowych XML. Miejsce *elementu członkowskiego* w podwójny cudzysłów ("").</span><span class="sxs-lookup"><span data-stu-id="818df-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="818df-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="818df-108">Remarks</span></span>  
 <span data-ttu-id="818df-109">\<Zobacz > należy określić łącze znajdujących się w tekście.</span><span class="sxs-lookup"><span data-stu-id="818df-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="818df-110">Użyj [ \<seealso >](../../../csharp/programming-guide/xmldoc/seealso.md) aby wskazać, że tekst powinna zostać umieszczona w sekcji Zobacz też.</span><span class="sxs-lookup"><span data-stu-id="818df-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="818df-111">Użyj [cref — atrybut](../../../csharp/programming-guide/xmldoc/cref-attribute.md) można utworzyć wewnętrznego hiperłącza do stron dokumentacji dla elementów kodu.</span><span class="sxs-lookup"><span data-stu-id="818df-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="818df-112">Kompiluj z użyciem [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) na przetwarzanie komentarzy dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="818df-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="818df-113">W poniższym przykładzie przedstawiono \<zobacz > tagu w sekcji podsumowania.</span><span class="sxs-lookup"><span data-stu-id="818df-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="818df-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="818df-114">See Also</span></span>  
 [<span data-ttu-id="818df-115">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="818df-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="818df-116">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="818df-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)