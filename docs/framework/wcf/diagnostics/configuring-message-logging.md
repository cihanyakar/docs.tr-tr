---
title: "İleti Günlüğe Kaydetmeyi Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message logging [WCF]
ms.assetid: 0ff4c857-8f09-4b85-9dc0-89084706e4c9
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e42b4007d438fbabaf497981b654415ca7eeb415
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-message-logging"></a><span data-ttu-id="04a73-102">İleti Günlüğe Kaydetmeyi Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="04a73-102">Configuring Message Logging</span></span>
<span data-ttu-id="04a73-103">Bu konuda, ileti günlüğe kaydetme farklı senaryolar için nasıl yapılandırabileceğiniz açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="04a73-103">This topic describes how you can configure message logging for different scenarios.</span></span>  
  
## <a name="enabling-message-logging"></a><span data-ttu-id="04a73-104">İleti günlüğü etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="04a73-104">Enabling Message Logging</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="04a73-105">ileti, varsayılan olarak günlüğe kaydetmez.</span><span class="sxs-lookup"><span data-stu-id="04a73-105"> does not log messages by default.</span></span> <span data-ttu-id="04a73-106">İleti günlüğe kaydetmeyi etkinleştirmek için bir izleme dinleyicisi eklemek `System.ServiceModel.MessageLogging` izleme kaynağı ve ayarlamak için öznitelikler `<messagelogging>` yapılandırma dosyası öğesi.</span><span class="sxs-lookup"><span data-stu-id="04a73-106">To activate message logging, you must add a trace listener to the `System.ServiceModel.MessageLogging` trace source and set attributes for the `<messagelogging>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="04a73-107">Aşağıdaki örnek, günlüğe yazılmasını etkinleştirmek ve ek seçenekleri belirtmek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="04a73-107">The following example shows how to enable logging and specify additional options.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
    </sources>  
</system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics>  
    <messageLogging   
         logEntireMessage="true"   
         logMalformedMessages="false"  
         logMessagesAtServiceLevel="true"   
         logMessagesAtTransportLevel="false"  
         maxMessagesToLog="3000"  
         maxSizeOfMessageToLog="2000"/>  
  </diagnostics>  
</system.serviceModel>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04a73-108">İleti günlüğe kaydetme ayarlarını, bkz: [izleme ve ileti günlüğe kaydetme için önerilen ayarları](../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="04a73-108"> message logging settings, see [Recommended Settings for Tracing and Message Logging](../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="04a73-109">Kullanabileceğiniz `add` adını ve kullanmak istediğiniz dinleyici türünü belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="04a73-109">You can use `add` to specify the name and type of the listener you want to use.</span></span> <span data-ttu-id="04a73-110">Örnek yapılandırma dinleyicisi "iletileri" olarak adlandırılır ve standart .NET Framework İzleme dinleyicisi ekler (`System.Diagnostics.XmlWriterTraceListener`) olarak kullanmak üzere türü.</span><span class="sxs-lookup"><span data-stu-id="04a73-110">In the example configuration, the Listener is named "messages" and adds the standard .NET Framework trace listener (`System.Diagnostics.XmlWriterTraceListener`) as the type to use.</span></span> <span data-ttu-id="04a73-111">Kullanırsanız `System.Diagnostics.XmlWriterTraceListener`, yapılandırma dosyasında çıktı dosya konumunu ve adını belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="04a73-111">If you use `System.Diagnostics.XmlWriterTraceListener`, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="04a73-112">Bu ayarlayarak yapılır `initializeData` günlük dosyasının adı.</span><span class="sxs-lookup"><span data-stu-id="04a73-112">This is done by setting `initializeData` to the name of the log file.</span></span> <span data-ttu-id="04a73-113">Aksi takdirde, sistem bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="04a73-113">Otherwise, the system throws an exception.</span></span> <span data-ttu-id="04a73-114">Ayrıca varsayılan dosyasına yayar özel bir dinleyici uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="04a73-114">You can also implement a custom listener that emits logs to a default file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a73-115">Disk alanı ileti günlüğe kaydetme eriştiği için belirli bir hizmet için diske yazılan iletilerin sayısını sınırlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="04a73-115">Because message logging accesses disk space, you should limit the number of messages that are written to disk for a particular service.</span></span> <span data-ttu-id="04a73-116">İleti sınırına ulaşıldığında, bir izleme bilgileri düzeyinde oluşturulur ve tüm ileti günlüğe kaydetme etkinlikleri durdurun.</span><span class="sxs-lookup"><span data-stu-id="04a73-116">When the message limit is reached, a trace at the Information level is produced and all message logging activities stop.</span></span>  
  
 <span data-ttu-id="04a73-117">Günlüğe kaydetme düzeyi gibi ek seçenekler, günlük düzeyi ve Seçenekleri bölümünde ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="04a73-117">The logging level, as well as the additional options, are discussed in the Logging Level and Options section.</span></span>  
  
 <span data-ttu-id="04a73-118">`switchValue` Özniteliği bir `source` yalnızca izleme için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="04a73-118">The `switchValue` attribute of a `source` is only valid for tracing.</span></span> <span data-ttu-id="04a73-119">Belirtirseniz bir `switchValue` için öznitelik `System.ServiceModel.MessageLogging` izleme kaynağı olarak izler, herhangi bir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="04a73-119">If you specify a `switchValue` attribute for the `System.ServiceModel.MessageLogging` trace source as follows, it has no effect.</span></span>  
  
