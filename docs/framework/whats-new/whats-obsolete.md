---
title: "&#39; teki .NET Framework Sınıf Kitaplığı'te eski"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4560988445b91939deef84211a1c8c13ed938560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="what39s-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="6579e-102">&#39; teki .NET Framework Sınıf Kitaplığı'te eski</span><span class="sxs-lookup"><span data-stu-id="6579e-102">What&#39;s Obsolete in the .NET Framework Class Library</span></span>
<span data-ttu-id="6579e-103">.NET Framework zaman içinde değişir.</span><span class="sxs-lookup"><span data-stu-id="6579e-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="6579e-104">Her yeni sürümü yeni türleri ve yeni işlevsellik sağlar tür üyeleri ekler.</span><span class="sxs-lookup"><span data-stu-id="6579e-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="6579e-105">Ayrıca varolan türleri ve üyeleri zamanla değiştirin.</span><span class="sxs-lookup"><span data-stu-id="6579e-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="6579e-106">Örneğin, bazı türleri destekledikleri teknolojisi tarafından yeni bir teknoloji değiştirilir daha az önemli hale gelmiştir ve bazı yöntemler daha kullanışlı ya da daha tam özellikli yeni yöntemler tarafından değiştirilen.</span><span class="sxs-lookup"><span data-stu-id="6579e-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>  
  
 <span data-ttu-id="6579e-107">Geriye dönük uyumluluk (.NET Framework'ün sonraki sürümünde çalıştırmak için .NET Framework'ün bir sürüm geliştirilen uygulamaların izin verecek şekilde) desteklemek .NET Framework ve ortak dil çalışma zamanı çalışmalar yapılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6579e-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="6579e-108">Bu, yalnızca bir tür veya bir tür üyesi kaldırmak zorlaştırır.</span><span class="sxs-lookup"><span data-stu-id="6579e-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="6579e-109">Bunun yerine, .NET Framework bir tür veya bir tür üyesi artık kullanılmayan veya kullanım dışı olarak işaretleyerek kullanılması gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6579e-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="6579e-110">Bir tür veya üye onaysız kılınmadan, böylece geliştiriciler, azalttıktan ve onun kaldırma yanıt zamanınız kullanan işaretleme içerir.</span><span class="sxs-lookup"><span data-stu-id="6579e-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="6579e-111">Ancak, tür veya üye kullanan var olan kod, .NET Framework'ün yeni sürümde çalışmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="6579e-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6579e-112">Koşulları *eski* ve *kullanım dışı* türleri ve .NET Framework üyelerini uygulandığında aynı anlamı yoktur.</span><span class="sxs-lookup"><span data-stu-id="6579e-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>  
  
## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="6579e-113">ObsoleteAttribute özniteliği</span><span class="sxs-lookup"><span data-stu-id="6579e-113">The ObsoleteAttribute Attribute</span></span>  
 <span data-ttu-id="6579e-114">.NET Framework türü veya tür üyesi ile işaretleyerek eski gösterir <xref:System.ObsoleteAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="6579e-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="6579e-115">Öznitelik bir tür veya üye uygulamadan kesme kullanmadan .NET Framework bazı gelecek sürümünde tür veya üye kaldırılacak bu üyeyi kullanan kodu derlenmiş gösterir.</span><span class="sxs-lookup"><span data-stu-id="6579e-115">Applying the attribute to a type or member indicates that that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>  
  
 <span data-ttu-id="6579e-116">Bir tür veya bir tür üyesi eski olarak olduğunu belirten ek olarak <xref:System.ObsoleteAttribute> derleyici bu tür veya üye içeren kaynak kodu işleme biçimini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="6579e-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="6579e-117">Derleyici Kodu derlemek ancak bir uyarı iletisi yayma ya da hata olarak tür veya üye kullanımını davranabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6579e-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="6579e-118">İlk durumda, kodu başarılı bir şekilde derleyebilir, ancak tür veya üye kullanımdan kalkmıştır bir uyarı iletisi gösterir.</span><span class="sxs-lookup"><span data-stu-id="6579e-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="6579e-119">İkinci durumda, derleme başarısız oluyor.</span><span class="sxs-lookup"><span data-stu-id="6579e-119">In the second case, compilation fails.</span></span>  
  
 <span data-ttu-id="6579e-120">Derleme bir uyarı iletisi yerine bir hata oluşturursa bile <xref:System.ObsoleteAttribute> çalışma zamanı davranışını etkilemez.</span><span class="sxs-lookup"><span data-stu-id="6579e-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="6579e-121">Diğer bir deyişle, tür veya üye kullanan ve başarıyla derlediğiniz uygulamalar her zaman başarıyla çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="6579e-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="6579e-122">Yalnızca tür veya üye kullanan bir uygulama derleyin denemesi başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="6579e-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>  
  
## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="6579e-123">Eski türler ve üyeleri nasıl ele alınacağını</span><span class="sxs-lookup"><span data-stu-id="6579e-123">How to Handle Obsolete Types and Members</span></span>  
 <span data-ttu-id="6579e-124">Yükseltme ve var olan kodu yeniden derleyin, eski türü veya uygulamanızda derleyici uyarısı üreten üye edilebilir kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="6579e-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="6579e-125">Ancak, uygulama kodunuzun değiştirmelisiniz olup olmadığını belirlemek için derleyici uyarı iletisi gözden geçirmelidir.</span><span class="sxs-lookup"><span data-stu-id="6579e-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="6579e-126">İleti için uygun bir alternatif işaret etmiyorsa, aşağıdakilerden birini yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="6579e-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>  
  
-   <span data-ttu-id="6579e-127">Kodunuzu, tür veya üye, kullanımını mümkünse kaldırarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="6579e-127">Change your code by removing the use of the type or member, if possible.</span></span>  
  
     <span data-ttu-id="6579e-128">veya</span><span class="sxs-lookup"><span data-stu-id="6579e-128">-or-</span></span>  
  
-   <span data-ttu-id="6579e-129">İçin kullanımdan yanıt vereceğinizi belirlemek bu teknoloji alanı belgelerini gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="6579e-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>  
  
 <span data-ttu-id="6579e-130">.NET Framework'ün sonraki bir sürümünü karşı var olan kodu derleyin değil seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6579e-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="6579e-131">Bunun yerine, göre var olan kodu çalıştırır derlenmiş .NET Framework sürümünü belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6579e-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="6579e-132">Örneğin, karşı derlenen app1.exe adlı bir uygulamanız olduğunu varsayın [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], ancak uygulamayı karşı çalıştırmak istediğiniz [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6579e-132">For example, suppose that you have an application named app1.exe that was compiled against the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], but you want the application to run against the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="6579e-133">Bu, aşağıdaki adımları gerektirir:</span><span class="sxs-lookup"><span data-stu-id="6579e-133">This requires the following steps:</span></span>  
  
1.  <span data-ttu-id="6579e-134">Ana yürütülebilir dosyanın için bir yapılandırma dosyası oluşturun ve adlandırın *appName*. exe.config, burada *appName* uygulama yürütülebilir dosyasının adıdır.</span><span class="sxs-lookup"><span data-stu-id="6579e-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="6579e-135">Örneğimizde App1.exe adı geçen uygulama için app1.exe.config adlı bir yapılandırma dosyası oluşturursunuz.</span><span class="sxs-lookup"><span data-stu-id="6579e-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>  
  
