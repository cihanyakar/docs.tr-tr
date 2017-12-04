---
title: "Bir DataTable tablosundaki verileri düzenleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 341723d44960d4eaf9d8338e3c266720816c0899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="198d2-102">Bir DataTable tablosundaki verileri düzenleme</span><span class="sxs-lookup"><span data-stu-id="198d2-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="198d2-103">Oluşturduktan sonra bir <xref:System.Data.DataTable> içinde bir <xref:System.Data.DataSet>, bir tablo bir veritabanında kullanırken yaptığınız aynı etkinliklerini gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="198d2-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="198d2-104">Ekle, görüntülemek, düzenlemek ve tablosundaki verileri Sil; hatalar ve olayları izleyebilirsiniz; ve tablodaki verileri sorgulayabilir.</span><span class="sxs-lookup"><span data-stu-id="198d2-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="198d2-105">Verilerde değişiklik yapıldığında bir **DataTable**, değişiklikler doğru olduğundan ve program aracılığıyla geçir çalıştırılmayacağını olup olmadığını da doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="198d2-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="198d2-106">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="198d2-106">In This Section</span></span>  
 [<span data-ttu-id="198d2-107">DataTable tablosuna veri ekleme</span><span class="sxs-lookup"><span data-stu-id="198d2-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="198d2-108">Yeni satırlar oluşturabilir ve bunları bir tabloya ekleyebilirsiniz açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="198d2-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="198d2-109">Bir DataTable tablosundaki verileri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="198d2-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="198d2-110">Veriler özgün ve geçerli sürümleri dahil olmak üzere bir satır verilere erişim açıklar.</span><span class="sxs-lookup"><span data-stu-id="198d2-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="198d2-111">Load yöntemi</span><span class="sxs-lookup"><span data-stu-id="198d2-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="198d2-112">Kullanımını açıklar **yük** doldurmak için yöntemi bir **DataTable** satırlarla.</span><span class="sxs-lookup"><span data-stu-id="198d2-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="198d2-113">DataTable düzenlemeler</span><span class="sxs-lookup"><span data-stu-id="198d2-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="198d2-114">Önerilen değişiklikler doğrulandı ve kabul kadar bir satır değişiklikleri askıya alma dahil olmak üzere bir satır verilerde değişiklik açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="198d2-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="198d2-115">Satır durumları ve satır sürümleri</span><span class="sxs-lookup"><span data-stu-id="198d2-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="198d2-116">Bir satır farklı durumlarını hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="198d2-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="198d2-117">DataRow silme</span><span class="sxs-lookup"><span data-stu-id="198d2-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="198d2-118">Bir tablodan satır kaldırmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="198d2-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="198d2-119">Satır hata bilgileri</span><span class="sxs-lookup"><span data-stu-id="198d2-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="198d2-120">Bir uygulamadaki verilerle sorunlarını gidermenize yardımcı satır başına hata bilgilerini eklemek açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="198d2-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="198d2-121">AcceptChanges ve RejectChanges</span><span class="sxs-lookup"><span data-stu-id="198d2-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="198d2-122">Kabul etmek veya reddetmek için bir satır yapılan değişiklikler açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="198d2-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="198d2-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="198d2-123">See Also</span></span>  
 [<span data-ttu-id="198d2-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="198d2-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="198d2-125">DataTable olayları işleme</span><span class="sxs-lookup"><span data-stu-id="198d2-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="198d2-126">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="198d2-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)