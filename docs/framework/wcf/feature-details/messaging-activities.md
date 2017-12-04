---
title: "Mesajlaşma Etkinlikleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c08d57f36d733312793ab9de1699b83a1e22ce31
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="messaging-activities"></a><span data-ttu-id="c556e-102">Mesajlaşma Etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="c556e-102">Messaging Activities</span></span>
<span data-ttu-id="c556e-103">Mesajlaşma etkinlikleri WCF ileti gönderme ve alma için iş akışlarını izin verir.</span><span class="sxs-lookup"><span data-stu-id="c556e-103">Messaging activities allow workflows to send and receive WCF messages.</span></span> <span data-ttu-id="c556e-104">Bir iş akışına Mesajlaşma etkinlikleri ekleyerek tüm rasgele karmaşık ileti exchange desenleri (MEP) model oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c556e-104">By adding messaging activities to a workflow you can model any arbitrarily complex message exchange patterns (MEP).</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="c556e-105">İleti Exchange desenleri</span><span class="sxs-lookup"><span data-stu-id="c556e-105">Message Exchange Patterns</span></span>  
 <span data-ttu-id="c556e-106">Üç temel ileti exchange desenleri vardır:</span><span class="sxs-lookup"><span data-stu-id="c556e-106">There are three basic message exchange patterns:</span></span>  
  
-   <span data-ttu-id="c556e-107">**Veri birimi** - MEP datagram kullanırken istemci hizmete ileti gönderir, ancak hizmeti yanıt vermiyor.</span><span class="sxs-lookup"><span data-stu-id="c556e-107">**Datagram** - When using the datagram MEP the client sends a message to the service, but the service does not respond.</span></span> <span data-ttu-id="c556e-108">Buna bazen "yangın ve unut" adı verilir.</span><span class="sxs-lookup"><span data-stu-id="c556e-108">This is sometimes called "fire and forget".</span></span> <span data-ttu-id="c556e-109">A yangın ve exchange başarılı teslimat bant dışı onay gerektiren bir tane olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c556e-109">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="c556e-110">İleti, geçiş sırasında kaybolur ve hiçbir zaman hizmete erişmek.</span><span class="sxs-lookup"><span data-stu-id="c556e-110">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="c556e-111">İstemci başarıyla bir ileti gönderir, bu hizmet ileti aldı garanti etmez.</span><span class="sxs-lookup"><span data-stu-id="c556e-111">If the client successfully sends a message, it does not guarantee that the service has received the message.</span></span> <span data-ttu-id="c556e-112">Veri birimi Mesajlaşma için temel yapı bloğu aynıdır, üzerinde kendi MEPs oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c556e-112">The datagram is a fundamental building block for messaging, as you can build your own MEPs on top of it.</span></span>  
  
-   <span data-ttu-id="c556e-113">**İstek-yanıt** - istek-yanıt MEP istemci kullanarak hizmet, hizmet için bir ileti gereken işlem yapar ve sonra gönderir bir yanıt istemciye geri gönderir.</span><span class="sxs-lookup"><span data-stu-id="c556e-113">**Request-Response** - When using the request-response MEP the client sends a message to the service, the service does the required processing, and then sends a response back to the client.</span></span> <span data-ttu-id="c556e-114">Desen istek-yanıt çiftlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c556e-114">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="c556e-115">İstek-yanıt çağrıları örnekler uzaktan yordam çağrısı (RPC) ve tarayıcı GET istekleri.</span><span class="sxs-lookup"><span data-stu-id="c556e-115">Examples of request-response calls are remote procedure calls (RPC) and browser GET requests.</span></span> <span data-ttu-id="c556e-116">Bu desen yarı çift yönlü da bilinir.</span><span class="sxs-lookup"><span data-stu-id="c556e-116">This pattern is also known as half-duplex.</span></span>  
  
