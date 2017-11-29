---
title: "SQL Server veri türleri ve ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="b7336-102">SQL Server veri türleri ve ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b7336-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="b7336-103">SQL Server ve .NET Framework olası veri kaybına yol açabilir farklı tür sistemlerde temel alır.</span><span class="sxs-lookup"><span data-stu-id="b7336-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="b7336-104">Veri bütünlüğü, SQL Server için .NET Framework veri sağlayıcısı korumak için (<xref:System.Data.SqlClient>) SQL Server verilerle çalışmak için yazılan erişimci yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="b7336-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="b7336-105">Numaralandırmalara kullanabilirsiniz <xref:System.Data.SqlDbType> belirtmek için sınıflar <xref:System.Data.SqlClient.SqlParameter> veri türleri.</span><span class="sxs-lookup"><span data-stu-id="b7336-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="b7336-106">Daha fazla bilgi ve verileri tanımlayan SQL Server ve .NET Framework veri türleri arasındaki eşlemeleri yazın bir tablo için bkz: [SQL Server veri türü eşlemeleri](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="b7336-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="b7336-107">SQL Server 2008 yapılandırılmış, yarı yapılandırılmış ve yapılandırılmamış veri tarih ve saat ile çalışmak için iş gereksinimlerini karşılamak için tasarlanmış yeni veri türleri tanıtır.</span><span class="sxs-lookup"><span data-stu-id="b7336-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="b7336-108">Bu SQL Server 2008 Books Online içinde belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="b7336-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="b7336-109">Uygulamanızda kullanılabilir SQL Server veri türleri, kullanmakta olduğunuz SQL Server sürümüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="b7336-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="b7336-110">Daha fazla bilgi için SQL Server Books Online'nın ilgili sürümü aşağıdaki tabloda bakın.</span><span class="sxs-lookup"><span data-stu-id="b7336-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="b7336-111">**SQL Server Çevrimiçi Kitapları**</span><span class="sxs-lookup"><span data-stu-id="b7336-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="b7336-112">Veri türleri (veritabanı altyapısı)</span><span class="sxs-lookup"><span data-stu-id="b7336-112">Data Types (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="b7336-113">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="b7336-113">In This Section</span></span>  
 [<span data-ttu-id="b7336-114">SqlTypes ve veri kümesi</span><span class="sxs-lookup"><span data-stu-id="b7336-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="b7336-115">Türü desteğini açıklar `SqlTypes` içinde `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="b7336-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="b7336-116">Boş değerler işleme</span><span class="sxs-lookup"><span data-stu-id="b7336-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="b7336-117">Null değerler ve üç değerli mantığı ile nasıl çalışılacağı gösterir.</span><span class="sxs-lookup"><span data-stu-id="b7336-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="b7336-118">Karşılaştırma GUID ve uniqueidentifier değerleri</span><span class="sxs-lookup"><span data-stu-id="b7336-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="b7336-119">SQL Server ve .NET Framework GUID ve uniqueidentifier değerlerle çalışma gösterir.</span><span class="sxs-lookup"><span data-stu-id="b7336-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="b7336-120">Tarih ve saat verilerini</span><span class="sxs-lookup"><span data-stu-id="b7336-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="b7336-121">SQL Server 2008'de sunulan yeni tarih ve saat veri türleri kullanmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="b7336-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="b7336-122">Büyük atama</span><span class="sxs-lookup"><span data-stu-id="b7336-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="b7336-123">SQL Server 2008'de sunulan atama büyük değerinden veri almayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="b7336-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="b7336-124">SQL Server'da XML verileri</span><span class="sxs-lookup"><span data-stu-id="b7336-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="b7336-125">SQL Server'dan alınan XML veri ile nasıl çalışılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="b7336-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b7336-126">Başvuru</span><span class="sxs-lookup"><span data-stu-id="b7336-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="b7336-127">Açıklar `DataSet` sınıfı ve tüm üyeleri.</span><span class="sxs-lookup"><span data-stu-id="b7336-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="b7336-128">Açıklar `SqlTypes` ad alanı ve tüm üyeleri.</span><span class="sxs-lookup"><span data-stu-id="b7336-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="b7336-129">Açıklar `SqlDbType` numaralandırma ve tüm üyeleri.</span><span class="sxs-lookup"><span data-stu-id="b7336-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="b7336-130">Açıklar `DbType` numaralandırma ve tüm üyeleri.</span><span class="sxs-lookup"><span data-stu-id="b7336-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7336-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b7336-131">See Also</span></span>  
 [<span data-ttu-id="b7336-132">SQL Server veri türü eşlemeleri</span><span class="sxs-lookup"><span data-stu-id="b7336-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="b7336-133">Yapılandırma parametreleri ve parametre veri türleri</span><span class="sxs-lookup"><span data-stu-id="b7336-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="b7336-134">Tablo değerli parametreleri</span><span class="sxs-lookup"><span data-stu-id="b7336-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="b7336-135">SQL Server ikili ve değeri büyük veri</span><span class="sxs-lookup"><span data-stu-id="b7336-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="b7336-136">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="b7336-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)