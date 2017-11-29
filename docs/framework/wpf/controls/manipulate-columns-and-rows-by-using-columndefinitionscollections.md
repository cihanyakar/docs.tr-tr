---
title: "Nasıl yapılır: ColumnDefinitionsCollections ve RowDefinitionsCollections Kullanarak Sütunları ve Satırları İşleme"
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
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e87c5001a676bcda331d289c286cf6b3e87c136f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="eb07f-102">Nasıl yapılır: ColumnDefinitionsCollections ve RowDefinitionsCollections Kullanarak Sütunları ve Satırları İşleme</span><span class="sxs-lookup"><span data-stu-id="eb07f-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="eb07f-103">Bu örnek yöntemleri kullanmayı gösterir <xref:System.Windows.Controls.ColumnDefinitionCollection> ve <xref:System.Windows.Controls.RowDefinitionCollection> ekleme, temizleme veya satır veya sütun içeriğini sayma gibi eylemleri gerçekleştirmek için sınıflar.</span><span class="sxs-lookup"><span data-stu-id="eb07f-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="eb07f-104">Örneğin, <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, veya <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> içinde yer alan öğeleri bir <xref:System.Windows.Controls.ColumnDefinition> veya <xref:System.Windows.Controls.RowDefinition>.</span><span class="sxs-lookup"><span data-stu-id="eb07f-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb07f-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="eb07f-105">Example</span></span>  
 <span data-ttu-id="eb07f-106">Aşağıdaki örnekte bir <xref:System.Windows.Controls.Grid> öğesi ile bir <xref:System.Windows.FrameworkElement.Name%2A> , `grid1`.</span><span class="sxs-lookup"><span data-stu-id="eb07f-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="eb07f-107"><xref:System.Windows.Controls.Grid> İçeren bir <xref:System.Windows.Controls.StackPanel> tutan <xref:System.Windows.Controls.Button> öğeleri, her denetlenen farklı koleksiyon metodu tarafından.</span><span class="sxs-lookup"><span data-stu-id="eb07f-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="eb07f-108">' A tıkladığınızda bir <xref:System.Windows.Controls.Button>, arka plan kod dosyasına bir yöntem çağrısı etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="eb07f-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="eb07f-109">Bu örnek özel yöntemler, her karşılık gelen bir dizi tanımlayan bir <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olayında [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dosya.</span><span class="sxs-lookup"><span data-stu-id="eb07f-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="eb07f-110">Sütun ve satır sayısını değiştirebilirsiniz <xref:System.Windows.Controls.Grid> çeşitli yollarla da içeren ekleme veya satırları ve sütunları; kaldırma ve sayım satırları ve sütunları toplam sayısı.</span><span class="sxs-lookup"><span data-stu-id="eb07f-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="eb07f-111">Önlemek için <xref:System.ArgumentOutOfRangeException> ve <xref:System.ArgumentException> özel durumlar, hata denetleme işlevini kullanabilirsiniz, <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="eb07f-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="eb07f-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eb07f-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>