-   <span data-ttu-id="c556e-117">**Çift yönlü** - çift yönlü MEP istemci ve hizmet kullanarak iletileri göndermek için herhangi bir sırada gönderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c556e-117">**Duplex** - When using the duplex MEP the client and service can send messages to each other in any order.</span></span> <span data-ttu-id="c556e-118">Çift yönlü MEP bir telefon konuşması gibi konuşulan her sözcüğün bir ileti olduğu.</span><span class="sxs-lookup"><span data-stu-id="c556e-118">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span>  
  
 <span data-ttu-id="c556e-119">Mesajlaşma etkinlikleri, bu temel MEPs hiçbirini yanı sıra rasgele karmaşık herhangi MEP uygulamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="c556e-119">The messaging activities allow you to implement any of these basic MEPs as well as any arbitrarily complex MEP.</span></span>  
  
## <a name="messaging-activities"></a><span data-ttu-id="c556e-120">Mesajlaşma Etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="c556e-120">Messaging Activities</span></span>  
 <span data-ttu-id="c556e-121">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Aşağıdaki Mesajlaşma etkinlikleri tanımlar:</span><span class="sxs-lookup"><span data-stu-id="c556e-121">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] defines the following messaging activities:</span></span>  
  
-   <span data-ttu-id="c556e-122"><xref:System.ServiceModel.Activities.Send>-Kullanın <xref:System.ServiceModel.Activities.Send> bir ileti göndermek için etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-122"><xref:System.ServiceModel.Activities.Send>- Use the <xref:System.ServiceModel.Activities.Send> activity to send a message.</span></span>  
  
-   <span data-ttu-id="c556e-123"><xref:System.ServiceModel.Activities.SendReply>-Kullanın <xref:System.ServiceModel.Activities.SendReply> yanıt alınan ileti gönder etkinliği.</span><span class="sxs-lookup"><span data-stu-id="c556e-123"><xref:System.ServiceModel.Activities.SendReply> - Use the <xref:System.ServiceModel.Activities.SendReply> activity to send a response to a received message.</span></span> <span data-ttu-id="c556e-124">Bu etkinlik bir istek/yanıt MEP uygulama iş akışı hizmetleri tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c556e-124">This activity is used by workflow services when implementing a request/reply MEP.</span></span>  
  
-   <span data-ttu-id="c556e-125"><xref:System.ServiceModel.Activities.Receive>-Kullanın <xref:System.ServiceModel.Activities.Receive> etkinliği bir ileti alırsınız.</span><span class="sxs-lookup"><span data-stu-id="c556e-125"><xref:System.ServiceModel.Activities.Receive>- Use the <xref:System.ServiceModel.Activities.Receive> activity to receive a message.</span></span>  
  
-   <span data-ttu-id="c556e-126"><xref:System.ServiceModel.Activities.ReceiveReply>-Kullanın <xref:System.ServiceModel.Activities.ReceiveReply> etkinliği bir yanıt iletisi alırsınız.</span><span class="sxs-lookup"><span data-stu-id="c556e-126"><xref:System.ServiceModel.Activities.ReceiveReply> - Use the <xref:System.ServiceModel.Activities.ReceiveReply> activity to receive a reply message.</span></span> <span data-ttu-id="c556e-127">Bu etkinlik bir istek/yanıt MEP uygularken iş akışı hizmeti istemciler tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c556e-127">This activity is used by workflow service clients when implementing a request/reply MEP.</span></span>  
  
