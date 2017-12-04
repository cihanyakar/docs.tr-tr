---
title: "Yönetilmeyen Kod İçin Güvenli Kodlama Yönergeleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code security, unmanaged code
- unmanaged code, securing
- security [.NET Framework], unmanaged code
- secure coding, unmanaged code
ms.assetid: a8d15139-d368-4c9c-a747-ba757781117c
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b6eec726342381f7e3ec71aeedd2ff012bc6c3e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="secure-coding-guidelines-for-unmanaged-code"></a><span data-ttu-id="48452-102">Yönetilmeyen Kod İçin Güvenli Kodlama Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="48452-102">Secure Coding Guidelines for Unmanaged Code</span></span>
<span data-ttu-id="48452-103">Yönetilmeyen kod (örneğin, yerel kod gibi Win32 API'ları) çağırmak bazı kitaplık kodu gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-103">Some library code needs to call into unmanaged code (for example, native code APIs, such as Win32).</span></span> <span data-ttu-id="48452-104">Bu yönetilen kod için güvenlik çevre dışında son giderek gösterdiğinden dikkat gereklidir.</span><span class="sxs-lookup"><span data-stu-id="48452-104">Because this means going outside the security perimeter for managed code, due caution is required.</span></span> <span data-ttu-id="48452-105">Tarafsız güvenlik kodunuzu ise hem kodunuz hem de çağırır herhangi bir kod kod izni yönetilmeyen gerekir (<xref:System.Security.Permissions.SecurityPermission> ile <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> bayrağı belirtilmiş).</span><span class="sxs-lookup"><span data-stu-id="48452-105">If your code is security-neutral, both your code and any code that calls it must have unmanaged code permission (<xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> flag specified).</span></span>  
  
 <span data-ttu-id="48452-106">Ancak, genellikle, çağıran gibi güçlü izinlerine sahip olmasını aşırı olur.</span><span class="sxs-lookup"><span data-stu-id="48452-106">However, it is often unreasonable for your caller to have such powerful permissions.</span></span> <span data-ttu-id="48452-107">Böyle durumlarda, güvenilir kodunuzu yönetilen sarmalayıcı benzer aracılık olabilir veya kitaplık kodu açıklanan [sarmalayıcı kodunun güvenliğini sağlama](../../../docs/framework/misc/securing-wrapper-code.md).</span><span class="sxs-lookup"><span data-stu-id="48452-107">In such cases, your trusted code can be the go-between, similar to the managed wrapper or library code described in [Securing Wrapper Code](../../../docs/framework/misc/securing-wrapper-code.md).</span></span> <span data-ttu-id="48452-108">Temel yönetilmeyen kod işlevsellik tümüyle güvenli ise, doğrudan verilebilen; Aksi takdirde, uygun izni denetimi (isteğe bağlı) ilk gereklidir.</span><span class="sxs-lookup"><span data-stu-id="48452-108">If the underlying unmanaged code functionality is totally safe, it can be directly exposed; otherwise, a suitable permission check (demand) is required first.</span></span>  
  
 <span data-ttu-id="48452-109">Yönetilmeyen koda kodunuzu çağırması ancak, çağrı yönetimsiz kod erişim iznine sahip gerektiren istemediğiniz durumlarda hak assert gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-109">When your code calls into unmanaged code but you do not want to require your callers to have permission to access unmanaged code, you must assert that right.</span></span> <span data-ttu-id="48452-110">Bir onaylama Çerçevenizi adresindeki yığın ilerlemesi engeller.</span><span class="sxs-lookup"><span data-stu-id="48452-110">An assertion blocks the stack walk at your frame.</span></span> <span data-ttu-id="48452-111">Bu işlemde güvenlik delik oluşturmayın dikkatli olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-111">You must be careful that you do not create a security hole in this process.</span></span> <span data-ttu-id="48452-112">Genellikle, bu, arayanlar, uygun bir izin talep ve yalnızca ne bu izin verir ve artık gerçekleştirmek için yönetilmeyen kod kullanmak anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="48452-112">Usually, this means that you must demand a suitable permission of your callers and then use unmanaged code to perform only what that permission allows and no more.</span></span> <span data-ttu-id="48452-113">Bazı durumlarda (örneğin, bir get gün saat işlevi) yönetilmeyen kod doğrudan tüm güvenlik denetimleri olmadan arayanlara gösterilebilir.</span><span class="sxs-lookup"><span data-stu-id="48452-113">In some cases (for example, a get time-of-day function), unmanaged code can be directly exposed to callers without any security checks.</span></span> <span data-ttu-id="48452-114">Herhangi bir durumda, onaylar herhangi bir kod güvenlik sorumluluğunu almanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-114">In any case, any code that asserts must take responsibility for security.</span></span>  
  
 <span data-ttu-id="48452-115">Yerel kod içine bir kod yolu sağlayan herhangi bir yönetilen kod kötü amaçlı kod olası hedefi olduğundan, hangi yönetilmeyen kod belirleme güvenli bir şekilde kullanılabilmesi için ve son derece dikkatli olunmalıdır nasıl kullanılmalıdır gerektirir.</span><span class="sxs-lookup"><span data-stu-id="48452-115">Because any managed code that provides a code path into native code is a potential target for malicious code, determining which unmanaged code can be safely used and how it must be used requires extreme care.</span></span> <span data-ttu-id="48452-116">Genellikle, yönetilmeyen kod hiçbir zaman doğrudan kısmen güvenilen arayanlara açılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="48452-116">Generally, unmanaged code should never be directly exposed to partially trusted callers.</span></span> <span data-ttu-id="48452-117">Yönetilmeyen kod kullanımı kısmen güvenilen kod tarafından çağrılabilir kitaplıkları güvenliği hesaplama iki birincil noktalar vardır:</span><span class="sxs-lookup"><span data-stu-id="48452-117">There are two primary considerations in evaluating the safety of unmanaged code use in libraries that are callable by partially trusted code:</span></span>  
  
-   <span data-ttu-id="48452-118">**İşlevselliği**.</span><span class="sxs-lookup"><span data-stu-id="48452-118">**Functionality**.</span></span> <span data-ttu-id="48452-119">Yönetilmeyen API potansiyel olarak tehlikeli olabilecek işlemlerini gerçekleştirmek arayanlara izin vermiyor işlevsellik sağlar mı?</span><span class="sxs-lookup"><span data-stu-id="48452-119">Does the unmanaged API provide functionality that does not allow callers to perform potentially dangerous operations?</span></span> <span data-ttu-id="48452-120">Kod erişimi güvenliği izinleri kaynaklarına erişimi zorlamak için bu nedenle API dosyaları, bir kullanıcı arabirimi kullanıp kullanmadığını göz önünde bulundurun kullanır veya iş parçacığı oluşturma, ya da bilgi korumalı olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="48452-120">Code access security uses permissions to enforce access to resources, so consider whether the API uses files, a user interface, or threading, or whether it exposes protected information.</span></span> <span data-ttu-id="48452-121">Bulursa, onu kaydırma yönetilen kod girilmesi kendisine izin vermeden önce gerekli izinleri talep gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-121">If it does, the managed code wrapping it must demand the necessary permissions before allowing it to be entered.</span></span> <span data-ttu-id="48452-122">Ayrıca, bir izin tarafından korunmayan olsa da, bellek erişimi için kesin tür güvenliği sınırlı gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-122">Additionally, while not protected by a permission, memory access must be confined to strict type safety.</span></span>  
  
-   <span data-ttu-id="48452-123">**Parametre denetimi**.</span><span class="sxs-lookup"><span data-stu-id="48452-123">**Parameter checking**.</span></span> <span data-ttu-id="48452-124">Ortak bir saldırı geçişleri beklenmeyen parametreleri yönetilmeyen kod API yöntemlerini dışında belirtimi çalışmasına neden girişimi de sağlanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="48452-124">A common attack passes unexpected parameters to exposed unmanaged code API methods in an attempt to cause them to operate out of specification.</span></span> <span data-ttu-id="48452-125">Aralık çıkış dizini kullanarak arabellek taşmasına neden veya arka plandaki kod hatada yararlanabilir herhangi bir parametre olarak uzaklık değerleri bu tür saldırılar, yaygın bir örneği değil.</span><span class="sxs-lookup"><span data-stu-id="48452-125">Buffer overruns using out-of-range index or offset values are one common example of this type of attack, as are any parameters that might exploit a bug in the underlying code.</span></span> <span data-ttu-id="48452-126">Yönetilmeyen kod API (sonra gerekli taleplerini) kısmen güvenilir işlevsel olarak güvenli olsa bile bu nedenle, yönetilen arayanlar, gereken ayrıca ayrıntısına hiçbir istenmeyen çağrıları kötü amaçlı koddan yönetilen kullanarak olası olduğundan emin olmak için onay parametre geçerlilik kod kod sarmalayıcı katmanı.</span><span class="sxs-lookup"><span data-stu-id="48452-126">Thus, even if the unmanaged code API is functionally safe (after necessary demands) for partially trusted callers, managed code must also check parameter validity exhaustively to ensure that no unintended calls are possible from malicious code using the managed code wrapper layer.</span></span>  
  
## <a name="using-suppressunmanagedcodesecurityattribute"></a><span data-ttu-id="48452-127">SuppressUnmanagedCodeSecurityAttribute Kullanma</span><span class="sxs-lookup"><span data-stu-id="48452-127">Using SuppressUnmanagedCodeSecurityAttribute</span></span>  
 <span data-ttu-id="48452-128">Bir performans boy sunduğundan ve yönetilmeyen kodu çağırma yoktur.</span><span class="sxs-lookup"><span data-stu-id="48452-128">There is a performance aspect to asserting and then calling unmanaged code.</span></span> <span data-ttu-id="48452-129">Her tür çağrısı için güvenlik sistemi otomatik olarak her zaman bir yığın ilerlemesi kaynaklanan yönetilmeyen kod iznine ihtiyaç duyar.</span><span class="sxs-lookup"><span data-stu-id="48452-129">For every such call, the security system automatically demands unmanaged code permission, resulting in a stack walk each time.</span></span> <span data-ttu-id="48452-130">Assert ve hemen yönetilmeyen kodu çağırma yığın ilerlemesi anlamsız olabilir:, assert ve yönetilmeyen kod aramanız oluşur.</span><span class="sxs-lookup"><span data-stu-id="48452-130">If you assert and immediately call unmanaged code, the stack walk can be meaningless: it consists of your assert and your unmanaged code call.</span></span>  
  
 <span data-ttu-id="48452-131">Özel bir öznitelik adı verilen <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> talep normal güvenlik denetimi devre dışı bırakmak için yönetilmeyen kod giriş noktaları için uygulanabilir <xref:System.Security.Permissions.SecurityPermission> ile <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> belirtilen izni.</span><span class="sxs-lookup"><span data-stu-id="48452-131">A custom attribute called <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> can be applied to unmanaged code entry points to disable the normal security check that demands <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> permission specified.</span></span> <span data-ttu-id="48452-132">Bu eylem, çalışma zamanı güvenlik ile yönetilmeyen koda açık bir kapı oluşturduğundan, bunu denetlediğinde son derece dikkatli olun her zaman alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-132">Extreme caution must always be taken when doing this, because this action creates an open door into unmanaged code with no runtime security checks.</span></span> <span data-ttu-id="48452-133">Not ettiğiniz, hatta ile **SuppressUnmanagedCodeSecurityAttribute** uygulanan, anında arayanlar çağırma izni olduğundan emin olmak için tam zamanında (JIT) derleme olur bir kerelik güvenlik denetimi yoktur yönetilmeyen kod.</span><span class="sxs-lookup"><span data-stu-id="48452-133">It should be noted that even with **SuppressUnmanagedCodeSecurityAttribute** applied, there is a one-time security check that happens at just-in-time (JIT) compilation to ensure that the immediate caller has permission to call unmanaged code.</span></span>  
  
 <span data-ttu-id="48452-134">Kullanırsanız **SuppressUnmanagedCodeSecurityAttribute**, aşağıdaki noktaları denetleyin:</span><span class="sxs-lookup"><span data-stu-id="48452-134">If you use the **SuppressUnmanagedCodeSecurityAttribute**, check the following points:</span></span>  
  
-   <span data-ttu-id="48452-135">Yönetilmeyen kod giriş noktası iç ya da kodunuzu dışında herhangi bir şekilde erişilemez olun.</span><span class="sxs-lookup"><span data-stu-id="48452-135">Make the unmanaged code entry point internal or otherwise inaccessible outside your code.</span></span>  
  
-   <span data-ttu-id="48452-136">Tüm yönetilmeyen koda olası bir güvenlik delik çağrıdır.</span><span class="sxs-lookup"><span data-stu-id="48452-136">Any call into unmanaged code is a potential security hole.</span></span> <span data-ttu-id="48452-137">Kodunuzu dolaylı olarak yönetilmeyen koda çağırın ve güvenlik denetimi önlemek kötü amaçlı kod için bir portal olmadığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="48452-137">Make sure your code is not a portal for malicious code to indirectly call into unmanaged code and avoid a security check.</span></span> <span data-ttu-id="48452-138">İzinler, uygunsa talep.</span><span class="sxs-lookup"><span data-stu-id="48452-138">Demand permissions, if appropriate.</span></span>  
  
-   <span data-ttu-id="48452-139">Aşağıdaki bölümde açıklandığı gibi yönetilmeyen koda tehlikeli yolu oluştururken açıkça tanımlamak için bir adlandırma kuralını kullanın...</span><span class="sxs-lookup"><span data-stu-id="48452-139">Use a naming convention to explicitly identify when you are creating a dangerous path into unmanaged code, as described in the section below..</span></span>  
  
## <a name="naming-convention-for-unmanaged-code-methods"></a><span data-ttu-id="48452-140">Yönetilmeyen kod yöntemleri için adlandırma kuralı</span><span class="sxs-lookup"><span data-stu-id="48452-140">Naming convention for unmanaged code methods</span></span>  
 <span data-ttu-id="48452-141">Yönetilmeyen kod yöntemleri adlandırmak için kullanışlı ve yüksek oranda önerilen kuralı kuruldu.</span><span class="sxs-lookup"><span data-stu-id="48452-141">A useful and highly recommended convention has been established for naming unmanaged code methods.</span></span> <span data-ttu-id="48452-142">Tüm yönetilmeyen kod yöntemleri üç kategoriye ayrılır: **güvenli**, **yerel**, ve **güvensiz**.</span><span class="sxs-lookup"><span data-stu-id="48452-142">All unmanaged code methods are separated into three categories: **safe**, **native**, and **unsafe**.</span></span> <span data-ttu-id="48452-143">Bu anahtar sözcükler içinde çeşitli yönetilmeyen kod giriş noktaları tanımlanan sınıf adları kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="48452-143">These keywords can be used as class names within which the various kinds of unmanaged code entry points are defined.</span></span> <span data-ttu-id="48452-144">Kaynak kodunda bu anahtar sözcükler sınıf adı olarak eklenmesi gerektiğini `Safe.GetTimeOfDay`, `Native.Xyz`, veya `Unsafe.DangerousAPI`, örneğin.</span><span class="sxs-lookup"><span data-stu-id="48452-144">In source code, these keywords should be added to the class name, as in `Safe.GetTimeOfDay`, `Native.Xyz`, or `Unsafe.DangerousAPI`, for example.</span></span> <span data-ttu-id="48452-145">Aşağıdaki tabloda açıklandığı gibi her şu anahtar sözcüklerden biri o sınıfın kullanan geliştiriciler için yararlı bir güvenlik bilgileri sağlar.</span><span class="sxs-lookup"><span data-stu-id="48452-145">Each of these keywords provides useful security information for developers using that class, as described in the following table.</span></span>  
  
|<span data-ttu-id="48452-146">Anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="48452-146">Keyword</span></span>|<span data-ttu-id="48452-147">Güvenlik konuları</span><span class="sxs-lookup"><span data-stu-id="48452-147">Security considerations</span></span>|  
|-------------|-----------------------------|  
|<span data-ttu-id="48452-148">**Güvenli**</span><span class="sxs-lookup"><span data-stu-id="48452-148">**safe**</span></span>|<span data-ttu-id="48452-149">Herhangi bir kod için çağırmak için bile kötü amaçlı kod zararsız tamamen.</span><span class="sxs-lookup"><span data-stu-id="48452-149">Completely harmless for any code, even malicious code, to call.</span></span> <span data-ttu-id="48452-150">Diğer yönetilen kod gibi kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="48452-150">Can be used just like other managed code.</span></span> <span data-ttu-id="48452-151">Örneğin, günün saatini alır bir işlev genellikle güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="48452-151">For example, a function that gets the time of day is typically safe.</span></span>|  
|<span data-ttu-id="48452-152">**Yerel**</span><span class="sxs-lookup"><span data-stu-id="48452-152">**native**</span></span>|<span data-ttu-id="48452-153">Tarafsız güvenlik; diğer bir deyişle, kodu çağırma izni gerektiren yönetilmeyen kod yönetilmeyen.</span><span class="sxs-lookup"><span data-stu-id="48452-153">Security-neutral; that is, unmanaged code that requires unmanaged code permission to call.</span></span> <span data-ttu-id="48452-154">Güvenlik, yetkisiz bir arayan vermemeye denetlenir.</span><span class="sxs-lookup"><span data-stu-id="48452-154">Security is checked, which stops an unauthorized caller.</span></span>|  
|<span data-ttu-id="48452-155">**güvenli olmayan**</span><span class="sxs-lookup"><span data-stu-id="48452-155">**unsafe**</span></span>|<span data-ttu-id="48452-156">Gizlenen güvenlik potansiyel olarak tehlikeli olabilecek yönetilmeyen kod giriş noktası.</span><span class="sxs-lookup"><span data-stu-id="48452-156">Potentially dangerous unmanaged code entry point with security suppressed.</span></span> <span data-ttu-id="48452-157">Geliştiriciler en dikkat gibi yönetilmeyen kod kullanırken diğer korumaları bir güvenlik açığı önlemek için yerine getirildiğinden emin kullanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="48452-157">Developers should use the greatest caution when using such unmanaged code, making sure that other protections are in place to prevent a security vulnerability.</span></span> <span data-ttu-id="48452-158">Bu anahtar sözcük güvenlik sistemi geçersiz kılmaları geliştiriciler sorumlu olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="48452-158">Developers must be responsible, as this keyword overrides the security system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48452-159">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="48452-159">See Also</span></span>  
 [<span data-ttu-id="48452-160">Güvenli kodlama yönergeleri</span><span class="sxs-lookup"><span data-stu-id="48452-160">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)