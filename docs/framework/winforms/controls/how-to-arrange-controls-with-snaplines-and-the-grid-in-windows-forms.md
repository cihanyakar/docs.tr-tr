---
title: "Nasıl yapılır: Windows Formlarında Dayama Çizgileri ve Kılavuz ile Denetimleri Düzenleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ab199f390fa6a704ad3b3d2a17387d034cf2e57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="94c16-102">Nasıl yapılır: Windows Formlarında Dayama Çizgileri ve Kılavuz ile Denetimleri Düzenleme</span><span class="sxs-lookup"><span data-stu-id="94c16-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="94c16-103">Düzen özelliklerini kullanarak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], tam olarak bir form üzerinde denetimleri yerleştirildiği yönlendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94c16-103">Using the layout features of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="94c16-104">Bir form için eklenip bir form üzerinde denetimleri otomatik olarak satırları ve sütunları Windows Forms Tasarımcısı kılavuzunun hizalanabilir veya dayama çizgileri özelliğini kullanarak denetimleri hizalama.</span><span class="sxs-lookup"><span data-stu-id="94c16-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94c16-105">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="94c16-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="94c16-106">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="94c16-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="94c16-107">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="94c16-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="94c16-108">Tüm denetimleri kılavuza Daya için</span><span class="sxs-lookup"><span data-stu-id="94c16-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="94c16-109">Seçin **Snaptogrıd** Düzen Windows Form Tasarımcısı modunda **seçenekleri** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="94c16-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="94c16-110">Daha fazla bilgi için bkz: [genel, Windows Form Tasarımcısı, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="94c16-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="94c16-111">Tüm denetimler şimdi kendilerini kılavuz noktalarında boyunca hizalar.</span><span class="sxs-lookup"><span data-stu-id="94c16-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="94c16-112">Yerinde kilitleyerek tek tek denetimleri kılavuza Daya.</span><span class="sxs-lookup"><span data-stu-id="94c16-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="94c16-113">Kilitli olan olsa da, ancak bunlar taşınmış yeniden boyutlandırılmış veya silinemez.</span><span class="sxs-lookup"><span data-stu-id="94c16-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="94c16-114">Kilitleme denetimleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: Windows formlarına denetimler kilitleme](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="94c16-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="94c16-115">Dayama çizgileri kullanarak denetimleri hizalamak için</span><span class="sxs-lookup"><span data-stu-id="94c16-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="94c16-116">Seçin **dayama çizgileri** Düzen Windows Form Tasarımcısı modunda **seçenekleri** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="94c16-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="94c16-117">Daha fazla bilgi için bkz: [izlenecek yol: Windows Forms kullanarak dayama çizgileri düzenleme denetimlerinde](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="94c16-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="94c16-118">Dayama çizgileri şimdi hizalama ve form üzerinde denetimleri düzenlemek için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94c16-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c16-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="94c16-119">See Also</span></span>  
 [<span data-ttu-id="94c16-120">Genel, Windows Form Tasarımcısı, Seçenekler iletişim kutusu</span><span class="sxs-lookup"><span data-stu-id="94c16-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="94c16-121">İzlenecek yol: Dayama çizgileri kullanarak Windows Forms'ta denetimleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="94c16-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="94c16-122">Windows Forms denetimleri</span><span class="sxs-lookup"><span data-stu-id="94c16-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="94c16-123">Nasıl yapılır: Windows formlarına denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="94c16-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="94c16-124">Windows Forms'ta denetimleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="94c16-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="94c16-125">Ayrı Windows Forms denetimlerini etiketleme ve kısayollarını sunma</span><span class="sxs-lookup"><span data-stu-id="94c16-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="94c16-126">Windows Forms'ta kullanılacak denetimler</span><span class="sxs-lookup"><span data-stu-id="94c16-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="94c16-127">Windows Forms denetimleri işlevi</span><span class="sxs-lookup"><span data-stu-id="94c16-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)