## <a name="messaging-activities-and-message-exchange-patterns"></a><span data-ttu-id="c556e-128">Mesajlaşma etkinlikleri ve ileti Exchange desenleri</span><span class="sxs-lookup"><span data-stu-id="c556e-128">Messaging Activities and Message Exchange Patterns</span></span>  
 <span data-ttu-id="c556e-129">Veri birimi MEP bir ileti ve iletiyi alan bir hizmet gönderme bir istemcinin içerir.</span><span class="sxs-lookup"><span data-stu-id="c556e-129">A datagram MEP involves a client sending a message and a service receiving the message.</span></span> <span data-ttu-id="c556e-130">İstemci bir iş akışı kullanımı ise bir <xref:System.ServiceModel.Activities.Send> ileti göndermek için etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-130">If the client is a workflow use a <xref:System.ServiceModel.Activities.Send> activity to send the message.</span></span> <span data-ttu-id="c556e-131">Bu ileti bir iş akışında almak için kullandığınız bir <xref:System.ServiceModel.Activities.Receive> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-131">To receive that message in a workflow, use a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="c556e-132"><xref:System.ServiceModel.Activities.Send> Ve <xref:System.ServiceModel.Activities.Receive> etkinlikleri her adlı bir özellik olması `Content`.</span><span class="sxs-lookup"><span data-stu-id="c556e-132">The <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> activities each have a property named `Content`.</span></span> <span data-ttu-id="c556e-133">Bu özellik gönderilen veya alınan verileri içerir.</span><span class="sxs-lookup"><span data-stu-id="c556e-133">This property contains the data being sent or received.</span></span> <span data-ttu-id="c556e-134">İstek-yanıt MEP uygularken hem istemci hem de hizmet etkinliklerin çiftlerini kullanır.</span><span class="sxs-lookup"><span data-stu-id="c556e-134">When implementing the request-response MEP both the client and the service use pairs of activities.</span></span> <span data-ttu-id="c556e-135">İstemcinin kullandığı bir <xref:System.ServiceModel.Activities.Send> ileti göndermek için etkinliği ve bir <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik Hizmeti'nden yanıtı alırsınız.</span><span class="sxs-lookup"><span data-stu-id="c556e-135">The client uses a <xref:System.ServiceModel.Activities.Send> activity to send the message and a <xref:System.ServiceModel.Activities.ReceiveReply> activity to receive the response from the service.</span></span> <span data-ttu-id="c556e-136">Bu iki etkinlikleri birbirine göre ilişkili <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="c556e-136">These two activities are associated with each other by the <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> property.</span></span> <span data-ttu-id="c556e-137">Bu özelliği ayarlamak <xref:System.ServiceModel.Activities.Send> özgün ileti gönderilen etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-137">This property is set to the <xref:System.ServiceModel.Activities.Send> activity that sent the original message.</span></span> <span data-ttu-id="c556e-138">Hizmet Ayrıca ilişkili etkinlikleri çifti kullanır: <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="c556e-138">The service also uses a pair of associated activities: <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>.</span></span> <span data-ttu-id="c556e-139">Bu iki etkinlik tarafından ilişkili <xref:System.ServiceModel.Activities.SendReply.Request%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="c556e-139">These two activities are associated by the <xref:System.ServiceModel.Activities.SendReply.Request%2A> property.</span></span> <span data-ttu-id="c556e-140">Bu özelliği ayarlamak <xref:System.ServiceModel.Activities.Receive> özgün iletisi aldı etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-140">This property is set to the <xref:System.ServiceModel.Activities.Receive> activity that received the original message.</span></span> <span data-ttu-id="c556e-141"><xref:System.ServiceModel.Activities.ReceiveReply> Ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri, ister <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.Receive> göndermenize izin bir <xref:System.ServiceModel.Channels.Message> örneği veya sözleşme türü bir ileti.</span><span class="sxs-lookup"><span data-stu-id="c556e-141">The <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities, like <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> allow you to send a <xref:System.ServiceModel.Channels.Message> instance or a message contract type.</span></span>  
  
 <span data-ttu-id="c556e-142">İş akışı uzun süre çalışan yapısı nedeniyle, uzun süre çalışan görüşmeleri de desteklemek için iletişim çift yönlü düzeni için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="c556e-142">Because of the long-running nature of workflows, it is important for the duplex pattern of communication to also support long-running conversations.</span></span> <span data-ttu-id="c556e-143">Uzun süre çalışan görüşmeleri desteklemek için konuşma başlatmak istemciler hizmet veriler kullanılabilir duruma geldiğinde, daha sonraki bir zamanda geri arama fırsatına sahip sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="c556e-143">To support long-running conversations, clients who initiate the conversation must provide the service with an opportunity to call it back at a later time when the data becomes available.</span></span> <span data-ttu-id="c556e-144">Örneğin, bir satın alma siparişi isteği için yönetici onayı gönderildi ancak, bir gün, haftada bir ya da bile bir yıl için işlenmedi; satın alma siparişi onayı yönetir iş akışı onayı verilen sonra devam etmek için bilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="c556e-144">For example, a purchase order request is submitted for manager approval, but it might not be processed for a day, a week, or even a year; the workflow that manages the purchase order approval must know to resume after the approval is given.</span></span> <span data-ttu-id="c556e-145">Bu deseni çift yönlü iletişim bağıntı kullanarak iş akışlarında desteklenir.</span><span class="sxs-lookup"><span data-stu-id="c556e-145">This pattern of duplex communication is supported in workflows using correlation.</span></span> <span data-ttu-id="c556e-146">Çift yönlü bir desen uygulamak için kullandığınız <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.Receive> etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="c556e-146">To implement a duplex pattern, use <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="c556e-147">Üzerinde <xref:System.ServiceModel.Activities.Receive> etkinlik, bir özel anahtar değeri kullanılarak bağıntı Initialize <!--zz <xref:System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName%2A>--> `System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName`.</span><span class="sxs-lookup"><span data-stu-id="c556e-147">On the <xref:System.ServiceModel.Activities.Receive> activity, initialize a correlation using the special key value of <!--zz <xref:System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName%2A>-->`System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName`.</span></span> <span data-ttu-id="c556e-148">Üzerinde <xref:System.ServiceModel.Activities.Send> etkinliği o bağıntı tanıtıcının olarak ayarlandı <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> özellik değeri.</span><span class="sxs-lookup"><span data-stu-id="c556e-148">On the <xref:System.ServiceModel.Activities.Send> activity set that correlation handle as the <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> property value.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c556e-149">[Dayanıklı çift yönlü](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="c556e-149"> [Durable Duplex](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c556e-150">Çift yönlü bir geri çağırma bağıntı ("dayanıklı çift yönlü") kullanarak iş akışının uyarlamasını uzun süre çalışan görüşmeleri için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="c556e-150">Workflow’s implementation of duplex using a callback correlation ("Durable Duplex") is intended for long-running conversations.</span></span> <span data-ttu-id="c556e-151">Bu geri çağırma Sözleşmelerle çift yönlü WCF ile aynı olduğu konuşma kısa (kanal ömrü) çalışan olduğu değildir.</span><span class="sxs-lookup"><span data-stu-id="c556e-151">This is not the same as WCF duplex with callback contracts where the conversation is short-running (the lifetime of the channel).</span></span>  
  
