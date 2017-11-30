---
title: '&lt;SeeAlso&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a1acbf2ee8f416e28987cc9d63dd3bf6d8c2dcf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="a3666-102">&lt;SeeAlso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3666-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="a3666-103">Określa łącze, które pojawia się w sekcji Zobacz też.</span><span class="sxs-lookup"><span data-stu-id="a3666-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3666-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3666-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3666-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a3666-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="a3666-106">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywoływania z bieżącym środowisku kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a3666-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="a3666-107">Kompilator sprawdza, czy element podanego kodu istnieje i przekazuje `member` do nazwy elementu w danych wyjściowych XML.</span><span class="sxs-lookup"><span data-stu-id="a3666-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="a3666-108">`member`musi występować w podwójny cudzysłów ("").</span><span class="sxs-lookup"><span data-stu-id="a3666-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3666-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3666-109">Remarks</span></span>  
 <span data-ttu-id="a3666-110">Użyj `<seealso>` tag, aby określić tekst, który ma być wyświetlany w sekcji Zobacz też.</span><span class="sxs-lookup"><span data-stu-id="a3666-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="a3666-111">Użyj [ \<zobacz >](../../../visual-basic/language-reference/xmldoc/see.md) można określić łącze od w tekście.</span><span class="sxs-lookup"><span data-stu-id="a3666-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="a3666-112">Kompiluj z użyciem [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) na przetwarzanie komentarzy dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="a3666-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3666-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3666-113">Example</span></span>  
 <span data-ttu-id="a3666-114">W tym przykładzie użyto `<seealso>` tagów w `DoesRecordExist` uwagi sekcji, aby odwołać się do `UpdateRecord` metody.</span><span class="sxs-lookup"><span data-stu-id="a3666-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a3666-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3666-115">See Also</span></span>  
 [<span data-ttu-id="a3666-116">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="a3666-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)