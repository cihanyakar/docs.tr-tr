---
title: "İşlev vs. Yordam programlama (LINQ-XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b6aa8ce45afdb68f7ff544b8c8f2f5e1e4a79533
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="2d677-102">İşlev vs. Yordam programlama (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d677-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2d677-103">XML uygulamaları çeşitli türleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="2d677-103">There are various types of XML applications:</span></span>  
  
-   <span data-ttu-id="2d677-104">Bazı uygulamalar kaynak XML belgelerini almak ve kaynak belgeleri değerinden farklı bir şeklinde olan yeni XML belgeleri oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="2d677-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
-   <span data-ttu-id="2d677-105">Bazı uygulamalar kaynak XML belgelerini ayırın ve HTML veya CSV metin dosyaları gibi tamamen farklı bir form sonuç belgelerde üretir.</span><span class="sxs-lookup"><span data-stu-id="2d677-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
-   <span data-ttu-id="2d677-106">Bazı uygulamalar kaynak XML belgelerini almak ve bir veritabanına kayıtları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="2d677-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
-   <span data-ttu-id="2d677-107">Bazı uygulamalar, bir veritabanı gibi başka bir kaynaktan veri almak ve XML belgeleri oluşturun.</span><span class="sxs-lookup"><span data-stu-id="2d677-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="2d677-108">Bu tüm XML uygulama türlerini değildir, ancak bunlar temsilcisi uygulamak için bir XML Programcı sahip işlevselliği türlerini kümesidir.</span><span class="sxs-lookup"><span data-stu-id="2d677-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="2d677-109">Tüm bu tür uygulamalar, bir geliştirici sürebilir karşıt iki yaklaşım vardır:</span><span class="sxs-lookup"><span data-stu-id="2d677-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
-   <span data-ttu-id="2d677-110">Bildirim temelli bir yaklaşım kullanarak işlev oluşturma.</span><span class="sxs-lookup"><span data-stu-id="2d677-110">Functional construction using a declarative approach.</span></span>  
  
-   <span data-ttu-id="2d677-111">Bellek içi XML ağaç değişikliği yordam kodu kullanarak.</span><span class="sxs-lookup"><span data-stu-id="2d677-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="2d677-112">LINQ-XML her iki yaklaşımın destekler.</span><span class="sxs-lookup"><span data-stu-id="2d677-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="2d677-113">İşlev yaklaşımı kullanarak, kaynak belgeleri yapan ve oluşturmak istediğiniz şekli tamamen yeni sonuç belgelerle dönüşümleri yazma.</span><span class="sxs-lookup"><span data-stu-id="2d677-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="2d677-114">Bir XML ağacı yerinde değiştirirken, ekleme, silme ve gerektiğinde düğümleri değiştirme erişir ve bir bellek içi XML ağacında düğümler üzerinden gider kod yazın.</span><span class="sxs-lookup"><span data-stu-id="2d677-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="2d677-115">LINQ-XML her iki yaklaşım ile kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2d677-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="2d677-116">Aynı sınıflarını kullanın ve bazı durumlarda aynı yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="2d677-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="2d677-117">Ancak, iki yaklaşım, hedefler ve yapısı çok farklı değildir.</span><span class="sxs-lookup"><span data-stu-id="2d677-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="2d677-118">Örneğin, farklı durumlarda bir ya da bir yaklaşım genellikle daha iyi performans sahip ve fazla veya az bellek kullanır.</span><span class="sxs-lookup"><span data-stu-id="2d677-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="2d677-119">Ayrıca, bir ya da bir yaklaşım yazmak ve daha fazla Bakımı yapılabilir kodu elde etmek daha kolay olacaktır.</span><span class="sxs-lookup"><span data-stu-id="2d677-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="2d677-120">Contrasted iki yaklaşım görmek için bkz: [bellek içi XML ağaç değişikliği vs. İşlev yapımı (LINQ-XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2d677-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2d677-121">İşlev dönüşümleri yazma bir öğretici için bkz: [saf işlevsel dönüşümleri XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2d677-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d677-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2d677-122">See Also</span></span>  
 [<span data-ttu-id="2d677-123">LINQ-XML programlamaya genel bakış (C#)</span><span class="sxs-lookup"><span data-stu-id="2d677-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)