## <a name="message-formatting-and-messaging-activities"></a><span data-ttu-id="c556e-152">İleti biçimlendirme ve mesajlaşma etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="c556e-152">Message Formatting and Messaging Activities</span></span>  
 <span data-ttu-id="c556e-153"><xref:System.ServiceModel.Activities.Receive> Ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikleri adlı bir özellik olması `Content`.</span><span class="sxs-lookup"><span data-stu-id="c556e-153">The <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.ReceiveReply> activities have a property named `Content`.</span></span> <span data-ttu-id="c556e-154">Bu özellik türünde <xref:System.ServiceModel.Activities.ReceiveContent> ve verileri temsil <xref:System.ServiceModel.Activities.Receive> veya <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik alır.</span><span class="sxs-lookup"><span data-stu-id="c556e-154">This property is of type <xref:System.ServiceModel.Activities.ReceiveContent> and represents data the <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.ReceiveReply> activity receives.</span></span> <span data-ttu-id="c556e-155">.NET Framework adlı iki ilişkili sınıfları tanımlar <xref:System.ServiceModel.Activities.ReceiveMessageContent> ve <xref:System.ServiceModel.Activities.ReceiveParametersContent> her ikisi de türetilmiş <xref:System.ServiceModel.Activities.ReceiveContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-155">The .NET Framework defines two related classes called <xref:System.ServiceModel.Activities.ReceiveMessageContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> both of which are derived from <xref:System.ServiceModel.Activities.ReceiveContent>.</span></span> <span data-ttu-id="c556e-156">Ayarlama <xref:System.ServiceModel.Activities.Receive> veya <xref:System.ServiceModel.Activities.ReceiveReply> etkinliğin `Content` özelliği bir iş akışı hizmetinde veri almak için şu türlerden birine örneği.</span><span class="sxs-lookup"><span data-stu-id="c556e-156">Set the <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.ReceiveReply> activity’s `Content` property to an instance of one of these types to receive data into a workflow service.</span></span> <span data-ttu-id="c556e-157">Kullanılacak türü etkinlik aldığı veri türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="c556e-157">The type to use depends upon the type of data the activity receives.</span></span> <span data-ttu-id="c556e-158">Etkinlik alırsa bir `Message` nesne veya sözleşme türü, kullanan bir ileti <xref:System.ServiceModel.Activities.ReceiveMessageContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-158">If the activity receives a `Message` object or a message contract type, use <xref:System.ServiceModel.Activities.ReceiveMessageContent>.</span></span> <span data-ttu-id="c556e-159">Etkinlik veri sözleşmesi ya da serileştirilebilir XML türleri alırsa, kullanmak <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-159">If the activity receives a set of data contract or XML types that can be serialized, use <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span></span> <span data-ttu-id="c556e-160"><xref:System.ServiceModel.Activities.ReceiveParametersContent>birden çok parametre göndermenize olanak sağlarken <xref:System.ServiceModel.Activities.ReceiveMessageContent> yalnızca gönderme bir nesne, ileti (veya ileti sözleşme türü) sağlar.</span><span class="sxs-lookup"><span data-stu-id="c556e-160"><xref:System.ServiceModel.Activities.ReceiveParametersContent> allows you to send multiple parameters, whereas <xref:System.ServiceModel.Activities.ReceiveMessageContent> only allows you to send one object, the message (or message contract type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c556e-161"><xref:System.ServiceModel.Activities.ReceiveMessageContent>Ayrıca bir tek veri sözleşmesi veya seri hale getirilebilir XML türü ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c556e-161"><xref:System.ServiceModel.Activities.ReceiveMessageContent> can also be used with a single data contract or XML type that can be serialized.</span></span> <span data-ttu-id="c556e-162">Kullanarak arasındaki farkı <xref:System.ServiceModel.Activities.ReceiveParametersContent> tek bir parametre ve doğrudan geçirilen nesnesi ile <xref:System.ServiceModel.Activities.ReceiveMessageContent> kablo biçimi.</span><span class="sxs-lookup"><span data-stu-id="c556e-162">The difference between using <xref:System.ServiceModel.Activities.ReceiveParametersContent> with a single parameter and the object passed directly to <xref:System.ServiceModel.Activities.ReceiveMessageContent> is the wire-format.</span></span> <span data-ttu-id="c556e-163">Parametrenin içeriği işlemi adına karşılık gelen bir XML öğesi paketlenir ve serileştirilmiş nesne bir XML öğesi parametre adı ile sarılır (örneğin, `<Echo><msg>Hello, World</msg></Echo>`).</span><span class="sxs-lookup"><span data-stu-id="c556e-163">The parameter’s content is wrapped in an XML element that corresponds to the operation name and the serialized object is wrapped in an XML element using the parameter name (for example, `<Echo><msg>Hello, World</msg></Echo>`).</span></span> <span data-ttu-id="c556e-164">İleti içeriği, işlem adı tarafından sarmalanmamış.</span><span class="sxs-lookup"><span data-stu-id="c556e-164">The message content is not wrapped by the operation name.</span></span> <span data-ttu-id="c556e-165">Bunun yerine, serileştirilmiş nesne XML nitelenmiş tür adını kullanarak bir XML öğesi içinde yerleştirilir (örneğin, `<string>Hello, World</string>`).</span><span class="sxs-lookup"><span data-stu-id="c556e-165">Instead, the serialized object is placed within an XML element using the XML-qualified type name (for example, `<string>Hello, World</string>`).</span></span>  
  
 <span data-ttu-id="c556e-166"><xref:System.ServiceModel.Activities.Send> Ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri adlı bir özellik de `Content`.</span><span class="sxs-lookup"><span data-stu-id="c556e-166">The <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendReply> activities also have a property named `Content`.</span></span> <span data-ttu-id="c556e-167">Bu özellik türünde <xref:System.ServiceModel.Activities.SendContent> ve verileri temsil <xref:System.ServiceModel.Activities.Send> veya <xref:System.ServiceModel.Activities.SendReply> etkinlik gönderir.</span><span class="sxs-lookup"><span data-stu-id="c556e-167">This property is of type <xref:System.ServiceModel.Activities.SendContent> and represents data the <xref:System.ServiceModel.Activities.Send> or <xref:System.ServiceModel.Activities.SendReply> activity sends.</span></span> <span data-ttu-id="c556e-168">.NET Framework adlı iki ilgili türlerini tanımlar <xref:System.ServiceModel.Activities.SendMessageContent> ve <xref:System.ServiceModel.Activities.SendParametersContent> her ikisi de türetilmiş <xref:System.ServiceModel.Activities.SendContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-168">The .NET Framework defines two related types called <xref:System.ServiceModel.Activities.SendMessageContent> and <xref:System.ServiceModel.Activities.SendParametersContent> both of which are derived from <xref:System.ServiceModel.Activities.SendContent>.</span></span> <span data-ttu-id="c556e-169">Ayarlama <xref:System.ServiceModel.Activities.Send> veya <xref:System.ServiceModel.Activities.SendReply> etkinliğin `Content` özelliği bir iş akışı hizmetinden veri göndermek için şu türlerden birine örneği.</span><span class="sxs-lookup"><span data-stu-id="c556e-169">Set the <xref:System.ServiceModel.Activities.Send> or <xref:System.ServiceModel.Activities.SendReply> activity’s `Content` property to an instance of one of these types to send data from a workflow service.</span></span> <span data-ttu-id="c556e-170">Kullanılacak türü etkinlik gönderdiği veri türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="c556e-170">The type to use depends upon the type of data the activity sends.</span></span> <span data-ttu-id="c556e-171">Etkinlik gönderirse bir `Message` nesne veya sözleşme türü, kullanan bir ileti <xref:System.ServiceModel.Activities.SendMessageContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-171">If the activity sends a `Message` object or a message contract type, use <xref:System.ServiceModel.Activities.SendMessageContent>.</span></span> <span data-ttu-id="c556e-172">Etkinlik bir veri sözleşmesi türü kullanım gönderirse <xref:System.ServiceModel.Activities.SendParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="c556e-172">If the activity sends a data contract type use <xref:System.ServiceModel.Activities.SendParametersContent>.</span></span> <span data-ttu-id="c556e-173"><xref:System.ServiceModel.Activities.SendParametersContent>birden çok parametre göndermenize olanak sağlarken <xref:System.ServiceModel.Activities.SendMessageContent> yalnızca bir nesne, ileti (veya ileti sözleşme türü) göndermenize izin verir.</span><span class="sxs-lookup"><span data-stu-id="c556e-173"><xref:System.ServiceModel.Activities.SendParametersContent> allows you to send multiple parameters, whereas <xref:System.ServiceModel.Activities.SendMessageContent> only allows you to send one object, the message (or the message contract type).</span></span>  
  
 <span data-ttu-id="c556e-174">Mesajlaşma etkinlikleriyle imperatively programlama, genel kullanın <xref:System.Activities.InArgument%601> ve <xref:System.Activities.OutArgument%601> ileti veya parametre özellikleri atadığınız nesneleri sarmalamak için <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive>ve <xref:System.ServiceModel.Activities.ReceiveReply>etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="c556e-174">When programming imperatively with the messaging activities, you use the generic <xref:System.Activities.InArgument%601> and <xref:System.Activities.OutArgument%601> to wrap the objects you assign to the message or parameters properties of the <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span> <span data-ttu-id="c556e-175">Kullanım <xref:System.Activities.InArgument%601> için <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri ve <xref:System.Activities.OutArgument%601> için <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="c556e-175">Use <xref:System.Activities.InArgument%601> for the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendReply> activities and <xref:System.Activities.OutArgument%601> for <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span> <span data-ttu-id="c556e-176">`In`Veri etkinliklerine geçtiğinden bağımsız değişkenleri gönderme etkinlikleri ile kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c556e-176">`In` arguments are used with the send activities because the data is being passed into the activities.</span></span> <span data-ttu-id="c556e-177">`Out`bağımsız değişkenler veri dışında etkinlikleri, aşağıdaki örnekte gösterildiği gibi geçirilmiş alma etkinlikleri ile kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c556e-177">`Out` arguments are used with the receive activities because data is being passed out of the activities, as shown in the following example.</span></span>  
  
