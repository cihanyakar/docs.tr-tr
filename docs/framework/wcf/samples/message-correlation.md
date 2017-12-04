---
title: "İleti Bağıntısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef105626d2427f0ea6dd49f696b78ffac4834f92
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="message-correlation"></a><span data-ttu-id="fa5ad-102">İleti Bağıntısı</span><span class="sxs-lookup"><span data-stu-id="fa5ad-102">Message Correlation</span></span>
<span data-ttu-id="fa5ad-103">Bu örnek bir Message Queuing (MSMQ) uygulaması bir MSMQ iletisi nasıl gönderebilirsiniz gösteren bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] hizmeti ve nasıl iletileri bir istek/yanıt senaryosunda göndereni ve alıcısı uygulamalar arasında ilişkili olabilir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="fa5ad-104">Bu örnek MsmqIntegrationBinding bağlama kullanır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="fa5ad-105">Bu durumda, alan hizmetini sıraya alınan iletileri gözlemleyin olanak tanımak için bir kendi kendini barındıran konsol uygulaması hizmetidir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="fa5ad-106">K</span><span class="sxs-lookup"><span data-stu-id="fa5ad-106">k</span></span>  
  
 <span data-ttu-id="fa5ad-107">Hizmet gönderenden alınan ileti işler ve gönderene bir yanıt iletisi gönderir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="fa5ad-108">Gönderenin karşılık gelen yanıtı başlangıçta gönderilen isteği alındı.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="fa5ad-109">`MessageID` Ve `CorrelationID` ileti özelliklerini istek ve yanıt iletileri ilişkilendirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>  
  
 <span data-ttu-id="fa5ad-110">`IOrderProcessor` Hizmet sözleşmesini tanımlayan queuing ile kullanım için uygun bir tek yönlü hizmet işlemi.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="fa5ad-111">Farklı MSMQ iletileri işlemi sözleşmeleri için otomatik olarak eşlemeye mümkün değildir bir MSMQ iletisinin bir eylem üstbilgisi yok.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="fa5ad-112">Bu nedenle, olabilir yalnızca bir işlem sözleşmesi bu durumda.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="fa5ad-113">Tanımlamak istiyorsanız daha fazla işlem hizmetinde sözleşmeler, uygulamanın hangi MSMQ üstbilgisinde (örneğin, etiket veya correlationıd değeri) ileti gönderme işlemi sözleşmeyi karar vermek için kullanılabilir bilgileri sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span> <span data-ttu-id="fa5ad-114">Bu, gösterilmiştir [özel Demux](../../../../docs/framework/wcf/samples/custom-demux.md).</span><span class="sxs-lookup"><span data-stu-id="fa5ad-114">This is demonstrated in the [Custom Demux](../../../../docs/framework/wcf/samples/custom-demux.md).</span></span>  
  
 <span data-ttu-id="fa5ad-115">MSMQ iletisi aldığını üstbilgileri işlemi sözleşme farklı parametreler için eşlenen bilgileri de içermiyor.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-115">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="fa5ad-116">Bu nedenle, işlem sözleşmede yalnızca bir parametre olabilir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-116">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="fa5ad-117">Parametre türünde <!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`--> , `System.ServiceModel.MSMQIntegration.MsmqMessage` temel alınan MSMQ iletisi içerir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-117">The parameter is of type <!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`--> , `System.ServiceModel.MSMQIntegration.MsmqMessage` which contains the underlying MSMQ message.</span></span> <span data-ttu-id="fa5ad-118">Türünde "T" `MsmqMessage<T>` sınıf MSMQ İleti gövdesi seri verileri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-118">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="fa5ad-119">Bu örnekte `PurchaseOrder` türü MSMQ İleti gövdesi seri.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-119">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
