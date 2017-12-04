---
title: "Nasıl yapılır: varlıklar seri hale getirilebilir hale getirin"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 96d8e05fd6ce71536eacd909a831da0e14aa2f3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="14a3a-102">Nasıl yapılır: varlıklar seri hale getirilebilir hale getirin</span><span class="sxs-lookup"><span data-stu-id="14a3a-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="14a3a-103">Kodunuzu oluşturduğunuzda, varlıkları seri hale getirilebilir yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14a3a-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="14a3a-104">Sınıflar ile donatılmış <xref:System.Runtime.Serialization.DataContractAttribute> özniteliği ve sütunlarla <xref:System.Runtime.Serialization.DataMemberAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="14a3a-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="14a3a-105">Kullanan geliştiriciler [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] kullanabilirsiniz [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bu amaç için.</span><span class="sxs-lookup"><span data-stu-id="14a3a-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="14a3a-106">SQLMetal komut satırı aracı kullanıyorsanız **/serialization** seçeneğini `unidirectional` bağımsız değişkeni.</span><span class="sxs-lookup"><span data-stu-id="14a3a-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="14a3a-107">Daha fazla bilgi için bkz: [SqlMetal.exe (kod üretme aracı)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="14a3a-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14a3a-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="14a3a-108">Example</span></span>  
 <span data-ttu-id="14a3a-109">Aşağıdaki SQLMetal komut satırlarını seri hale getirilebilir varlık sahip dosyalar üretin.</span><span class="sxs-lookup"><span data-stu-id="14a3a-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="14a3a-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="14a3a-110">See Also</span></span>  
 [<span data-ttu-id="14a3a-111">Seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="14a3a-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="14a3a-112">Nesne modeli oluşturma</span><span class="sxs-lookup"><span data-stu-id="14a3a-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)