```  
Receive reserveSeat = new Receive  
{   
    ...   
    Content = new ReceiveParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationInfo", new OutArgument<ReservationRequest>(reservationInfo) }  
        }  
    }  
};  
SendReply reserveSeat = new SendReply  
{   
    ...   
    Request = reserveSeat,  
    Content = new SendParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationId", new InArgument<string>(reservationId) }  
        }  
    },  
};  
```  
  
 <span data-ttu-id="c556e-178">Bir istek/yanıt işlemi tanımlayan bir iş akışı hizmeti uygularken void döndüren, örneği gerekir bir <xref:System.ServiceModel.Activities.SendReply> etkinliği ve kümesi <xref:System.ServiceModel.Activities.SendReply.Content%2A> içerik türlerden birinde boş bir örnek özelliğine (<xref:System.ServiceModel.Activities.SendMessageContent> veya <xref:System.ServiceModel.Activities.SendParametersContent>) aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="c556e-178">When implementing a workflow service that defines a request/response operation that returns void, you must instantiate a <xref:System.ServiceModel.Activities.SendReply> activity and set the <xref:System.ServiceModel.Activities.SendReply.Content%2A> property to an empty instance of one of the content types (<xref:System.ServiceModel.Activities.SendMessageContent> or <xref:System.ServiceModel.Activities.SendParametersContent>) as shown in the following example.</span></span>  
  
