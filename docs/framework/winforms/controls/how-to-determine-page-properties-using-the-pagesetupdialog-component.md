---
title: "Nasıl Yapılır: PageSetupDialog Bileşenini Kullanarak Sayfa Özelliklerini Belirleme"
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
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dc3603d37106c122f3e92503b37dcfc02d7fef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="bdead-102">Nasıl Yapılır: PageSetupDialog Bileşenini Kullanarak Sayfa Özelliklerini Belirleme</span><span class="sxs-lookup"><span data-stu-id="bdead-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="bdead-103">[PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) kullanıcı bir belge için bileşen sunar düzeni, sayfa boyutu ve diğer sayfa düzeni seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="bdead-103">The [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="bdead-104">Örneği belirtmek zorunda <xref:System.Drawing.Printing.PrintDocument> sınıfı — yazdırılması belgeye budur.</span><span class="sxs-lookup"><span data-stu-id="bdead-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="bdead-105">Ayrıca, bu kısmen olduğu gibi kullanıcıların bilgisayarlarında, yerel olarak veya bir ağ üzerinden yüklü bir yazıcı olmalıdır nasıl <xref:System.Windows.Forms.PageSetupDialog> bileşeni kullanıcıya sunulan seçimleri biçimlendirme sayfa belirler.</span><span class="sxs-lookup"><span data-stu-id="bdead-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="bdead-106">İle çalışma önemli bir yönü <xref:System.Windows.Forms.PageSetupDialog> bileşenidir, ile nasıl etkileşim kurduğu <xref:System.Drawing.Printing.PageSettings> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bdead-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="bdead-107"><xref:System.Drawing.Printing.PageSettings> Sınıfı, bir sayfa yazdırılabilir, sayfayı ve kenar boşluklarını boyutunu Kağıt yönlendirmesi gibi şekilde değiştiren ayarları belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bdead-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="bdead-108">Bu ayarların her biri bir özelliği olarak temsil edilir <xref:System.Drawing.Printing.PageSettings> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bdead-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="bdead-109"><xref:System.Windows.Forms.PageSetupDialog> Sınıfı, belirli bir örneği için bu özellik değerlerini değiştirir <xref:System.Drawing.Printing.PageSettings> belge ile ilişkili sınıfı (ve olarak temsil edilen bir <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> özelliği).</span><span class="sxs-lookup"><span data-stu-id="bdead-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="bdead-110">PageSetupDialog bileşenini kullanarak sayfa özelliklerini ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="bdead-110">To set page properties using the PageSetupDialog component</span></span>  
  
1.  <span data-ttu-id="bdead-111">Kullanmak <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> iletişim kutusunu görüntülemek için yöntemi belirtme <xref:System.Drawing.Printing.PrintDocument> kullanmak için.</span><span class="sxs-lookup"><span data-stu-id="bdead-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="bdead-112">Aşağıdaki örnekte <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Click> olay işleyicisi açılır örneği <xref:System.Windows.Forms.PageSetupDialog> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="bdead-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="bdead-113">Var olan bir belgeyi belirtilen <xref:System.Windows.Forms.PageSetupDialog.Document%2A> özelliği ve kendi <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> özelliği ayarlanmış `false`.</span><span class="sxs-lookup"><span data-stu-id="bdead-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="bdead-114">Formunuz sahip örnek varsayar bir <xref:System.Windows.Forms.Button> denetimi, bir <xref:System.Drawing.Printing.PrintDocument> adlı bileşeni `myDocument`ve bir <xref:System.Windows.Forms.PageSetupDialog> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="bdead-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="bdead-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] ve [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="bdead-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bdead-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bdead-116">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="bdead-117">Nasıl yapılır: standart Windows Forms yazdırma işleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="bdead-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="bdead-118">PageSetupDialog bileşeni</span><span class="sxs-lookup"><span data-stu-id="bdead-118">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)