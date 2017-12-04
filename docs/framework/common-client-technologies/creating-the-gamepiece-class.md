---
title: "GamePiece Sınıfı Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a27a86-ac1c-47be-b477-cb4b819459d3
caps.latest.revision: "9"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 989883034b30c3ec67f5441c5512418643546519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-gamepiece-class"></a><span data-ttu-id="4ff64-102">GamePiece Sınıfı Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4ff64-102">Creating the GamePiece Class</span></span>
<span data-ttu-id="4ff64-103">**GamePiece** sınıfı yalıtır Microsoft XNA oyun parça görüntü yükleme, oyun parça sitedeki fare durumunu izlemek, fare yakalama, düzenleme ve eylemsizlik işleme sağlamak için gerekli tüm işlevlere ve Oyun parça görünümü bağlantı noktasının sınırlarını ulaştığında Sıçrama yeteneği sağlar.</span><span class="sxs-lookup"><span data-stu-id="4ff64-103">The **GamePiece** class encapsulates all the functionality required to load a Microsoft XNA game piece image, track the state of the mouse in relation to the game piece, capture the mouse, provide manipulation and inertia processing, and provide bouncing capability when the game piece reaches the limits of the view port.</span></span>  
  
## <a name="private-members"></a><span data-ttu-id="4ff64-104">Özel üyeler</span><span class="sxs-lookup"><span data-stu-id="4ff64-104">Private Members</span></span>  
 <span data-ttu-id="4ff64-105">Üstündeki **GamePiece** sınıfı, birkaç özel üyelerin bildirildiğinde.</span><span class="sxs-lookup"><span data-stu-id="4ff64-105">At the top of the **GamePiece** class, several private members are declared.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privatemembers)]  
  
## <a name="public-properties"></a><span data-ttu-id="4ff64-106">Ortak Özellikler</span><span class="sxs-lookup"><span data-stu-id="4ff64-106">Public Properties</span></span>  
 <span data-ttu-id="4ff64-107">Bu özel üyelerin üç ortak özellikler sunulur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-107">Three of these private members are exposed through public properties.</span></span> <span data-ttu-id="4ff64-108">**Ölçek** ve **PieceColor** özellikleri etkinleştirin uygulamanın sırasıyla ölçeği ve parça rengini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4ff64-108">The **Scale** and **PieceColor** properties enable the application to specify the scale and the color of the piece, respectively.</span></span> <span data-ttu-id="4ff64-109">**Sınırları** özelliği başka bir sınır kendisi, ne zaman bir parça başka Kaplama gibi işlemek için kullanılacak bir parça etkinleştirmek için gösterilir.</span><span class="sxs-lookup"><span data-stu-id="4ff64-109">The **Bounds** property is exposed to enable one piece to use the bounds of another to render itself, such as when one piece should overlay another.</span></span> <span data-ttu-id="4ff64-110">Aşağıdaki kod genel özelliklerin bildirimi gösterir.</span><span class="sxs-lookup"><span data-stu-id="4ff64-110">The following code shows the declaration of the public properties.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PublicProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_publicproperties)]  
  
## <a name="class-constructor"></a><span data-ttu-id="4ff64-111">Sınıf oluşturucusu</span><span class="sxs-lookup"><span data-stu-id="4ff64-111">Class Constructor</span></span>  
 <span data-ttu-id="4ff64-112">Oluşturucusu **GamePiece** sınıfı aşağıdaki parametreleri kabul eder:</span><span class="sxs-lookup"><span data-stu-id="4ff64-112">The constructor for the **GamePiece** class accepts the following parameters:</span></span>  
  