```  
Receive rcv = new Receive()  
{  
ServiceContractName = "IService",  
OperationName = "NullReturningContract",  
Content = new ReceiveParametersContent( new Dictionary<string, OutArgument>() { { "message", new OutArgument<string>() } } )  
};  
SendReply sr = new SendReply()  
{  
Request = rcv  
   Content = new SendParametersContent();  
};  
```  
  
## <a name="add-service-reference"></a><span data-ttu-id="c556e-179">Hizmet Başvurusu Ekle</span><span class="sxs-lookup"><span data-stu-id="c556e-179">Add Service Reference</span></span>  
 <span data-ttu-id="c556e-180">Bir iş akışı hizmeti bir iş akışı uygulamasından çağrılırken [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] normal kapsülleyen özel Mesajlaşma etkinlikleri oluşturur <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> bir istek/yanıt MEP kullanılan etkinliklerin.</span><span class="sxs-lookup"><span data-stu-id="c556e-180">When calling a workflow service from a workflow application, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] generates custom messaging activities that encapsulate the usual <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities used in a request/reply MEP.</span></span> <span data-ttu-id="c556e-181">Bu özelliği kullanmak için istemci projeye sağ tıklayın [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] seçip **hizmet Başvurusu Ekle**.</span><span class="sxs-lookup"><span data-stu-id="c556e-181">To use this feature right-click the client project in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and select **Add Service Reference**.</span></span> <span data-ttu-id="c556e-182">Hizmetin taban adresi adres kutusuna yazın ve Git'i tıklatın.</span><span class="sxs-lookup"><span data-stu-id="c556e-182">Type the base address of the service in the address box and click Go.</span></span> <span data-ttu-id="c556e-183">Kullanılabilir hizmetler görüntülenir **Hizmetleri:** kutusu.</span><span class="sxs-lookup"><span data-stu-id="c556e-183">The available services are displayed in the **Services:** box.</span></span> <span data-ttu-id="c556e-184">Desteklenen sözleşmeleri görüntülemek için hizmet düğümünü genişletin.</span><span class="sxs-lookup"><span data-stu-id="c556e-184">Expand the service node to display the contracts supported.</span></span> <span data-ttu-id="c556e-185">Çağrı istediğiniz sözleşmeyi seçin ve kullanılabilir işlemleri listesi görüntülenir **Operations** kutusu.</span><span class="sxs-lookup"><span data-stu-id="c556e-185">Select the contract you want to call and the list of available operations is displayed in the **Operations** box.</span></span> <span data-ttu-id="c556e-186">Oluşturulan etkinlik için ad alanını belirtin ve tıklatın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="c556e-186">You can then specify the namespace for the generated activity and click **OK**.</span></span> <span data-ttu-id="c556e-187">Ardından işlemi başarıyla tamamlandı bildiren ve projeyi yeniden sonra oluşturulan özel etkinlikler Araç Kutusu'nda olan bir iletişim kutusu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="c556e-187">You then see a dialog that says the operation completed successfully and that the generated custom activities are in the toolbox after you have rebuilt the project.</span></span> <span data-ttu-id="c556e-188">Hizmet sözleşmesini tanımlanan her işlem için bir etkinlik yok.</span><span class="sxs-lookup"><span data-stu-id="c556e-188">There is one activity for each operation defined on the service contract.</span></span> <span data-ttu-id="c556e-189">Projeyi yeniden derlemeyi sonra sürükleyin ve özel etkinlikler, iş akışınızı bırakabilir ve Özellikler penceresinde tüm gerekli özellikleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c556e-189">After rebuilding the project you can drag and drop the custom activities onto your workflow and set any required properties in the properties window.</span></span>  
  
