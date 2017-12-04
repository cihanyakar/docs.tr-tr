---
title: "Nasıl yapılır: Komutu Etkinleştirme"
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
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e90f7f69aebf48bbc27321d3808468a2df49f793
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-a-command"></a><span data-ttu-id="67b56-102">Nasıl yapılır: Komutu Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="67b56-102">How to: Enable a Command</span></span>
<span data-ttu-id="67b56-103">Aşağıdaki örnekte, komut verme kullanımı gösterilmiştir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b56-103">The following example demonstrates how to use commanding in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  <span data-ttu-id="67b56-104">Bu örnek ile nasıl ilişkilendirildiğini gösterir bir <xref:System.Windows.Input.RoutedCommand> için bir <xref:System.Windows.Controls.Button>, oluşturma bir <xref:System.Windows.Input.CommandBinding>ve uygulayan olay işleyicileri oluşturma <xref:System.Windows.Input.RoutedCommand>.</span><span class="sxs-lookup"><span data-stu-id="67b56-104">The example shows how to associate a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Button>, create a <xref:System.Windows.Input.CommandBinding>, and create the event handlers which implement the <xref:System.Windows.Input.RoutedCommand>.</span></span>  <span data-ttu-id="67b56-105">Komut verme hakkında daha fazla bilgi için bkz: [kumanda genel bakış](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67b56-105">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b56-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="67b56-106">Example</span></span>  
 <span data-ttu-id="67b56-107">Kodun ilk bölümü oluşturur [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], oluşan ve bir <xref:System.Windows.Controls.Button> ve <xref:System.Windows.Controls.StackPanel>ve oluşturan bir <xref:System.Windows.Input.CommandBinding> komut işleyicileri ile ilişkilendirir <xref:System.Windows.Input.RoutedCommand>.</span><span class="sxs-lookup"><span data-stu-id="67b56-107">The first section of code creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], which consists of a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.StackPanel>, and creates a <xref:System.Windows.Input.CommandBinding> that associates the command handlers with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="67b56-108"><xref:System.Windows.Input.ICommandSource.Command%2A> Özelliği <xref:System.Windows.Controls.Button> ile ilişkili <xref:System.Windows.Input.ApplicationCommands.Close%2A> komutu.</span><span class="sxs-lookup"><span data-stu-id="67b56-108">The <xref:System.Windows.Input.ICommandSource.Command%2A> property of the <xref:System.Windows.Controls.Button> is associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="67b56-109"><xref:System.Windows.Input.CommandBinding> Eklenen <xref:System.Windows.Input.CommandBindingCollection> kök <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="67b56-109">The <xref:System.Windows.Input.CommandBinding> is added to the <xref:System.Windows.Input.CommandBindingCollection> of the root <xref:System.Windows.Window>.</span></span> <span data-ttu-id="67b56-110"><xref:System.Windows.Input.CommandBinding.Executed> Ve <xref:System.Windows.Input.CommandBinding.CanExecute> olay işleyicileri bu bağlama eklenmiş ve ilişkili <xref:System.Windows.Input.ApplicationCommands.Close%2A> komutu.</span><span class="sxs-lookup"><span data-stu-id="67b56-110">The <xref:System.Windows.Input.CommandBinding.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers are attached to this binding and associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="67b56-111">Olmadan <xref:System.Windows.Input.CommandBinding> komut mantığı, yalnızca komut çağırma mekanizması vardır.</span><span class="sxs-lookup"><span data-stu-id="67b56-111">Without the <xref:System.Windows.Input.CommandBinding> there is no command logic, only a mechanism to invoke the command.</span></span>  <span data-ttu-id="67b56-112">Zaman <xref:System.Windows.Controls.Button> tıklandığında, <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> ve ardından komut hedefi üzerinde ortaya <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.</span><span class="sxs-lookup"><span data-stu-id="67b56-112">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> is raised on the command target followed by the <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.</span></span>  <span data-ttu-id="67b56-113">Bu olaylar aramakta öğesi ağacı gezme bir <xref:System.Windows.Input.CommandBinding> o belirli komut için.</span><span class="sxs-lookup"><span data-stu-id="67b56-113">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for that particular command.</span></span>  <span data-ttu-id="67b56-114">Çünkü dikkate değerdir <xref:System.Windows.RoutedEvent> tünel ve kabarcık öğe ağacı üzerinden, bakım gerekir alınması where <xref:System.Windows.Input.CommandBinding> yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="67b56-114">It is worth noting that because <xref:System.Windows.RoutedEvent> tunnel and bubble through the element tree, care must be taken in where the <xref:System.Windows.Input.CommandBinding> is put.</span></span>   <span data-ttu-id="67b56-115">Varsa <xref:System.Windows.Input.CommandBinding> komut hedefi veya rotası üzerinde değil başka bir düğüme bir eşdüzeyi açıktır <xref:System.Windows.RoutedEvent>, <xref:System.Windows.Input.CommandBinding> değil erişilir.</span><span class="sxs-lookup"><span data-stu-id="67b56-115">If the <xref:System.Windows.Input.CommandBinding> is on a sibling of the command target or another node that is not on the route of the <xref:System.Windows.RoutedEvent>, the <xref:System.Windows.Input.CommandBinding> will not be accessed.</span></span>  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 <span data-ttu-id="67b56-116">Kod uygular, sonraki bölümünde bulunan <xref:System.Windows.Input.CommandManager.Executed> ve <xref:System.Windows.Input.CommandBinding.CanExecute> olay işleyicileri.</span><span class="sxs-lookup"><span data-stu-id="67b56-116">The next section of code implements the <xref:System.Windows.Input.CommandManager.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers.</span></span>  
  
 <span data-ttu-id="67b56-117"><xref:System.Windows.Input.CommandManager.Executed> İşleyicisi açık dosyayı kapatmak için bir yöntem çağırır.</span><span class="sxs-lookup"><span data-stu-id="67b56-117">The <xref:System.Windows.Input.CommandManager.Executed> handler calls a method to close the open file.</span></span>  <span data-ttu-id="67b56-118"><xref:System.Windows.Input.CommandBinding.CanExecute> İşleyicisi bir dosyanın açık olup olmadığını belirlemek için bir yöntem çağırır.</span><span class="sxs-lookup"><span data-stu-id="67b56-118">The <xref:System.Windows.Input.CommandBinding.CanExecute> handler calls a method to determine whether a file is open.</span></span>  <span data-ttu-id="67b56-119">Bir dosya açıksa <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> ayarlanır `true`; Aksi takdirde ayarlanır `false`.</span><span class="sxs-lookup"><span data-stu-id="67b56-119">If a file is open, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> is set to `true`; otherwise, it is set to `false`.</span></span>  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a><span data-ttu-id="67b56-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="67b56-120">See Also</span></span>  
 [<span data-ttu-id="67b56-121">Komut verme genel bakış</span><span class="sxs-lookup"><span data-stu-id="67b56-121">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)