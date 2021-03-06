---
title: 'Nasıl Yapılır: Bir Öğe veya Fırça Opaklığına Animasyon Ekleme'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 659b051fe63c113bf1a4488b1fab12bbee75b1e3
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451254"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Nasıl Yapılır: Bir Öğe veya Fırça Opaklığına Animasyon Ekleme
Görünümü içine ve dışına Soldurma çerçeve öğesi yapmak için animasyon uygulayabilirsiniz, <xref:System.Windows.UIElement.Opacity%2A> , özelliği veya animasyon <xref:System.Windows.Media.Brush.Opacity%2A> özelliği <xref:System.Windows.Media.Brush> (veya Fırçalar) onu boyamak için kullanılan. Kolaylaştırır öğenin opaklık animasyon ekleme ve alt görünüm içine ve dışına Soldurma ancak öğe boyamak için kullanılan fırçayı animasyon ekleme öğesi hangi kısmının belirmesi konusunda daha Seçici olmasını sağlar. Örneğin, bir düğmenin arka plan boyamak için kullanılan fırça opaklığına animasyon uygulayabilirsiniz. Bu, giriş ve çıkış metnini ila tamamen opak bırakarak sırasında görünümün soluklaştırılacak düğmenin arka plan neden olur.  
  
> [!NOTE]
>  Animasyon ekleme <xref:System.Windows.Media.Brush.Opacity%2A> , bir <xref:System.Windows.Media.Brush> hareketlendirme üzerinde performans avantajı sağlar <xref:System.Windows.UIElement.Opacity%2A> bir öğenin özelliği.  
  
 Böylece bunlar görünümü içine ve dışına Soldurma aşağıdaki örnekte, iki düğme oynatılır. İlk opaklığını <xref:System.Windows.Controls.Button> gelen animasyonlu `1.0` için `0.0` üzerinden bir <xref:System.Windows.Media.Animation.Timeline.Duration%2A> beş saniye. İkinci düğme ayrıca animasyon, ancak SolidColorBrush donukluğu boyamak için kullanılan kendi <xref:System.Windows.Controls.Control.Background%2A> opaklığını tümü yerine bir animasyon görünür. Örneği çalıştırdığınızda yalnızca ikinci düğmenin arka plan görünüm içine ve dışına soldurur sırada ilk düğmeyi tamamen görünümü içine ve dışına soldurur. Kendi metin ve kenarlık ila tamamen opak kalır.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Bu örnekte, kod çıkarıldı. Tam örnek opaklığına işlemini de gösterir. bir <xref:System.Windows.Media.Color> içinde bir <xref:System.Windows.Media.LinearGradientBrush>.  Tam bir örnek için bkz: [öğesi örneği Donukluğa animasyon ekleme](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
