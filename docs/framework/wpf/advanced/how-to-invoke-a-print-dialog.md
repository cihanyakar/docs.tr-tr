---
title: "Nasıl yapılır: Yazdır İletişim Kutusu Çağırma"
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
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ba541b367e56a809fa444528dccd69860c4de46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="7a205-102">Nasıl yapılır: Yazdır İletişim Kutusu Çağırma</span><span class="sxs-lookup"><span data-stu-id="7a205-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="7a205-103">Uygulamanızdan yazdırma olanağı sağlamak için yalnızca oluşturma açın ve bir <xref:System.Windows.Controls.PrintDialog> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="7a205-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a205-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="7a205-104">Example</span></span>  
 <span data-ttu-id="7a205-105"><xref:System.Windows.Controls.PrintDialog> Denetimi için bir tek giriş noktası sağlar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], yapılandırması ve [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] iş gönderme.</span><span class="sxs-lookup"><span data-stu-id="7a205-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="7a205-106">Kullanımı kolay bir denetimdir ve kullanarak oluşturulabilir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] işaretleme veya kod.</span><span class="sxs-lookup"><span data-stu-id="7a205-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="7a205-107">Aşağıdaki örnekte nasıl örneği ve kodda Denetimi'ni açmak ve ondan yazdırmak nasıl gösterilir.</span><span class="sxs-lookup"><span data-stu-id="7a205-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="7a205-108">Ayrıca, iletişim kutusu sayfaları belirli bir dizi ayarlama seçeneği kullanıcıya vermek emin olmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="7a205-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="7a205-109">Kod örneği, C: sürücüsünün kök dizininde bir dosyada FixedDocumentSequence.xps olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="7a205-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="7a205-110">İletişim kutusu açıldıktan sonra kullanıcıların bilgisayarlarında yüklü yazıcılar seçmek mümkün olacaktır.</span><span class="sxs-lookup"><span data-stu-id="7a205-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="7a205-111">Seçme seçeneği de sağlanır [Microsoft XPS Belge Yazıcısı](http://go.microsoft.com/fwlink/?LinkId=147319) oluşturmak için bir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] yazdırma yerine dosya.</span><span class="sxs-lookup"><span data-stu-id="7a205-111">They will also have the option of selecting the [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a205-112"><xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Denetimini [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], bu konuda ele alınmıştır karıştırılmamalıdır ile <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> bileşenini [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a205-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="7a205-113">NET olarak söylemek kullanabileceğiniz <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> hiç iletişim kutusunu açmadan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7a205-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="7a205-114">Bu anlamda denetim görünmeyen yazdırma bileşeni kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7a205-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="7a205-115">Ancak performans nedenleriyle kullanın ya da daha iyi olur <xref:System.Printing.PrintQueue.AddJob%2A> yöntemi veya çok biri <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> ve <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> yöntemlerini <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="7a205-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="7a205-116">Bu konu hakkında daha fazla bilgi için bkz: [program aracılığıyla yazdırma XPS dosyaları](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) ve.</span><span class="sxs-lookup"><span data-stu-id="7a205-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a205-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7a205-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="7a205-118">WPF belgeleri</span><span class="sxs-lookup"><span data-stu-id="7a205-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="7a205-119">Yazdırma genel bakış</span><span class="sxs-lookup"><span data-stu-id="7a205-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="7a205-120">Microsoft XPS Belge Yazıcısı</span><span class="sxs-lookup"><span data-stu-id="7a205-120">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)