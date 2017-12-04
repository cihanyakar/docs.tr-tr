---
title: "Internet Information Services Tarafından Barındırılan Bir WCF Hizmeti Dağıtma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9b19e111e11097cbb4b4af60ae0b28956a4a381
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a><span data-ttu-id="63eb4-102">Internet Information Services Tarafından Barındırılan Bir WCF Hizmeti Dağıtma</span><span class="sxs-lookup"><span data-stu-id="63eb4-102">Deploying an Internet Information Services-Hosted WCF Service</span></span>
<span data-ttu-id="63eb4-103">Geliştirme ve dağıtma bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Internet Information Services (IIS) barındırılan hizmeti, aşağıdaki görevleri içerir:</span><span class="sxs-lookup"><span data-stu-id="63eb4-103">Developing and deploying a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS) consists of the following tasks:</span></span>  
  
-   <span data-ttu-id="63eb4-104">Sağlamak bu IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] etkinleştirme bileşen doğru yüklendiğinden ve kayıtlı.</span><span class="sxs-lookup"><span data-stu-id="63eb4-104">Ensure that IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activation component are correctly installed and registered.</span></span>  
  
-   <span data-ttu-id="63eb4-105">Yeni bir IIS uygulaması oluşturun veya varolan bir yeniden [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] uygulama.</span><span class="sxs-lookup"><span data-stu-id="63eb4-105">Create a new IIS application, or reuse an existing [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
-   <span data-ttu-id="63eb4-106">İçin bir .svc dosyası oluşturmak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet.</span><span class="sxs-lookup"><span data-stu-id="63eb4-106">Create a .svc file for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
-   <span data-ttu-id="63eb4-107">Hizmet uygulaması için IIS uygulama dağıtın.</span><span class="sxs-lookup"><span data-stu-id="63eb4-107">Deploy the service implementation to the IIS application.</span></span>  
  
-   <span data-ttu-id="63eb4-108">Yapılandırma [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet.</span><span class="sxs-lookup"><span data-stu-id="63eb4-108">Configure the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="63eb4-109">Bir IIS tarafından barındırılan oluşturma ayrıntılı kılavuz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet için bkz: [nasıl yapılır: IIS'de WCF Hizmeti barındırma](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="63eb4-109">For a detailed walkthrough of creating an IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a><span data-ttu-id="63eb4-110">IIS, ASP.NET ve WCF doğru olduğundan emin olun yüklü ve kayıtlı</span><span class="sxs-lookup"><span data-stu-id="63eb4-110">Ensure That IIS, ASP.NET and WCF Are Correctly Installed and Registered</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="63eb4-111">, IIS ve ASP.NET yüklü olmalıdır için IIS tarafından barındırılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] düzgün çalışması için hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="63eb4-111">, IIS, and ASP.NET must be installed for IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to function correctly.</span></span> <span data-ttu-id="63eb4-112">Yükleme yordamlarına [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (bir parçası olarak [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET ve IIS kullanılan işletim sistemi sürümüne bağlı olarak farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-112">The procedures for installing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (as part of the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET and IIS vary depending on the operating system version being used.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="63eb4-113">Yükleme [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], bkz: [Microsoft .NET Framework 4 Web yükleyicisi](http://go.microsoft.com/fwlink/?LinkId=201185).</span><span class="sxs-lookup"><span data-stu-id="63eb4-113"> installing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], see [Microsoft .NET Framework 4 Web Installer](http://go.microsoft.com/fwlink/?LinkId=201185).</span></span> <span data-ttu-id="63eb4-114">IIS yüklemek için yönergeleri bulunabilir [IIS yükleme](http://go.microsoft.com/fwlink/?LinkId=201188).</span><span class="sxs-lookup"><span data-stu-id="63eb4-114">Instructions for installing IIS can be found at [Installing IIS](http://go.microsoft.com/fwlink/?LinkId=201188).</span></span>  
  
 <span data-ttu-id="63eb4-115">Yükleme işlemi [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] otomatik olarak kaydeder [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] IIS makinede zaten varsa, IIS ile.</span><span class="sxs-lookup"><span data-stu-id="63eb4-115">The installation process for the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] automatically registers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with IIS if IIS is already present on the machine.</span></span> <span data-ttu-id="63eb4-116">Sonra IIS yüklü değilse [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], ek bir adım kaydetmek için gerekli [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] IIS ile ve [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63eb4-116">If IIS is installed after the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], an additional step is required to register [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with IIS and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="63eb4-117">Aşağıdaki gibi işletim sistemine bağlı olarak bunu yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="63eb4-117">You can do this as follows, depending on your operating system:</span></span>  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]<span data-ttu-id="63eb4-118">, Windows 7 ve [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: kullanmak [ServiceModel Kayıt Aracı (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) kaydetmek için aracı [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] IIS ile: Bu aracı kullanmak için yazın **ServiceModelReg.exe /i /x** içinde Visual Studio komut istemi.</span><span class="sxs-lookup"><span data-stu-id="63eb4-118">, Windows 7, and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: Use the [ServiceModel Registration Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) tool to register [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with IIS: To use this tool, type **ServiceModelReg.exe /i /x** in the Visual Studio command prompt.</span></span> <span data-ttu-id="63eb4-119">Bu komut istemi Başlat düğmesine tıkladığınızda, seçerek açabilirsiniz **tüm programlar**, **Microsoft Visual Studio 2012**, **Visual Studio Araçları**, ve  **Visual Studio komut istemi**</span><span class="sxs-lookup"><span data-stu-id="63eb4-119">You can open this command prompt by clicking the start button, selecting **All Programs**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**, and **Visual Studio Command Prompt**</span></span>  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]<span data-ttu-id="63eb4-120">: Windows Communication Foundation etkinleştirme bileşenleri alt bileşeni yüklemek [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63eb4-120">: Install the Windows Communication Foundation Activation Components subcomponent of the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span> <span data-ttu-id="63eb4-121">Bu, Denetim Masası'nda yapmak için **Program Ekle veya Kaldır** ve ardından **Ekle\/Windows bileşenleri Kaldır**.</span><span class="sxs-lookup"><span data-stu-id="63eb4-121">To do this, in Control Panel, click **Add or Remove Programs** and then **Add\/Remove Windows Components**.</span></span> <span data-ttu-id="63eb4-122">Bu etkinleştirir **Windows Bileşen Sihirbazı**.</span><span class="sxs-lookup"><span data-stu-id="63eb4-122">This activates the **Windows Component Wizard**.</span></span>  
  
-   <span data-ttu-id="63eb4-123">Windows 7:</span><span class="sxs-lookup"><span data-stu-id="63eb4-123">Windows 7:</span></span>  
  
 <span data-ttu-id="63eb4-124">Son olarak ASP.NET, .NET Framework sürüm 4 kullanmak için yapılandırıldığını doğrulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-124">Finally you must verify that ASP.NET is configured to use the .NET Framework version 4.</span></span> <span data-ttu-id="63eb4-125">– İ ASPNET_Regiis Aracı'nı çalıştırarak bunu seçeneği.</span><span class="sxs-lookup"><span data-stu-id="63eb4-125">You do this by running the ASPNET_Regiis tool with the –i option.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="63eb4-126">[ASP.NET IIS Kayıt Aracı](http://go.microsoft.com/fwlink/?LinkId=201186)</span><span class="sxs-lookup"><span data-stu-id="63eb4-126"> [ASP.NET IIS Registration Tool](http://go.microsoft.com/fwlink/?LinkId=201186)</span></span>  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a><span data-ttu-id="63eb4-127">Yeni bir IIS uygulama oluşturmak veya mevcut bir ASP.NET uygulamasını kullanın</span><span class="sxs-lookup"><span data-stu-id="63eb4-127">Create a New IIS Application or Reuse an Existing ASP.NET Application</span></span>  
 <span data-ttu-id="63eb4-128">IIS barındırılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri, bir IIS uygulamasının içinde bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-128">IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services must reside inside of an IIS application.</span></span> <span data-ttu-id="63eb4-129">Ana bilgisayar için yeni bir IIS uygulama oluşturabileceğiniz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] özel olarak Hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="63eb4-129">You can create a new IIS application to host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services exclusively.</span></span> <span data-ttu-id="63eb4-130">Alternatif olarak, dağıtabileceğiniz bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mevcut uygulamaya zaten barındırma hizmet [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] içerik (örneğin, .aspx sayfaları ve ASP.NET Web Hizmetleri [ASMX]).</span><span class="sxs-lookup"><span data-stu-id="63eb4-130">Alternatively, you can deploy an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service into an existing application that is already hosting [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] content (such as .aspx pages and ASP.NET Web services [ASMX]).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="63eb4-131">bkz. Bu seçenekleri "barındırma WCF yan yana ASP.NET ile" ve "Barındırma WCF hizmetleri, ASP.NET uyumluluk modu" bölümlerde [WCF hizmetleri ve ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="63eb4-131"> these options, see the "Hosting WCF Side-by-Side with ASP.NET" and "Hosting WCF Services in ASP.NET Compatibility Mode" sections in [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>  
  
 <span data-ttu-id="63eb4-132">Unutmayın [!INCLUDE[iis601](../../../../includes/iis601-md.md)] ve sonraki sürümleri düzenli aralıklarla yalıtılmış bir nesne odaklı programlama uygulamayı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="63eb4-132">Note that [!INCLUDE[iis601](../../../../includes/iis601-md.md)] and later versions periodically restart an isolated object-oriented programming application.</span></span> <span data-ttu-id="63eb4-133">Varsayılan değer 1740 dakikadır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-133">The default value is 1740 minutes.</span></span> <span data-ttu-id="63eb4-134">Desteklenen en yüksek değer 71,582 dakikadır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-134">The maximum value supported is 71,582 minutes.</span></span> <span data-ttu-id="63eb4-135">Bu yeniden başlatma devre dışı bırakılabilir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-135">This restart can be disabled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="63eb4-136">Bu özellik, bkz: [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).</span><span class="sxs-lookup"><span data-stu-id="63eb4-136"> this property, see the [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).</span></span>  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a><span data-ttu-id="63eb4-137">Bir .svc dosyası için WCF hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="63eb4-137">Create an .svc File for the WCF Service</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="63eb4-138">IIS barındırılan hizmetleri özel içerik dosyalarını (.svc dosyalarını) IIS uygulama olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-138"> services hosted in IIS are represented as special content files (.svc files) inside the IIS application.</span></span> <span data-ttu-id="63eb4-139">Bu model, ASMX sayfaları içinde bir IIS uygulama .asmx dosyalarını olarak temsil edilir şekilde benzerdir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-139">This model is similar to the way ASMX pages are represented inside of an IIS application as .asmx files.</span></span> <span data-ttu-id="63eb4-140">.Svc dosyasını içeren bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-özel işleme yönergesi ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) izin veren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] barındırılan hizmetler gelen iletilere yanıt olarak etkinleştirmek için barındırma altyapı.</span><span class="sxs-lookup"><span data-stu-id="63eb4-140">A .svc file contains a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-specific processing directive ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) that allows the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hosting infrastructure to activate hosted services in response to incoming messages.</span></span> <span data-ttu-id="63eb4-141">En yaygın sözdizimi .svc dosyası için aşağıdaki deyimi şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-141">The most common syntax for a .svc file is in the following statement.</span></span>  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 <span data-ttu-id="63eb4-142">Oluşur [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) yönergesi ve tek bir öznitelik `Service`.</span><span class="sxs-lookup"><span data-stu-id="63eb4-142">It consists of the [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive and a single attribute, `Service`.</span></span> <span data-ttu-id="63eb4-143">Değeri `Service` özniteliktir hizmet uygulaması ortak dil çalışma zamanı (CLR) türünün adı.</span><span class="sxs-lookup"><span data-stu-id="63eb4-143">The value of the `Service` attribute is the common language runtime (CLR) type name of the service implementation.</span></span> <span data-ttu-id="63eb4-144">Bu yönerge kullanarak, aşağıdaki kodu kullanarak hizmet ana bilgisayarını oluşturmak için temel olarak eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-144">Using this directive is basically equivalent to creating a service host using the following code.</span></span>  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 <span data-ttu-id="63eb4-145">Hizmet için temel adres listesi oluşturma gibi ek barındırma yapılandırma de yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-145">Additional hosting configuration, such as creating a list of base addresses for the service can also be done.</span></span> <span data-ttu-id="63eb4-146">Özel bir de kullanabilirsiniz <xref:System.ServiceModel.Activation.ServiceHostFactory> yönergesi barındırma özel çözümler ile kullanılmak üzere genişletmek için.</span><span class="sxs-lookup"><span data-stu-id="63eb4-146">You can also use a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> to extend the directive for use with custom hosting solutions.</span></span> <span data-ttu-id="63eb4-147">Barındıran IIS uygulamalar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri oluşturulmasını ve yaşam süresini yönetmekten sorumlu olmayan <xref:System.ServiceModel.ServiceHost> örnekleri.</span><span class="sxs-lookup"><span data-stu-id="63eb4-147">The IIS applications that host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are not responsible for managing the creation and lifetime of <xref:System.ServiceModel.ServiceHost> instances.</span></span> <span data-ttu-id="63eb4-148">Yönetilen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oluşturur gerekli altyapı barındırma <xref:System.ServiceModel.ServiceHost> .svc dosya için yapılan ilk istek alındığında dinamik olarak örneği.</span><span class="sxs-lookup"><span data-stu-id="63eb4-148">The managed [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hosting infrastructure creates the necessary <xref:System.ServiceModel.ServiceHost> instance dynamically when the first request is received for the .svc file.</span></span> <span data-ttu-id="63eb4-149">Ya da açıkça kod veya uygulamanın ne zaman dönüştürülmeden kapatılana kadar örnek serbest bırakılmaz.</span><span class="sxs-lookup"><span data-stu-id="63eb4-149">The instance is not released until either it is closed explicitly by code or when the application is recycled.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="63eb4-150">.svc dosyalarını sözdizimi bkz [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).</span><span class="sxs-lookup"><span data-stu-id="63eb4-150"> the syntax for .svc files, see [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).</span></span>  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a><span data-ttu-id="63eb4-151">Hizmet uygulaması için IIS uygulama dağıtma</span><span class="sxs-lookup"><span data-stu-id="63eb4-151">Deploy the Service Implementation to the IIS Application</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="63eb4-152">IIS barındırılan hizmetleri aynı dinamik derleme model olarak kullanmak [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63eb4-152"> services hosted in IIS use the same dynamic compilation model as [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)].</span></span> <span data-ttu-id="63eb4-153">İle olarak yalnızca [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], uygulama kodunu dağıtabilirsiniz IIS tarafından barındırılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] çeşitli konumlara çeşitli şekillerde gibi hizmetleri:</span><span class="sxs-lookup"><span data-stu-id="63eb4-153">Just as with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], you can deploy the implementation code for IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in several ways at various locations, as follows:</span></span>  
  
-   <span data-ttu-id="63eb4-154">Genel Derleme Önbelleği (GAC) veya uygulamanın \bin dizinine önceden derlenmiş .dll dosyasını yer gibi.</span><span class="sxs-lookup"><span data-stu-id="63eb4-154">As a precompiled .dll file located in the global assembly cache (GAC) or in the application’s \bin directory.</span></span> <span data-ttu-id="63eb4-155">Sınıf kitaplığı yeni bir sürümü dağıtılana kadar önceden derlenmiş ikili dosyaları güncelleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="63eb4-155">Precompiled binaries are not updated until a new version of the class library is deployed.</span></span>  
  
-   <span data-ttu-id="63eb4-156">Uygulamanın \App_Code dizininde derlenmemiş kaynak dosyaları gibi.</span><span class="sxs-lookup"><span data-stu-id="63eb4-156">As un-compiled source files located in the application’s \App_Code directory.</span></span> <span data-ttu-id="63eb4-157">Bu dizinde bulunan kaynak dosyaları uygulamanın ilk isteği işleme sırasında dinamik olarak gereklidir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-157">Source files located in this directory are dynamically required when processing the application’s first request.</span></span> <span data-ttu-id="63eb4-158">Herhangi bir değişiklik \App_Code dizindeki dosyaların silinmesini ve bir sonraki istekte alındığında yeniden derlenmesi tüm uygulama neden.</span><span class="sxs-lookup"><span data-stu-id="63eb4-158">Any changes to files in the \App_Code directory cause the entire application to be recycled and recompiled when the next request is received.</span></span>  
  
-   <span data-ttu-id="63eb4-159">Doğrudan .svc dosyasında derlenmemiş kod yerleştirilmiş olarak.</span><span class="sxs-lookup"><span data-stu-id="63eb4-159">As un-compiled code placed directly in the .svc file.</span></span> <span data-ttu-id="63eb4-160">Uygulama kodu da olabilir hizmetin .svc dosyasında bulunan satır içi sonra @ServiceHost yönergesi.</span><span class="sxs-lookup"><span data-stu-id="63eb4-160">Implementation code can also be located inline in the service’s .svc file, after the @ServiceHost directive.</span></span> <span data-ttu-id="63eb4-161">Satır içi kod yapılan değişikliklerin geri dönüşüm ve bir sonraki istekte alındığında yeniden derlenmesi uygulamanın neden.</span><span class="sxs-lookup"><span data-stu-id="63eb4-161">Any changes to inline code cause the application to be recycled and recompiled when the next request is received.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="63eb4-162">[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] derleme modeli bkz [ASP.NET derleme genel bakış](http://go.microsoft.com/fwlink/?LinkId=94773).</span><span class="sxs-lookup"><span data-stu-id="63eb4-162"> the [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] compilation model, see [ASP.NET Compilation Overview](http://go.microsoft.com/fwlink/?LinkId=94773).</span></span>  
  
## <a name="configure-the-wcf-service"></a><span data-ttu-id="63eb4-163">WCF hizmetini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="63eb4-163">Configure the WCF Service</span></span>  
 <span data-ttu-id="63eb4-164">IIS barındırılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri uygulamaları Web.config dosyasında yapılandırmalarını depolar.</span><span class="sxs-lookup"><span data-stu-id="63eb4-164">IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services store their configuration in the applications Web.config file.</span></span> <span data-ttu-id="63eb4-165">IIS barındırılan hizmetleri kullanmak aynı yapılandırma öğeleri ve söz dizimine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] IIS dışında barındırılan hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="63eb4-165">IIS-hosted services use the same configuration elements and syntax as [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services hosted outside of IIS.</span></span> <span data-ttu-id="63eb4-166">Ancak, aşağıdaki kısıtlamalar IIS barındırma ortamı benzersiz şunlardır:</span><span class="sxs-lookup"><span data-stu-id="63eb4-166">However, the following constraints are unique to the IIS hosting environment:</span></span>  
  
-   <span data-ttu-id="63eb4-167">IIS barındırılan hizmetler için temel adres.</span><span class="sxs-lookup"><span data-stu-id="63eb4-167">Base addresses for IIS-hosted services.</span></span>  
  
-   <span data-ttu-id="63eb4-168">Barındırma uygulamaları [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] IIS dışında hizmetlerini barındıran bir dizi temel adres için URI geçirerek services temel adresini denetleyebilir <xref:System.ServiceModel.ServiceHost> Oluşturucusu veya sağlayarak bir [ \<ana bilgisayar >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) hizmetin yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="63eb4-168">Applications hosting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services outside of IIS can control the base address of the services they host by passing a set of base address URIs to the <xref:System.ServiceModel.ServiceHost> constructor or by providing a [\<host>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) element in the service’s configuration.</span></span> <span data-ttu-id="63eb4-169">IIS barındırılan hizmetleri, kendi taban adresi denetleme olanağı yoktur; IIS barındırılan hizmetin taban adresi .svc dosya adresidir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-169">Services hosted in IIS do not have the ability to control their base address; the base address of an IIS-hosted service is the address of its .svc file.</span></span>  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a><span data-ttu-id="63eb4-170">IIS barındırılan hizmetleri için uç nokta adresleri</span><span class="sxs-lookup"><span data-stu-id="63eb4-170">Endpoint Addresses for IIS-Hosted Services</span></span>  
 <span data-ttu-id="63eb4-171">IIS içinde barındırıldığında, uç nokta adresleri her zaman hizmeti temsil .svc dosya adres göreli olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-171">When hosted in IIS, endpoint addresses are always considered to be relative to the address of the .svc file that represents the service.</span></span> <span data-ttu-id="63eb4-172">Örneğin, varsa taban adresini bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] http://localhost/Application1/MyService.svc şu uç nokta yapılandırması ile bir hizmettir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-172">For example, if the base address of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is http://localhost/Application1/MyService.svc with the following endpoint configuration.</span></span>  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 <span data-ttu-id="63eb4-173">Bu, "http://localhost/Application1/MyService.svc/anotherEndpoint" ulaşılabilen bir uç nokta sağlar.</span><span class="sxs-lookup"><span data-stu-id="63eb4-173">This provides an endpoint that can be reached at "http://localhost/Application1/MyService.svc/anotherEndpoint".</span></span>  
  
 <span data-ttu-id="63eb4-174">Benzer şekilde, boş bir dize göreli adresini kullanan uç nokta yapılandırma öğesi bir uç nokta http://localhost/Application1/MyService.svc erişilebilir olan taban adresi sağlar.</span><span class="sxs-lookup"><span data-stu-id="63eb4-174">Similarly, the endpoint configuration element that uses an empty string as the relative address provides an endpoint reachable at http://localhost/Application1/MyService.svc, which is the base address.</span></span>  
  
```xml  
<endpoint address="" ... />  
```  
  
 <span data-ttu-id="63eb4-175">Ayrıca, IIS tarafından barındırılan hizmet uç noktaları için her zaman göreli uç nokta adresleri kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-175">You must always use relative endpoint addresses for IIS-hosted service endpoints.</span></span> <span data-ttu-id="63eb4-176">Uç nokta adresi IIS bitiş noktası gösterme hizmeti barındıran uygulamasını işaret etmiyorsa tam uç noktası adresi (örneğin, http://localhost/MyService.svc) biri hizmet dağıtımı hatalara yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-176">Supplying a fully-qualified endpoint address (for example, http://localhost/MyService.svc) can lead to errors in the deployment of the service if the endpoint address does not point to the IIS-application that hosts the service exposing the endpoint.</span></span> <span data-ttu-id="63eb4-177">Barındırılan hizmetleri göreli uç nokta adresleri kullanarak, bu olası çakışmaları ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-177">Using relative endpoint addresses for hosted services avoids these potential conflicts.</span></span>  
  
### <a name="available-transports"></a><span data-ttu-id="63eb4-178">Kullanılabilir taşımalar</span><span class="sxs-lookup"><span data-stu-id="63eb4-178">Available Transports</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="63eb4-179">IIS 5.1, barındırılan hizmetleri ve [!INCLUDE[iis601](../../../../includes/iis601-md.md)] HTTP tabanlı iletişim kullanmak için kısıtlanır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-179"> services hosted in IIS 5.1 and [!INCLUDE[iis601](../../../../includes/iis601-md.md)] are restricted to using HTTP-based communication.</span></span> <span data-ttu-id="63eb4-180">Bu IIS platformlarda HTTP olmayan bağlama kullanmak için bir barındırılan hizmet yapılandırma hatayla hizmeti etkinleştirme sırasında sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-180">On these IIS platforms, configuring a hosted service to use a non-HTTP binding results in an error during service activation.</span></span> <span data-ttu-id="63eb4-181">İçin [!INCLUDE[iisver](../../../../includes/iisver-md.md)], desteklenen aktarmalar HTTP Net.TCP, Net.Pipe, Net.MSMQ ve msmq.formatname için geriye doğru uyumluluk mevcut MSMQ uygulamalarla yer alır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-181">For [!INCLUDE[iisver](../../../../includes/iisver-md.md)], the supported transports include HTTP, Net.TCP, Net.Pipe, Net.MSMQ, and msmq.formatname for backwards compatibility with existing MSMQ applications.</span></span>  
  
### <a name="http-transport-security"></a><span data-ttu-id="63eb4-182">HTTP Taşıma Güvenliği</span><span class="sxs-lookup"><span data-stu-id="63eb4-182">HTTP Transport Security</span></span>  
 <span data-ttu-id="63eb4-183">IIS barındırılan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri HTTP kullanan yapabilir hizmeti içeren IIS sanal dizininde desteklediği sürece aktarım güvenliği (örneğin, HTTPS ve HTTP kimlik doğrulama şemasını temel, Özet ve Windows tümleşik kimlik doğrulaması gibi) Bu ayarlar.</span><span class="sxs-lookup"><span data-stu-id="63eb4-183">IIS-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can make use of HTTP transport security (for example, HTTPS and HTTP authentication schemes such as Basic, Digest, and Windows Integrated Authentication) as long as the IIS virtual directory that contains the service supports those settings.</span></span> <span data-ttu-id="63eb4-184">HTTP taşıma güvenliği ayarları üzerinde barındırılan bir uç noktanın bağlama taşıma güvenlik ayarları içerdiği IIS sanal dizininde eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="63eb4-184">The HTTP Transport Security settings on a hosted endpoint’s binding must match the transport security settings on the IIS virtual directory that contains it.</span></span>  
  
 <span data-ttu-id="63eb4-185">Örneğin, bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP digest kimlik doğrulaması kullanmak üzere yapılandırılmış uç noktası, HTTP digest kimlik doğrulaması izin vermek için yapılandırılmış bir IIS sanal dizininde bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-185">For example, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint configured to use HTTP digest authentication must reside in an IIS virtual directory that is also configured to allow HTTP digest authentication.</span></span> <span data-ttu-id="63eb4-186">IIS ayarları eşleşmeyen birleşimlerini ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uç noktası ayarları hizmeti etkinleştirme sırasında bir hata sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="63eb4-186">Unmatched combinations of IIS settings and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint settings result in an error during service activation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63eb4-187">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="63eb4-187">See Also</span></span>  
 [<span data-ttu-id="63eb4-188">Internet Information Services'te barındırma</span><span class="sxs-lookup"><span data-stu-id="63eb4-188">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="63eb4-189">Internet Information Services barındırma en iyi uygulamaları</span><span class="sxs-lookup"><span data-stu-id="63eb4-189">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="63eb4-190">Windows Server App Fabric barındırma özellikleri</span><span class="sxs-lookup"><span data-stu-id="63eb4-190">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)