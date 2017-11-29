---
title: "Desteklenen Dağıtım Senaryoları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22dcace51b2c73193356450b4b210d1c1a899e28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="supported-deployment-scenarios"></a><span data-ttu-id="36cd7-102">Desteklenen Dağıtım Senaryoları</span><span class="sxs-lookup"><span data-stu-id="36cd7-102">Supported Deployment Scenarios</span></span>
<span data-ttu-id="36cd7-103">Alt kümesini [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kısmen güvenilir uygulamalar kullanımda kullanmak için ancak bazı değil tüm senaryoların gereksinimleri karşılamak üzere tasarlanmıştır için desteklenen özellikler [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36cd7-103">The subset of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] features supported for use in partially trusted applications is designed to meet the requirements of some, but not all, scenarios for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="36cd7-104">Sunucusunda, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] karşılıyor Internet ölçeğinde gereksinimlerini paylaşılan üçüncü taraf uygulamaları çalıştırmak barındırma hizmeti sağlayıcıları, [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Orta güven izni güvenlik nedenleriyle ayarlandı.</span><span class="sxs-lookup"><span data-stu-id="36cd7-104">On the server, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] meets the requirements of Internet-scale shared hosting providers who run third-party applications in the [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Medium Trust permission set for security reasons.</span></span> <span data-ttu-id="36cd7-105">İstemci üzerindeki [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kısmi güven desteği gibi dağıtım teknolojileri gereksinimlerini karşılamak üzere tasarlanmıştır [ClickOnce dağıtımı](http://go.microsoft.com/fwlink/?LinkId=83712) veya [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]'s sorunsuz izin XAML tarayıcısı uygulaması teknoloji ve Masaüstü uygulamaları güvenilmeyen sitelerden güvenli dağıtımı.</span><span class="sxs-lookup"><span data-stu-id="36cd7-105">On the client, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] partial trust support is designed to meet the requirements of deployment technologies such as [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) or [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]'s XAML Browser Application technology, which allow seamless and secure deployment of desktop applications from untrusted sites.</span></span>  
  
## <a name="minimum-permission-requirements"></a><span data-ttu-id="36cd7-106">Minimum izin gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="36cd7-106">Minimum Permission Requirements</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="36cd7-107">özelliklerinin bir kısmı ya da aşağıdaki standart adlandırılmış izin kümeleri altında çalışan uygulamaları destekler:</span><span class="sxs-lookup"><span data-stu-id="36cd7-107"> supports a subset of features in applications running under either of the following standard named permission sets:</span></span>  
  
-   <span data-ttu-id="36cd7-108">Orta güven izinleri</span><span class="sxs-lookup"><span data-stu-id="36cd7-108">Medium Trust permissions</span></span>  
  
-   <span data-ttu-id="36cd7-109">Internet bölgesi izinleri</span><span class="sxs-lookup"><span data-stu-id="36cd7-109">Internet Zone permissions</span></span>  
  
 <span data-ttu-id="36cd7-110">Kullanılmaya çalışılıyor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] daha kısıtlayıcı izinlerle kısmen güvenilir uygulamalar çalışma zamanında güvenlik özel durumlarda neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="36cd7-110">Attempting to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in partially trusted applications with more restrictive permissions may result in security exceptions at runtime.</span></span>  
  
 <span data-ttu-id="36cd7-111">Bu izin kümeleri desteklenen özellikler hakkında daha fazla bilgi için bkz: [kısmi güven özelliği uyumluluğu](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="36cd7-111">For more information about the features supported in these permission sets, see [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).</span></span>  
  
## <a name="partial-trust-on-the-server"></a><span data-ttu-id="36cd7-112">Sunucu üzerindeki kısmi güven</span><span class="sxs-lookup"><span data-stu-id="36cd7-112">Partial Trust on the Server</span></span>  
 <span data-ttu-id="36cd7-113">Birçok ticari sağlayıcılarından [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] uygulama Web barındırma hizmetleri sunucularında çalışan uygulamaların Çalıştır zorunluluğuna [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Orta güven izin kümesi.</span><span class="sxs-lookup"><span data-stu-id="36cd7-113">Many commercial providers of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application hosting services mandate that applications running on their servers run in the [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Medium Trust permission set.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="36cd7-114">Hizmetleri, bu ortamlarda çalıştırabilir, kullandıkları sağlanan <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, ya da <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> ile aktarım düzeyinde güvenlik.</span><span class="sxs-lookup"><span data-stu-id="36cd7-114"> services can run in these environments provided they use the <xref:System.ServiceModel.BasicHttpBinding>, the <xref:System.ServiceModel.WebHttpBinding>, or the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with transport-level security.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="36cd7-115">barındırma ortamları Medium Trust çalışan hizmetler, ayrıca diğer sunuculara istemci isteklerine yanıt iletileri göndererek orta katman hizmet olarak davranamaz.</span><span class="sxs-lookup"><span data-stu-id="36cd7-115"> services running in Medium Trust hosting environments can also act as middle-tier services by sending messages to other servers in response to client requests.</span></span> <span data-ttu-id="36cd7-116">Barındırma ortamı uygulama uygun verildi, sunucuda orta katman senaryoları desteklenir <xref:System.Net.WebPermission> istenen sunucuya giden istekleri yapma.</span><span class="sxs-lookup"><span data-stu-id="36cd7-116">Middle-tier scenarios on the server are supported if the hosting environment has granted the application the appropriate <xref:System.Net.WebPermission> to make outbound requests to the desired server.</span></span>  
  
 <span data-ttu-id="36cd7-117">Desteklenen SOAP bağlamaları birini kullanarak SOAP Mesajlaşma yanı sıra [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] destekleyen <xref:System.ServiceModel.WebHttpBinding> Web stili Hizmetleri'nde kısmen güvenilir uygulamalar oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="36cd7-117">In addition to SOAP messaging using one of the supported SOAP bindings, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the <xref:System.ServiceModel.WebHttpBinding> for building Web-style services in partially trusted applications.</span></span> <span data-ttu-id="36cd7-118">[WCF Web HTTP programlama modeli](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF dağıtımı](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), ve [AJAX tümleştirme ve JSON desteği](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) özelliklerini [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] olan tüm kısmi güvende desteklenir.</span><span class="sxs-lookup"><span data-stu-id="36cd7-118">The [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), and [AJAX Integration and JSON Support](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) features of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are all supported in partial trust.</span></span>  
  
 <span data-ttu-id="36cd7-119">İş akışı hizmetleri tam güven izinleri gerektirir ve kısmen güvenilir uygulamalar içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="36cd7-119">Workflow Services require Full Trust permissions and cannot be used in partially trusted applications.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="36cd7-120">[Nasıl yapılır: ASP.NET 2.0 Orta güven kullanmak](http://go.microsoft.com/fwlink/?LinkId=84603).</span><span class="sxs-lookup"><span data-stu-id="36cd7-120"> [How to: Use Medium Trust in ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603).</span></span>  
  
## <a name="partial-trust-on-the-client"></a><span data-ttu-id="36cd7-121">İstemci üzerinde kısmi güven</span><span class="sxs-lookup"><span data-stu-id="36cd7-121">Partial Trust on the Client</span></span>  
 <span data-ttu-id="36cd7-122">Belirli güvenlik önlemleri indiriliyor ve güvenilmeyen Internet siteleriyle kod çalıştırırken alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="36cd7-122">Certain security precautions must be taken when downloading and running code from untrusted Internet sites.</span></span> <span data-ttu-id="36cd7-123">Her ikisi de [ClickOnce dağıtımı](http://go.microsoft.com/fwlink/?LinkId=83712) ve [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]kullanıcının XAML tarayıcısı uygulaması (XBAP) teknolojisi olun kısmi güven sınırlı (Internet bölgesi) güvenilmeyen kod izinleri için kullanın.</span><span class="sxs-lookup"><span data-stu-id="36cd7-123">Both [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) and [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]'s XAML Browser Application (XBAP) technology make use of partial trust to grant limited permissions (Internet Zone) to untrusted code.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="36cd7-124">kısmen güvenilir uygulamalar tarafından dağıtılan içinde uzak sunuculardan ile iletişim kurmak için kullanılan [ClickOnce dağıtımı](http://go.microsoft.com/fwlink/?LinkId=83712) veya XBAP.</span><span class="sxs-lookup"><span data-stu-id="36cd7-124"> can be used to communicate with remote servers from within partially trusted applications deployed by either [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) or XBAP.</span></span> <span data-ttu-id="36cd7-125">Internet bölgesi izin kümesi içerir <xref:System.Net.WebPermission> kaynak ana bilgisayar için sağlayan desteklenen birini kullanarak kendi kaynak sunucu ile iletişim kurmak bu uygulamaları [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bağlamaları açıklanan [kısmi güven özelliği Uyumluluk](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="36cd7-125">The Internet Zone permission set includes <xref:System.Net.WebPermission> for the originating host, which allows these applications to communicate with their origin server using any of the supported [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings described in [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cd7-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="36cd7-126">See Also</span></span>  
 [<span data-ttu-id="36cd7-127">Kod erişimi güvenliği</span><span class="sxs-lookup"><span data-stu-id="36cd7-127">Code Access Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [<span data-ttu-id="36cd7-128">Windows Presentation Foundation tarayıcıda barındırılan uygulamalar genel bakış</span><span class="sxs-lookup"><span data-stu-id="36cd7-128">Windows Presentation Foundation Browser-Hosted Applications Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [<span data-ttu-id="36cd7-129">Kısmi güven</span><span class="sxs-lookup"><span data-stu-id="36cd7-129">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [<span data-ttu-id="36cd7-130">ASP.Net Orta güven</span><span class="sxs-lookup"><span data-stu-id="36cd7-130">ASP.Net Medium Trust</span></span>](http://go.microsoft.com/fwlink/?LinkId=69328)