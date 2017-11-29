---
title: "SQL Server ortak dil çalışma zamanı tümleştirmesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3705db8b9d359ce83c6c47bef58de327745bed44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="c7b43-102">SQL Server ortak dil çalışma zamanı tümleştirmesi</span><span class="sxs-lookup"><span data-stu-id="c7b43-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="c7b43-103">.NET Framework ortak dil çalışma zamanı (CLR) bileşeni tümleştirme Windows için Microsoft SQL Server 2005 sunmuştur.</span><span class="sxs-lookup"><span data-stu-id="c7b43-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="c7b43-104">Bu, saklı yordamlar, Tetikleyiciler, kullanıcı tanımlı türler, kullanıcı tanımlı işlevler, kullanıcı tanımlı toplamlarda ve akış tablo değerli işlevler, Microsoft Visual Basic .NET ve Microsoft dahil olmak üzere, herhangi bir .NET Framework dil kullanarak yazabildiğinizi anlamına gelir. Visual C#.</span><span class="sxs-lookup"><span data-stu-id="c7b43-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="c7b43-105"><xref:Microsoft.SqlServer.Server> Ad alanı, böylece yönetilen kod ile Microsoft SQL Server ortamını etkileşim kurabilen bir dizi yeni uygulama programlama arabirimleri (API) içerir.</span><span class="sxs-lookup"><span data-stu-id="c7b43-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="c7b43-106">Bu bölümde, özellikleri ve SQL Server ortak dil çalışma zamanı (CLR) tümleştirmesini ve SQL Server işlem içi belirli uzantılar ADO.NET özgü davranışları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c7b43-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="c7b43-107">Bu bölümde, SQL Server CLR Tümleştirmesi ile programlamaya başlamak için yeterli bilgi yalnızca sağlamak için tasarlanmıştır ve kapsamlı olması düşünülmemiştir.</span><span class="sxs-lookup"><span data-stu-id="c7b43-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="c7b43-108">Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü, kullanmakta olduğunuz SQL Server sürümü için bkz.</span><span class="sxs-lookup"><span data-stu-id="c7b43-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="c7b43-109">**SQL Server Çevrimiçi Kitapları**</span><span class="sxs-lookup"><span data-stu-id="c7b43-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c7b43-110">Ortak dil çalışma zamanı (CLR) tümleştirmesini programlama kavramları</span><span class="sxs-lookup"><span data-stu-id="c7b43-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="c7b43-111">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="c7b43-111">In This Section</span></span>  
 [<span data-ttu-id="c7b43-112">SQL Server CLR tümleştirmesine giriş</span><span class="sxs-lookup"><span data-stu-id="c7b43-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="c7b43-113">SQL Server CLR tümleştirmesi tanıtılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c7b43-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="c7b43-114">Ek konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c7b43-115">CLR kullanıcı tanımlı işlevler</span><span class="sxs-lookup"><span data-stu-id="c7b43-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="c7b43-116">CLR işlevleri çeşitli türleri uygulamak ve nasıl kullanılacağını açıklar: Tablo değerli, skaler ve kullanıcı tanımlı toplama işlevleri.</span><span class="sxs-lookup"><span data-stu-id="c7b43-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="c7b43-117">CLR kullanıcı tanımlı türler</span><span class="sxs-lookup"><span data-stu-id="c7b43-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="c7b43-118">CLR kullanıcı tanımlı türler uygulamak ve nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="c7b43-119">Ek konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c7b43-120">CLR saklı yordamlar</span><span class="sxs-lookup"><span data-stu-id="c7b43-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="c7b43-121">CLR saklı yordamları uygulayın ve nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="c7b43-122">Ek konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c7b43-123">CLR Tetikleyiciler</span><span class="sxs-lookup"><span data-stu-id="c7b43-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="c7b43-124">CLR Tetikleyiciler uygulamak ve nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="c7b43-125">Ek konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c7b43-126">İçerik Bağlantısı</span><span class="sxs-lookup"><span data-stu-id="c7b43-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="c7b43-127">İçerik Bağlantısı açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="c7b43-128">SQL Server içinde-işleme özgü ADO.NET davranışını</span><span class="sxs-lookup"><span data-stu-id="c7b43-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="c7b43-129">SQL Server işlem içi belirli uzantılara ADO.NET ve içerik bağlantısı açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="c7b43-130">Ek konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7b43-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b43-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c7b43-131">See Also</span></span>  
 [<span data-ttu-id="c7b43-132">SQL Server ve ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c7b43-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="c7b43-133">Yönetilen kodda SQL Server 2005'te nesneleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="c7b43-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="c7b43-134">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="c7b43-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)