```  
  
 <span data-ttu-id="fa5ad-120">Hizmet işlemini satın alma siparişi işler ve satın alma siparişi ve durumunu içeriğini hizmet konsol penceresinde görüntüler.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-120">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="fa5ad-121"><xref:System.ServiceModel.OperationBehaviorAttribute> İşlemi sıranın ile bir işlemde listeleme veya işlemi döndürdüğünde işlem tamamlandı olarak işaretlemek için yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-121">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="fa5ad-122">`PurchaseOrder` Hizmeti tarafından işlenmesi gereken sipariş ayrıntılarını içerir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-122">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>  
  
```  
// Service class that implements the service contract.  
public class OrderProcessorService : IOrderProcessor  
{  
   [OperationBehavior(TransactionScopeRequired = true,   
          TransactionAutoComplete = true)]  
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)  
   {  
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;  
       Random statusIndexer = new Random();  
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
       Console.WriteLine("Processing {0} ", po);  
       //Send a response to the client that the order has been received   
         and is pending fullfillment.   
       SendResponse(ordermsg);  
    }  
  
    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)  
    {  
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");  
  
        //Set the correlation ID such that the client can correlate the response to the order.  
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);  
        orderResponsemsg.CorrelationId = ordermsg.Id;  
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
        {  
            client.SendOrderResponse(orderResponsemsg);  
            scope.Complete();  
        }  
  
        client.Close();  
    }  
}  
```  
  
 <span data-ttu-id="fa5ad-123">Özel bir istemci hizmetin kullandığı `OrderResponseClient` MSMQ ileti kuyruğuna göndermek için.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-123">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="fa5ad-124">Alan ve iletiyi işleyen bir uygulama bir MSMQ uygulaması olduğundan ve bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulama, iki uygulama hiçbir örtük hizmet sözleşmesini yoktur.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-124">Because the application that receives and processes the message is an MSMQ application and not a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="fa5ad-125">Bu senaryoda Svcutil.exe aracını kullanarak bir proxy şekilde oluşturamıyoruz.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-125">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>  
  
 <span data-ttu-id="fa5ad-126">Özel proxy temelde tüm aynıdır [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kullanan uygulamalar `msmqIntegrationBinding` iletileri göndermek için bağlama.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-126">The custom proxy is essentially the same for all [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="fa5ad-127">Diğer proxy'leri, bir dizi hizmet işlemleri içermeyecek.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-127">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="fa5ad-128">Bir Gönder ileti yalnızca işlemdir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-128">It is a submit message operation only.</span></span>  
  
```  
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderResponse  
{  
  
    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]  
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse  
{  
  
    public OrderResponseClient()  
    { }  
  
    public OrderResponseClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SendOrderResponse(msg);  
    }  
}  
```  
  
 <span data-ttu-id="fa5ad-129">Kendi kendini barındırılan hizmetidir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-129">The service is self hosted.</span></span> <span data-ttu-id="fa5ad-130">MSMQ tümleştirme taşıma kullanırken, sıranın kullanılan önceden oluşturulmuş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-130">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="fa5ad-131">Bu, el ile veya kod aracılığıyla yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-131">This can be done manually or through code.</span></span> <span data-ttu-id="fa5ad-132">Bu örnekte, hizmeti içeren <xref:System.Messaging> kod sıranın varlığını denetlemek ve gerekirse oluşturun.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-132">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="fa5ad-133">Kuyruk adı yapılandırma dosyasından okunur.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-133">The queue name is read from the configuration file.</span></span>  
  
```  
public static void Main()  
{  
       // Get the MSMQ queue name from application settings in configuration.  
      string queueName =   
                ConfigurationManager.AppSettings["orderQueueName"];  
      // Create the transacted MSMQ queue if necessary.  
      if (!MessageQueue.Exists(queueName))  
                MessageQueue.Create(queueName, true);  
     // Create a ServiceHost for the OrderProcessorService type.  
     using (ServiceHost serviceHost = new   
                   ServiceHost(typeof(OrderProcessorService)))  
     {  
            serviceHost.Open();  
            // The service can now be accessed.  
            Console.WriteLine("The service is ready.");  
            Console.WriteLine("Press <ENTER> to terminate service.");  
            Console.ReadLine();  
            // Close the ServiceHost to shutdown the service.  
            serviceHost.Close();  
      }  
}  
```  
  
 <span data-ttu-id="fa5ad-134">Sipariş isteklerinin gönderilme MSMQ sırası yapılandırma dosyasının appSettings bölümünde belirtilir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-134">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="fa5ad-135">İstemci ve hizmet uç noktaları yapılandırma dosyası system.serviceModel bölümünde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-135">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="fa5ad-136">Her ikisini de belirtin `msmqIntegrationbinding` bağlama.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-136">Both specify the `msmqIntegrationbinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