-   <span data-ttu-id="4ff64-113">A [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) türü.</span><span class="sxs-lookup"><span data-stu-id="4ff64-113">A [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) type.</span></span> <span data-ttu-id="4ff64-114">Özel üye burada geçirilen başvuru atanan `spriteBatch`ve kullanılan erişimi [SpriteBatch.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.draw.aspx) oyun parça kendisini işler yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-114">The reference passed here is assigned to the private member `spriteBatch`, and is used to access the [SpriteBatch.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.draw.aspx) method when the game piece renders itself.</span></span> <span data-ttu-id="4ff64-115">Ayrıca, [GraphicsDevice](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.graphicsdevice.aspx) özelliği oluşturmak için kullanılan [doku](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.texture.aspx) oyun parçası olan ve oyun parça karşılaştığında saptamak amacıyla görünüm bağlantı noktası boyutunu edinmek için ilişkili nesne bir Pencere sınır böylece parça Sıçrama.</span><span class="sxs-lookup"><span data-stu-id="4ff64-115">In addition, the [GraphicsDevice](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.graphicsdevice.aspx) property is used to create the [Texture](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.texture.aspx) object associated with the game piece, and to obtain the size of the view port in order to detect when the game piece encounters a window boundary so that the piece can bounce.</span></span>  
  
-   <span data-ttu-id="4ff64-116">Oyun parça için kullanılacak görüntünün dosya adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="4ff64-116">A string that specifies the file name of the image to use for the game piece.</span></span>  
  
 <span data-ttu-id="4ff64-117">Ayrıca Oluşturucusu oluşturur bir <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> nesne ve bir <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> nesne ve bunların olayları için olay işleyicileri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-117">The constructor also creates a <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> object and an <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> object, and establishes event handlers for their events.</span></span>  
  
 <span data-ttu-id="4ff64-118">Aşağıdaki kod Oluşturucusu gösterir **GamePiece** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4ff64-118">The following code shows the constructor for the **GamePiece** class.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Constructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_constructor)]  
  
## <a name="capturing-mouse-input"></a><span data-ttu-id="4ff64-119">Fare girişi yakalama</span><span class="sxs-lookup"><span data-stu-id="4ff64-119">Capturing Mouse Input</span></span>  
 <span data-ttu-id="4ff64-120">**UpdateFromMouse** yöntemdir fare oyun parça sınırlar içinde ve ne zaman algılamak için fare düğmesini yayımlandı fare düğmesine basıldığında algılamayla sorumlu.</span><span class="sxs-lookup"><span data-stu-id="4ff64-120">The **UpdateFromMouse** method is responsible for detecting when a mouse button is pressed while the mouse is within the boundaries of the game piece, and for detecting when the mouse button has been released.</span></span>  
  
 <span data-ttu-id="4ff64-121">(Fare parça sınırları içinde iken) sol fare düğmesine basıldığında, bu yöntem bu oyun parça fare yakalandı ve denetleme işleme başlar belirten bir bayrak ayarlar.</span><span class="sxs-lookup"><span data-stu-id="4ff64-121">When the left mouse button is pressed (while the mouse is inside the piece boundaries), this method sets a flag to indicate that this game piece has captured the mouse, and begins manipulation processing.</span></span>  
  
 <span data-ttu-id="4ff64-122">Denetleme işleme, bir dizi oluşturarak başlatıldığında <xref:System.Windows.Input.Manipulations.Manipulator2D> nesneleri ve bunlara geçirme <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-122">Manipulation processing is started by creating an array of <xref:System.Windows.Input.Manipulations.Manipulator2D> objects and passing them to the <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> object.</span></span> <span data-ttu-id="4ff64-123">Bu, manipülatörleri (Bu durumda bir tek manipulator) olarak değerlendirmek ve işleme olaylarını işleme işlemci neden olur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-123">This causes the manipulation processor to evaluate the manipulators (in this case a single manipulator), and raise manipulation events.</span></span>  
  
 <span data-ttu-id="4ff64-124">Ayrıca, sürükle gerçekleştiğini noktası kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="4ff64-124">In addition, the point at which the drag is occurring is saved.</span></span> <span data-ttu-id="4ff64-125">Bu, daha sonra sırasında kullanılır <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> delta çeviri ayarlamak için olay noktayı sürükleyin arkasında hale oyun parça swings böylece değerleri.</span><span class="sxs-lookup"><span data-stu-id="4ff64-125">This is used later during the <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> event to adjust the delta translation values so that the game piece swings into line behind the drag point.</span></span>  
  
 <span data-ttu-id="4ff64-126">Son olarak, bu yöntem, fare yakalama durumunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="4ff64-126">Finally, this method returns the state of the mouse capture.</span></span> <span data-ttu-id="4ff64-127">Böylece [GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) birden çok oyun parça olduğunda yakalama yönetmek için nesnesi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-127">This enables the [GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) object to manage capturing when there are multiple game pieces.</span></span>  
  
 <span data-ttu-id="4ff64-128">Aşağıdaki kodda gösterildiği **UpdateFromMouse** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-128">The following code shows the **UpdateFromMouse** method.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_updatefrommouse)]  
  
