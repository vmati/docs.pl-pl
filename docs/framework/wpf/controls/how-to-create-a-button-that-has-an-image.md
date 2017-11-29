---
title: "Jak utworzyć przycisk, który posiada obraz"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa3aa5454629d53fd8864df6a4f204e22028208f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="20d5c-102">Jak utworzyć przycisk, który posiada obraz</span><span class="sxs-lookup"><span data-stu-id="20d5c-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="20d5c-103">W tym przykładzie pokazano, jak dołączyć obrazu na <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="20d5c-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20d5c-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="20d5c-104">Example</span></span>  
 <span data-ttu-id="20d5c-105">Poniższy przykład tworzy dwa <xref:System.Windows.Controls.Button> kontrolki.</span><span class="sxs-lookup"><span data-stu-id="20d5c-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="20d5c-106">Jeden <xref:System.Windows.Controls.Button> zawiera tekst, a drugi zawiera obraz.</span><span class="sxs-lookup"><span data-stu-id="20d5c-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="20d5c-107">Obraz znajduje się w folderze o nazwie danych, który jest podfolderem folderu projektu w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="20d5c-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="20d5c-108">Gdy użytkownik kliknie <xref:System.Windows.Controls.Button> mający obrazu, tła i tekstu z innych <xref:System.Windows.Controls.Button> zmienić.</span><span class="sxs-lookup"><span data-stu-id="20d5c-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="20d5c-109">Ten przykład tworzy <xref:System.Windows.Controls.Button> steruje się za pomocą znacznika, ale kod używany do zapisu <xref:System.Windows.Controls.Primitives.ButtonBase.Click> procedury obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="20d5c-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="20d5c-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="20d5c-110">See Also</span></span>  
 [<span data-ttu-id="20d5c-111">Formanty</span><span class="sxs-lookup"><span data-stu-id="20d5c-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="20d5c-112">Biblioteka formantów</span><span class="sxs-lookup"><span data-stu-id="20d5c-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)