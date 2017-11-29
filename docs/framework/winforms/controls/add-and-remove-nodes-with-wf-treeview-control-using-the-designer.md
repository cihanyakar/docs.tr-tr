---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları TreeView Denetimi ile Düğüm Ekleme ve Kaldırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f6295f915e9204e9996d8902b07a3dfc4c5c2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="21f58-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları TreeView Denetimi ile Düğüm Ekleme ve Kaldırma</span><span class="sxs-lookup"><span data-stu-id="21f58-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="21f58-103">Windows Forms çünkü <xref:System.Windows.Forms.TreeView> denetimi kendi üst düğümlerinin nedir için dikkat ödeme gerekir bir düğüm eklerken bu düğümler hiyerarşik bir biçimde görüntüler.</span><span class="sxs-lookup"><span data-stu-id="21f58-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="21f58-104">Aşağıdaki yordam gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.TreeView> denetim.</span><span class="sxs-lookup"><span data-stu-id="21f58-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="21f58-105">Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="21f58-105">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21f58-106">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="21f58-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="21f58-107">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="21f58-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="21f58-108">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="21f58-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="21f58-109">Ekleme veya düğümleri Tasarımcısı'nda kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="21f58-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="21f58-110">Seçin <xref:System.Windows.Forms.TreeView> denetim.</span><span class="sxs-lookup"><span data-stu-id="21f58-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="21f58-111">İçinde **özellikleri** penceresinde tıklatın **üç nokta** (![VisualStudioEllipsesButton ekran](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) düğmesine <xref:System.Windows.Forms.TreeView.Nodes%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="21f58-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="21f58-112">**TreeNode Düzenleyicisi** görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="21f58-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="21f58-113">Düğümler eklemek için bir kök düğümü olmalıdır; bir mevcut değilse, önce bir kök tıklayarak eklemelisiniz **eklemek kök** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="21f58-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="21f58-114">Kök veya başka bir düğüme seçerek ve tıklatarak daha sonra alt düğümler ekleyebilirsiniz **alt öğe Ekle** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="21f58-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="21f58-115">Düğümleri silmek için silin ve ardından düğümü seçin **silmek** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="21f58-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f58-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="21f58-116">See Also</span></span>  
 [<span data-ttu-id="21f58-117">TreeView denetimi</span><span class="sxs-lookup"><span data-stu-id="21f58-117">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="21f58-118">TreeView denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="21f58-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="21f58-119">Nasıl yapılır: Windows Forms TreeView denetimi için simgeler ayarlama</span><span class="sxs-lookup"><span data-stu-id="21f58-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="21f58-120">Nasıl yapılır: Windows Forms TreeView denetiminin tüm düğümlerinde yineleme</span><span class="sxs-lookup"><span data-stu-id="21f58-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="21f58-121">Nasıl yapılır: hangi TreeView düğümüne tıklandığını belirleme</span><span class="sxs-lookup"><span data-stu-id="21f58-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="21f58-122">Nasıl yapılır: bir TreeView veya ListView denetimi (Windows Forms) özel bilgi ekleme</span><span class="sxs-lookup"><span data-stu-id="21f58-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)