## <a name="processing-manipulations"></a><span data-ttu-id="4ff64-129">İşlemeleri işleme</span><span class="sxs-lookup"><span data-stu-id="4ff64-129">Processing Manipulations</span></span>  
 <span data-ttu-id="4ff64-130">Düzenleme işlemi başladığında, <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started> olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-130">When manipulation begins, the <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started> event is raised.</span></span> <span data-ttu-id="4ff64-131">Bu olay işleyicisi oluştuğunu ve ayarlar eylemsizlik işlemeyi durdurur *processInertia* bayrağını `false`.</span><span class="sxs-lookup"><span data-stu-id="4ff64-131">The handler for this event stops inertia processing if it is occurring, and sets the *processInertia* flag to `false`.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationStarted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationstarted)]  
  
 <span data-ttu-id="4ff64-132">İşleme değişiklikle ilişkili değerler olarak <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-132">As the values associated with the manipulation change, the <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> event is raised.</span></span> <span data-ttu-id="4ff64-133">Bu olay işleyicisi oyun parça konum ve dönüş değerleri için değişiklik yapmak için olay bağımsız değişken geçirildi delta değerleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="4ff64-133">The handler for this event uses the delta values passed in the event arguments to make changes to the position and rotation values of the game piece.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationdelta)]  
  
 <span data-ttu-id="4ff64-134">Tüm işleme ile ilişkili manipülatörleri (Bu durumda, bir tek manipulator içinde) kaldırıldığında, işleme işlemci başlatır <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed> olay.</span><span class="sxs-lookup"><span data-stu-id="4ff64-134">When all of the manipulators (in this case, a single manipulator) that are associated with a manipulation are removed, the manipulation processor raises the <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed> event.</span></span> <span data-ttu-id="4ff64-135">Bu olay işleyicisi bu olay bağımsız değişkenleri tarafından bildirilen üzere eylemsizlik işlemcinin ilk velocities ayarlayarak işlemleri eylemsizlik başlar ve ayarlar *processInertia* bayrağını `true`.</span><span class="sxs-lookup"><span data-stu-id="4ff64-135">The handler for this event begins inertia processing by setting the initial velocities of the inertia processor to those reported by the event arguments, and sets the *processInertia* flag to `true`.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationcompleted)]  
  
