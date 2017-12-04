---
title: "ASP.NET Web Hizmetlerini WCF'ye Taşıma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ca1eb73842f3f7dac5557c1eafff637396d317a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-aspnet-web-services-to-wcf"></a><span data-ttu-id="fc246-102">ASP.NET Web Hizmetlerini WCF'ye Taşıma</span><span class="sxs-lookup"><span data-stu-id="fc246-102">Migrating ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="fc246-103">ASP.NET Web Hizmetleri gibi Hizmetleri Internet Information Services (IIS) içinde barındırmak için tesis oluşturmak için .NET Framework sınıf kitaplıkları ve araçlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc246-103">ASP.NET provides .NET Framework class libraries and tools for building Web services, as well as facilities for hosting services within Internet Information Services (IIS).</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="fc246-104">.NET Framework sınıf kitaplıkları, araçları ve Web Hizmetleri tarafından kullanılan dahil olmak üzere herhangi bir protokol kullanarak iletişim kurmak için yazılım varlıkları etkinleştirme barındırma olanakları sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc246-104"> provides .NET Framework class libraries, tools and hosting facilities for enabling software entities to communicate using any protocols, including those used by Web services.</span></span>  <span data-ttu-id="fc246-105">Geçirme ASP.NET Web Hizmetleri [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] yeni özellikleri ve özgü geliştirmeleri avantajlarından yararlanmak, uygulamaların sağlayan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-105">Migrating ASP.NET Web Services to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows your applications to take advantage of new features and improvements that are unique to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fc246-106">ASP.NET Web Hizmetleri göre birkaç önemli avantajı vardır.</span><span class="sxs-lookup"><span data-stu-id="fc246-106"> has several important advantages relative to ASP.NET Web services.</span></span> <span data-ttu-id="fc246-107">ASP.NET Web Hizmetleri Araçları yalnızca Web hizmetleri oluşturmak için durumdayken [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] birbirleriyle iletişim kurmak için yazılım varlıkları yapılmalıdır zaman kullanılabilen araçlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc246-107">While ASP.NET Web services tools are solely for building Web services, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides tools that can be used when software entities must be made to communicate with one another.</span></span> <span data-ttu-id="fc246-108">Bu geliştiriciler sırayla yazılım tamamlamak için geçen süre yanı sıra yazılım geliştirme kaynaklarını maliyetini azaltır farklı yazılım iletişimi senaryolara yer vermek için bilmesi için gerekli olan teknolojileri sayısını azaltır. geliştirme projelerini.</span><span class="sxs-lookup"><span data-stu-id="fc246-108">This will reduce the number of technologies that developers are required to know in order to accommodate different software communication scenarios, which in turn will reduce the cost of software development resources, as well as the time to complete software development projects.</span></span>  
  
 <span data-ttu-id="fc246-109">Web hizmeti geliştirme projeleri için bile [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] destekler destek ASP.NET Web Hizmetleri daha hizmeti protokolleri diğer Web.</span><span class="sxs-lookup"><span data-stu-id="fc246-109">Even for Web service development projects, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports more Web service protocols than ASP.NET Web services support.</span></span> <span data-ttu-id="fc246-110">Bu ek protokoller, ilgili, daha karmaşık çözümleri için sağlar diğer şeyleri, güvenilir oturumlar ve işlemler arasında.</span><span class="sxs-lookup"><span data-stu-id="fc246-110">These additional protocols provide for more sophisticated solutions involving, amongst other things, reliable sessions and transactions.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fc246-111">ASP.NET Web Hizmetleri daha iletileri taşıma için daha fazla protokollerini destekler.</span><span class="sxs-lookup"><span data-stu-id="fc246-111"> supports more protocols for transporting messages than ASP.NET Web services.</span></span> <span data-ttu-id="fc246-112">ASP.NET Web hizmetlerini yalnızca Köprü Metni Aktarım Protokolü (HTTP) kullanarak iletileri göndermeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="fc246-112">ASP.NET Web services only support sending messages by using the Hypertext Transfer Protocol (HTTP).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fc246-113">İletim Denetimi Protokolü (Adlandırılmış Kanallar ve Microsoft Message Queuing (MSMQ) TCP), yanı sıra, HTTP kullanarak iletileri göndermeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="fc246-113"> supports sending messages by using HTTP, as well as the Transmission Control Protocol (TCP), named pipes, and Microsoft Message Queuing (MSMQ).</span></span> <span data-ttu-id="fc246-114">Daha da önemlisi, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ek aktarım protokolleri desteklemek için genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="fc246-114">More important, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be extended to support additional transport protocols.</span></span> <span data-ttu-id="fc246-115">Bu nedenle, geliştirilmiş yazılımlar kullanarak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] çok çeşitli böylece yatırım dönüş olası artırma diğer yazılım ile birlikte çalışmak için uyarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="fc246-115">Therefore, software developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be adapted to work together with a wider variety of other software, thereby increasing the potential return on the investment.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fc246-116">uygulamaları dağıtma ve ASP.NET Web hizmetleri sağladığından daha yönetme için çok daha zengin özellikleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc246-116"> provides much richer facilities for deploying and managing applications than ASP.NET Web services provides.</span></span> <span data-ttu-id="fc246-117">ASP.NET de sahip bir yapılandırma sistemi yanı sıra [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] yapılandırma Düzenleyicisi sunar alıcıları ve aracılar, bir izleme Görüntüleyici, ileti günlüğe kaydetme, performans büyük bir dizi herhangi bir sayıda aracılığıyla geri göndericilerden gelen Etkinlik izleme sayaçlar ve Windows Yönetim Araçları için destek.</span><span class="sxs-lookup"><span data-stu-id="fc246-117">In addition to a configuration system, which ASP.NET also has, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offers a configuration editor, activity tracing from senders to receivers and back through any number of intermediaries, a trace viewer, message logging, a vast number of performance counters, and support for Windows Management Instrumentation.</span></span>  
  
 <span data-ttu-id="fc246-118">Bu olası faydaları verilen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET Web Hizmetleri göre kullanıyorsanız veya ASP.NET Web hizmetlerini kullanarak dikkate alarak, birkaç seçeneğiniz vardır:</span><span class="sxs-lookup"><span data-stu-id="fc246-118">Given these potential benefits of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relative to ASP.NET Web services, if you are using, or are considering using ASP.NET Web services you have several options:</span></span>  
  
