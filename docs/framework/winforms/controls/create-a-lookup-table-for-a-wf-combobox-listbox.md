---
title: "Nasıl yapılır: Bir Windows Forms ComboBox, ListBox veya CheckedListBox Denetimi için Arama Tablosu Oluşturma"
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
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb7ffb8a7f20c1e53b24a1db8bda326d73743a93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="a6381-102">Nasıl yapılır: Bir Windows Forms ComboBox, ListBox veya CheckedListBox Denetimi için Arama Tablosu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="a6381-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="a6381-103">Bazen kullanımı kolay bir biçimde bir Windows formunda veri görüntüleme, ancak veri programınıza daha anlamlı bir biçimde depolamak kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="a6381-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="a6381-104">Örneğin, bir sipariş formu Yemek için bir liste kutusunda ada göre menü öğelerini görüntüleyebilir.</span><span class="sxs-lookup"><span data-stu-id="a6381-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="a6381-105">Ancak, sipariş kaydı veri tablosu yemek temsil eden benzersiz kimlik numaraları içerecektir.</span><span class="sxs-lookup"><span data-stu-id="a6381-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="a6381-106">Aşağıdaki tablolarda, depolamak ve Yemek Sipariş formu verileri görüntülemek nasıl bir örneği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="a6381-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="a6381-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="a6381-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="a6381-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="a6381-108">OrderID</span></span>|<span data-ttu-id="a6381-109">Öğe kimliği</span><span class="sxs-lookup"><span data-stu-id="a6381-109">ItemID</span></span>|<span data-ttu-id="a6381-110">Miktar</span><span class="sxs-lookup"><span data-stu-id="a6381-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="a6381-111">4085</span><span class="sxs-lookup"><span data-stu-id="a6381-111">4085</span></span>|<span data-ttu-id="a6381-112">12</span><span class="sxs-lookup"><span data-stu-id="a6381-112">12</span></span>|<span data-ttu-id="a6381-113">1.</span><span class="sxs-lookup"><span data-stu-id="a6381-113">1</span></span>|  
|<span data-ttu-id="a6381-114">4086</span><span class="sxs-lookup"><span data-stu-id="a6381-114">4086</span></span>|<span data-ttu-id="a6381-115">13</span><span class="sxs-lookup"><span data-stu-id="a6381-115">13</span></span>|<span data-ttu-id="a6381-116">3</span><span class="sxs-lookup"><span data-stu-id="a6381-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="a6381-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="a6381-117">ItemTable</span></span>  
  
|<span data-ttu-id="a6381-118">Kimlik</span><span class="sxs-lookup"><span data-stu-id="a6381-118">ID</span></span>|<span data-ttu-id="a6381-119">Ad</span><span class="sxs-lookup"><span data-stu-id="a6381-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="a6381-120">12</span><span class="sxs-lookup"><span data-stu-id="a6381-120">12</span></span>|<span data-ttu-id="a6381-121">Patates</span><span class="sxs-lookup"><span data-stu-id="a6381-121">Potato</span></span>|  
|<span data-ttu-id="a6381-122">13</span><span class="sxs-lookup"><span data-stu-id="a6381-122">13</span></span>|<span data-ttu-id="a6381-123">Tavuk</span><span class="sxs-lookup"><span data-stu-id="a6381-123">Chicken</span></span>|  
  
 <span data-ttu-id="a6381-124">Bu senaryoda, bir tablo **OrderDetailsTable**, kaydetme ve görüntüleme ile ilgili gerçek bilgileri depolar.</span><span class="sxs-lookup"><span data-stu-id="a6381-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="a6381-125">Ancak alanı kaydetmek için bunu oldukça şifreli biçimde yapar.</span><span class="sxs-lookup"><span data-stu-id="a6381-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="a6381-126">Diğer tablo **ItemTable**, hangi kimliği hakkında sayıdır hangi yemek adına ve gerçek yemek siparişler hakkında hiçbir şey eşdeğer yalnızca görünüm ilgili bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="a6381-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="a6381-127">**ItemTable** bağlı <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, veya <xref:System.Windows.Forms.CheckedListBox> denetim üç özellik aracılığıyla.</span><span class="sxs-lookup"><span data-stu-id="a6381-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="a6381-128">`DataSource` Özelliği, bu tablonun adını içerir.</span><span class="sxs-lookup"><span data-stu-id="a6381-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="a6381-129">`DisplayMember` Özelliği (yemek adı) denetiminde görüntülemek istediğiniz bu tablonun veri sütunu içerir.</span><span class="sxs-lookup"><span data-stu-id="a6381-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="a6381-130">`ValueMember` Özelliği (kimlik numarası) depolanmış bilgilerle bu tablonun veri sütunu içerir.</span><span class="sxs-lookup"><span data-stu-id="a6381-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="a6381-131">**OrderDetailsTable** üzerinden erişilen kendi bağlamaları koleksiyonu tarafından denetime bağlı <xref:System.Windows.Forms.Control.DataBindings%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a6381-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="a6381-132">Koleksiyona bir bağlama nesnesi eklediğinizde, denetim özelliğini bir veri kaynağındaki belirli veri üyesini (kimlik numaraları sütun) bağlandığınız ( **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="a6381-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="a6381-133">Denetimde bir seçim yapıldığında, bu form girişi kaydedildiği tablodur.</span><span class="sxs-lookup"><span data-stu-id="a6381-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="a6381-134">Arama tablosu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a6381-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="a6381-135">Ekleme bir <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, veya <xref:System.Windows.Forms.CheckedListBox> forma denetim.</span><span class="sxs-lookup"><span data-stu-id="a6381-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="a6381-136">Veri kaynağına bağlanın.</span><span class="sxs-lookup"><span data-stu-id="a6381-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="a6381-137">İki tablo arasında veri ilişkisi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a6381-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="a6381-138">Bkz: [DataRelation nesnelerine giriş](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span><span class="sxs-lookup"><span data-stu-id="a6381-138">See [Introduction to DataRelation Objects](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span></span>  
  