<!--## Messaging Activity Templates  
 To make setting up a request/response MEP on the client and service easier, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] provides two messaging activity templates. <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> is used on the service and <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> is used on the client. In both cases the templates add the appropriate messaging activities to your workflow. On the service, the <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> adds a <xref:System.ServiceModel.Activities.Receive> activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity. The <xref:System.ServiceModel.Activities.SendReply.Request> property is automatically set to the <xref:System.ServiceModel.Activities.Receive> activity. On the client, the <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> adds a <xref:System.ServiceModel.Activities.Send> activity followed by a <xref:System.ServiceModel.Activities.ReceiveReply>. The <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> property is automatically set to the <xref:System.ServiceModel.Activities.Send> activity. To use these templates, just drag and drop the appropriate template onto your workflow.  
-->
## <a name="messaging-activities-and-transactions"></a><span data-ttu-id="c556e-190">Mesajlaşma etkinlikleri ve işlemler</span><span class="sxs-lookup"><span data-stu-id="c556e-190">Messaging Activities and Transactions</span></span>  
 <span data-ttu-id="c556e-191">Bir iş akışı hizmetine çağrı yapıldığında hizmet işlemi için işlem akış isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c556e-191">When a call is made to a workflow service you may want to flow a transaction to the service operation.</span></span> <span data-ttu-id="c556e-192">Burası yapmak için <xref:System.ServiceModel.Activities.Receive> içinde etkinlik bir <xref:System.ServiceModel.Activities.TransactedReceiveScope> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c556e-192">To do this place the <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="c556e-193"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Etkinlik içeren bir `Receive` etkinliği ve gövde.</span><span class="sxs-lookup"><span data-stu-id="c556e-193">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity contains a `Receive` activity and a body.</span></span> <span data-ttu-id="c556e-194">Hizmet kalır gövdesini yürütme ortam için işlem akışı yapılan işlem <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="c556e-194">The transaction flowed to the service remains ambient throughout the execution of the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="c556e-195">Gövde yürütme tamamlandığında işlem tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="c556e-195">The transaction is completed when the body finishes executing.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c556e-196">İş akışları ve işlem görür [iş akışı işlemleri](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c556e-196"> workflows and transactions see [Workflow Transactions](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c556e-197">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c556e-197">See Also</span></span>  
 [<span data-ttu-id="c556e-198">İş akışı hizmetleri hataları alıp göndermek nasıl</span><span class="sxs-lookup"><span data-stu-id="c556e-198">How to Send and Receive Faults in Workflow Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=189151)  
 [<span data-ttu-id="c556e-199">Uzun süre çalışan iş akışı hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="c556e-199">Creating a Long-running Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)