-   <span data-ttu-id="fc246-119">ASP.NET Web Hizmetleri kullanmaya ve tarafından proffered avantajları forego devam [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-119">Continue to use ASP.NET Web services, and forego the benefits proffered by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
-   <span data-ttu-id="fc246-120">Uygulamasını kullanma amacıyla ASP.NET Web hizmetlerini kullanmaya devam [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelecekte bir zamanda.</span><span class="sxs-lookup"><span data-stu-id="fc246-120">Keep using ASP.NET Web services with the intention of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] at some time in the future.</span></span> <span data-ttu-id="fc246-121">Bu bölümdeki konular, yeni ASP.NET Web hizmeti uygulama gelecekteki birlikte kullanabilmek için için aday en üst düzeye çıkarmak açıklanmaktadır [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="fc246-121">The topics in this section explain how to maximize the prospects for being able to use new ASP.NET Web service applications together with future [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span> <span data-ttu-id="fc246-122">Bu bölümdeki konular, ayrıca yeni ASP.NET Web Hizmetleri için bunları kolaylaştırmak amacıyla nasıl oluşturulacağını açıklayan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-122">The topics in this section also explain how to build new ASP.NET Web services so as to make it easier to migrate them to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="fc246-123">Ancak, hizmetleri güvenli hale getirme önemli ya da güvenilirlik veya işlem çıkışların gerekli ise ya da özel yönetim olanakları olmasını oluşturulması sonra benimsemek için daha iyi bir seçenektir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-123">However, if securing the services is important, or reliability or transaction assurances are required, or if custom management facilities will have to be constructed, then it is a better option to adopt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fc246-124">tam olarak bu tür senaryoları için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fc246-124"> is designed for precisely such scenarios.</span></span>  
  
-   <span data-ttu-id="fc246-125">Benimsemeyi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mevcut ASP.NET Web hizmeti uygulamalarınızı sürdürmek devam ederken yeni geliştirme.</span><span class="sxs-lookup"><span data-stu-id="fc246-125">Adopt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for new development, while continuing to maintain your existing ASP.NET Web service applications.</span></span> <span data-ttu-id="fc246-126">Bu büyük olasılıkla en iyi bir seçimdir.</span><span class="sxs-lookup"><span data-stu-id="fc246-126">This choice is very likely the optimal one.</span></span> <span data-ttu-id="fc246-127">Avantajları verir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], kullanmak için var olan uygulamaları değiştirmeyi maliyetini sparing oluştu.</span><span class="sxs-lookup"><span data-stu-id="fc246-127">It yields the benefits of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], while sparing the cost of modifying the existing applications to use it.</span></span> <span data-ttu-id="fc246-128">Bu senaryoda, yeni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamaları mevcut ASP.NET uygulamaları ile birlikte bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="fc246-128">In this scenario, new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can co-exist with existing ASP.NET applications.</span></span> <span data-ttu-id="fc246-129">Yeni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamaları mevcut ASP.NET Web hizmetlerini kullanmak mümkün olacaktır ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] yeni işlemsel özellikleri tarafından virtue, varolan ASP.NET uygulamalarına programlamak için kullanılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET uyumluluk modunda.</span><span class="sxs-lookup"><span data-stu-id="fc246-129">New [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications will be able to use existing ASP.NET Web services, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be used to program new operational capabilities into existing ASP.NET applications by virtue of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode.</span></span>  
  
-   <span data-ttu-id="fc246-130">Benimsemeyi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve ASP.NET Web hizmeti uygulamalarınız için geçiş [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-130">Adopt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and migrate existing ASP.NET Web service applications to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="fc246-131">Tarafından sağlanan özellikleri ile mevcut uygulamaları geliştirmek için bu seçeneği tercih edebilirsiniz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], veya işlevselliğini mevcut ASP.NET Web Hizmetleri içinde yeni, daha güçlü oluşturmaya [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="fc246-131">You may choose this option to enhance the existing applications with features provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], or to reproduce the functionality of existing ASP.NET Web services within new, more powerful [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc246-132">Durumunda dikkatli'nin alınması gereken bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet barındırılır IIS tarafından 5.x ve ASP.NET kaldırılır.</span><span class="sxs-lookup"><span data-stu-id="fc246-132">Care must be taken if a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by IIS 5.x and ASP.NET is uninstalled.</span></span> <span data-ttu-id="fc246-133">Zaman bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmeti IIS tarafından barındırılan ASP.NET kaldırılırsa 5.x, hizmet için kod istenebilir.</span><span class="sxs-lookup"><span data-stu-id="fc246-133">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by IIS 5.x, the code for the service can be requested if ASP.NET is uninstalled.</span></span> <span data-ttu-id="fc246-134">ASP.NET IIS çalıştıran bir işletim sisteminde kaldırılması zaman 5.x ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] olduğu kaldırılırken .svc uzantılı bir dosya bir metin dosyası olarak kabul edilir ve tüm kaynak kodu da dahil olmak üzere içeriği, istemciye döndürülür.</span><span class="sxs-lookup"><span data-stu-id="fc246-134">When ASP.NET is uninstalled on an operating system that is running IIS 5.x and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is uninstalled, a file with the .svc extension is considered a text file and the contents, including any source code, is returned to the requester.</span></span>  
  
 <span data-ttu-id="fc246-135">Bu bölümde bu seçenekler ayrıntılı açıklar, ASP.NET Web Hizmetleri için karşılaştırır [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve ASP.NET Web Hizmetleri kodunuzu geçirmek yönergeler sağlar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc246-135">This section describes these options in detail, compares ASP.NET Web Services to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and provides instructions on how to migrate your ASP.NET Web Services code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc246-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fc246-136">See Also</span></span>  
 [<span data-ttu-id="fc246-137">Windows Communication Foundation'ı benimsemeyi bekleme: gelecekteki taşınmayı kolaylaştırma</span><span class="sxs-lookup"><span data-stu-id="fc246-137">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [<span data-ttu-id="fc246-138">Windows Communication Foundation'ı benimsemeyi bekleme: gelecekteki tümleştirmeyi kolaylaştırma</span><span class="sxs-lookup"><span data-stu-id="fc246-138">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [<span data-ttu-id="fc246-139">Windows Communication Foundation'ı benimsemeyi</span><span class="sxs-lookup"><span data-stu-id="fc246-139">Adopting Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [<span data-ttu-id="fc246-140">ASP.NET Web hizmetlerini amaç temel alarak WCF ve kullanılan standartları karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="fc246-140">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [<span data-ttu-id="fc246-141">ASP.NET Web hizmetlerini geliştirmeye göre WCF karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="fc246-141">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)