## <a name="processing-inertia"></a><span data-ttu-id="4ff64-136">Eylemsizlik işleme</span><span class="sxs-lookup"><span data-stu-id="4ff64-136">Processing Inertia</span></span>  
 <span data-ttu-id="4ff64-137">Eylemsizlik işleme Açısal ve doğrusal velocities, konumu (çevirisi) koordinatları ve döndürme, yeni değerleri extrapolates gibi <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-137">As inertia processing extrapolates new values for angular and linear velocities, position (translation) coordinates, and rotation, the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> event is raised.</span></span> <span data-ttu-id="4ff64-138">Bu olay işleyicisi, konum ve oyun parça dönüşünü değiştirmek için olay bağımsız değişken geçirildi delta değerleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="4ff64-138">The handler for this event uses the delta values passed in the event arguments to modify the position and rotation of the game piece.</span></span>  
  
 <span data-ttu-id="4ff64-139">Görünüm bağlantı noktası sınırlarının dışına taşıma oyun parçadaki yeni koordinatlar neden oluyorsa eylemsizlik işleme hızı ters çevrilir.</span><span class="sxs-lookup"><span data-stu-id="4ff64-139">If the new coordinates result in the game piece moving beyond the view port boundaries, the velocity of the inertia processing is reversed.</span></span> <span data-ttu-id="4ff64-140">Bu, oyun parça, karşılaştı görünüm bağlantı noktası sınır gelmesine neden olur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-140">This causes the game piece to bounce off the view port boundary that it has encountered.</span></span>  
  
 <span data-ttu-id="4ff64-141">Özelliklerini değiştiremezsiniz bir <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> dış değer bulmayı çalışırken nesne.</span><span class="sxs-lookup"><span data-stu-id="4ff64-141">You cannot change the properties of an <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> object while it is running extrapolation.</span></span> <span data-ttu-id="4ff64-142">Bu nedenle, X veya Y hız Ters kaydederken, olay işleyicisi ilk eylemsizlik çağırarak durdurur <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Complete%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-142">Therefore, when reversing the X or Y velocity, the event handler first stops inertia by calling the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Complete%2A> method.</span></span> <span data-ttu-id="4ff64-143">Ardından (Sünger davranışını ayarlanır) geçerli hız değerler yeni ilk hız değerleri atar ve ayarlar *processInertia* bayrağını `true`.</span><span class="sxs-lookup"><span data-stu-id="4ff64-143">It then assigns the new initial velocity values to be the current velocity values (adjusted for sponge behavior), and sets the *processInertia* flag to `true`.</span></span>  
  
 <span data-ttu-id="4ff64-144">Aşağıdaki kod için olay işleyicisini gösterir <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> olay.</span><span class="sxs-lookup"><span data-stu-id="4ff64-144">The following code shows the event handler for the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> event.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiadelta)]  
  
 <span data-ttu-id="4ff64-145">Eylemsizlik işlem tamamlandığında, eylemsizlik işlemci başlatır <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Completed> olay.</span><span class="sxs-lookup"><span data-stu-id="4ff64-145">When inertia processing is complete, the inertia processor raises the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Completed> event.</span></span> <span data-ttu-id="4ff64-146">Bu olay işleyicisi ayarlar *processInertia* bayrağını `false`.</span><span class="sxs-lookup"><span data-stu-id="4ff64-146">The handler for this event sets the *processInertia* flag to `false`.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiacompleted)]  
  
 <span data-ttu-id="4ff64-147">Şu ana kadar sunulan mantığı hiçbiri gerçekte gerçekleşmek üzere eylemsizlik dış değer bulmayı neden olur.</span><span class="sxs-lookup"><span data-stu-id="4ff64-147">None of the logic presented so far actually causes inertia extrapolation to occur.</span></span> <span data-ttu-id="4ff64-148">Bu, gerçekleştirilir **ProcessInertia** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4ff64-148">This is accomplished in the **ProcessInertia** method.</span></span> <span data-ttu-id="4ff64-149">Bu yöntem oyun güncelleştirme döngüden sürekli olarak adlandırılır ( [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) yöntemi) denetler *processInertia* bayrağı ayarlanmış `true`ve bu durumda, çağıran <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Process%2A> yöntem.</span><span class="sxs-lookup"><span data-stu-id="4ff64-149">This method, which is called repeatedly from the game update loop (the [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method) checks to see if the *processInertia* flag is set to `true`, and if so, calls the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Process%2A> method.</span></span> <span data-ttu-id="4ff64-150">Bu yöntem nedenler görevlendirebilir gerçekleşmesi için ve başlatır çağırma <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> olay.</span><span class="sxs-lookup"><span data-stu-id="4ff64-150">Calling this method causes extrapolation to occur, and raises the <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta> event.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_ProcessInertia](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_processinertia)]  
  
 <span data-ttu-id="4ff64-151">Draw yöntemi aşırı yüklemelerinden birini çağrılıncaya kadar oyun parça gerçekte işlenmez.</span><span class="sxs-lookup"><span data-stu-id="4ff64-151">The game piece is not actually rendered until one of the Draw method overloads is called.</span></span> <span data-ttu-id="4ff64-152">Bu yöntem ilk yüklemesini tekrar tekrar oyun çizim döngüden adlı ( [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) yöntemi).</span><span class="sxs-lookup"><span data-stu-id="4ff64-152">The first overload of this method is called repeatedly from the game draw loop (the [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method).</span></span> <span data-ttu-id="4ff64-153">Geçerli konumu, döndürme ve ölçek Etkenler oyun parça işler.</span><span class="sxs-lookup"><span data-stu-id="4ff64-153">This renders the game piece with the current position, rotation, and scale factors.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Draw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_draw)]  
  
