---
title: "Nasıl yapılır: Doldurmayı kullanarak Windows Forms Denetiminin Çevresinde Kenarlık Oluşturma"
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
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 573a27343a15ef12ad955295c3beb3fef9130023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="f0a8e-102">Nasıl yapılır: Doldurmayı kullanarak Windows Forms Denetiminin Çevresinde Kenarlık Oluşturma</span><span class="sxs-lookup"><span data-stu-id="f0a8e-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="f0a8e-103">Aşağıdaki kod örneğinde kenarlık oluşturma veya geçici anahat gösteren bir <xref:System.Windows.Forms.RichTextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="f0a8e-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="f0a8e-104">Örnek değerini ayarlar bir <xref:System.Windows.Forms.Panel> denetimin <xref:System.Windows.Forms.Padding> özelliğini 5 ve ayarlar <xref:System.Windows.Forms.Control.Dock%2A> bir alt özelliği <xref:System.Windows.Forms.RichTextBox> denetimini <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="f0a8e-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="f0a8e-105"><xref:System.Windows.Forms.Control.BackColor%2A> , <xref:System.Windows.Forms.Panel> Denetim ayarlanmış <xref:System.Drawing.Color.Blue%2A>, mavi kenarlık oluşturur <xref:System.Windows.Forms.RichTextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="f0a8e-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0a8e-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="f0a8e-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f0a8e-107">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f0a8e-107">See Also</span></span>  
 <xref:System.Windows.Forms.Padding>  
 [<span data-ttu-id="f0a8e-108">Kenar boşlukları ve Windows Forms denetimleri doldurma</span><span class="sxs-lookup"><span data-stu-id="f0a8e-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)