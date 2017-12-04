---
title: "Klavye Olaylarını Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 19bad48188a039baeeb6365a2cd38671f83fca4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-keyboard-events"></a><span data-ttu-id="4bcbd-102">Klavye Olaylarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="4bcbd-102">Using Keyboard Events</span></span>
<span data-ttu-id="4bcbd-103">Windows Forms programlarının çoğu klavye girişi klavye olayları işleme göre işler.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-103">Most Windows Forms programs process keyboard input by handling the keyboard events.</span></span> <span data-ttu-id="4bcbd-104">Bu konu, her olay ve sağlanan verileri her olay için kullanmak ne zaman ayrıntılar dahil olmak üzere klavye olayları genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-104">This topic provides an overview of the keyboard events, including details on when to use each event and the data that is supplied for each event.</span></span>  <span data-ttu-id="4bcbd-105">Ayrıca bkz. [olay işleyicilerine genel bakış (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [olaylara genel bakış (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4bcbd-105">Also see [Event Handlers Overview (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Events Overview (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\)).</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="4bcbd-106">Klavye olayları</span><span class="sxs-lookup"><span data-stu-id="4bcbd-106">Keyboard Events</span></span>  
 <span data-ttu-id="4bcbd-107">Windows Forms kullanıcı klavye tuşuna bastığında oluşan iki olayları ve bir kullanıcı bir klavye tuşu bıraktığında bir olay sağlar:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-107">Windows Forms provides two events that occur when a user presses a keyboard key and one event when a user releases a keyboard key:</span></span>  
  
-   <span data-ttu-id="4bcbd-108"><xref:System.Windows.Forms.Control.KeyDown> Olay oluştuktan sonra</span><span class="sxs-lookup"><span data-stu-id="4bcbd-108">The <xref:System.Windows.Forms.Control.KeyDown> event occurs once</span></span>  
  
-   <span data-ttu-id="4bcbd-109"><xref:System.Windows.Forms.Control.KeyPress> Birden çok kez ne zaman bir kullanıcı aynı tuşunu tutan oluşabilir olay.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-109">The <xref:System.Windows.Forms.Control.KeyPress> event, which can occur multiple times when a user holds down the same key.</span></span>  
  
-   <span data-ttu-id="4bcbd-110"><xref:System.Windows.Forms.Control.KeyUp> Olayı, bir kullanıcı bir anahtar zaman serbest sonra oluşur.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-110">The <xref:System.Windows.Forms.Control.KeyUp> event occurs once when a user releases a key.</span></span>  
  
 <span data-ttu-id="4bcbd-111">Bir kullanıcı bir tuşuna bastığında klavye iletiyi karakter anahtar ya da fiziksel bir anahtar belirtir yükseltmek için hangi olay tabanlı Windows Forms belirler.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-111">When a user presses a key, Windows Forms determines which event to raise based on whether the keyboard message specifies a character key or a physical key.</span></span> <span data-ttu-id="4bcbd-112">Karakter ve fiziksel anahtarlar hakkında daha fazla bilgi için bkz: [nasıl klavye girişi çalışır](../../../docs/framework/winforms/how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="4bcbd-112">For more information about character and physical keys, see [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md).</span></span>  
  
 <span data-ttu-id="4bcbd-113">Aşağıdaki tabloda, üç klavye olaylarını açıklar.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-113">The following table describes the three keyboard events.</span></span>  
  
|<span data-ttu-id="4bcbd-114">Klavye olayı</span><span class="sxs-lookup"><span data-stu-id="4bcbd-114">Keyboard event</span></span>|<span data-ttu-id="4bcbd-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4bcbd-115">Description</span></span>|<span data-ttu-id="4bcbd-116">Sonuçları</span><span class="sxs-lookup"><span data-stu-id="4bcbd-116">Results</span></span>|  
|--------------------|-----------------|-------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|<span data-ttu-id="4bcbd-117">Bir kullanıcı bir fiziksel tuşuna bastığında bu olay tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-117">This event is raised when a user presses a physical key.</span></span>|<span data-ttu-id="4bcbd-118">İşleyicisi <xref:System.Windows.Forms.Control.KeyDown> alır:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-118">The handler for <xref:System.Windows.Forms.Control.KeyDown> receives:</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-119">A <xref:System.Windows.Forms.KeyEventArgs> sağlayan parametresi <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (fiziksel klavye düğmesi belirtir) özelliği.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-119">A <xref:System.Windows.Forms.KeyEventArgs> parameter, which provides the <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> property (which specifies a physical keyboard button).</span></span></li><li><span data-ttu-id="4bcbd-120"><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Özelliği (SHIFT, CTRL ya da ALT).</span><span class="sxs-lookup"><span data-stu-id="4bcbd-120">The <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property (SHIFT, CTRL, or ALT).</span></span></li><li><span data-ttu-id="4bcbd-121"><xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> (Anahtar kodu ve değiştirici birleştirir) özelliği.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-121">The <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property (which combines the key code and modifier).</span></span> <span data-ttu-id="4bcbd-122"><xref:System.Windows.Forms.KeyEventArgs> Parametresi de sağlar:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-122">The <xref:System.Windows.Forms.KeyEventArgs> parameter also provides:</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-123"><xref:System.Windows.Forms.KeyEventArgs.Handled%2A> Temel denetim anahtar almasını önlemek için ayarlanabilir özelliği.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-123">The <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property, which can be set to prevent the underlying control from receiving the key.</span></span></li><li><span data-ttu-id="4bcbd-124"><xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> Gizlemek için kullanılan özellik <xref:System.Windows.Forms.Control.KeyPress> ve <xref:System.Windows.Forms.Control.KeyUp> bu tuş vuruşu olayları.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-124">The <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property, which can be used to suppress the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events for that keystroke.</span></span></li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|<span data-ttu-id="4bcbd-125">Anahtarı veya anahtarları sonuç bir karakter tuşuna bastığınızda, bu olay tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-125">This event is raised when the key or keys pressed result in a character.</span></span> <span data-ttu-id="4bcbd-126">Örneğin, bir kullanıcı kaydırma ve küçük harf bir büyük harf "A" karakter neden "a" tuşuna bastığında.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-126">For example, a user presses SHIFT and the lowercase "a" keys, which result in a capital letter "A" character.</span></span>|<span data-ttu-id="4bcbd-127"><xref:System.Windows.Forms.Control.KeyPress>sonra tetiklenir <xref:System.Windows.Forms.Control.KeyDown>.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-127"><xref:System.Windows.Forms.Control.KeyPress> is raised after <xref:System.Windows.Forms.Control.KeyDown>.</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-128">İşleyicisi <xref:System.Windows.Forms.Control.KeyPress> alır:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-128">The handler for <xref:System.Windows.Forms.Control.KeyPress> receives:</span></span></li><li><span data-ttu-id="4bcbd-129">A <xref:System.Windows.Forms.KeyPressEventArgs> basıldı anahtar karakter kodunu içerir parametresi.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-129">A <xref:System.Windows.Forms.KeyPressEventArgs> parameter, which contains the character code of the key that was pressed.</span></span> <span data-ttu-id="4bcbd-130">Bu karakter kodu her bir karakteri anahtarı ve değiştirici tuşa birleşimi için benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-130">This character code is unique for every combination of a character key and a modifier key.</span></span><br /><br />     <span data-ttu-id="4bcbd-131">Örneğin, "A" anahtar üretir:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-131">For example, the "A" key will generate:</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-132">SHIFT tuşuyla basıldıysa 65 karakter kodu</span><span class="sxs-lookup"><span data-stu-id="4bcbd-132">The character code 65, if it is pressed with the SHIFT key</span></span></li><li><span data-ttu-id="4bcbd-133">Veya tek başına basıldığında varsa 97 CAPS LOCK tuşunun,</span><span class="sxs-lookup"><span data-stu-id="4bcbd-133">Or the CAPS LOCK key, 97 if it is pressed by itself,</span></span></li><li><span data-ttu-id="4bcbd-134">Ve 1 ile CTRL tuşunu basılı olduğunda.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-134">And 1, if it is pressed with the CTRL key.</span></span></li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|<span data-ttu-id="4bcbd-135">Bir kullanıcı bir fiziksel anahtar yayımlandığında bu olay tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-135">This event is raised when a user releases a physical key.</span></span>|<span data-ttu-id="4bcbd-136">İşleyicisi <xref:System.Windows.Forms.Control.KeyUp> alır:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-136">The handler for <xref:System.Windows.Forms.Control.KeyUp> receives:</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-137">A <xref:System.Windows.Forms.KeyEventArgs> parametre:</span><span class="sxs-lookup"><span data-stu-id="4bcbd-137">A <xref:System.Windows.Forms.KeyEventArgs> parameter:</span></span><br /><br /> <ul><li><span data-ttu-id="4bcbd-138">Sağlayan <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (fiziksel klavye düğmesi belirtir) özelliği.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-138">Which provides the <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> property (which specifies a physical keyboard button).</span></span></li><li><span data-ttu-id="4bcbd-139"><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Özelliği (SHIFT, CTRL ya da ALT).</span><span class="sxs-lookup"><span data-stu-id="4bcbd-139">The <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property (SHIFT, CTRL, or ALT).</span></span></li><li><span data-ttu-id="4bcbd-140"><xref:System.Globalization.SortKey.KeyData%2A> (Anahtar kodu ve değiştirici birleştirir) özelliği.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-140">The <xref:System.Globalization.SortKey.KeyData%2A> property (which combines the key code and modifier).</span></span></li></ul></li></ul>|  
  
## <a name="see-also"></a><span data-ttu-id="4bcbd-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-141">See Also</span></span>  
 [<span data-ttu-id="4bcbd-142">Forms bir Windows uygulamasında klavye girdisi</span><span class="sxs-lookup"><span data-stu-id="4bcbd-142">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="4bcbd-143">Klavye girdisi nasıl çalışır</span><span class="sxs-lookup"><span data-stu-id="4bcbd-143">How Keyboard Input Works</span></span>](../../../docs/framework/winforms/how-keyboard-input-works.md)  
 [<span data-ttu-id="4bcbd-144">Forms bir Windows uygulamasında fare girdisi</span><span class="sxs-lookup"><span data-stu-id="4bcbd-144">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)