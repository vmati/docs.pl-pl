---
title: Tworzenie klasy Game1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 1e4fd15013f10667b397e010fff56b7bc6a0f641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="75d42-102">Tworzenie klasy Game1</span><span class="sxs-lookup"><span data-stu-id="75d42-102">Creating the Game1 Class</span></span>
<span data-ttu-id="75d42-103">Jak z wszystkich projektów Microsoft XNA pochodną klasy Game1 [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) klasy, która dostarcza inicjowania urządzenia podstawowe grafiki, gier logiki i renderowania kodu dla platformy XNA gier.</span><span class="sxs-lookup"><span data-stu-id="75d42-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="75d42-104">Klasy Game1 jest dość proste, ponieważ większość pracy w GamePiece i GamePieceCollection klasy.</span><span class="sxs-lookup"><span data-stu-id="75d42-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="75d42-105">Tworzenie kodu</span><span class="sxs-lookup"><span data-stu-id="75d42-105">Creating the Code</span></span>  
 <span data-ttu-id="75d42-106">Prywatne elementy członkowskie klasy składają się z **GamePieceCollection** obiektu do przechowywania figur, [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) obiektu, a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) obiekt używany do renderowania figur.</span><span class="sxs-lookup"><span data-stu-id="75d42-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="75d42-107">Podczas inicjowania gier te obiekty są tworzone.</span><span class="sxs-lookup"><span data-stu-id="75d42-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="75d42-108">Gdy [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) metoda jest wywoływana, figur są tworzone i przypisywane do **GamePieceCollection** obiektu.</span><span class="sxs-lookup"><span data-stu-id="75d42-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="75d42-109">Istnieją dwa typy figur.</span><span class="sxs-lookup"><span data-stu-id="75d42-109">There are two types of game pieces.</span></span> <span data-ttu-id="75d42-110">Współczynnik skali dla części zostanie zmieniona nieco, które są niektóre mniejsze lub większe niektóre elementy.</span><span class="sxs-lookup"><span data-stu-id="75d42-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="75d42-111">[Aktualizacji](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) metoda jest wywoływana wielokrotnie przez program XNA Framework gry jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="75d42-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="75d42-112">[Aktualizacji](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) wywołania metody **ProcessInertia** i **UpdateFromMouse** metody gry element kolekcji.</span><span class="sxs-lookup"><span data-stu-id="75d42-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="75d42-113">Te metody są opisane w [Tworzenie klasy GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="75d42-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="75d42-114">[Rysowania](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) metody jest również nazywany wielokrotnie przez program XNA Framework gry jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="75d42-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="75d42-115">[Rysowania](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) metoda przeprowadza renderowanie figur wywołując **rysowania** metody **GamePieceCollection** obiektu.</span><span class="sxs-lookup"><span data-stu-id="75d42-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="75d42-116">Ta metoda została opisana w[Tworzenie klasy GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="75d42-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="75d42-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75d42-117">See Also</span></span>  
 [<span data-ttu-id="75d42-118">Manipulacje i bezwładność</span><span class="sxs-lookup"><span data-stu-id="75d42-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="75d42-119">Korzystanie z manipulacji i bezwładności w aplikacji platformy XNA</span><span class="sxs-lookup"><span data-stu-id="75d42-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="75d42-120">Tworzenie klasy GamePiece</span><span class="sxs-lookup"><span data-stu-id="75d42-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="75d42-121">Tworzenie klasy GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="75d42-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="75d42-122">Listy pełnego kodu</span><span class="sxs-lookup"><span data-stu-id="75d42-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)