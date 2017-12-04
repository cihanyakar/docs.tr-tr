---
title: "Nasıl yapılır: Bir Animasyonu Gelen, İçin ve Göre Kullanarak Denetleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a><span data-ttu-id="d97cc-102">Nasıl yapılır: Bir Animasyonu Gelen, İçin ve Göre Kullanarak Denetleme</span><span class="sxs-lookup"><span data-stu-id="d97cc-102">How to: Control an Animation using From, To, and By</span></span>
<span data-ttu-id="d97cc-103">"From/To/By" veya "temel animasyon" iki hedef değer arasında bir geçiş oluşturur (bkz [animasyon genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) giriş animasyon farklı türleri için).</span><span class="sxs-lookup"><span data-stu-id="d97cc-103">A "From/To/By" or "basic animation" creates a transition between two target values (see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) for an introduction to different types of animations).</span></span> <span data-ttu-id="d97cc-104">Temel animasyonun hedef değerlerini ayarlamak için kullanın, <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d97cc-104">To set the target values of a basic animation, use its <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>  <span data-ttu-id="d97cc-105">Aşağıdaki tabloda özetlenmiştir nasıl <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri kullanılabilir birlikte veya ayrı ayrı animasyonun hedef değerlerini belirlemek için.</span><span class="sxs-lookup"><span data-stu-id="d97cc-105">The following table summarizes how the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties may be used together or separately to determine an animation's target values.</span></span>  
  
|<span data-ttu-id="d97cc-106">Belirtilen özellikleri</span><span class="sxs-lookup"><span data-stu-id="d97cc-106">Properties specified</span></span>|<span data-ttu-id="d97cc-107">Bunun sonucunda oluşan davranışı</span><span class="sxs-lookup"><span data-stu-id="d97cc-107">Resulting behavior</span></span>|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|<span data-ttu-id="d97cc-108">İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliğini özelliğin temel değerini veya önceki bir animasyon animasyonun önceki animasyonun nasıl yapılandırıldığına bağlı olarak değeri, çıktı.</span><span class="sxs-lookup"><span data-stu-id="d97cc-108">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the base value of the property being animated or to a previous animation's output value, depending on how the previous animation is configured.</span></span>|  
|<span data-ttu-id="d97cc-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>ve<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span><span class="sxs-lookup"><span data-stu-id="d97cc-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span></span>|<span data-ttu-id="d97cc-110">İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliği tarafından belirtilen değere <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d97cc-110">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<span data-ttu-id="d97cc-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>ve<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span><span class="sxs-lookup"><span data-stu-id="d97cc-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span></span>|<span data-ttu-id="d97cc-112">İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliğini toplamı tarafından belirtilen değere <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d97cc-112">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the sum of the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|<span data-ttu-id="d97cc-113">Animasyonun ilerler animasyonlu özelliğin temel değerinden veya önceki bir animasyon değeri tarafından belirtilen değere çıkışını <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d97cc-113">The animation progresses from the animated property's base value or a previous animation's output value to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|<span data-ttu-id="d97cc-114">Bu değer ve tarafından belirtilen değeri toplamı değerine özelliğin temel değerini animasyon ilerler veya önceki animasyonun çıktı <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d97cc-114">The animation progresses from the base value of the property being animated or a previous animation's output value to the sum of that value and the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d97cc-115">Her ikisini birden ayarlamayın <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> aynı animasyon özelliği.</span><span class="sxs-lookup"><span data-stu-id="d97cc-115">Do not set both the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property and the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property on the same animation.</span></span>  
  
 <span data-ttu-id="d97cc-116">İkiden fazla hedef değerleri arasında hareketli hale getirmeyi veya diğer ilişkilendirme yöntemlerini kullanmak üzere bir anahtar çerçevesi animasyonu kullanın.</span><span class="sxs-lookup"><span data-stu-id="d97cc-116">To use other interpolation methods or animate between more than two target values, use a key frame animation.</span></span> <span data-ttu-id="d97cc-117">Bkz: [anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="d97cc-117">See [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="d97cc-118">Tek bir özellik için birden çok animasyon uygulama hakkında daha fazla bilgi için bkz: [anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d97cc-118">For information about applying multiple animations to a single property, see [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="d97cc-119">Aşağıdaki örnek, ayarı farklı etkilerini gösterir <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> animasyonları özellikleri.</span><span class="sxs-lookup"><span data-stu-id="d97cc-119">The example below shows the different effects of setting <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> properties on animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d97cc-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="d97cc-120">Example</span></span>  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d97cc-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d97cc-121">See Also</span></span>  
 [<span data-ttu-id="d97cc-122">Animasyon genel bakış</span><span class="sxs-lookup"><span data-stu-id="d97cc-122">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d97cc-123">Anahtar çerçeve animasyonları genel bakış</span><span class="sxs-lookup"><span data-stu-id="d97cc-123">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d97cc-124">Öğesinden, için ve animasyon hedef değerleri örneği</span><span class="sxs-lookup"><span data-stu-id="d97cc-124">From, To, and By Animation Target Values Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159988)