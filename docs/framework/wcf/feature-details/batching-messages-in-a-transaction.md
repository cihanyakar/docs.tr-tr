---
title: "Bir İşlemde Toplu İleti İşleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d9effe9b44a8e6f786103162930852de80ab4f8d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="batching-messages-in-a-transaction"></a><span data-ttu-id="144e5-102">Bir İşlemde Toplu İleti İşleme</span><span class="sxs-lookup"><span data-stu-id="144e5-102">Batching Messages in a Transaction</span></span>
<span data-ttu-id="144e5-103">Sıraya alınan uygulamaları işlemleri doğruluk ve iletilerin güvenilir teslimini emin olmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="144e5-103">Queued applications use transactions to ensure correctness and reliable delivery of messages.</span></span> <span data-ttu-id="144e5-104">İşlemler, ancak pahalı işlemleri ve ileti işleme önemli ölçüde azaltabilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-104">Transactions, however, are expensive operations and can dramatically reduce message throughput.</span></span> <span data-ttu-id="144e5-105">İleti verimini artırmak için bir uygulamanın okuma ve tek bir işlem içinde birden çok iletileri işlemek için yoludur.</span><span class="sxs-lookup"><span data-stu-id="144e5-105">One way to improve message throughput is to have an application read and process multiple messages within a single transaction.</span></span> <span data-ttu-id="144e5-106">Performans ve kurtarma arasında dengelemeyi olduğundan: toplu ileti sayısı arttıkça, bu nedenle işlemler geri alınacak, gerekli kurtarma iş miktarı verir.</span><span class="sxs-lookup"><span data-stu-id="144e5-106">The trade-off is between performance and recovery: as the number of messages in a batch increases, so does the amount of recovery work that required if transactions are rolled back.</span></span> <span data-ttu-id="144e5-107">Toplu işlem ve oturumları ileti işleme arasındaki farkı dikkate almak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="144e5-107">It is important to note the difference between batching messages in a transaction and sessions.</span></span> <span data-ttu-id="144e5-108">A *oturum* tek bir uygulama tarafından işlenen ve tek bir birim olarak kabul edilen ilgili iletiler grubudur.</span><span class="sxs-lookup"><span data-stu-id="144e5-108">A *session* is a grouping of related messages that are processed by a single application and committed as a single unit.</span></span> <span data-ttu-id="144e5-109">Oturumlar, genellikle bir grup ilgili iletiler birlikte işlenmesi gereken olduğunda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="144e5-109">Sessions are generally used when a group of related messages must be processed together.</span></span> <span data-ttu-id="144e5-110">Bunun bir örneğini çevrimiçi bir alışveriş Web sitesidir.</span><span class="sxs-lookup"><span data-stu-id="144e5-110">An example of this is an online shopping Web site.</span></span> <span data-ttu-id="144e5-111">*Toplu* birden çok işlemek için kullanılan, ilgisiz artar verimlilik ileti şekilde iletileri.</span><span class="sxs-lookup"><span data-stu-id="144e5-111">*Batches* are used to process multiple, unrelated messages in a way that increases message throughput.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="144e5-112">oturumları, bkz: [gruplandırma sıraya alınan iletileri bir oturumda](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span><span class="sxs-lookup"><span data-stu-id="144e5-112"> sessions, see [Grouping Queued Messages in a Session](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span></span> <span data-ttu-id="144e5-113">Bir toplu iletiler de tek bir uygulama tarafından işlenen ve tek bir birim olarak kabul edilen, ancak toplu iletileri arasında hiçbir ilişki olabilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-113">Messages in a batch are also processed by a single application and committed as a single unit, but there may be no relationship between the messages in the batch.</span></span> <span data-ttu-id="144e5-114">Bir işlemde toplu ileti işleme, uygulama nasıl çalışacağını değişmeyen bir hale getirilmesidir.</span><span class="sxs-lookup"><span data-stu-id="144e5-114">Batching messages in a transaction is an optimization that does not change how the application runs.</span></span>  
  
