---
title: "Nasıl yapılır: Metin Seçimi Alma"
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d5e1c362c02d2d1d9e1840ea2a55df6875a80ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="3b1fd-102">Nasıl yapılır: Metin Seçimi Alma</span><span class="sxs-lookup"><span data-stu-id="3b1fd-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="3b1fd-103">Bu örnek kullanmanın tek yolu gösterir <xref:System.Windows.Controls.TextBox.SelectedText%2A> özelliği kullanıcının seçtiği metni almak için bir <xref:System.Windows.Controls.TextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b1fd-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="3b1fd-104">Example</span></span>  
 <span data-ttu-id="3b1fd-105">Aşağıdaki [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] örnek tanımını gösterir bir <xref:System.Windows.Controls.TextBox> seçmek için bazı metinleri içeren denetim ve <xref:System.Windows.Controls.Button> belirtilen bir denetimle <xref:System.Windows.Controls.Button.OnClick%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="3b1fd-106">Bu örnekte, ile ilişkili bir düğme <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay işleyicisi metin seçimini almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="3b1fd-107">Kullanıcı düğmesini tıklattığında <xref:System.Windows.Controls.Button.OnClick%2A> yöntemi metin kutusuna tüm seçili metinleri bir dizeye kopyalar.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="3b1fd-108">Belirli durumlarda olarak metin seçimini (bir düğmeye tıklama) yanı sıra (metin seçimini dizeye kopyalama) bu seçimle gerçekleştirilecek eylemi kolayca değiştirilebilir çok çeşitli senaryoları uyum sağlayacak şekilde alınır.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="3b1fd-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="3b1fd-109">Example</span></span>  
 <span data-ttu-id="3b1fd-110">Aşağıdaki [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] örnekte gösterildiği bir <xref:System.Windows.Controls.Button.OnClick%2A> içinde tanımlanmış düğme için olay işleyicisini [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Bu örnek için.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-110">The following [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="3b1fd-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3b1fd-111">See Also</span></span>  
 [<span data-ttu-id="3b1fd-112">TextBox genel bakış</span><span class="sxs-lookup"><span data-stu-id="3b1fd-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="3b1fd-113">RichTextBox Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3b1fd-113">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)