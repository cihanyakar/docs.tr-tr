---
title: ".NET Native'i Kullanmaya Başlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
caps.latest.revision: "29"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eeda0c58e9b5e9f8b48e335849ce12f7e8d94a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-net-native"></a><span data-ttu-id="0cde6-102">.NET Native'i Kullanmaya Başlama</span><span class="sxs-lookup"><span data-stu-id="0cde6-102">Getting Started with .NET Native</span></span>
<span data-ttu-id="0cde6-103">Windows 10 için yeni bir Windows uygulaması yazma veya varolan bir Windows mağazası uygulaması geçirdiğiniz yordamları aynı kümesini izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cde6-103">Whether you are writing a new Windows app for Windows 10 or you are migrating an existing Windows Store app, you can follow the same set of procedures.</span></span> <span data-ttu-id="0cde6-104">Oluşturmak için bir [!INCLUDE[net_native](../../../includes/net-native-md.md)] uygulama, şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="0cde6-104">To create a [!INCLUDE[net_native](../../../includes/net-native-md.md)] app, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0cde6-105">[Windows 10 hedefleyen bir evrensel Windows Platformu (UWP) uygulaması geliştirme](#Step1)ve hata ayıklama derlemeleri düzgün çalıştığından emin olmak için uygulamanızı test.</span><span class="sxs-lookup"><span data-stu-id="0cde6-105">[Develop a Universal Windows Platform (UWP) app that targets Windows 10](#Step1), and test the debug builds of your app to ensure that it works properly.</span></span>  
  
2.  <span data-ttu-id="0cde6-106">[Ek yansıma ve Serileştirme kullanım işlemek](#Step2).</span><span class="sxs-lookup"><span data-stu-id="0cde6-106">[Handle additional reflection and serialization usage](#Step2).</span></span>  
  
3.  <span data-ttu-id="0cde6-107">[Dağıtma ve yayın derlemeleri, uygulamanızın sınama](#Step3).</span><span class="sxs-lookup"><span data-stu-id="0cde6-107">[Deploy and test the release builds of your app](#Step3).</span></span>  
  
4.  <span data-ttu-id="0cde6-108">[El ile eksik meta veri çözümleme](#Step4)ve yineleyin [3. adım](#Step3) tüm sorunlar çözülene kadar.</span><span class="sxs-lookup"><span data-stu-id="0cde6-108">[Manually resolve missing metadata](#Step4), and repeat [step 3](#Step3) until all issues are resolved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde6-109">Varolan bir Windows mağazası uygulaması taşıyorsanız [!INCLUDE[net_native](../../../includes/net-native-md.md)], gözden geçirmeyi unutmayın [geçirme Windows mağazası uygulamanızı .NET yerele](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-109">If you are migrating an existing Windows Store app to [!INCLUDE[net_native](../../../includes/net-native-md.md)], be sure to review [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span></span>  
  
<a name="Step1"></a>   
## <a name="step-1-develop-and-test-debug-builds-of-your-uwp-app"></a><span data-ttu-id="0cde6-110">1. adım: Geliştirmek ve UWP uygulamanızı test hata ayıklama derlemeleri</span><span class="sxs-lookup"><span data-stu-id="0cde6-110">Step 1: Develop and test debug builds of your UWP app</span></span>  
 <span data-ttu-id="0cde6-111">Mevcut bir geçiş veya yeni bir uygulama geliştiren olsun, herhangi bir Windows uygulama için olduğu gibi aynı süreci izleyin.</span><span class="sxs-lookup"><span data-stu-id="0cde6-111">Whether you are developing a new app or migrating an existing one, you follow the same process as for any Windows app.</span></span>  
  
1.  <span data-ttu-id="0cde6-112">Visual C# veya Visual Basic için evrensel Windows uygulaması şablonu kullanarak Visual Studio'da yeni bir UWP projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="0cde6-112">Create a new UWP project in Visual Studio by using the Universal Windows app template for Visual C# or Visual Basic.</span></span> <span data-ttu-id="0cde6-113">Varsayılan olarak, tüm UWP uygulamaları CoreCLR hedef ve .NET yerel araç zinciri kullanarak sürüm yapılarına derlenir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-113">By default, all UWP applications target the CoreCLR and their release builds are compiled by using the .NET Native tool chain.</span></span>  
  
2.  <span data-ttu-id="0cde6-114">Olduğunu bazı bilinen uyumluluk sorunlarına olmadan .NET yerel araç zinciri ile UWP uygulaması projeleri derleme arasında unutmayın.</span><span class="sxs-lookup"><span data-stu-id="0cde6-114">Note that there are some known compatibility issues between compiling UWP app projects with the .NET Native tool chain and without it.</span></span> <span data-ttu-id="0cde6-115">Başvurmak [Geçiş Kılavuzu](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="0cde6-115">Refer to the [migration guide](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) for more information.</span></span>  
  
 <span data-ttu-id="0cde6-116">C# veya Visual Basic kod karşı şimdi yazabilirsiniz [!INCLUDE[net_native](../../../includes/net-native-md.md)] yüzey yerel sistemde (veya benzetici) çalışır alanı.</span><span class="sxs-lookup"><span data-stu-id="0cde6-116">You can now write C# or Visual Basic code against the [!INCLUDE[net_native](../../../includes/net-native-md.md)] surface area that runs on the local system (or in the simulator).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0cde6-117">Uygulamanızı geliştirirken, seri hale getirme veya yansıma kodunuzda herhangi bir kullanımından unutmayın.</span><span class="sxs-lookup"><span data-stu-id="0cde6-117">As you develop your app, note any use of serialization or reflection in your code.</span></span>  
  
 <span data-ttu-id="0cde6-118">JIT-derlenmiş kullanarak sürüm derlemeleri derlenmiş sırada hızlı F5 dağıtımını etkinleştirmek için varsayılan olarak, hata ayıklama yapıları [!INCLUDE[net_native](../../../includes/net-native-md.md)] ön derleme teknolojisi.</span><span class="sxs-lookup"><span data-stu-id="0cde6-118">By default, debug builds are JIT-compiled to enable rapid F5 deployment, while release builds are compiled by using the [!INCLUDE[net_native](../../../includes/net-native-md.md)] pre-compilation technology.</span></span> <span data-ttu-id="0cde6-119">Derleme ve hata ayıklama test anlamına gelir, bunlar normalde olan .NET yerel araç zinciri derleme önce çalışmasını sağlamak için uygulamanızın oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0cde6-119">This means you should build and test the debug builds of your app to ensure that they work normally before compiling them with the .NET Native tool chain.</span></span>  
  
<a name="Step2"></a>   
## <a name="step-2-handle-additional-reflection-and-serialization-usage"></a><span data-ttu-id="0cde6-120">2. adım: ek yansıma ve seri hale getirme kullanım işleme</span><span class="sxs-lookup"><span data-stu-id="0cde6-120">Step 2: Handle additional reflection and serialization usage</span></span>  
 <span data-ttu-id="0cde6-121">Oluşturduğunuzda Default.rd.xml, bir çalışma zamanı yönergeleri dosyayı projenize otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-121">A runtime directives file, Default.rd.xml, is automatically added to your project when you create it.</span></span> <span data-ttu-id="0cde6-122">C# geliştirme, projenizin içinde bulunur **özellikleri** klasör.</span><span class="sxs-lookup"><span data-stu-id="0cde6-122">If you develop in C#, it is found in your project's **Properties** folder.</span></span> <span data-ttu-id="0cde6-123">Visual Basic'te ortaya çıkarsa, projenizin içinde bulunur **My proje** klasör.</span><span class="sxs-lookup"><span data-stu-id="0cde6-123">If you develop in Visual Basic, it is found in your project's **My Project** folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde6-124">Arka plan üzerinde neden sağlar .NET yerel derleme işlemine genel bakış için bir çalışma zamanı yönergeleri dosyası, bkz: gerekli [.NET yerel ve derleme](../../../docs/framework/net-native/net-native-and-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-124">For an overview of the .NET Native compilation process that provides background on why a runtime directives file is needed, see [.NET Native and Compilation](../../../docs/framework/net-native/net-native-and-compilation.md).</span></span>  
  
 <span data-ttu-id="0cde6-125">Çalışma zamanı yönergeleri dosya çalışma zamanında uygulamanızın gerektiğini meta verileri tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0cde6-125">The runtime directives file is used to define the metadata that your app needs at run time.</span></span> <span data-ttu-id="0cde6-126">Bazı durumlarda, dosyanın varsayılan sürümü yeterli olabilir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-126">In some cases, the default version of the file may be adequate.</span></span> <span data-ttu-id="0cde6-127">Ancak, serileştirme veya yansıma dayanır biraz kod ek giriş çalışma zamanı yönergeleri dosyası gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-127">However, some code that relies on serialization or reflection may require additional entries in the runtime directives file.</span></span>  
  
 <span data-ttu-id="0cde6-128">**Seri hale getirme**</span><span class="sxs-lookup"><span data-stu-id="0cde6-128">**Serialization**</span></span>  
 <span data-ttu-id="0cde6-129">Serileştiricileri iki kategorisi vardır ve her ikisi de ek giriş çalışma zamanı yönergeleri dosyası gerektirebilir:</span><span class="sxs-lookup"><span data-stu-id="0cde6-129">There are two categories of serializers, and both may require additional entries in the runtime directives file:</span></span>  
  
-   <span data-ttu-id="0cde6-130">Olmayan yansıma serileştiricileri temel.</span><span class="sxs-lookup"><span data-stu-id="0cde6-130">Non-reflection based serializers.</span></span> <span data-ttu-id="0cde6-131">Serileştiricileri bulunan .NET Framework Sınıf Kitaplığı'nda gibi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, ve <xref:System.Xml.Serialization.XmlSerializer> sınıfları, yansıma bağlı değil.</span><span class="sxs-lookup"><span data-stu-id="0cde6-131">The serializers found in the .NET Framework class library, such as the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes, do not rely on reflection.</span></span> <span data-ttu-id="0cde6-132">Ancak, gerekli serileştirilecek veya seri için nesne üzerinde temel kod oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-132">However, they do require that code be generated based on the object to be serialized or deserialized.</span></span>  <span data-ttu-id="0cde6-133">Daha fazla bilgi için "Microsoft Serializers" bölümüne bakın [serileştirme ve meta veri](../../../docs/framework/net-native/serialization-and-metadata.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-133">For more information, see the "Microsoft Serializers" section in [Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md).</span></span>  
  
-   <span data-ttu-id="0cde6-134">Üçüncü taraf serileştiricileri.</span><span class="sxs-lookup"><span data-stu-id="0cde6-134">Third-party serializers.</span></span> <span data-ttu-id="0cde6-135">Üçüncü taraf serileştirme kitaplıkları, en sık karşılaşılan biri olan Newtonsoft JSON seri hale getirici genellikle yansıma tabanlı ve girişleri *. nesne seri hale getirme ve seri durumdan çıkarma desteklemek için rd.xml dosya.</span><span class="sxs-lookup"><span data-stu-id="0cde6-135">Third-party serialization libraries, the most common of which is the Newtonsoft JSON serializer, are generally reflection-based and require entries in the *.rd.xml file to support object serialization and deserialization.</span></span> <span data-ttu-id="0cde6-136">Daha fazla bilgi için "Üçüncü taraf serileştiricileri" bölümüne bakın [serileştirme ve meta veri](../../../docs/framework/net-native/serialization-and-metadata.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-136">For more information, see the "Third-Party Serializers" section in [Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md).</span></span>  
  
 <span data-ttu-id="0cde6-137">**Yansıma kullanan yöntemleri**</span><span class="sxs-lookup"><span data-stu-id="0cde6-137">**Methods that rely on reflection**</span></span>  
 <span data-ttu-id="0cde6-138">Bazı durumlarda, kodda yansıma kullanımını açık değil.</span><span class="sxs-lookup"><span data-stu-id="0cde6-138">In some cases, the use of reflection in code is not obvious.</span></span> <span data-ttu-id="0cde6-139">Bazı ortak API'ler veya programlama desenleri API yansıma bir parçası olarak kabul değil ancak başarıyla yürütmek için yansıma kullanan.</span><span class="sxs-lookup"><span data-stu-id="0cde6-139">Some common APIs or programming patterns aren't considered part of the reflection API but rely on reflection to execute successfully.</span></span> <span data-ttu-id="0cde6-140">Bu aşağıdaki türü örnek oluşturma ve yöntemi oluşturma yöntemleri içerir:</span><span class="sxs-lookup"><span data-stu-id="0cde6-140">This includes the following type instantiation and method construction methods:</span></span>  
  
-   <span data-ttu-id="0cde6-141"><xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0cde6-141">The <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method</span></span>  
  
-   <span data-ttu-id="0cde6-142"><xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> Ve <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> yöntemleri</span><span class="sxs-lookup"><span data-stu-id="0cde6-142">The <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> and <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> methods</span></span>  
  
-   <span data-ttu-id="0cde6-143"><xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> Yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0cde6-143">The <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="0cde6-144">Daha fazla bilgi için bkz: [API'leri, Bel yansıma](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-144">For more information, see [APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde6-145">Çalışma zamanı yönergeleri dosyalarında kullanılan tür adları tam olarak nitelenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0cde6-145">Type names used in runtime directives files must be fully qualified.</span></span> <span data-ttu-id="0cde6-146">Örneğin, dosyayı "Dize" yerine "System.String" belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-146">For example, the file must specify "System.String" instead of "String".</span></span>  
  
<a name="Step3"></a>   
## <a name="step-3-deploy-and-test-the-release-builds-of-your-app"></a><span data-ttu-id="0cde6-147">3. adım: Dağıtın ve yayın derlemeleri, uygulamanızın test edin</span><span class="sxs-lookup"><span data-stu-id="0cde6-147">Step 3: Deploy and test the release builds of your app</span></span>  
 <span data-ttu-id="0cde6-148">Çalışma zamanı yönergeleri dosya güncelleştirdikten sonra yeniden oluşturun ve yayın derlemeleri, uygulamanızın dağıtın.</span><span class="sxs-lookup"><span data-stu-id="0cde6-148">After you’ve updated the runtime directives file, you can rebuild and deploy release builds of your app.</span></span> <span data-ttu-id="0cde6-149">.NET yerel ikili dosyaları içinde belirtilen dizin ILC.out alt yerleştirilir **yapı çıkış yolu** projenin metin kutusunun **özellikleri** iletişim kutusu, **derleme**sekmesi. Bu klasörde olmayan ikili dosyaları .NET yerel ile derlenmiş henüz.</span><span class="sxs-lookup"><span data-stu-id="0cde6-149">.NET Native binaries are placed in the ILC.out subdirectory of the directory specified in the **Build output path** text box of  the project's **Properties** dialog box, **Compile** tab. Binaries that aren't in this folder haven't been compiled with .NET Native.</span></span> <span data-ttu-id="0cde6-150">Uygulamanızı sınamanız ve her hedef platformlar hatası senaryoları dahil olmak üzere tüm senaryoları sınayın.</span><span class="sxs-lookup"><span data-stu-id="0cde6-150">Test your app thoroughly, and test all scenarios, including failure scenarios, on each of its target platforms.</span></span>  
  
 <span data-ttu-id="0cde6-151">Uygulamanızın düzgün çalışmıyorsa (özellikle burada oluşturur durumlarda [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) veya [Missingınteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) çalışma zamanında özel durumlar), sonraki'ndaki yönergeleri izleyin bölümünde, [4. adım: el ile eksik meta veri çözümleme](#Step4).</span><span class="sxs-lookup"><span data-stu-id="0cde6-151">If your app doesn’t work properly (particularly in cases where it throws [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) or [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) exceptions at run time), follow the instructions in the next section, [Step 4: Manually resolve missing metadata](#Step4).</span></span> <span data-ttu-id="0cde6-152">İlk fırsat özel durum etkinleştirme bu hatalar bulmanıza yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-152">Enabling first-chance exceptions may help you find these bugs.</span></span>  
  
 <span data-ttu-id="0cde6-153">Ne zaman artık test ve hata ayıklama hata ayıklaması uygulamanızı oluşturur ve bunu ortadan emin [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) ve [Missingınteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) test özel durumlar Uygulamanızı bir en iyi duruma getirilmiş olarak [!INCLUDE[net_native](../../../includes/net-native-md.md)] uygulama.</span><span class="sxs-lookup"><span data-stu-id="0cde6-153">When you’ve tested and debugged the debug builds of your app and you’re confident that you’ve eliminated the [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) and [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) exceptions, you should test your app as an optimized [!INCLUDE[net_native](../../../includes/net-native-md.md)] app.</span></span> <span data-ttu-id="0cde6-154">Bunu yapmak için etkin proje yapılandırmasından değiştirin **hata ayıklama** için **sürüm**.</span><span class="sxs-lookup"><span data-stu-id="0cde6-154">To do this, change your active project configuration from **Debug** to **Release**.</span></span>  
  
<a name="Step4"></a>   
## <a name="step-4-manually-resolve-missing-metadata"></a><span data-ttu-id="0cde6-155">4. adım: El ile eksik meta veri çözümleme</span><span class="sxs-lookup"><span data-stu-id="0cde6-155">Step 4: Manually resolve missing metadata</span></span>  
 <span data-ttu-id="0cde6-156">En yaygın hatası ile karşılaşırsanız [!INCLUDE[net_native](../../../includes/net-native-md.md)] masaüstünde karşılaştığınız olmayan bir çalışma zamanı olan [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [Missingınteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), veya [ MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) özel durum.</span><span class="sxs-lookup"><span data-stu-id="0cde6-156">The most common failure you'll encounter with [!INCLUDE[net_native](../../../includes/net-native-md.md)] that you don't encounter on the desktop is a runtime [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), or [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="0cde6-157">Bazı durumlarda, meta veri yokluğu kendisini beklenmeyen davranışlara veya bile uygulama hataları bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="0cde6-157">In some cases, the absence of metadata can manifest itself in unpredictable behavior or even in app failures.</span></span> <span data-ttu-id="0cde6-158">Bu bölümde, nasıl hata ayıklama ve çalışma zamanı yönergeleri dosyasına yönergeleri ekleyerek bu özel durumları çözmek anlatılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0cde6-158">This section discusses how you can debug and resolve these exceptions by adding directives to the runtime directives file.</span></span> <span data-ttu-id="0cde6-159">Çalışma zamanı yönergeleri biçimi hakkında daha fazla bilgi için bkz: [çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-159">For information about the format of runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="0cde6-160">Çalışma zamanı yönergeleri ekledikten sonra yapmanız gerekenler [dağıtın ve uygulamanızı test](#Step3) yeniden ve herhangi bir yeni çözmek [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [Missingınteropdataexception](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), ve [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) daha fazla hiçbir özel durum karşılaştığınız kadar özel durumları.</span><span class="sxs-lookup"><span data-stu-id="0cde6-160">After you’ve added runtime directives, you should [deploy and test your app](#Step3) again and resolve any new [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), and  [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions until you encounter no more exceptions.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="0cde6-161">Kod değişikliklerini hataya dayanıklı uygulamanızı etkinleştirmek için çalışma zamanı yönergeleri yüksek bir düzeyde belirtin.</span><span class="sxs-lookup"><span data-stu-id="0cde6-161">Specify the runtime directives at a high level to enable your app to be resilient to code changes.</span></span>  <span data-ttu-id="0cde6-162">Üye düzeyi yerine ad alanı ve tür düzeyleri çalışma zamanı yönergeleri ekleme öneririz.</span><span class="sxs-lookup"><span data-stu-id="0cde6-162">We recommend adding runtime directives at the namespace and type levels rather than the member level.</span></span> <span data-ttu-id="0cde6-163">Esneklik ve daha uzun derleme sürelerine sahip büyük ikili dosyalar arasında kolaylığını olabileceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="0cde6-163">Note that there may be a tradeoff between resiliency and larger binaries with longer compile times.</span></span>  
  
 <span data-ttu-id="0cde6-164">Eksik bir meta veri özel belirtirken şu noktaları dikkate alın:</span><span class="sxs-lookup"><span data-stu-id="0cde6-164">When addressing a missing metadata exception, consider these issues:</span></span>  
  
-   <span data-ttu-id="0cde6-165">Önce özel yapmak hangi uygulama çalışıyordu?</span><span class="sxs-lookup"><span data-stu-id="0cde6-165">What was the app trying to do before the exception?</span></span>  
  
    -   <span data-ttu-id="0cde6-166">Örneğin, bağlama, seri hale getirme verileri seri durumdan veya API yansıma kullanarak doğrudan veri neydi?</span><span class="sxs-lookup"><span data-stu-id="0cde6-166">For example, was it data binding, serializing or deserializing data, or directly using the reflection API?</span></span>  
  
-   <span data-ttu-id="0cde6-167">Bu yalıtılmış bir durumdur veya diğer türleri için aynı sorun karşılaşacağınız düşünüyorsanız?</span><span class="sxs-lookup"><span data-stu-id="0cde6-167">Is this an isolated case, or do you believe you'll encounter the same issue for other types?</span></span>  
  
    -   <span data-ttu-id="0cde6-168">Örneğin, bir [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) uygulamanın nesne modelinde bir türü seri hale getirme sırasında özel durum.</span><span class="sxs-lookup"><span data-stu-id="0cde6-168">For example, a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception is thrown when serializing a type in the app’s object model.</span></span>  <span data-ttu-id="0cde6-169">Seri hale diğer türleri biliyorsanız, aynı anda çalışma zamanı yönergeleri bu türleri (veya kodun ne kadar iyi organize bağlı olarak yöntem ad alanlarını,) ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cde6-169">If you know other types that will be serialized, you can add runtime directives for those types (or for their containing namespaces, depending on how well the code is organized) at the same time.</span></span>  
  
-   <span data-ttu-id="0cde6-170">Yansıma kullanmadığı için kod yazabilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="0cde6-170">Can you rewrite the code so it doesn’t use reflection?</span></span>  
  
    -   <span data-ttu-id="0cde6-171">Örneğin, kod kullanımı mu `dynamic` beklenir ne tür bildiğinizde anahtar sözcüğü?</span><span class="sxs-lookup"><span data-stu-id="0cde6-171">For example, does the code use the `dynamic` keyword when you know what type to expect?</span></span>  
  
    -   <span data-ttu-id="0cde6-172">Kodu daha iyi bir alternatif kullanılabilir olduğunda yansıma bağımlı olan bir yöntem çağrısı mu?</span><span class="sxs-lookup"><span data-stu-id="0cde6-172">Does the code call a method that depends on reflection when some better alternative is available?</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde6-173">Yansıma ve masaüstü uygulamalarında meta verilerinin kullanılabilirliği farklılıklar gelen gövdesi sorunlarını hakkında ek bilgi ve [!INCLUDE[net_native](../../../includes/net-native-md.md)], bkz: [API'leri, Bel yansıma](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="0cde6-173">For additional information about handling problems that stem from differences in reflection and the availability of metadata in desktop apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)], see [APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md).</span></span>  
  
 <span data-ttu-id="0cde6-174">Özel durumlar ve uygulamanızı test edilirken oluşan diğer sorunlar işleme bazı belirli örnekler için bkz:</span><span class="sxs-lookup"><span data-stu-id="0cde6-174">For some specific examples of handling exceptions and other issues that occur when testing your app, see:</span></span>  
  
-   [<span data-ttu-id="0cde6-175">Örnek: Veri bağlama sırasında özel durum işleme</span><span class="sxs-lookup"><span data-stu-id="0cde6-175">Example: Handling Exceptions When Binding Data</span></span>](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md)  
  
-   [<span data-ttu-id="0cde6-176">Örnek: Dinamik programlama sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="0cde6-176">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)  
  
-   [<span data-ttu-id="0cde6-177">.NET yerel uygulamalar çalışma zamanı özel durumları</span><span class="sxs-lookup"><span data-stu-id="0cde6-177">Runtime Exceptions in .NET Native Apps</span></span>](../../../docs/framework/net-native/runtime-exceptions-in-net-native-apps.md)  
  
## <a name="see-also"></a><span data-ttu-id="0cde6-178">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0cde6-178">See Also</span></span>  
 [<span data-ttu-id="0cde6-179">Çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu</span><span class="sxs-lookup"><span data-stu-id="0cde6-179">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="0cde6-180">NIB: .NET yerel kurulum ve yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0cde6-180">NIB: .NET Native Setup and Configuration</span></span>](http://msdn.microsoft.com/en-us/7c9bc375-8b87-4c33-bede-72d513e362ec)  
 [<span data-ttu-id="0cde6-181">.NET yerel ve derleme</span><span class="sxs-lookup"><span data-stu-id="0cde6-181">.NET Native and Compilation</span></span>](../../../docs/framework/net-native/net-native-and-compilation.md)  
 [<span data-ttu-id="0cde6-182">Yansıma ve .NET yerel</span><span class="sxs-lookup"><span data-stu-id="0cde6-182">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
 [<span data-ttu-id="0cde6-183">Yansıma kullanan API'ler</span><span class="sxs-lookup"><span data-stu-id="0cde6-183">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
 [<span data-ttu-id="0cde6-184">Serileştirme ve meta veriler</span><span class="sxs-lookup"><span data-stu-id="0cde6-184">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
 [<span data-ttu-id="0cde6-185">Windows mağazası uygulamanızı .NET Yerel'e taşıma</span><span class="sxs-lookup"><span data-stu-id="0cde6-185">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)