2.  <span data-ttu-id="6579e-136">Aşağıdaki yapılandırma dosyasına ekleyin.</span><span class="sxs-lookup"><span data-stu-id="6579e-136">Add the following to the configuration file.</span></span>  
  
    ```xml  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 <span data-ttu-id="6579e-137">Aşağıdaki tabloda, atayabilirsiniz dize değerlerini listeler `version` belirli bir .NET Framework sürümünü hedefleyecek şekilde özniteliği.</span><span class="sxs-lookup"><span data-stu-id="6579e-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework.</span></span>  
  
|<span data-ttu-id="6579e-138">.NET Framework sürümü</span><span class="sxs-lookup"><span data-stu-id="6579e-138">.NET Framework version</span></span>|<span data-ttu-id="6579e-139">`version`dize</span><span class="sxs-lookup"><span data-stu-id="6579e-139">`version` string</span></span>|
|-|-|  
|<span data-ttu-id="6579e-140">4.7 (4.7.1 dahil)</span><span class="sxs-lookup"><span data-stu-id="6579e-140">4.7 (including 4.7.1)</span></span>|<span data-ttu-id="6579e-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="6579e-141">v4.0</span></span>|  
|<span data-ttu-id="6579e-142">4.6 (4.6.1 ve 4.6.2 dahil)</span><span class="sxs-lookup"><span data-stu-id="6579e-142">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="6579e-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="6579e-143">v4.0</span></span>|  
|<span data-ttu-id="6579e-144">4.5 (4.5.1 ve 4.5.2 dahil)</span><span class="sxs-lookup"><span data-stu-id="6579e-144">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="6579e-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="6579e-145">v4.0</span></span>|  
|<span data-ttu-id="6579e-146">4</span><span class="sxs-lookup"><span data-stu-id="6579e-146">4</span></span>|<span data-ttu-id="6579e-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="6579e-147">v4.0</span></span>|  
|<span data-ttu-id="6579e-148">3.5</span><span class="sxs-lookup"><span data-stu-id="6579e-148">3.5</span></span>|<span data-ttu-id="6579e-149">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="6579e-149">v2.0.50727</span></span>|  
|<span data-ttu-id="6579e-150">2,0</span><span class="sxs-lookup"><span data-stu-id="6579e-150">2.0</span></span>|<span data-ttu-id="6579e-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="6579e-151">v2.0.50727</span></span>|  
|<span data-ttu-id="6579e-152">1.1</span><span class="sxs-lookup"><span data-stu-id="6579e-152">1.1</span></span>|<span data-ttu-id="6579e-153">V1.1.4322</span><span class="sxs-lookup"><span data-stu-id="6579e-153">v1.1.4322</span></span>|  
|<span data-ttu-id="6579e-154">1.0</span><span class="sxs-lookup"><span data-stu-id="6579e-154">1.0</span></span>|<span data-ttu-id="6579e-155">V1.0.3705</span><span class="sxs-lookup"><span data-stu-id="6579e-155">v1.0.3705</span></span>|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-46"></a><span data-ttu-id="6579e-156">.NET Framework 4.5 ve 4.6 için artık kullanılmayan listeleri</span><span class="sxs-lookup"><span data-stu-id="6579e-156">Obsolete Lists for the .NET Framework 4.5 and 4.6</span></span>  
 [<span data-ttu-id="6579e-157">Eski türler</span><span class="sxs-lookup"><span data-stu-id="6579e-157">Obsolete Types</span></span>](../../../docs/framework/whats-new/obsolete-types.md)  
  
 [<span data-ttu-id="6579e-158">Eski üyeler</span><span class="sxs-lookup"><span data-stu-id="6579e-158">Obsolete Members</span></span>](../../../docs/framework/whats-new/obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="6579e-159">Önceki sürümler için artık kullanılmayan listeleri</span><span class="sxs-lookup"><span data-stu-id="6579e-159">Obsolete Lists for Previous Versions</span></span>  
 [<span data-ttu-id="6579e-160">.NET Framework 4'te eski türler</span><span class="sxs-lookup"><span data-stu-id="6579e-160">Obsolete Types in the .NET Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [<span data-ttu-id="6579e-161">.NET Framework 4'te eski üyeler</span><span class="sxs-lookup"><span data-stu-id="6579e-161">Obsolete Members in the .NET Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [<span data-ttu-id="6579e-162">.NET framework 3.5 artık kullanılmayan liste</span><span class="sxs-lookup"><span data-stu-id="6579e-162">.NET Framework 3.5 Obsolete List</span></span>](http://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [<span data-ttu-id="6579e-163">.NET framework 2.0 artık kullanılmayan liste</span><span class="sxs-lookup"><span data-stu-id="6579e-163">.NET Framework 2.0 Obsolete List</span></span>](http://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a><span data-ttu-id="6579e-164">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6579e-164">See Also</span></span>  
 [<span data-ttu-id="6579e-165">\<supportedRuntime > öğesi</span><span class="sxs-lookup"><span data-stu-id="6579e-165">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)