```xml  
<source name="System.ServiceModel.MessageLogging" switchValue="Verbose">  
```  
  
 <span data-ttu-id="04a73-120">İzleme kaynağı devre dışı bırakmak istiyorsanız, kullanması gereken `logMessagesAtServiceLevel`, `logMalformedMessages`, ve `logMessagesAtTransportLevel` özniteliklerini `messageLogging` öğesi yerine.</span><span class="sxs-lookup"><span data-stu-id="04a73-120">If you want to disable the trace source, you should use the `logMessagesAtServiceLevel`, `logMalformedMessages`, and `logMessagesAtTransportLevel` attributes of the `messageLogging` element instead.</span></span> <span data-ttu-id="04a73-121">Bu öznitelikler kümesine `false`.</span><span class="sxs-lookup"><span data-stu-id="04a73-121">You should set all these attributes to `false`.</span></span> <span data-ttu-id="04a73-122">Bu yapılandırma Düzenleyicisi UI arabirimi aracılığıyla önceki kod örneğinde, yapılandırma dosyası kullanarak veya WMI kullanılarak yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-122">This can be done by using the configuration file in the previous code example, through the Configuration Editor UI interface, or using WMI.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04a73-123">Yapılandırma Düzenleyicisi araç bkz [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="04a73-123"> the Configuration Editor tool, see [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04a73-124">WMI, bkz: [tanılama için Windows Yönetim araçları kullanarak](../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="04a73-124"> WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
## <a name="logging-levels-and-options"></a><span data-ttu-id="04a73-125">Günlük düzeyleri ve seçenekleri</span><span class="sxs-lookup"><span data-stu-id="04a73-125">Logging Levels and Options</span></span>  
 <span data-ttu-id="04a73-126">Gelen iletiler için günlüğe kaydetme hemen ileti hizmet düzeyi için kullanıcı kodu büyümeden hemen ileti, biçimlendirilmemiş sonra ve hatalı biçimlendirilmiş iletileri algılandığında gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="04a73-126">For incoming messages, logging happens immediately after the message is formed, immediately before the message gets to user code in the service level, and when malformed messages are detected.</span></span>  
  
 <span data-ttu-id="04a73-127">Giden iletiler için günlüğe kaydetme hemen ileti kullanıcı kodu ayrıldığında sonra ve ileti kablo göründükten hemen önce gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="04a73-127">For outgoing messages, logging happens immediately after the message leaves user code and immediately before the message goes on the wire.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="04a73-128">iki farklı düzeylerde, hizmet ve aktarım iletilerini günlüğe kaydeder.</span><span class="sxs-lookup"><span data-stu-id="04a73-128"> logs messages at two different levels, service and transport.</span></span> <span data-ttu-id="04a73-129">Hatalı biçimlendirilmiş iletileri da günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-129">Malformed messages are also logged.</span></span> <span data-ttu-id="04a73-130">Üç kategoride birbirinden bağımsızdır ve yapılandırmada ayrı olarak etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-130">The three categories are independent from each other and can be activated separately in configuration.</span></span>  
  
 <span data-ttu-id="04a73-131">Ayarlayarak günlük düzeyini denetleyebilirsiniz `logMessagesAtServiceLevel`, `logMalformedMessages`, ve `logMessagesAtTransportLevel` özniteliklerini `messageLogging` öğesi.</span><span class="sxs-lookup"><span data-stu-id="04a73-131">You can control the logging level by setting the `logMessagesAtServiceLevel`, `logMalformedMessages`, and `logMessagesAtTransportLevel` attributes of the `messageLogging` element.</span></span>  
  
### <a name="service-level"></a><span data-ttu-id="04a73-132">Hizmet düzeyi</span><span class="sxs-lookup"><span data-stu-id="04a73-132">Service Level</span></span>  
 <span data-ttu-id="04a73-133">Bu katmanda günlüğe kaydedilen iletileri olan yaklaşık (alma üzerinde) girin veya (gönderme) ayrılma kullanıcı kodu.</span><span class="sxs-lookup"><span data-stu-id="04a73-133">Messages logged at this layer are about to enter (on receiving) or leave (on sending) user code.</span></span> <span data-ttu-id="04a73-134">Filtreler tanımladıysanız, filtrelerle eşleşen iletileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-134">If filters have been defined, only messages that match the filters are logged.</span></span> <span data-ttu-id="04a73-135">Aksi takdirde, hizmet düzeyinde tüm iletileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-135">Otherwise, all messages at the service level are logged.</span></span> <span data-ttu-id="04a73-136">Altyapı iletileri (işlemler, eş kanalı ve güvenlik) de güvenilir Mesajlaşma iletileri dışında bu düzeyde günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-136">Infrastructure messages (transactions, peer channel, and security) are also logged at this level, except for Reliable Messaging messages.</span></span> <span data-ttu-id="04a73-137">Akış iletilerde yalnızca üstbilgileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-137">On streamed messages, only the headers are logged.</span></span> <span data-ttu-id="04a73-138">Ayrıca, bu düzeyde şifresi güvenli iletiler kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-138">In addition, secure messages are logged decrypted at this level.</span></span>  
  
### <a name="transport-level"></a><span data-ttu-id="04a73-139">Aktarım düzeyi</span><span class="sxs-lookup"><span data-stu-id="04a73-139">Transport Level</span></span>  
 <span data-ttu-id="04a73-140">Bu katmanda günlüğe kaydedilen iletileri kodlanmış veya için veya taşıma hattaki sonra kodunu çözdü hazırsınız demektir.</span><span class="sxs-lookup"><span data-stu-id="04a73-140">Messages logged at this layer are ready to be encoded or decoded for or after transportation on the wire.</span></span> <span data-ttu-id="04a73-141">Filtreler tanımladıysanız, filtrelerle eşleşen iletileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-141">If filters have been defined, only messages that match the filters are logged.</span></span> <span data-ttu-id="04a73-142">Aksi takdirde, Aktarım katmanı tüm iletileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-142">Otherwise, all messages at the transport layer are logged.</span></span> <span data-ttu-id="04a73-143">Tüm altyapı iletileri güvenilir Mesajlaşma iletileri de dahil olmak üzere bu katmanda günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-143">All infrastructure messages are logged at this layer, including reliable messaging messages.</span></span> <span data-ttu-id="04a73-144">Akış iletilerde yalnızca üstbilgileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-144">On streamed messages, only the headers are logged.</span></span> <span data-ttu-id="04a73-145">Ayrıca, güvenli iletiler IF dışında bu düzeyde HTTPS kullanılan gibi güvenli bir taşıma şifrelenmiş olarak kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-145">In addition, secure messages are logged as encrypted at this level, except if a secure transport such as HTTPS is used.</span></span>  
  
### <a name="malformed-level"></a><span data-ttu-id="04a73-146">Hatalı biçimlendirilmiş düzeyi</span><span class="sxs-lookup"><span data-stu-id="04a73-146">Malformed Level</span></span>  
 <span data-ttu-id="04a73-147">Hatalı biçimlendirilmiş iletiler olan tarafından reddedilen iletiler [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] işleminin herhangi bir aşamada yığını.</span><span class="sxs-lookup"><span data-stu-id="04a73-147">Malformed messages are messages that are rejected by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack at any stage of processing.</span></span> <span data-ttu-id="04a73-148">Hatalı biçimlendirilmiş iletileri olarak kaydediliyor-olduğu: bunu uygun olmayan XML vb. ile olmaları durumunda şifrelenmiş.</span><span class="sxs-lookup"><span data-stu-id="04a73-148">Malformed messages are logged as-is: encrypted if they are so, with non-proper XML, and so on.</span></span> <span data-ttu-id="04a73-149">`maxSizeOfMessageToLog`CDATA olarak kaydedilen iletinin boyutunu tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-149">`maxSizeOfMessageToLog` defined the size of the message to be logged as CDATA.</span></span> <span data-ttu-id="04a73-150">Varsayılan olarak, `maxSizeOfMessageToLog` 256 K eşittir.</span><span class="sxs-lookup"><span data-stu-id="04a73-150">By default, `maxSizeOfMessageToLog` is equal to 256K.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04a73-151">Bu öznitelik diğer seçenekleri bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="04a73-151"> this attribute, see the Other Options section.</span></span>  
  
### <a name="other-options"></a><span data-ttu-id="04a73-152">Diğer seçenekleri</span><span class="sxs-lookup"><span data-stu-id="04a73-152">Other Options</span></span>  
 <span data-ttu-id="04a73-153">Günlüğe kaydetme düzeylerini yanı sıra kullanıcı aşağıdaki seçenekleri belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="04a73-153">In addition to the logging levels, the user can specify the following options:</span></span>  
  
-   <span data-ttu-id="04a73-154">Tüm ileti günlüğe (`logEntireMessage` özniteliği): Bu değer, iletinin tamamını (ileti başlığı ve gövde) günlüğe kaydedilip kaydedilmediğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="04a73-154">Log Entire Message (`logEntireMessage` attribute): This value specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="04a73-155">Varsayılan değer `false`, yalnızca üstbilgisi kaydedilir anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="04a73-155">The default value is `false`, meaning that only the header is logged.</span></span> <span data-ttu-id="04a73-156">Bu ayar, hizmet ve aktarım ileti günlüğe kaydetme düzeylerini etkiler...</span><span class="sxs-lookup"><span data-stu-id="04a73-156">This setting affects service and transport message logging levels..</span></span>  
  
-   <span data-ttu-id="04a73-157">Günlüğe kaydedilecek en fazla ileti (`maxMessagesToLog` özniteliği): Bu değer günlüğe kaydedilecek ileti sayısı üst sınırını belirtir.</span><span class="sxs-lookup"><span data-stu-id="04a73-157">Max messages to log (`maxMessagesToLog` attribute): This value specifies the maximum number of messages to log.</span></span> <span data-ttu-id="04a73-158">Tüm iletileri (hizmet, taşıma ve hatalı biçimlendirilmiş iletileri) Bu kota sayılır.</span><span class="sxs-lookup"><span data-stu-id="04a73-158">All messages (service, transport, and malformed messages) are counted towards this quota.</span></span> <span data-ttu-id="04a73-159">Kotasına ulaşıldığında, bir izleme yayılan ve hiçbir ek ileti günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-159">When the quota is reached, a trace is emitted and no additional message is logged.</span></span> <span data-ttu-id="04a73-160">Varsayılan değer 10000'dir.</span><span class="sxs-lookup"><span data-stu-id="04a73-160">The default value is 10000.</span></span>  
  
-   <span data-ttu-id="04a73-161">Oturum iletisinin en büyük boyutu (`maxSizeOfMessageToLog` özniteliği): Bu değer bayt cinsinden günlüğe kaydedilecek ileti boyut üst sınırını belirtir.</span><span class="sxs-lookup"><span data-stu-id="04a73-161">Max size of message to log (`maxSizeOfMessageToLog` attribute): This value specifies the maximum size of messages to log in bytes.</span></span> <span data-ttu-id="04a73-162">Boyut sınırını aşan iletileri günlüğe kaydedilmeyen ve başka bir etkinlik için bu iletiyi gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-162">Messages that exceed the size limit are not logged, and no other activity is performed for that message.</span></span> <span data-ttu-id="04a73-163">Bu ayar, tüm izleme düzeylerini etkiler.</span><span class="sxs-lookup"><span data-stu-id="04a73-163">This setting affects all trace levels.</span></span> <span data-ttu-id="04a73-164">ServiceModel izleme üzerindeyse bir uyarı düzeyi izleme ilk günlük (ServiceModelSend * veya TransportReceive) kullanıcıya bildirmek için noktada yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-164">If ServiceModel tracing is on, a Warning level trace is emitted at the first logging point (ServiceModelSend* or TransportReceive) to notify the user.</span></span> <span data-ttu-id="04a73-165">Hatalı biçimlendirilmiş iletileri için varsayılan değer 4 K olsa da hizmet düzeyi ve aktarım düzeyi iletileri için varsayılan değer 256 K ' dir.</span><span class="sxs-lookup"><span data-stu-id="04a73-165">The default value for service level and transport level messages is 256K, while the default value for malformed messages is 4K.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="04a73-166">Karşılaştırılacak hesaplanan ileti boyutu `maxSizeOfMessageToLog` seri hale getirme önce bellekte ileti boyutu.</span><span class="sxs-lookup"><span data-stu-id="04a73-166">The message size that is computed to compare against `maxSizeOfMessageToLog` is the message size in memory before serialization.</span></span> <span data-ttu-id="04a73-167">Bu boyut günlüğe kaydedilir ve birçok yerde gerçek boyutundan daha büyük olan ileti dizesi gerçek uzunluğuyla farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-167">This size can differ from the actual length of the message string that is being logged, and in many occasions is bigger than the actual size.</span></span> <span data-ttu-id="04a73-168">Sonuç olarak, iletileri kaydedilebilir değil.</span><span class="sxs-lookup"><span data-stu-id="04a73-168">As a result, messages may not be logged.</span></span> <span data-ttu-id="04a73-169">Bu bulgusunun belirterek hesabının `maxSizeOfMessageToLog` için öznitelik % 10 beklenen bir ileti boyutundan daha büyük olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="04a73-169">You can account for this fact by specifying the `maxSizeOfMessageToLog` attribute to be 10% larger than the expected message size.</span></span> <span data-ttu-id="04a73-170">Ek olarak, hatalı biçimlendirilmiş iletileri oturum açtıysanız, ileti günlükleri tarafından kullanılan gerçek disk alanı ile belirtilen değer boyutunu 5 kata olabilir `maxSizeOfMessageToLog`.</span><span class="sxs-lookup"><span data-stu-id="04a73-170">In addition, if malformed messages are logged, the actual disk space utilized by the message logs can be up to 5 times the size of the value specified by `maxSizeOfMessageToLog`.</span></span>  
  
 <span data-ttu-id="04a73-171">İzleme dinleyicisi yapılandırma dosyasında tanımlanmış olması durumunda, günlük çıktısı bakılmaksızın belirtilen günlüğe kaydetme düzeyi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="04a73-171">If no trace listener is defined in the configuration file, no logging output is generated regardless of the specified logging level.</span></span>  
  
 <span data-ttu-id="04a73-172">Bu bölümde açıklanan öznitelikleri gibi ileti günlüğe kaydetme seçeneklerini Windows Yönetim Araçları (WMI) kullanarak çalışma zamanında değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-172">Message logging options, such as the attributes described in this section, can be changed at runtime using Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="04a73-173">Bu erişerek yapılabilir [AppDomainInfo](../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) Boolean bu özellikleri sunar örneği: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, ve `LogMalformedMessages`.</span><span class="sxs-lookup"><span data-stu-id="04a73-173">This can be done by accessing the [AppDomainInfo](../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, and `LogMalformedMessages`.</span></span> <span data-ttu-id="04a73-174">Bu nedenle, ileti günlüğe kaydetme için bir izleme dinleyicisi yapılandırmanıza rağmen ayarlamak bu seçenekleri için `false` yapılandırması, daha sonra bunları değiştirebileceğiniz `true` uygulama çalışırken.</span><span class="sxs-lookup"><span data-stu-id="04a73-174">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="04a73-175">Bu ileti günlüğe kaydetme çalışma zamanında etkili bir şekilde sağlar.</span><span class="sxs-lookup"><span data-stu-id="04a73-175">This effectively enables message logging at runtime.</span></span> <span data-ttu-id="04a73-176">İleti günlüğe kaydetme, yapılandırma dosyanızda etkinleştirirseniz, benzer şekilde, size, WMI'yı kullanarak çalışma zamanında devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="04a73-176">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04a73-177">[Tanılama için Windows Yönetim Araçları'nı kullanma](../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="04a73-177"> [Using Windows Management Instrumentation for Diagnostics](../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
 <span data-ttu-id="04a73-178">`source` Bir ileti günlüğü alanında belirtir hangi bağlamda iletisi günlüğe kaydedilir: istek-yanıt ya da hizmet modeli veya aktarım katmanında veya hatalı bir ileti söz konusu olduğunda 1 yönlü isteği için bir istek iletisi gönderme/alma sırasında.</span><span class="sxs-lookup"><span data-stu-id="04a73-178">The `source` field in a message log specifies in which context the message is logged: when sending/receiving a request message, for a request-reply or 1-way request, at service model or transport layer, or in the case of a malformed message.</span></span>  
  
 <span data-ttu-id="04a73-179">Hatalı biçimlendirilmiş iletilerde `source` eşittir `Malformed`.</span><span class="sxs-lookup"><span data-stu-id="04a73-179">For malformed messages, `source`  is equal to `Malformed`.</span></span> <span data-ttu-id="04a73-180">Aksi halde, kaynak bağlamına dayalı aşağıdaki değerlere sahip.</span><span class="sxs-lookup"><span data-stu-id="04a73-180">Otherwise, source has the following values based on the context.</span></span>  
  
 <span data-ttu-id="04a73-181">İstek/yanıt</span><span class="sxs-lookup"><span data-stu-id="04a73-181">For Request/Reply</span></span>  
  
||<span data-ttu-id="04a73-182">İsteği Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-182">Send Request</span></span>|<span data-ttu-id="04a73-183">İsteği alma</span><span class="sxs-lookup"><span data-stu-id="04a73-183">Receive Request</span></span>|<span data-ttu-id="04a73-184">Yanıt gönderme</span><span class="sxs-lookup"><span data-stu-id="04a73-184">Send Reply</span></span>|<span data-ttu-id="04a73-185">Yanıtın</span><span class="sxs-lookup"><span data-stu-id="04a73-185">Receive Reply</span></span>|  
|-|------------------|---------------------|----------------|-------------------|  
|<span data-ttu-id="04a73-186">Hizmet modeli katmanı</span><span class="sxs-lookup"><span data-stu-id="04a73-186">Service Model layer</span></span>|<span data-ttu-id="04a73-187">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-187">Service</span></span><br /><br /> <span data-ttu-id="04a73-188">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-188">Level</span></span><br /><br /> <span data-ttu-id="04a73-189">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-189">Send</span></span><br /><br /> <span data-ttu-id="04a73-190">İstek</span><span class="sxs-lookup"><span data-stu-id="04a73-190">Request</span></span>|<span data-ttu-id="04a73-191">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-191">Service</span></span><br /><br /> <span data-ttu-id="04a73-192">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-192">Level</span></span><br /><br /> <span data-ttu-id="04a73-193">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-193">Receive</span></span><br /><br /> <span data-ttu-id="04a73-194">İstek</span><span class="sxs-lookup"><span data-stu-id="04a73-194">Request</span></span>|<span data-ttu-id="04a73-195">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-195">Service</span></span><br /><br /> <span data-ttu-id="04a73-196">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-196">Level</span></span><br /><br /> <span data-ttu-id="04a73-197">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-197">Send</span></span><br /><br /> <span data-ttu-id="04a73-198">Yanıtla</span><span class="sxs-lookup"><span data-stu-id="04a73-198">Reply</span></span>|<span data-ttu-id="04a73-199">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-199">Service</span></span><br /><br /> <span data-ttu-id="04a73-200">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-200">Level</span></span><br /><br /> <span data-ttu-id="04a73-201">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-201">Receive</span></span><br /><br /> <span data-ttu-id="04a73-202">Yanıtla</span><span class="sxs-lookup"><span data-stu-id="04a73-202">Reply</span></span>|  
|<span data-ttu-id="04a73-203">Aktarım Katmanı</span><span class="sxs-lookup"><span data-stu-id="04a73-203">Transport layer</span></span>|<span data-ttu-id="04a73-204">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-204">Transport</span></span><br /><br /> <span data-ttu-id="04a73-205">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-205">Send</span></span>|<span data-ttu-id="04a73-206">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-206">Transport</span></span><br /><br /> <span data-ttu-id="04a73-207">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-207">Receive</span></span>|<span data-ttu-id="04a73-208">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-208">Transport</span></span><br /><br /> <span data-ttu-id="04a73-209">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-209">Send</span></span>|<span data-ttu-id="04a73-210">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-210">Transport</span></span><br /><br /> <span data-ttu-id="04a73-211">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-211">Receive</span></span>|  
  
 <span data-ttu-id="04a73-212">Tek yönlü iste</span><span class="sxs-lookup"><span data-stu-id="04a73-212">For One-way Request</span></span>  
  
||<span data-ttu-id="04a73-213">İsteği Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-213">Send Request</span></span>|<span data-ttu-id="04a73-214">İsteği alma</span><span class="sxs-lookup"><span data-stu-id="04a73-214">Receive Request</span></span>|  
|-|------------------|---------------------|  
|<span data-ttu-id="04a73-215">Hizmet modeli katmanı</span><span class="sxs-lookup"><span data-stu-id="04a73-215">Service Model layer</span></span>|<span data-ttu-id="04a73-216">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-216">Service</span></span><br /><br /> <span data-ttu-id="04a73-217">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-217">Level</span></span><br /><br /> <span data-ttu-id="04a73-218">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-218">Send</span></span><br /><br /> <span data-ttu-id="04a73-219">Veri birimi</span><span class="sxs-lookup"><span data-stu-id="04a73-219">Datagram</span></span>|<span data-ttu-id="04a73-220">Hizmet</span><span class="sxs-lookup"><span data-stu-id="04a73-220">Service</span></span><br /><br /> <span data-ttu-id="04a73-221">Düzey</span><span class="sxs-lookup"><span data-stu-id="04a73-221">Level</span></span><br /><br /> <span data-ttu-id="04a73-222">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-222">Receive</span></span><br /><br /> <span data-ttu-id="04a73-223">Veri birimi</span><span class="sxs-lookup"><span data-stu-id="04a73-223">Datagram</span></span>|  
|<span data-ttu-id="04a73-224">Aktarım Katmanı</span><span class="sxs-lookup"><span data-stu-id="04a73-224">Transport layer</span></span>|<span data-ttu-id="04a73-225">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-225">Transport</span></span><br /><br /> <span data-ttu-id="04a73-226">Gönder</span><span class="sxs-lookup"><span data-stu-id="04a73-226">Send</span></span>|<span data-ttu-id="04a73-227">Taşıma</span><span class="sxs-lookup"><span data-stu-id="04a73-227">Transport</span></span><br /><br /> <span data-ttu-id="04a73-228">Alma</span><span class="sxs-lookup"><span data-stu-id="04a73-228">Receive</span></span>|  
  
## <a name="message-filters"></a><span data-ttu-id="04a73-229">İleti Filtreleri</span><span class="sxs-lookup"><span data-stu-id="04a73-229">Message Filters</span></span>  
 <span data-ttu-id="04a73-230">İleti filtreleri tanımlanmış `messageLogging` yapılandırma öğesinin `diagnostics` yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="04a73-230">Message filters are defined in the `messageLogging` configuration element of the `diagnostics` configuration section.</span></span> <span data-ttu-id="04a73-231">Bunlar hizmet ve aktarım düzeyinde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-231">They are applied at the service and transport level.</span></span> <span data-ttu-id="04a73-232">Bir veya daha fazla filtre tanımlandığında, en az bir filtre ile eşleşen iletileri günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-232">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="04a73-233">Hiçbir filtre tanımlanmış olması durumunda, tüm iletileri geçirir.</span><span class="sxs-lookup"><span data-stu-id="04a73-233">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="04a73-234">Filtreler tam XPath sözdizimini desteklemek ve yapılandırma dosyasında göründükleri sırada uygulanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-234">Filters support the full XPath syntax and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="04a73-235">Sözdizimsel olarak yanlış bir filtre yapılandırma istisnası ile sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-235">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="04a73-236">Ayrıca filtreleri sağla kullanarak bir güvenlik özelliği `nodeQuota` filtreyle eşleşen incelenmesi XPath DOM düğüm sayısının üst sınırını belirler özniteliği.</span><span class="sxs-lookup"><span data-stu-id="04a73-236">Filters also provide a safety feature using the `nodeQuota` attribute, which limits the maximum number of nodes in the XPath DOM that can be examined to match the filter.</span></span>  
  
 <span data-ttu-id="04a73-237">Aşağıdaki örnekte bir filtre yapılandırmak nasıl bir SOAP üstbilgi bölümüne sahip bu kayıtları yalnızca iletileri gösterir.</span><span class="sxs-lookup"><span data-stu-id="04a73-237">The following example shows how to configure a filter that records only messages that have a SOAP header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
    logMalformedMessages="true"   
    logMessagesAtServiceLevel="true"  
    logMessagesAtTransportLevel="true"  
    maxMessagesToLog="420">  
    <filters>  
        <add nodeQuota="10" xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                 /soap:Envelope/soap:Header  
        </add>  
     </filters>  
</messageLogging>  
```  
  
 <span data-ttu-id="04a73-238">Bir ileti gövdesini filtreleri uygulanamaz.</span><span class="sxs-lookup"><span data-stu-id="04a73-238">Filters cannot be applied to the body of a message.</span></span> <span data-ttu-id="04a73-239">Bir ileti gövdesini işlemek girişimi filtreleri filtreleri listesinden kaldırılır.</span><span class="sxs-lookup"><span data-stu-id="04a73-239">Filters that attempt to manipulate the body of a message are removed from the list of filters.</span></span> <span data-ttu-id="04a73-240">Bir olay da bu gösteren yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="04a73-240">An event is also emitted that indicates this.</span></span> <span data-ttu-id="04a73-241">Örneğin, aşağıdaki filtre filtre tablosundan kaldırılması.</span><span class="sxs-lookup"><span data-stu-id="04a73-241">For example, the following filter would be removed from the filter table.</span></span>  
  
```xml  
<add xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">/s:Envelope/s:Body[contains(text(), "Hello")]</add>  
```  
  
## <a name="configuring-a-custom-listener"></a><span data-ttu-id="04a73-242">Özel bir dinleyici yapılandırma</span><span class="sxs-lookup"><span data-stu-id="04a73-242">Configuring a Custom Listener</span></span>  
 <span data-ttu-id="04a73-243">Bu gibi durumlarda, özel bir dinleyici ayrıca ek seçenekleri yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="04a73-243">You can also configure a custom listener with additional options.</span></span> <span data-ttu-id="04a73-244">Özel bir dinleyici iletileri açmadan önce uygulamaya özgü PII öğelerinden filtreleme yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="04a73-244">A custom listener can be useful in filtering application-specific PII elements from messages before logging.</span></span> <span data-ttu-id="04a73-245">Aşağıdaki örnek, bir özel dinleyici yapılandırması gösterir.</span><span class="sxs-lookup"><span data-stu-id="04a73-245">The following example demonstrates a custom listener configuration.</span></span>  
  
```xml  
<system.diagnostics>  
   <sources>  
     <source name="System.ServiceModel.MessageLogging">  
           <listeners>  
             <add name="MyListener"   
                    type="YourCustomListener"  
                    initializeData="c:\logs\messages.svclog"  
                    maxDiskSpace="1000"/>  
           </listeners>  
     </source>  
   </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="04a73-246">Bilmeniz gereken, `type` türü için bir koşullu derleme adı özniteliği ayarlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="04a73-246">You should be aware that the `type` attribute should be set to a qualified assembly name of the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a73-247">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="04a73-247">See Also</span></span>  
 [<span data-ttu-id="04a73-248">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="04a73-248">\<messageLogging></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)  
 [<span data-ttu-id="04a73-249">İleti günlüğe kaydetme</span><span class="sxs-lookup"><span data-stu-id="04a73-249">Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [<span data-ttu-id="04a73-250">İleti izleme ve kaydetme için önerilen ayarları</span><span class="sxs-lookup"><span data-stu-id="04a73-250">Recommended Settings for Tracing and Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)