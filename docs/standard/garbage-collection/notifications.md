---
title: "Çöp Toplama Bildirimleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="85e9b-102">Çöp Toplama Bildirimleri</span><span class="sxs-lookup"><span data-stu-id="85e9b-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="85e9b-103">Bazı durumlarda, tam atık toplama (diğer bir deyişle, 2. nesil toplama) ortak dil çalışma zamanı tarafından performansını olumsuz etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="85e9b-104">Bu, özellikle büyük miktarda istekleri işlemek sunucuları ile ilgili bir sorun olabilir; Bu durumda, uzun çöp toplama istek zaman aşımı neden olabilir. Tam bir koleksiyon kritik bir dönem boyunca oluşmasını önlemek için tam atık toplama yaklaştığını ve iş yükünü başka bir sunucu örneğine yönlendirmek için önlem bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="85e9b-105">Geçerli sunucu örneğini istekleri işleyen gerekmez koşuluyla, ayrıca bir koleksiyon kendiniz anlamına.</span><span class="sxs-lookup"><span data-stu-id="85e9b-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="85e9b-106"><xref:System.GC.RegisterForFullGCNotification%2A> Yöntemi, tam atık toplama yaklaştığını çalışma zamanı algılayan tetiklenir için bildirimini kaydeder.</span><span class="sxs-lookup"><span data-stu-id="85e9b-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="85e9b-107">Bu bildirim için iki bölümden oluşur: tam atık toplama yaklaştığı ne zaman ve ne zaman tam atık toplama tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="85e9b-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="85e9b-108">Yalnızca engelleme çöp koleksiyonları bildirimleri yükseltin.</span><span class="sxs-lookup"><span data-stu-id="85e9b-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="85e9b-109">Zaman [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) yapılandırma öğesi etkinleştirildiğinde, arka plan çöp koleksiyonları değil bildirimleri Yükselt.</span><span class="sxs-lookup"><span data-stu-id="85e9b-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="85e9b-110">Ne zaman bir uyarı oluşturuldu belirlemek için <xref:System.GC.WaitForFullGCApproach%2A> ve <xref:System.GC.WaitForFullGCComplete%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="85e9b-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="85e9b-111">Bu yöntemleri genellikle, kullandığınız bir `while` sürekli olarak almak için döngü bir <xref:System.GCNotificationStatus> bildirim durumunu gösteren sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="85e9b-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="85e9b-112">Bu değer ise <xref:System.GCNotificationStatus.Succeeded>, aşağıdakileri yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="85e9b-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="85e9b-113">Yanıt ile elde edilen bir bildirim olarak <xref:System.GC.WaitForFullGCApproach%2A> yöntemi, iş yükü yönlendirebilir ve büyük olasılıkla bir koleksiyon kendiniz anlamına.</span><span class="sxs-lookup"><span data-stu-id="85e9b-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="85e9b-114">Yanıt ile elde edilen bir bildirim olarak <xref:System.GC.WaitForFullGCComplete%2A> yöntemi, geçerli sunucu örneğini yeniden isteklerini işlemek kullanılabilir yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="85e9b-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="85e9b-115">Ayrıca, bilgi toplayabilir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-115">You can also gather information.</span></span> <span data-ttu-id="85e9b-116">Örneğin, kullanabileceğiniz <xref:System.GC.CollectionCount%2A> koleksiyon sayısı kaydetmek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="85e9b-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="85e9b-117"><xref:System.GC.WaitForFullGCApproach%2A> Ve <xref:System.GC.WaitForFullGCComplete%2A> yöntemleri birlikte çalışmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="85e9b-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="85e9b-118">Diğer olmadan kullanarak belirsiz sonuçlara yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="85e9b-119">Tam çöp toplama</span><span class="sxs-lookup"><span data-stu-id="85e9b-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="85e9b-120">Aşağıdaki senaryoların herhangi biri doğru olduğunda çalışma zamanı tam atık toplama neden olur:</span><span class="sxs-lookup"><span data-stu-id="85e9b-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="85e9b-121">Yeterli bellek, sonraki 2. nesil koleksiyonu neden 2. nesil yükseltildi.</span><span class="sxs-lookup"><span data-stu-id="85e9b-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="85e9b-122">Yeterli bellek, sonraki 2. nesil koleksiyonu neden büyük nesne yığın yükseltildi.</span><span class="sxs-lookup"><span data-stu-id="85e9b-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="85e9b-123">2. nesil diğer etkenler nedeniyle koleksiyonu için 1. nesil koleksiyonu ilerletilen.</span><span class="sxs-lookup"><span data-stu-id="85e9b-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="85e9b-124">Belirttiğiniz eşikleri <xref:System.GC.RegisterForFullGCNotification%2A> yöntemi ilk iki senaryo için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="85e9b-125">Ancak, ilk senaryoda, her zaman bildirim için iki nedenden dolayı belirttiğiniz eşik değerleri orantılı zaman almaz:</span><span class="sxs-lookup"><span data-stu-id="85e9b-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="85e9b-126">Çalışma zamanı her küçük nesne ayırma (performans nedenleriyle) denetlemez.</span><span class="sxs-lookup"><span data-stu-id="85e9b-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="85e9b-127">Yalnızca 1 koleksiyonları nesil 2. nesil bellek yükseltin.</span><span class="sxs-lookup"><span data-stu-id="85e9b-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="85e9b-128">Üçüncü senaryo da bildirim aldığınızda, belirsizlik katkıda bulunur.</span><span class="sxs-lookup"><span data-stu-id="85e9b-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="85e9b-129">Bu bir garantisi olmasa da bu süre boyunca istekleri yönlendirme ya da daha iyi yerleştirilebilecek zaman koleksiyon kendiniz inducing çıkarsanız tam atık toplama etkilerini azaltmak için kullanışlı bir yoldur kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="85e9b-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="85e9b-130">Bildirim eşiği parametreleri</span><span class="sxs-lookup"><span data-stu-id="85e9b-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="85e9b-131"><xref:System.GC.RegisterForFullGCNotification%2A> Yöntemi kuşak 2 nesnelerinin ve büyük nesne yığın eşik değerlerini belirtmek için iki parametreye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="85e9b-132">Bu değerleri karşılandığında bir atık toplama bildirim oluşmalıdır.</span><span class="sxs-lookup"><span data-stu-id="85e9b-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="85e9b-133">Aşağıdaki tabloda bu parametreler açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="85e9b-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="85e9b-134">Parametre</span><span class="sxs-lookup"><span data-stu-id="85e9b-134">Parameter</span></span>|<span data-ttu-id="85e9b-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="85e9b-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="85e9b-136">Bildirim ne zaman oluşturulması belirten bir sayı 1 ile 99 arasında nesil 2 yükseltilmiş nesneleri temel.</span><span class="sxs-lookup"><span data-stu-id="85e9b-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="85e9b-137">Bildirim ne zaman oluşturulması belirten bir sayı 1 ile 99 arasında büyük nesne yığın ayrılmış nesneleri temel.</span><span class="sxs-lookup"><span data-stu-id="85e9b-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="85e9b-138">Çok yüksek bir değer belirtirseniz, bir bildirim alırsınız, ancak bir koleksiyon çalışma zamanı neden olmadan önce beklenecek çok uzun bir süre olabilir yüksek olasılık yoktur.</span><span class="sxs-lookup"><span data-stu-id="85e9b-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="85e9b-139">Bir koleksiyon kendiniz anlamına, çalışma zamanı koleksiyonu neden olursa iadesi daha çok nesne geri.</span><span class="sxs-lookup"><span data-stu-id="85e9b-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="85e9b-140">Çok düşük bir değer belirtirseniz, bildirim almak için yeterli süre beklendiğinden önce çalışma zamanı koleksiyonu neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="85e9b-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85e9b-141">Örnek</span><span class="sxs-lookup"><span data-stu-id="85e9b-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="85e9b-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="85e9b-142">Description</span></span>  
 <span data-ttu-id="85e9b-143">Aşağıdaki örnekte, bir sunucu grubu gelen Web isteklerini hizmet.</span><span class="sxs-lookup"><span data-stu-id="85e9b-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="85e9b-144">İstek işleme yükünü benzetimini yapmak için bayt dizileri eklenir bir <xref:System.Collections.Generic.List%601> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="85e9b-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="85e9b-145">Her sunucu için bir atık toplama bildirimi kaydeder ve ardından üzerinde bir iş parçacığı başlatır `WaitForFullGCProc` sürekli olarak izlemek için kullanıcı yöntemi <xref:System.GCNotificationStatus> tarafından döndürülen numaralandırma <xref:System.GC.WaitForFullGCApproach%2A> ve <xref:System.GC.WaitForFullGCComplete%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="85e9b-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="85e9b-146"><xref:System.GC.WaitForFullGCApproach%2A> Ve <xref:System.GC.WaitForFullGCComplete%2A> yöntemleri bir uyarı oluştuğunda kendi ilgili olay işleme kullanıcı yöntemlerini çağırın:</span><span class="sxs-lookup"><span data-stu-id="85e9b-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="85e9b-147">Bu yöntemi çağırır `RedirectRequests` gönderme askıya alma isteği queuing sunucusuna bildirir kullanıcı yöntemi sunucuya ister.</span><span class="sxs-lookup"><span data-stu-id="85e9b-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="85e9b-148">Bu sınıf düzeyi değişkeni ayarlayarak benzetilir `bAllocate` için `false` böylece daha fazla nesne ayrılır.</span><span class="sxs-lookup"><span data-stu-id="85e9b-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="85e9b-149">İleri `FinishExistingRequests` kullanıcı yöntemi bekleyen sunucu isteklerini işlemini bitirmek için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="85e9b-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="85e9b-150">Bu temizleyerek benzetilir <xref:System.Collections.Generic.List%601> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="85e9b-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="85e9b-151">Son olarak, iş yükü açık olduğundan çöp toplama işleminden.</span><span class="sxs-lookup"><span data-stu-id="85e9b-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="85e9b-152">Bu yöntem kullanıcı yöntemini çağırır `AcceptRequests` istekleri kabul edip, sunucu artık bir tam atık toplama uygulanmadıkça olmadığı için devam etmek için.</span><span class="sxs-lookup"><span data-stu-id="85e9b-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="85e9b-153">Bu eylem ayarlayarak benzetimli `bAllocate` değişkenini `true` nesnelerin eklenmesini devam edebilmeniz için <xref:System.Collections.Generic.List%601> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="85e9b-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="85e9b-154">Aşağıdaki kodu içeren `Main` örnek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="85e9b-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="85e9b-155">Aşağıdaki kodu içeren `WaitForFullGCProc` çöp toplama bildirimleri için denetlemek için döngü sırasında sürekli içeren kullanıcı yöntemi.</span><span class="sxs-lookup"><span data-stu-id="85e9b-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="85e9b-156">Aşağıdaki kodu içeren `OnFullGCApproachNotify` çağrılır gibi yöntemi</span><span class="sxs-lookup"><span data-stu-id="85e9b-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="85e9b-157">`WaitForFullGCProc`yöntem.</span><span class="sxs-lookup"><span data-stu-id="85e9b-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="85e9b-158">Aşağıdaki kodu içeren `OnFullGCApproachComplete` çağrılır gibi yöntemi</span><span class="sxs-lookup"><span data-stu-id="85e9b-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="85e9b-159">`WaitForFullGCProc`yöntem.</span><span class="sxs-lookup"><span data-stu-id="85e9b-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="85e9b-160">Aşağıdaki kod gelen adlı kullanıcı yöntemleri içeren `OnFullGCApproachNotify` ve `OnFullGCCompleteNotify` yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="85e9b-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="85e9b-161">Kullanıcı yöntemlerini yeniden yönlendirme istekleri, var olan istekleri bitiş ve tam atık toplama gerçekleştikten sonra istekleri Sürdür.</span><span class="sxs-lookup"><span data-stu-id="85e9b-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="85e9b-162">Tüm kodu örneği aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="85e9b-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="85e9b-163">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85e9b-163">See Also</span></span>  
 [<span data-ttu-id="85e9b-164">Çöp toplama</span><span class="sxs-lookup"><span data-stu-id="85e9b-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)