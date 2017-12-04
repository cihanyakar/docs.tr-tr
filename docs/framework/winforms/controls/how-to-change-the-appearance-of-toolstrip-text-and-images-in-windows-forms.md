---
title: "Nasıl yapılır: Windows Forms'ta ToolStrip Metni ve Görüntülerinin Görünüşünü Değiştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d926ce74db9723b6248dbb123513ca38d4adb1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="37335-102">Nasıl yapılır: Windows Forms'ta ToolStrip Metni ve Görüntülerinin Görünüşünü Değiştirme</span><span class="sxs-lookup"><span data-stu-id="37335-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="37335-103">Metin ve görüntüler üzerinde görüntülenip görüntülenmeyeceğini denetleyebilirsiniz bir <xref:System.Windows.Forms.ToolStripItem> ve bunların birbirlerine göre nasıl hizalandığını ve <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="37335-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="37335-104">Üzerinde ToolStripItem görüntülenenleri tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="37335-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="37335-105">Ayarlama <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> istenen değeri özelliğine.</span><span class="sxs-lookup"><span data-stu-id="37335-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="37335-106">Olasılıkları şunlardır `Image`, `ImageAndText`, `None`, ve `Text`.</span><span class="sxs-lookup"><span data-stu-id="37335-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="37335-107">Varsayılan, `ImageAndText` değeridir.</span><span class="sxs-lookup"><span data-stu-id="37335-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="37335-108">Bir ToolStripItem üzerine metni hizalama</span><span class="sxs-lookup"><span data-stu-id="37335-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="37335-109">Ayarlama <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> istenen değeri özelliğine.</span><span class="sxs-lookup"><span data-stu-id="37335-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="37335-110">Olasılıkları üst, Orta ve alt sol, Ortala ve sağa ile herhangi bir bileşimini şunlardır.</span><span class="sxs-lookup"><span data-stu-id="37335-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="37335-111">Varsayılan, `MiddleCenter` değeridir.</span><span class="sxs-lookup"><span data-stu-id="37335-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="37335-112">ToolStripItem görüntüde hizalamak için</span><span class="sxs-lookup"><span data-stu-id="37335-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="37335-113">Ayarlama <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> istenen değeri özelliğine.</span><span class="sxs-lookup"><span data-stu-id="37335-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="37335-114">Olasılıkları üst, Orta ve alt sol, Ortala ve sağa ile herhangi bir bileşimini şunlardır.</span><span class="sxs-lookup"><span data-stu-id="37335-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="37335-115">Varsayılan, `MiddleLeft` değeridir.</span><span class="sxs-lookup"><span data-stu-id="37335-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="37335-116">ToolStripItem metin ve görüntüler diğer göre nasıl görüntüleneceğini tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="37335-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="37335-117">Ayarlama <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> istenen değeri özelliğine.</span><span class="sxs-lookup"><span data-stu-id="37335-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="37335-118">Olasılıkları şunlardır `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, ve `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="37335-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="37335-119">Varsayılan, `ImageBeforeText` değeridir.</span><span class="sxs-lookup"><span data-stu-id="37335-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="37335-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="37335-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="37335-121">ToolStrip denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="37335-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="37335-122">ToolStrip denetim mimarisi</span><span class="sxs-lookup"><span data-stu-id="37335-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="37335-123">ToolStrip Teknoloiji özeti</span><span class="sxs-lookup"><span data-stu-id="37335-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)