## <a name="additional-properties"></a><span data-ttu-id="4ff64-154">Ek Özellikler</span><span class="sxs-lookup"><span data-stu-id="4ff64-154">Additional Properties</span></span>  
 <span data-ttu-id="4ff64-155">Üç özel özellikleri tarafından kullanılan **GamePiece** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4ff64-155">Three private properties are used by the **GamePiece** class.</span></span>  
  
1.  <span data-ttu-id="4ff64-156">**Zaman damgası** – işleme ve eylemsizlik işlemcileri tarafından kullanılmak üzere bir zaman damgası değeri alır.</span><span class="sxs-lookup"><span data-stu-id="4ff64-156">**Timestamp** – Gets a timestamp value to be used by the manipulation and inertia processors.</span></span>  
  
2.  <span data-ttu-id="4ff64-157">**X** – alır veya ayarlar oyun parça X koordinatı.</span><span class="sxs-lookup"><span data-stu-id="4ff64-157">**X** – Gets or sets the X coordinate of the game piece.</span></span> <span data-ttu-id="4ff64-158">İsabet testi ve işleme işlemci Özet konumu için kullanılan sınırları ayarlarken, ayarlar.</span><span class="sxs-lookup"><span data-stu-id="4ff64-158">When setting, adjusts the bounds used for hit testing and the pivot location of the manipulation processor.</span></span>  
  
3.  <span data-ttu-id="4ff64-159">**Y** – alır veya ayarlar oyun parça Y koordinatı.</span><span class="sxs-lookup"><span data-stu-id="4ff64-159">**Y** – Gets or sets the Y coordinate of the game piece.</span></span> <span data-ttu-id="4ff64-160">İsabet testi ve işleme işlemci Özet konumu için kullanılan sınırları ayarlarken, ayarlar.</span><span class="sxs-lookup"><span data-stu-id="4ff64-160">When setting, adjusts the bounds used for hit testing and the pivot location of the manipulation processor.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privateproperties)]  
  
## <a name="see-also"></a><span data-ttu-id="4ff64-161">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4ff64-161">See Also</span></span>  
 [<span data-ttu-id="4ff64-162">Düzenlemeler ve eylemsizlik</span><span class="sxs-lookup"><span data-stu-id="4ff64-162">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="4ff64-163">XNA uygulamasında düzenlemeleri ve Eylemsizliği kullanma</span><span class="sxs-lookup"><span data-stu-id="4ff64-163">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="4ff64-164">GamePieceCollection sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="4ff64-164">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="4ff64-165">Game1 sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="4ff64-165">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)