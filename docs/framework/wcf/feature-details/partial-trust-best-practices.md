---
title: "Kısmi Güven En İyi Uygulamaları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 74b1bd42472da61497124a04620aa02af25b32bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="partial-trust-best-practices"></a><span data-ttu-id="28d2e-102">Kısmi Güven En İyi Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="28d2e-102">Partial Trust Best Practices</span></span>
<span data-ttu-id="28d2e-103">Bu konu çalışırken en iyi uygulamaları açıklar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kısmi güven ortamında.</span><span class="sxs-lookup"><span data-stu-id="28d2e-103">This topic describes best practices when running [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a partial trust environment.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="28d2e-104">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="28d2e-104">Serialization</span></span>  
 <span data-ttu-id="28d2e-105">Kullanırken aşağıdaki yöntemleri uygulayın <xref:System.Runtime.Serialization.DataContractSerializer> kısmen güvenilen uygulamada.</span><span class="sxs-lookup"><span data-stu-id="28d2e-105">Apply the following practices when using the <xref:System.Runtime.Serialization.DataContractSerializer> in a partially-trusted application.</span></span>  
  
-   <span data-ttu-id="28d2e-106">Tüm seri hale getirilebilir türler ile açıkça işaretlenmelidir `[DataContract]` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="28d2e-106">All serializable types must be explicitly marked with the `[DataContract]` attribute.</span></span> <span data-ttu-id="28d2e-107">Aşağıdaki teknikler, kısmi güven ortamında desteklenmez:</span><span class="sxs-lookup"><span data-stu-id="28d2e-107">The following techniques are not supported in a partial trust environment:</span></span>  
  
-   <span data-ttu-id="28d2e-108">İle serileştirilecek sınıfları işaretleme <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="28d2e-108">Marking classes to be serialized with the <xref:System.SerializableAttribute>.</span></span>  
  
-   <span data-ttu-id="28d2e-109">Uygulama <xref:System.Runtime.Serialization.ISerializable> seri hale getirme işlemini kontrol eden bir sınıf izin vermek için arabirim.</span><span class="sxs-lookup"><span data-stu-id="28d2e-109">Implementing the <xref:System.Runtime.Serialization.ISerializable> interface to allow a class to control its serialization process.</span></span>  
  
### <a name="using-datacontractserializer"></a><span data-ttu-id="28d2e-110">DataContractSerializer kullanılarak</span><span class="sxs-lookup"><span data-stu-id="28d2e-110">Using DataContractSerializer</span></span>  
  
-   <span data-ttu-id="28d2e-111">Tüm türleri ile işaretlenen `[DataContract]` özniteliği ortak olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="28d2e-111">All types marked with the `[DataContract]` attribute must be public.</span></span> <span data-ttu-id="28d2e-112">Ortak olmayan türleri bir kısmi güven ortamında seri hale getirilemez.</span><span class="sxs-lookup"><span data-stu-id="28d2e-112">Non-public types cannot be serialized in a partial trust environment.</span></span>  
  
-   <span data-ttu-id="28d2e-113">Tüm `[DataContract]` üyeleri bir serileştirilebilir `[DataContract]` türü ortak olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="28d2e-113">All `[DataContract]` members in a serializable `[DataContract]` type must be public.</span></span> <span data-ttu-id="28d2e-114">Genel olmayan bir türüyle `[DataMember]` bir kısmi güven ortamında seri hale getirilemez.</span><span class="sxs-lookup"><span data-stu-id="28d2e-114">A type with a non-public `[DataMember]` cannot be serialized in a partial trust environment.</span></span>  
  
-   <span data-ttu-id="28d2e-115">Seri hale getirme olayları işlemek yöntemleri (gibi `OnSerializing`, `OnSerialized`, `OnDeserializing`, ve `OnDeserialized`) genel olarak bildirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-115">Methods that handle serialization events (such as `OnSerializing`, `OnSerialized`, `OnDeserializing`, and `OnDeserialized`) must be declared as public.</span></span> <span data-ttu-id="28d2e-116">Ancak, açık ve kapalı uygulamaları <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> desteklenir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-116">However, both explicit and implicit implementations of <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> are supported.</span></span>  
  
-   <span data-ttu-id="28d2e-117">`[DataContract]`derlemelerde uygulanan türleri ile işaretlenen <xref:System.Security.AllowPartiallyTrustedCallersAttribute> Tür oluşturucu Eylemler güvenlikle ilgili olarak gerçekleştirmelisiniz değil <xref:System.Runtime.Serialization.DataContractSerializer> Oluşturucusu yeni örneği nesnesinin seri durumdan çıkarma sırasında çağırmaz.</span><span class="sxs-lookup"><span data-stu-id="28d2e-117">`[DataContract]` types implemented in assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> must not perform security-related actions in the type constructor, as the <xref:System.Runtime.Serialization.DataContractSerializer> does not call the constructor of the newly-instantiated object during deserialization.</span></span> <span data-ttu-id="28d2e-118">Özellikle, aşağıdaki genel güvenlik teknikleri için kaçınılmalıdır `[DataContract]` türleri:</span><span class="sxs-lookup"><span data-stu-id="28d2e-118">Specifically, the following common security techniques must be avoided for `[DataContract]` types:</span></span>  
  
-   <span data-ttu-id="28d2e-119">İç veya özel tür Oluşturucu yaparak kısmi güven erişimi kısıtlamak çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="28d2e-119">Attempting to restrict partial trust access by making the type's constructor internal or private.</span></span>  
  
-   <span data-ttu-id="28d2e-120">Ekleyerek türü için erişimi kısıtlamak bir `[LinkDemand]` tür oluşturucuya.</span><span class="sxs-lookup"><span data-stu-id="28d2e-120">Restricting access to the type by adding a `[LinkDemand]` to the type's constructor.</span></span>  
  
-   <span data-ttu-id="28d2e-121">Nesne başarıyla örneği olduğundan oluşturucusu tarafından zorlanan tüm doğrulama denetimleri başarıyla başarılı olduğunu varsayarak.</span><span class="sxs-lookup"><span data-stu-id="28d2e-121">Assuming that because the object has been successfully instantiated, any validation checks enforced by the constructor have passed successfully.</span></span>  
  
### <a name="using-ixmlserializable"></a><span data-ttu-id="28d2e-122">IXmlSerializable kullanma</span><span class="sxs-lookup"><span data-stu-id="28d2e-122">Using IXmlSerializable</span></span>  
 <span data-ttu-id="28d2e-123">Uygulama türleri için aşağıdaki en iyi yöntemleri uygulayın <xref:System.Xml.Serialization.IXmlSerializable> ve kullanılarak serileştirilmiş <xref:System.Runtime.Serialization.DataContractSerializer>:</span><span class="sxs-lookup"><span data-stu-id="28d2e-123">The following best practices apply for types that implement <xref:System.Xml.Serialization.IXmlSerializable> and are serialized using the <xref:System.Runtime.Serialization.DataContractSerializer>:</span></span>  
  
-   <span data-ttu-id="28d2e-124"><xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> Statik yöntem uygulamalarını olmalıdır `public`.</span><span class="sxs-lookup"><span data-stu-id="28d2e-124">The <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> static method implementations must be `public`.</span></span>  
  
-   <span data-ttu-id="28d2e-125">Uygulama örnek yöntemleri <xref:System.Xml.Serialization.IXmlSerializable> arabirimi olmalıdır `public`.</span><span class="sxs-lookup"><span data-stu-id="28d2e-125">The instance methods that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface must be `public`.</span></span>  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a><span data-ttu-id="28d2e-126">WCF gelen çağrıları kısmen sağlayan tam olarak Güvenilir Platform kodundan kullanarak güvenilen arayanlara</span><span class="sxs-lookup"><span data-stu-id="28d2e-126">Using WCF from Fully-Trusted Platform Code that Allows Calls from Partially Trusted Callers</span></span>  
 <span data-ttu-id="28d2e-127">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Kısmi güven güvenlik modeli varsayar, tüm çağıran bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ortak yöntemi veya özelliği barındırma uygulama kod erişim güvenliği (CAS) bağlamında çalışır.</span><span class="sxs-lookup"><span data-stu-id="28d2e-127">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] partial trust security model assumes that any caller of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] public method or property is running in the code access security (CAS) context of the hosting application.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="28d2e-128">Ayrıca, yalnızca bir uygulama güvenlik bağlamı var her biri için varsayar <xref:System.AppDomain>, ve bu bağlamda adresindeki oluşturulmuş <xref:System.AppDomain> bir güvenilir ana bilgisayar tarafından oluşturma zamanı (örneğin, bir çağrı tarafından <xref:System.AppDomain.CreateDomain%2A> veya ASP.NET Uygulama Yöneticisi tarafından).</span><span class="sxs-lookup"><span data-stu-id="28d2e-128"> also assumes that only one application security context exists for each <xref:System.AppDomain>, and that this context is established at <xref:System.AppDomain> creation time by a trusted host (for example, by a call to <xref:System.AppDomain.CreateDomain%2A> or by the ASP.NET Application Manager).</span></span>  
  
 <span data-ttu-id="28d2e-129">Bu güvenlik modeli, bir orta güven ASP.NET uygulamasında çalışan kullanıcı kodu gibi ek CA'lar izinler assert olamaz kullanıcı tarafından yazılan uygulamaları için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-129">This security model applies to user-written applications that cannot assert additional CAS permissions, such as user code running in a Medium Trust ASP.NET application.</span></span> <span data-ttu-id="28d2e-130">Ancak, tam olarak güvenilir platform kodu (örneğin, genel derleme önbelleğinde yüklü olan ve kısmen güvenilen kod gelen çağrıları kabul eden bir üçüncü taraf derleme) açık içine çağrılırken özen gerekir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kısmen güvenilen bir adına Uygulama düzeyi güvenlik açıkları önlemek için uygulama.</span><span class="sxs-lookup"><span data-stu-id="28d2e-130">However, fully-trusted platform code (for example, a third-party assembly that is installed in the global assembly cache and accepts calls from partially-trusted code) must take explicit care when calling into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] on behalf of a partially-trusted application to avoid introducing application-level security vulnerabilities.</span></span>  
  
 <span data-ttu-id="28d2e-131">Tam güven kodlardan kaçının geçerli iş parçacığının CA'lar izin kümesini değiştirme (çağırarak <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, veya <xref:System.Security.PermissionSet.Deny%2A>) çağrılmadan önce [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kısmen güvenilen kod adına API'leri.</span><span class="sxs-lookup"><span data-stu-id="28d2e-131">Full-trust code should avoid altering the CAS permission set of the current thread (by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>) prior to calling [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] APIs on behalf of partially-trusted code.</span></span> <span data-ttu-id="28d2e-132">Sunduğundan, engelleme ya da aksi takdirde uygulama düzeyinde güvenlik bağlamı bağımsız olan bir iş parçacığına özgü izni bağlamı oluşturma beklenmeyen davranışlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-132">Asserting, denying, or otherwise creating a thread-specific permission context that is independent of the application-level security context can result in unexpected behavior.</span></span> <span data-ttu-id="28d2e-133">Uygulamaya bağlı olarak, bu davranış, uygulama düzeyinde güvenlik açıklarına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-133">Depending on the application, this behavior may result in application-level security vulnerabilities.</span></span>  
  
 <span data-ttu-id="28d2e-134">İçine çağıran kodu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] iş parçacığına özgü izni bağlamını kullanarak gerekir hazırlanmış kaynaklanabilecek aşağıdaki durumlarda işlemek için:</span><span class="sxs-lookup"><span data-stu-id="28d2e-134">Code that calls into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] using a thread-specific permission context must be prepared to handle the following situations that may arise:</span></span>  
  
