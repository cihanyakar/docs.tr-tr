---
title: "Windows Forms Denetimlerindeki Özellikler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5de09635fb92b46a2c0f89427ad03449de6bd53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="16b1a-102">Windows Forms Denetimlerindeki Özellikler</span><span class="sxs-lookup"><span data-stu-id="16b1a-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="16b1a-103">Bir Windows Forms denetimi birçok özellikler form temel sınıfı devralır <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16b1a-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="16b1a-104">Bunlar gibi özellikler içeren <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>ve diğer birçok.</span><span class="sxs-lookup"><span data-stu-id="16b1a-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="16b1a-105">Devralınan özellikler hakkında daha fazla ayrıntı için bkz: <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16b1a-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="16b1a-106">, Denetiminde devralınan özelliklerini geçersiz kılmak yanı sıra yeni özellikleri tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="16b1a-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16b1a-107">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="16b1a-107">In This Section</span></span>  
 [<span data-ttu-id="16b1a-108">Özellik tanımlama</span><span class="sxs-lookup"><span data-stu-id="16b1a-108">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="16b1a-109">Özellik tasarım ortamına tümleştirme nasıl gösterir ve özel denetimi veya bileşeni için bir özellik uygulamak gösterir.</span><span class="sxs-lookup"><span data-stu-id="16b1a-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="16b1a-110">Reset yöntemleri ve ShouldSerialize ile varsayılan değerleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="16b1a-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="16b1a-111">Özel denetimi veya bileşeni için varsayılan özellik değerlerini tanımlayabileceğiniz gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="16b1a-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="16b1a-112">Özellik değişti olayları</span><span class="sxs-lookup"><span data-stu-id="16b1a-112">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 <span data-ttu-id="16b1a-113">Özellik değişikliği bildirimlerini özellik değeri değiştiğinde etkinleştirmeyi açıklar.</span><span class="sxs-lookup"><span data-stu-id="16b1a-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="16b1a-114">Nasıl yapılır: bağlı denetimlerin özelliklerini kullanıma sunma</span><span class="sxs-lookup"><span data-stu-id="16b1a-114">How to: Expose Properties of Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="16b1a-115">Özel bir bileşik denetim bağlı denetimlerin özelliklerini ortaya gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="16b1a-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="16b1a-116">Özel denetimlerde yöntem uygulaması</span><span class="sxs-lookup"><span data-stu-id="16b1a-116">Method Implementation in Custom Controls</span></span>](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 <span data-ttu-id="16b1a-117">Özel denetimler ve bileşenler yöntemleri uygulamak açıklar.</span><span class="sxs-lookup"><span data-stu-id="16b1a-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="16b1a-118">Başvuru</span><span class="sxs-lookup"><span data-stu-id="16b1a-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="16b1a-119">Bileşik denetimler uygulamak için temel sınıf belgeler.</span><span class="sxs-lookup"><span data-stu-id="16b1a-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="16b1a-120">Belirten özniteliği belgeleri <xref:System.ComponentModel.TypeConverter> bir özel özellik türü için kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="16b1a-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="16b1a-121">Belirten özniteliği belgeleri <xref:System.Drawing.Design.UITypeEditor> bir özel özellik için kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="16b1a-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="16b1a-122">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="16b1a-122">Related Sections</span></span>  
 [<span data-ttu-id="16b1a-123">Windows Forms denetimlerindeki öznitelikler</span><span class="sxs-lookup"><span data-stu-id="16b1a-123">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="16b1a-124">Özellikleri veya diğer özel denetimleri ve bileşenleri üyeleri uygulayabilirsiniz öznitelikleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="16b1a-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="16b1a-125">Bileşenleri için tasarım zamanı öznitelikleri</span><span class="sxs-lookup"><span data-stu-id="16b1a-125">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="16b1a-126">Böylece doğru görsel tasarımcılar tasarım zamanında görüntülendikleri bileşenleri ve denetimler uygulamak için meta veri öznitelikleri listeler.</span><span class="sxs-lookup"><span data-stu-id="16b1a-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="16b1a-127">Tasarım zamanı desteği genişletme</span><span class="sxs-lookup"><span data-stu-id="16b1a-127">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="16b1a-128">Sınıfları düzenleyicileri ve tasarım zamanı desteği tasarımcıları gibi uygulamak açıklar.</span><span class="sxs-lookup"><span data-stu-id="16b1a-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>