## <a name="entering-batching-mode"></a><span data-ttu-id="144e5-115">Toplu işleme modunu girme</span><span class="sxs-lookup"><span data-stu-id="144e5-115">Entering Batching Mode</span></span>  
 <span data-ttu-id="144e5-116"><xref:System.ServiceModel.Description.TransactedBatchingBehavior> Toplu işleme uç noktası davranışı denetimleri.</span><span class="sxs-lookup"><span data-stu-id="144e5-116">The <xref:System.ServiceModel.Description.TransactedBatchingBehavior> endpoint behavior controls batching.</span></span> <span data-ttu-id="144e5-117">Bu uç noktası davranışı bir hizmet uç noktası ekleme söyler [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bir işlemde toplu iletileri.</span><span class="sxs-lookup"><span data-stu-id="144e5-117">Adding this endpoint behavior to a service endpoint tells [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to batch messages in a transaction.</span></span> <span data-ttu-id="144e5-118">Bir işlem gerektiren yalnızca iletileri bir toplu işlemde yerleştirilir bunu tüm iletileri bir işlem gerektirir ve yalnızca işlemlerinden gönderilen iletiler ile işaretlenen `TransactionScopeRequired`  =  `true` ve `TransactionAutoComplete`  =  `true` olan Toplu işlem için kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-118">Not all messages require a transaction, so only messages that require a transaction are placed in a batch, and only messages sent from operations marked with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true` are considered for a batch.</span></span> <span data-ttu-id="144e5-119">Hizmet sözleşmesi tüm işlemler ile işaretlenmiş ise `TransactionScopeRequired`  =  `false` ve `TransactionAutoComplete`  =  `false`, toplu işlem modu hiç girilmedi sonra.</span><span class="sxs-lookup"><span data-stu-id="144e5-119">If all operations on the service contract are marked with `TransactionScopeRequired` = `false` and `TransactionAutoComplete` = `false`, then batching mode is never entered.</span></span>  
  
## <a name="committing-a-transaction"></a><span data-ttu-id="144e5-120">Bir işlem yapılıyor</span><span class="sxs-lookup"><span data-stu-id="144e5-120">Committing a Transaction</span></span>  
 <span data-ttu-id="144e5-121">Bir toplu işlem, aşağıdaki ölçütlere dayalı taahhüt eder:</span><span class="sxs-lookup"><span data-stu-id="144e5-121">A batched transaction is committed based on the following:</span></span>  
  
-   <span data-ttu-id="144e5-122">`MaxBatchSize`.</span><span class="sxs-lookup"><span data-stu-id="144e5-122">`MaxBatchSize`.</span></span> <span data-ttu-id="144e5-123">Bir özelliği <xref:System.ServiceModel.Description.TransactedBatchingBehavior> davranışı.</span><span class="sxs-lookup"><span data-stu-id="144e5-123">A property of the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> behavior.</span></span> <span data-ttu-id="144e5-124">Bu özellik toplu yerleştirilir iletilerin sayısını belirler.</span><span class="sxs-lookup"><span data-stu-id="144e5-124">This property determines the maximum number of messages that are placed into a batch.</span></span> <span data-ttu-id="144e5-125">Bu sayıya ulaşıldığında, toplu taahhüt eder.</span><span class="sxs-lookup"><span data-stu-id="144e5-125">When this number is reached, the batch is committed.</span></span> <span data-ttu-id="144e5-126">Bu değer katı bir sınır değil, bu ileti sayısı almadan önce bir toplu iş yürütme mümkündür.</span><span class="sxs-lookup"><span data-stu-id="144e5-126">This is value is not a strict limit, it is possible to commit a batch before receiving this number of messages.</span></span>  
  
-   <span data-ttu-id="144e5-127">`Transaction Timeout`.</span><span class="sxs-lookup"><span data-stu-id="144e5-127">`Transaction Timeout`.</span></span> <span data-ttu-id="144e5-128">Yüzde 80'işlemdeki zaman aşımı geçtikten sonra toplu taahhüt eder ve yeni bir toplu işi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="144e5-128">After 80 percent of the transaction's time-out has elapsed, the batch is committed and a new batch is created.</span></span> <span data-ttu-id="144e5-129">Bu, yüzde 20 anlamına gelir veya bir işlem için verilen süreyi daha az korunur, toplu taahhüt eder.</span><span class="sxs-lookup"><span data-stu-id="144e5-129">This means that if 20 percent or less of the time given for a transaction to complete remains, the batch is committed.</span></span>  
  
-   <span data-ttu-id="144e5-130">`TransactionScopeRequired`.</span><span class="sxs-lookup"><span data-stu-id="144e5-130">`TransactionScopeRequired`.</span></span> <span data-ttu-id="144e5-131">Toplu iletiler, varsa işlerken [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sahip bir tane bulana `TransactionScopeRequired`  =  `false`, toplu işi tamamlar ve yeni bir toplu işi ile ilk iletinin alınması, üzerinde açana `TransactionScopeRequired`  =  `true` ve `TransactionAutoComplete` = `true`.</span><span class="sxs-lookup"><span data-stu-id="144e5-131">When processing a batch of messages, if [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] finds one that has `TransactionScopeRequired` = `false`, it commits the batch and reopens a new batch on receipt of the first message with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true`.</span></span>  
  
-   <span data-ttu-id="144e5-132">Sırada başka ileti mevcut sonra geçerli toplu işlem kararlıdır olsa bile `MaxBatchSize` ulaşılana veya yüzde 80'işlemdeki zaman aşımı geçtikten değil.</span><span class="sxs-lookup"><span data-stu-id="144e5-132">If no more messages exist in the queue, then the current batch is committed, even if the `MaxBatchSize` has not been reached or 80 percent of the transaction's time-out has not elapsed.</span></span>  
  
## <a name="leaving-batching-mode"></a><span data-ttu-id="144e5-133">Toplu işleme modunu bırakarak</span><span class="sxs-lookup"><span data-stu-id="144e5-133">Leaving Batching Mode</span></span>  
 <span data-ttu-id="144e5-134">Bir ileti bir toplu işlemin iptal etmek neden olursa, aşağıdaki adımlardan oluşur:</span><span class="sxs-lookup"><span data-stu-id="144e5-134">If a message in a batch causes the transaction to abort, the following steps occur:</span></span>  
  
1.  <span data-ttu-id="144e5-135">Toplu işin tamamını iletilerinin geri alınır.</span><span class="sxs-lookup"><span data-stu-id="144e5-135">The entire batch of messages is rolled back.</span></span>  
  
2.  <span data-ttu-id="144e5-136">İleti iki kez Maksimum toplu iş boyutu okuma iletilerin sayısını aşıyor kadar bir kerede salt okunurdur.</span><span class="sxs-lookup"><span data-stu-id="144e5-136">Messages are read one at a time until the number of messages read exceeds twice the maximum batch size.</span></span>  
  
3.  <span data-ttu-id="144e5-137">Toplu iş modunda yeniden girilen ' dir.</span><span class="sxs-lookup"><span data-stu-id="144e5-137">Batch mode is re-entered.</span></span>  
  
## <a name="choosing-the-batch-size"></a><span data-ttu-id="144e5-138">Toplu iş boyutu seçme</span><span class="sxs-lookup"><span data-stu-id="144e5-138">Choosing the Batch Size</span></span>  
 <span data-ttu-id="144e5-139">Bir toplu iş boyutu uygulama bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="144e5-139">The size of a batch is application-dependent.</span></span> <span data-ttu-id="144e5-140">Ampirik yöntemi, bir uygulama için en iyi toplu boyutta ulaşması için en iyi yoludur.</span><span class="sxs-lookup"><span data-stu-id="144e5-140">The empirical method is the best way to arrive at an optimal batch size for the application.</span></span> <span data-ttu-id="144e5-141">Uygulamanızın gerçek dağıtım modeli göre boyutu seçmek için bir toplu iş boyutu seçerken unutmamak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="144e5-141">It is important to remember when choosing a batch size to choose the size according to your application's actual deployment model.</span></span> <span data-ttu-id="144e5-142">Örneğin, uzak makine ve sıra yayılan bir işlem üzerinde bir SQL server ve SQL server gerekiyorsa Uygulama dağıtırken, ardından toplu iş boyutu en iyi tam bu yapılandırma çalışan tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="144e5-142">For example, when deploying the application, if you need an SQL server on a remote machine and a transaction that spans the queue and the SQL server, then the batch size is best determined by running this exact configuration.</span></span>  
  
## <a name="concurrency-and-batching"></a><span data-ttu-id="144e5-143">Eşzamanlılık ve toplu işleme</span><span class="sxs-lookup"><span data-stu-id="144e5-143">Concurrency and Batching</span></span>  
 <span data-ttu-id="144e5-144">Verimliliğini artırmak için de aynı anda çalışacak birçok toplu sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-144">To increase throughput, you can also have many batches run concurrently.</span></span> <span data-ttu-id="144e5-145">Ayarlayarak `ConcurrencyMode.Multiple` içinde `ServiceBehaviorAttribute`, eş zamanlı toplu etkinleştirme.</span><span class="sxs-lookup"><span data-stu-id="144e5-145">By setting `ConcurrencyMode.Multiple` in `ServiceBehaviorAttribute`, you enable concurrent batching.</span></span>  
  
 <span data-ttu-id="144e5-146">*Hizmet azaltma* hizmette kaç maksimum eşzamanlı çağrı yapılabilmesi için göstermek için kullanılan bir hizmet davranıştır.</span><span class="sxs-lookup"><span data-stu-id="144e5-146">*Service throttling* is a service behavior that is used to indicate how many maximum concurrent calls can be made on the service.</span></span> <span data-ttu-id="144e5-147">Çok sayıda eş zamanlı toplu çalıştırılabilir nasıl toplu işleme ile kullanıldığında, bu yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="144e5-147">When used with batching, this is interpreted as how many concurrent batches can be run.</span></span> <span data-ttu-id="144e5-148">Azaltma hizmet ayarlanmamışsa [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en fazla eşzamanlı çağrıları 16 Varsayılanları.</span><span class="sxs-lookup"><span data-stu-id="144e5-148">If the service throttling is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] defaults the maximum concurrent calls to 16.</span></span> <span data-ttu-id="144e5-149">Toplu işleme davranışı varsayılan olarak eklendiyse, bu nedenle, en fazla 16 toplu işlemler aynı anda etkin olabilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-149">Thus, if batching behavior were added by default, a maximum of 16 batches can be active at the same time.</span></span> <span data-ttu-id="144e5-150">Azaltma hizmet ayarlamak en iyisidir ve kapasite toplu işleme dayalı.</span><span class="sxs-lookup"><span data-stu-id="144e5-150">It is best to tune the service throttling and batching based on your capacity.</span></span> <span data-ttu-id="144e5-151">İşleme bağlı olarak 16 işlemleri olabileceğinden, etkin, açık toplu işleme olmamasından benzer Örneğin, 100 iletileri kuyruğa varsa ve 20 toplu istenen, 16'ya ayarlanmış maksimum eşzamanlı çağrıları sahip yararlı değil.</span><span class="sxs-lookup"><span data-stu-id="144e5-151">For example, if the queue has 100 messages and a batch of 20 is desired, having the maximum concurrent calls set to 16 is not useful because, depending on throughput, 16 transactions could be active, similar to not having batching turned on.</span></span> <span data-ttu-id="144e5-152">Bu nedenle, performansı için ince ayar olduğunda değil eşzamanlı toplu işleme sahip ya da eş zamanlı doğru hizmet kısıtlama boyutuyla toplu işleme sahip.</span><span class="sxs-lookup"><span data-stu-id="144e5-152">Therefore, when fine-tuning for performance, either do not have concurrent batching or have concurrent batching with the correct service throttle size.</span></span>  
  
## <a name="batching-and-multiple-endpoints"></a><span data-ttu-id="144e5-153">Toplu işleme ve birden çok uç noktaları</span><span class="sxs-lookup"><span data-stu-id="144e5-153">Batching and Multiple Endpoints</span></span>  
 <span data-ttu-id="144e5-154">Bir uç nokta bir adresi ve bir sözleşme oluşur.</span><span class="sxs-lookup"><span data-stu-id="144e5-154">An endpoint is composed of an address and a contract.</span></span> <span data-ttu-id="144e5-155">Aynı bağlama paylaşan birden çok uç nokta olabilir.</span><span class="sxs-lookup"><span data-stu-id="144e5-155">There may be multiple endpoints that share the same binding.</span></span> <span data-ttu-id="144e5-156">Aynı bağlama paylaşma ve Tekdüzen Kaynak Tanımlayıcısı (URI) veya sıra adresini dinlemek iki uç nokta için mümkündür.</span><span class="sxs-lookup"><span data-stu-id="144e5-156">It is possible for two endpoints to share the same binding and listen Uniform Resource Identifier (URI), or queue address.</span></span> <span data-ttu-id="144e5-157">İki uç nokta aynı sıra okunurken ve işlenen ise davranışı toplu işleme, her iki uç noktaları, belirtilen boyutlarını meydana gelebilecek toplu işlemindeki bir çakışma eklenir.</span><span class="sxs-lookup"><span data-stu-id="144e5-157">If two endpoints are reading from the same queue, and transacted batching behavior is added to both endpoints, a conflict in the batch sizes specified could arise.</span></span> <span data-ttu-id="144e5-158">Bu, iki işlenen toplu davranışları arasında belirtilen en düşük toplu iş boyutu kullanarak toplu işleme uygulayarak çözümlenir.</span><span class="sxs-lookup"><span data-stu-id="144e5-158">This is resolved by implementing batching using the minimal batch size specified between the two transacted batching behaviors.</span></span> <span data-ttu-id="144e5-159">Uç noktalardan biri işlenen toplu işleme, belirtmiyor Bu senaryoda, ardından her iki uç noktaları toplu işleme kullanmamanız.</span><span class="sxs-lookup"><span data-stu-id="144e5-159">In this scenario, if one of the endpoints does not specify transacted batching, then both endpoints would not use batching.</span></span>  
  
## <a name="example"></a><span data-ttu-id="144e5-160">Örnek</span><span class="sxs-lookup"><span data-stu-id="144e5-160">Example</span></span>  
 <span data-ttu-id="144e5-161">Aşağıdaki örnekte nasıl belirtileceğini gösterir `TransactedBatchingBehavior` bir yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="144e5-161">The following example shows how to specify the `TransactedBatchingBehavior` in a configuration file.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 <span data-ttu-id="144e5-162">Aşağıdaki örnekte nasıl belirtileceğini gösterir <xref:System.ServiceModel.Description.TransactedBatchingBehavior> kod.</span><span class="sxs-lookup"><span data-stu-id="144e5-162">The following example shows how to specify the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> in code.</span></span>  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));
     
     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="144e5-163">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="144e5-163">See Also</span></span>  
 [<span data-ttu-id="144e5-164">Kuyruklar genel bakış</span><span class="sxs-lookup"><span data-stu-id="144e5-164">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="144e5-165">WCF'de kuyruğa alma</span><span class="sxs-lookup"><span data-stu-id="144e5-165">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)