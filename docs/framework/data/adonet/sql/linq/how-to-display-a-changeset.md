---
title: "Nasıl yapılır: bir değişiklik kümesini görüntüleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 19f0198103999da687e07f472cd5a480406830cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="eebf8-102">Nasıl yapılır: bir değişiklik kümesini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="eebf8-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="eebf8-103">Tarafından izlenen değişiklikleri görüntüleyebilirsiniz bir <xref:System.Data.Linq.DataContext> kullanarak <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span><span class="sxs-lookup"><span data-stu-id="eebf8-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eebf8-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="eebf8-104">Example</span></span>  
 <span data-ttu-id="eebf8-105">Aşağıdaki örnek, şehir Londra olduğundan, Paris için Şehir değiştirir ve değişiklikleri veritabanına geri gönderir müşteriler alır.</span><span class="sxs-lookup"><span data-stu-id="eebf8-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="eebf8-106">Bu kod çıktısı aşağıdakine benzer görünür.</span><span class="sxs-lookup"><span data-stu-id="eebf8-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="eebf8-107">Sonunda Özet sekiz değişikliklerin yapıldığı gösterdiğine dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="eebf8-107">Note that the summary at the end shows that eight changes were made.</span></span>  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## <a name="see-also"></a><span data-ttu-id="eebf8-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eebf8-108">See Also</span></span>  
 [<span data-ttu-id="eebf8-109">Hata ayıklama desteği</span><span class="sxs-lookup"><span data-stu-id="eebf8-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)