-   <span data-ttu-id="28d2e-135">İş parçacığına özgü güvenlik bağlamı olası güvenlik özel durumlarıyla sonuçları işlemi süresince saklanması değil.</span><span class="sxs-lookup"><span data-stu-id="28d2e-135">The thread-specific security context may not be maintained for the duration of the operation, which results in potential security exceptions.</span></span>  
  
-   <span data-ttu-id="28d2e-136">İç [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kodun yanı sıra tüm kullanıcı tarafından sağlanan geri aramalar farklı güvenlik bağlamı altında çağrı başlangıçta başlatıldı fazla çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-136">Internal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] code as well as any user-provided callbacks may run in a different security context than the one under which the call was originally initiated.</span></span> <span data-ttu-id="28d2e-137">Bu içerikler şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="28d2e-137">These contexts include:</span></span>  
  
    -   <span data-ttu-id="28d2e-138">Uygulama izni bağlamı.</span><span class="sxs-lookup"><span data-stu-id="28d2e-138">The application permission context.</span></span>  
  
    -   <span data-ttu-id="28d2e-139">Daha önce çağırmak için kullanılan başka bir kullanıcı iş parçacığı tarafından oluşturulan her iş parçacığına özgü izni bağlam [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] şu anda çalışan kullanım ömrü süresince <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="28d2e-139">Any thread-specific permission context previously created by other user threads used to call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] during the lifetime of the currently running <xref:System.AppDomain>.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="28d2e-140">Bu izinlere içine çağrılmadan önce tam olarak güvenilir bir bileşen tarafından uygulanan sürece kısmen güvenilen kodu tam güven izinleri elde edemiyor garanti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ortak API'ler.</span><span class="sxs-lookup"><span data-stu-id="28d2e-140"> guarantees that partially-trusted code cannot obtain full-trust permissions unless such permissions are asserted by a fully-trusted component prior to calling into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] public APIs.</span></span> <span data-ttu-id="28d2e-141">Ancak, onu tam güven sunduğundan etkilerini belirli iş parçacığı, işlem veya kullanıcı eylemi yalıtılmış garanti etmez.</span><span class="sxs-lookup"><span data-stu-id="28d2e-141">However, it does not guarantee that the effects of asserting full trust is isolated to a particular thread, operation, or user action.</span></span>  
  
 <span data-ttu-id="28d2e-142">En iyi uygulama, iş parçacığına özgü izni bağlam çağırarak oluşturmamak <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, veya <xref:System.Security.PermissionSet.Deny%2A>.</span><span class="sxs-lookup"><span data-stu-id="28d2e-142">As a best practice, avoid creating thread-specific permission context by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>.</span></span> <span data-ttu-id="28d2e-143">Bunun yerine, vermek ya da uygulamaya kendisini ayrıcalık reddetmek için hiçbir <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A>, veya <xref:System.Security.PermissionSet.PermitOnly%2A> gereklidir.</span><span class="sxs-lookup"><span data-stu-id="28d2e-143">Instead, grant or deny the privilege to the application itself, so that no <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A>, or <xref:System.Security.PermissionSet.PermitOnly%2A> is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d2e-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="28d2e-144">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Xml.Serialization.IXmlSerializable>