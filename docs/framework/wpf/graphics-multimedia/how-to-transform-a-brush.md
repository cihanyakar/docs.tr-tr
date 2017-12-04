---
title: "Nasıl yapılır: Fırça Dönüşümü"
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
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a36ba5bce60b88d662f03fcff75a6fa04cad039d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="35396-102">Nasıl yapılır: Fırça Dönüşümü</span><span class="sxs-lookup"><span data-stu-id="35396-102">How to: Transform a Brush</span></span>
<span data-ttu-id="35396-103">Bu örnek nasıl dönüştürüleceğini gösterir <xref:System.Windows.Media.Brush> iki dönüşüm özelliklerini kullanarak nesneleri: <xref:System.Windows.Media.Brush.RelativeTransform%2A> ve <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="35396-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="35396-104">Aşağıdaki örnekler bir <xref:System.Windows.Media.RotateTransform> içeriğini döndürmek için bir <xref:System.Windows.Media.ImageBrush> 45 derece.</span><span class="sxs-lookup"><span data-stu-id="35396-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="35396-105">Aşağıdaki çizimde gösterildiği <xref:System.Windows.Media.ImageBrush> olmadan bir <xref:System.Windows.Media.RotateTransform>, ile <xref:System.Windows.Media.RotateTransform> uygulanan <xref:System.Windows.Media.Brush.RelativeTransform%2A> özelliği ile <xref:System.Windows.Media.RotateTransform> uygulanan <xref:System.Windows.Media.Brush.Transform%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="35396-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="35396-106">![Fırça göreli dönüştürmesi ve dönüşüm ayarları](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="35396-106">![Brush RelativeTransform and Transform settings](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="35396-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="35396-107">Example</span></span>  
 <span data-ttu-id="35396-108">İlk örnek geçerli bir <xref:System.Windows.Media.RotateTransform> için <xref:System.Windows.Media.Brush.RelativeTransform%2A> özelliği bir <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="35396-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="35396-109"><xref:System.Windows.Media.RotateTransform.CenterX%2A> Ve <xref:System.Windows.Media.RotateTransform.CenterY%2A> özelliklerini bir <xref:System.Windows.Media.RotateTransform> her ikisi de ayarlanır, bu içeriğin orta noktasının göreli koordinatı olan 0,5 olarak nesne.</span><span class="sxs-lookup"><span data-stu-id="35396-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="35396-110">Sonuç olarak, <xref:System.Windows.Media.ImageBrush> içeriği ortasından döner.</span><span class="sxs-lookup"><span data-stu-id="35396-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="35396-111">İkinci örnek de geçerlidir bir <xref:System.Windows.Media.RotateTransform> için bir <xref:System.Windows.Media.ImageBrush>; ancak, bu örnek kullanır <xref:System.Windows.Media.Brush.Transform%2A> özelliği yerine <xref:System.Windows.Media.Brush.RelativeTransform%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="35396-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="35396-112">Kendi Merkezi hakkında fırça döndürmek için örnek ayarlar <xref:System.Windows.Media.RotateTransform.CenterX%2A> ve <xref:System.Windows.Media.RotateTransform.CenterY%2A> özelliklerini <xref:System.Windows.Media.RotateTransform> mutlak koordinatları nesnesine.</span><span class="sxs-lookup"><span data-stu-id="35396-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="35396-113">Fırça 175 90 piksel olan bir dikdörtgen boyar çünkü dikdörtgenin merkez noktasıdır (87.5, 45).</span><span class="sxs-lookup"><span data-stu-id="35396-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="35396-114">Bir açıklaması için nasıl <xref:System.Windows.Media.Brush.RelativeTransform%2A> ve <xref:System.Windows.Media.Brush.Transform%2A> özellikleri çalışma, bkz [fırça dönüşümüne genel bakış](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="35396-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="35396-115">Tam bir örnek için bkz: [Fırçalar örnek](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="35396-115">For the complete sample, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="35396-116">Fırçalar hakkında daha fazla bilgi için bkz: [gradyan genel bakış ve düz renk ile Boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="35396-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35396-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35396-117">See Also</span></span>  
 [<span data-ttu-id="35396-118">Fırça dönüşümüne genel bakış</span><span class="sxs-lookup"><span data-stu-id="35396-118">Brush Transformation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [<span data-ttu-id="35396-119">Boyama düz renklerle ve gradyan genel bakış</span><span class="sxs-lookup"><span data-stu-id="35396-119">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="35396-120">Dönüşümler genel bakış</span><span class="sxs-lookup"><span data-stu-id="35396-120">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)