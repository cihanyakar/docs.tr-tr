---
title: 'Nasıl yapılır: Win32 Konak Kapsayıcısı Kullanan Tıklama Testi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: bb175e0f8aeb126b7f7fa85d5af1c4afcf5bea61
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397822"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Nasıl yapılır: Win32 Konak Kapsayıcısı Kullanan Tıklama Testi
Görsel nesneler içinde oluşturduğunuz bir [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] görsel nesneler için bir konak penceresini kapsayıcı sağlayarak penceresi. Olay içindeki görsel nesneler için işleme sağlamak için ana penceresi kapsayıcının İleti Filtresi döngüsüne iletileri işler. Başvurmak [eğitmen: Win32 uygulamasında görsel nesneler barındırma](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) içindeki görsel nesneler barındırma hakkında daha fazla bilgi için bir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] penceresi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, fare olay işleyicilerini ayarlama işlemi gösterilmektedir bir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pencere konak kapsayıcısı olarak görsel nesneler için kullanılır.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Aşağıdaki örnekte, belirli fare olayları yakalama yanıt isabet sınaması ayarlanacağı gösterilmektedir.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> Nesne sunan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] içerik içinde bir [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] penceresi. Değerini <xref:System.Windows.Interop.HwndSource.RootVisual%2A> özelliği <xref:System.Windows.Interop.HwndSource> nesne görsel ağaç hiyerarşisinde en üstteki düğümü temsil eder.  
  
 Win32 Konak Kapsayıcısı kullanan isabet sınaması tam örnek nesneleri için bkz. [Win32 birlikte çalışması örnek ile isabet sınaması](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Interop.HwndSource>  
 [Görsel Katmanda Tıklama Testi](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Eğitmen: Win32 Uygulamasında Görsel Nesneler Barındırma](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
