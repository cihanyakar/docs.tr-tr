---
title: "Hızlı Başlangıç (WCF Veri Hizmetleri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08296be1002ee50e18a45c546645f4cc117d6bb5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="83abd-102">Hızlı Başlangıç (WCF Veri Hizmetleri)</span><span class="sxs-lookup"><span data-stu-id="83abd-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="83abd-103">Bu hızlı başlangıç öğrenmeniz yardımcı olan [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ve [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] konular, destek görevleri bir dizi [Başlarken](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="83abd-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="83abd-104">Ne öğreneceksiniz</span><span class="sxs-lookup"><span data-stu-id="83abd-104">What You Will Learn</span></span>  
 <span data-ttu-id="83abd-105">Bu hızlı başlangıç ilk görevde kullanıma sunmak için veri hizmeti oluşturmayı gösteren bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Northwind örnek veritabanından akış.</span><span class="sxs-lookup"><span data-stu-id="83abd-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="83abd-106">Sonraki konularda size erişecek [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] bir Web tarayıcısı kullanarak akış ve ayrıca oluşturabilirsiniz bir [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] tüketir istemci uygulaması [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] istemci kitaplıkları kullanarak akış.</span><span class="sxs-lookup"><span data-stu-id="83abd-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83abd-107">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="83abd-107">Prerequisites</span></span>  
 <span data-ttu-id="83abd-108">Bu hızlı başlangıç tamamlamak için aşağıdaki bileşenleri yüklemeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="83abd-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="83abd-109">.</span><span class="sxs-lookup"><span data-stu-id="83abd-109">.</span></span>  
  
-   <span data-ttu-id="83abd-110">Örneği [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83abd-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83abd-111">Bu varsayılan yüklemede bulunan SQL Server Express içerir [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83abd-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="83abd-112">Northwind örnek veritabanı.</span><span class="sxs-lookup"><span data-stu-id="83abd-112">The Northwind sample database.</span></span> <span data-ttu-id="83abd-113">Bu örnek veritabanı karşıdan yüklemek için indirme sayfasına bakın [örnek veritabanları için SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="83abd-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="83abd-114">Hızlı Başlangıç görevleri WCF Veri Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="83abd-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="83abd-115">Veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="83abd-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="83abd-116">Tanımlamak [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] uygulama, veri modelini tanımlar, veri hizmeti oluşturma ve kaynaklarına erişimi etkinleştirme.</span><span class="sxs-lookup"><span data-stu-id="83abd-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="83abd-117">Bir Web tarayıcısından hizmetine erişim</span><span class="sxs-lookup"><span data-stu-id="83abd-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="83abd-118">Hizmeti Başlat [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] ve HTTP GET isteklerini gösterilen akışa bir Web tarayıcısı aracılığıyla göndererek hizmet erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="83abd-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="83abd-119">.NET Framework istemci uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="83abd-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="83abd-120">Oluşturma bir [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] kullanmak için istemci uygulaması [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akışı, Windows denetimlere veri bağlama, veri bağlama denetimleri değiştirin ve değişiklikleri veri hizmetine geri gönderin.</span><span class="sxs-lookup"><span data-stu-id="83abd-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83abd-121">Hızlı Başlangıç tamamlanmış bir sürümünden proje dosyalarını adresinden yüklenebilir [WCF Veri Hizmetleri belgeleri örnekleri](http://go.microsoft.com/fwlink/?LinkId=179994) sayfası.</span><span class="sxs-lookup"><span data-stu-id="83abd-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83abd-122">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="83abd-122">Next Steps</span></span>  
 <span data-ttu-id="83abd-123">[Hızlı Başlat](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="83abd-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83abd-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="83abd-124">See Also</span></span>  
 [<span data-ttu-id="83abd-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="83abd-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)