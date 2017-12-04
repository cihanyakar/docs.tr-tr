---
title: "Game1 Sınıfı Oluşturma"
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
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="46a61-102">Game1 Sınıfı Oluşturma</span><span class="sxs-lookup"><span data-stu-id="46a61-102">Creating the Game1 Class</span></span>
<span data-ttu-id="46a61-103">Game1 sınıfı türetilen tüm Microsoft XNA projelerle gibi [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) temel grafik cihaz başlatma, oyun mantığı ve kod oyunlar için XNA işleme sağlayan sınıf.</span><span class="sxs-lookup"><span data-stu-id="46a61-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="46a61-104">Game1 sınıfı işlerin çoğunu içinde GamePiece ve GamePieceCollection sınıfları için oldukça basittir.</span><span class="sxs-lookup"><span data-stu-id="46a61-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="46a61-105">Kod oluşturma</span><span class="sxs-lookup"><span data-stu-id="46a61-105">Creating the Code</span></span>  
 <span data-ttu-id="46a61-106">Sınıfı için özel üyelerin oluşur bir **GamePieceCollection** oyun parçaları tutacak nesne bir [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) nesnesi ve [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) kullanılan nesnesi Oyun parça işlenecek.</span><span class="sxs-lookup"><span data-stu-id="46a61-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="46a61-107">Oyun başlatılması sırasında bu nesneler oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="46a61-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="46a61-108">Zaman [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) yöntemi çağrıldığında, oyun parçaları oluşturulur ve atanan **GamePieceCollection** nesnesi.</span><span class="sxs-lookup"><span data-stu-id="46a61-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="46a61-109">Oyun parça iki tür vardır.</span><span class="sxs-lookup"><span data-stu-id="46a61-109">There are two types of game pieces.</span></span> <span data-ttu-id="46a61-110">Parçaları ölçek çarpanını biraz vardır, bazı küçük ve bazı büyük parçalarını şekilde değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="46a61-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="46a61-111">[Güncelleştirme](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) yöntemi çağrıldığında art arda XNA Framework tarafından oyun çalışırken.</span><span class="sxs-lookup"><span data-stu-id="46a61-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="46a61-112">[Güncelleştirme](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) yöntem çağrılarını **ProcessInertia** ve **UpdateFromMouse** oyun yöntemlere parçası koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="46a61-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="46a61-113">Bu yöntemler açıklanmıştır [GamePieceCollection sınıfı oluşturma](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="46a61-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="46a61-114">[Çizin](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) yöntemi olarak da adlandırılır art arda XNA Framework tarafından oyun çalışırken.</span><span class="sxs-lookup"><span data-stu-id="46a61-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="46a61-115">[Çizin](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) yöntemi çağrılarak oyun parça işlemeyi gerçekleştirir **çizin** yöntemi **GamePieceCollection** nesnesi.</span><span class="sxs-lookup"><span data-stu-id="46a61-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="46a61-116">Bu yöntem açıklanan[GamePieceCollection sınıfı oluşturma](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="46a61-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="46a61-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="46a61-117">See Also</span></span>  
 [<span data-ttu-id="46a61-118">Düzenlemeler ve eylemsizlik</span><span class="sxs-lookup"><span data-stu-id="46a61-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="46a61-119">XNA uygulamasında düzenlemeleri ve Eylemsizliği kullanma</span><span class="sxs-lookup"><span data-stu-id="46a61-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="46a61-120">GamePiece sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="46a61-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="46a61-121">GamePieceCollection sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="46a61-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="46a61-122">Tam kod listeleri</span><span class="sxs-lookup"><span data-stu-id="46a61-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)