4.  <span data-ttu-id="a6381-139">Aşağıdaki özellikleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="a6381-139">Set the following properties.</span></span> <span data-ttu-id="a6381-140">Bunlar, kod veya tasarımcı ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="a6381-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="a6381-141">Özellik</span><span class="sxs-lookup"><span data-stu-id="a6381-141">Property</span></span>|<span data-ttu-id="a6381-142">Ayar</span><span class="sxs-lookup"><span data-stu-id="a6381-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="a6381-143">Hangi kimliği hakkında hangi öğeye eşdeğer sayıdır bilgi içeren tablo.</span><span class="sxs-lookup"><span data-stu-id="a6381-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="a6381-144">Önceki senaryoda budur `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="a6381-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="a6381-145">Denetimde görüntülemek istediğiniz veri kaynağı tablosuna sütun.</span><span class="sxs-lookup"><span data-stu-id="a6381-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="a6381-146">Önceki senaryoda budur `"Name"` (kodda ayarlamak için tırnak işaretleri kullanın).</span><span class="sxs-lookup"><span data-stu-id="a6381-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="a6381-147">Depolanan bilgiler içeren veri kaynağı tablo sütun.</span><span class="sxs-lookup"><span data-stu-id="a6381-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="a6381-148">Önceki senaryoda budur `"ID"` (kodda ayarlamak için tırnak işaretleri kullanın).</span><span class="sxs-lookup"><span data-stu-id="a6381-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="a6381-149">Bir yordamda çağrısı <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> yöntemi <xref:System.Windows.Forms.ControlBindingsCollection> denetimin bağlamak için sınıf <xref:System.Windows.Forms.ListControl.SelectedValue%2A> form girişi kaydı tabloya özelliği.</span><span class="sxs-lookup"><span data-stu-id="a6381-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="a6381-150">Ayrıca, kodda yerine tasarımcısında denetimin erişerek bunu yapabilirsiniz <xref:System.Windows.Forms.Control.DataBindings%2A> özelliğinde **özellikleri** penceresi.</span><span class="sxs-lookup"><span data-stu-id="a6381-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="a6381-151">Önceki senaryoda budur `OrderDetailsTable`, ve sütun `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="a6381-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a6381-152">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a6381-152">See Also</span></span>  
 [<span data-ttu-id="a6381-153">Veri bağlama ve Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6381-153">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="a6381-154">ListBox denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="a6381-154">ListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="a6381-155">ComboBox denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="a6381-155">ComboBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [<span data-ttu-id="a6381-156">CheckedListBox denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="a6381-156">CheckedListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="a6381-157">Windows Forms denetimleri seçenekleri listelemek için kullanılır</span><span class="sxs-lookup"><span data-stu-id="a6381-157">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)