<system.serviceModel>  
  <client>  
    <endpoint    name="OrderResponseEndpoint"   
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"  
              binding="msmqIntegrationBinding"  
              bindingConfiguration="OrderProcessorBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">  
    </endpoint>  
  </client>  
  
  <services>  
    <service   
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"  
                            binding="msmqIntegrationBinding"  
                bindingConfiguration="OrderProcessorBinding"   
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">  
      </endpoint>  
    </service>  
  </services>  
  
  <bindings>  
    <msmqIntegrationBinding>  
      <binding name="OrderProcessorBinding" >  
        <security mode="None" />  
      </binding>  
    </msmqIntegrationBinding>  
  </bindings>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="fa5ad-137">İstemci uygulaması kullanan <xref:System.Messaging> dayanıklı ve işlemsel ileti kuyruğuna göndermek için.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-137">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="fa5ad-138">İleti gövdesi satın alma siparişi içerir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-138">The message's body contains the purchase order.</span></span>  
  
```  
static void PlaceOrder()  
{  
    //Connect to the queue  
    MessageQueue orderQueue =   
            new MessageQueue(  
                    ConfigurationManager.AppSettings["orderQueueName"])   
    // Create the purchase order.  
    PurchaseOrder po = new PurchaseOrder();  
    po.CustomerId = "somecustomer.com";  
    po.PONumber = Guid.NewGuid().ToString();  
    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
    lineItem1.ProductId = "Blue Widget";  
    lineItem1.Quantity = 54;  
    lineItem1.UnitCost = 29.99F;  
  
    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
    lineItem2.ProductId = "Red Widget";  
    lineItem2.Quantity = 890;  
    lineItem2.UnitCost = 45.89F;  
  
    po.orderLineItems = new PurchaseOrderLineItem[2];  
    po.orderLineItems[0] = lineItem1;  
    po.orderLineItems[1] = lineItem2;  
  
    Message msg = new Message();  
    msg.UseDeadLetterQueue = true;  
    msg.Body = po;  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new      
     TransactionScope(TransactionScopeOption.Required))  
    {  
        // Submit the purchase order.  
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);  
        // Complete the transaction.  
        scope.Complete();  
    }  
    //Save the messageID for order response correlation.  
    orderMessageID = msg.Id;  
    Console.WriteLine("Placed the order, waiting for response...");  
}  
```  
  
 <span data-ttu-id="fa5ad-139">Sırası yanıtlarını alındığı MSMQ sırası, aşağıdaki örnek yapılandırmada gösterildiği gibi bir yapılandırma dosyasının appSettings bölümünde belirtilir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-139">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa5ad-140">Kuyruk adı, ters eğik çizgi ayırıcıları yolundaki ve yerel bilgisayar için bir nokta (.) kullanır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-140">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="fa5ad-141">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Uç noktası adresi msmq.formatname düzeni belirtir ve yerel bilgisayar için "localhost" kullanır.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-141">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="fa5ad-142">Doğru oluşturulmamış biçim adı MSMQ yönergelerine göre URI msmq.formatname izler.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-142">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>  
  
```xml  
<appSettings>  
    <add key=" orderResponseQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
 <span data-ttu-id="fa5ad-143">İstemci uygulama kaydeder `messageID` sipariş istek iletisinin hizmetine gönderir ve hizmetinden bir yanıt bekler.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-143">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="fa5ad-144">Bir yanıt sırada geldikten sonra istemci, gönderilen kullanarak sipariş iletiyle karşılık gelen `correlationID` içeren iletinin özelliği `messageID` sırasını ileti hizmete ilk olarak gönderilen istemci.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-144">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>  
  
```  
static void DisplayOrderStatus()  
{  
    MessageQueue orderResponseQueue = new   
     MessageQueue(ConfigurationManager.AppSettings              
                  ["orderResponseQueueName"]);  
    //Create a transaction scope.  
    bool responseReceived = false;  
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;  
    while (!responseReceived)  
    {  
       Message responseMsg;  
       using (TransactionScope scope2 = new    
         TransactionScope(TransactionScopeOption.Required))  
       {  
          //Receive the Order Response message.  
          responseMsg =   
              orderResponseQueue.Receive  
                   (MessageQueueTransactionType.Automatic);  
          scope2.Complete();  
     }  
     responseMsg.Formatter = new   
     System.Messaging.XmlMessageFormatter(new Type[] {   
         typeof(PurchaseOrder) });  
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;  
    //Check if the response is for the order placed.  
    if (orderMessageID == responseMsg.CorrelationId)  
    {  
       responseReceived = true;  
       Console.WriteLine("Status of current Order: OrderID-{0},Order   
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
    else  
    {  
       Console.WriteLine("Status of previous Order: OrderID-{0},Order    
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
  }  
}  
```  
  
 <span data-ttu-id="fa5ad-145">Örneği çalıştırdığınızda, istemci ve hizmet etkinlikleri hem hizmet hem de istemci konsol pencerelerinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-145">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="fa5ad-146">Bir yanıt istemciye geri hizmeti alma iletileri gönderir ve istemci görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-146">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="fa5ad-147">İstemci hizmetinden alınan yanıtta görüntüler.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-147">The client displays the response received from the service.</span></span> <span data-ttu-id="fa5ad-148">Her konsol penceresinde hizmet ve istemci kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa5ad-149">Bu örnek, Message Queuing (MSMQ), yükleme gerektirir.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-149">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="fa5ad-150">Ayrıca Bkz bölümündeki MSMQ yükleme yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-150">See the MSMQ installation instructions in the See Also section.</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="fa5ad-151">Kurulum, yapı ve örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="fa5ad-151">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fa5ad-152">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa5ad-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fa5ad-153">Hizmetin ilk olarak çalışıyorsa, sıranın var olduğundan emin olmak için kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-153">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="fa5ad-154">Hizmet sırası mevcut değilse oluşturur.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-154">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="fa5ad-155">İlk sırayı oluşturmak için hizmet çalıştırabilirsiniz veya bir MSMQ sıra Yöneticisi aracılığıyla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-155">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="fa5ad-156">Windows 2008'de bir kuyruk oluşturmak için aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-156">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="fa5ad-157">Sunucu Yöneticisi'nde açın [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa5ad-157">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="fa5ad-158">Genişletme **özellikleri** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-158">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="fa5ad-159">Sağ **özel ileti kuyrukları**seçip **yeni**, **özel sıra**.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-159">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="fa5ad-160">Denetleme **işlem** kutusu.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-160">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="fa5ad-161">Girin `ServiceModelSamplesTransacted` yeni kuyruk adından farklı.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-161">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="fa5ad-162">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa5ad-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="fa5ad-163">Tek bilgisayarlı yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa5ad-163">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="fa5ad-164">Bilgisayarlar arasında örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="fa5ad-164">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="fa5ad-165">Hizmet program dosyalarını dile özgü klasörü altındaki \service\bin\ klasöründen hizmet bilgisayara kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-165">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="fa5ad-166">İstemci program dosyaları \client\bin\ klasöründen dile özgü klasörü altında istemci bilgisayara kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-166">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="fa5ad-167">Hizmet bilgisayar adı yerine belirtmek için orderQueueName Client.exe.config dosyasında değiştirmek ".".</span><span class="sxs-lookup"><span data-stu-id="fa5ad-167">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="fa5ad-168">Service.exe.config dosyasında yerine istemci bilgisayarın adını belirtmek için istemci uç noktası adresi değiştirmek ".".</span><span class="sxs-lookup"><span data-stu-id="fa5ad-168">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>  
  
5.  <span data-ttu-id="fa5ad-169">Hizmet bilgisayarda bir komut isteminden Service.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-169">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
6.  <span data-ttu-id="fa5ad-170">İstemci bilgisayarda bir komut isteminden Client.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-170">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa5ad-171">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-171">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fa5ad-172">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fa5ad-173">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fa5ad-174">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`  
  
## <a name="see-also"></a><span data-ttu-id="fa5ad-175">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fa5ad-175">See Also</span></span>  
 [<span data-ttu-id="fa5ad-176">WCF'de kuyruğa alma</span><span class="sxs-lookup"><span data-stu-id="fa5ad-176">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="fa5ad-177">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="fa5ad-177">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=94968)