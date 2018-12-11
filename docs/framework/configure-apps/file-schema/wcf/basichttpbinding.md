---
title: '&lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- basicHttpBinding Element
ms.assetid: 85cf1a4f-26c2-48c7-bda6-6c960d5d3fb3
ms.openlocfilehash: c20271fd5b053d82786adec8dd5a7d4fd4c5ad5a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131059"
---
# <a name="ltbasichttpbindinggt"></a><span data-ttu-id="0d7ac-102">&lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="0d7ac-102">&lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="0d7ac-103">Bir Windows Communication Foundation (WCF) hizmeti yapılandırmak ve ASMX tabanlı Web Hizmetleri, istemci ve WS uyumlu diğer hizmetler ile iletişim kurabilen bitiş noktaları ortaya çıkarmak için kullanabileceğiniz bir bağlama temsil-ı Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span>  
  
 <span data-ttu-id="0d7ac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0d7ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0d7ac-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-105">\<bindings></span></span>  
<span data-ttu-id="0d7ac-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-106">\<basicHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7ac-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0d7ac-107">Syntax</span></span>  
  
```xml  
<basicHttpBinding>  
   <binding allowCookies="Boolean"  
            bypassProxyOnLocal="Boolean"  
            closeTimeout="TimeSpan"   
            envelopeVersion="None/Soap11/Soap12"  
            hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
            maxBufferPoolSize="Integer"  
            maxBufferSize="Integer"  
            maxReceivedMessageSize="Integer"  
            messageEncoding="Text/Mtom"  
            name="string"   
            openTimeout="TimeSpan"   
            proxyAddress="URI"  
            receiveTimeout="TimeSpan"  
            sendTimeout="TimeSpan"  
            textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
            transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
            useDefaultWebProxy="Boolean">
       <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
           <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                      proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                      realm="string" />  
           <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                     clientCredentialType="UserName/Certificate"/>  
       </security>  
       <readerQuotas maxArrayLength="Integer"  
                     maxBytesPerRead="Integer"  
                     maxDepth="Integer"
                     maxNameTableCharCount="Integer"
                     maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d7ac-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d7ac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d7ac-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d7ac-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0d7ac-110">Attributes</span></span>  
  
|<span data-ttu-id="0d7ac-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="0d7ac-111">Attribute</span></span>|<span data-ttu-id="0d7ac-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d7ac-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="0d7ac-113">İstemci tanımlama bilgilerini kabul eder ve bunları gelecekteki isteklerde yayar gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-113">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="0d7ac-114">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="0d7ac-115">Tanımlama bilgileri kullanan ASMX Web Hizmetleri ile etkileşim kurduğunuzda bu özelliği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-115">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="0d7ac-116">Bu şekilde, sunucudan döndürülen tanımlama bilgilerini aydaki hizmet için tüm istemci isteklerini otomatik olarak kopyalanır emin olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-116">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="0d7ac-117">Yerel adresler için proxy sunucusunun atlanıp atlanmayacağını gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="0d7ac-118">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="0d7ac-119">Bir Internet kaynağına, yerel adres varsa yereldir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-119">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="0d7ac-120">Yerel bir adres aynı bilgisayarda, yerel LAN veya intranet ve, sözdizimsel olarak, URI'ler olduğu gibi bir nokta (.) eksikliği tarafından tanımlanan biridir "http://webserver/" ve "http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="0d7ac-120">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="0d7ac-121">Bu öznitelik ayarlama BasicHttpBinding ile yapılandırılmış uç noktaları yerel kaynaklara erişirken proxy sunucusu kullanıp kullanmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-121">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="0d7ac-122">Bu öznitelik ise `true`, istekleri yerel Internet kaynakları için proxy sunucusu kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-122">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="0d7ac-123">Bu öznitelik ayarlandığında Hizmetleri aynı makinede konuşurken bir proxy üzerinden Git istemcilerin istiyorsanız ana bilgisayarın adı (localhost yerine) kullanın `true`.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-123">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="0d7ac-124">Bu öznitelik olduğunda `false`, tüm Internet isteklerini Ara sunucu üzerinden yapılır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-124">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="0d7ac-125">A <xref:System.TimeSpan> bir kapatma işlemi tamamlamak sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="0d7ac-126">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0d7ac-127">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-127">The default is 00:01:00.</span></span>|  
|`envelopeVersion`|<span data-ttu-id="0d7ac-128">Bu bağlama tarafından işlenen iletiler için kullanılan SOAP sürümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-128">Specifies the version of SOAP that is used for messages that are processed by this binding.</span></span> <span data-ttu-id="0d7ac-129">Yalnızca geçerli Soap11 değerdir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-129">The only valid value is Soap11.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="0d7ac-130">URI ayrıştırmak için kullanılan HTTP ana bilgisayar adını karşılaştırma modunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-130">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="0d7ac-131">Bu öznitelik türünde <xref:System.ServiceModel.HostNameComparisonMode>, ana bilgisayar üzerinde URI'yi eşleştirirken hizmete erişmek için kullanılıp kullanılmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-131">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="0d7ac-132">Varsayılan değer <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, ana bilgisayar adı eşleşme yok sayar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-132">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="0d7ac-133">Kanaldan iletiler alan ileti arabelleklerinin Yöneticisi tarafından kullanılmak için ayrılan maksimum belleğin belirten bir tamsayı değeri.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-133">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="0d7ac-134">Varsayılan değer: 524288 (0x80000) bayt.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-134">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="0d7ac-135">Arabellek Yöneticisi bir arabellek havuzu kullanarak arabellekler maliyetini en aza indirir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-135">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="0d7ac-136">Bunlar dışında kanal geldiğinizde arabellekler iletilerini işlemek için hizmet tarafından gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-136">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="0d7ac-137">İleti yükü işlemek için arabellek havuzunda yeterli bellek yoksa, arabellek Yöneticisi çöp toplama taşması artıran CLR yığından ek bellek tahsis etmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-137">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="0d7ac-138">CLR çöp yığınındaki gelen kapsamlı ayırma arabellek havuzu boyutu çok küçük olduğunu ve bu özniteliği tarafından belirtilen sınırı artırarak performans daha büyük bir ayırma ile geliştirilebilir göstergesidir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-138">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="0d7ac-139">Bu bağlama ile yapılandırılan bir uç nokta için işlenirken iletileri depolayan bir arabellek, bayt cinsinden en büyük boyutunu belirten bir tamsayı değeri.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-139">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="0d7ac-140">65.536 bayt varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-140">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="0d7ac-141">Bu bağlama ile yapılandırılan bir kanalda alınan iletinin üst bilgiler dahil bayt cinsinden en büyük ileti boyutunu tanımlar. pozitif bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-141">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="0d7ac-142">İleti alıcısı için çok büyük ise, gönderici bir SOAP hatasını alır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-142">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="0d7ac-143">Alıcı, iletiyi bırakır ve izleme günlüğüne etkinliğin bir giriş oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="0d7ac-144">Varsayılan 65.536 bayt'tır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-144">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="0d7ac-145">SOAP iletisi kodlamak için kullanılan Kodlayıcısı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-145">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="0d7ac-146">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="0d7ac-146">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0d7ac-147">-Metni: Bir metin ileti Kodlayıcı kullanın.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-147">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="0d7ac-148">-Mtom: İleti Aktarım kuruluş mekanizması 1.0 (MTOM) encoder'ı kullanın.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-148">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="0d7ac-149">Metin varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-149">The default is Text.</span></span> <span data-ttu-id="0d7ac-150">Bu öznitelik türünde <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-150">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="0d7ac-151">Bağlama yapılandırma adını içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="0d7ac-152">Bağlama için bir tanımlayıcı olarak kullanıldığından, bu değer benzersiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="0d7ac-153">Her bağlama sahip bir `name` ve `namespace` birlikte benzersiz özniteliği hizmetinin meta verilerde tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-153">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="0d7ac-154">Ayrıca, bu ad aynı türdeki bağlamaları arasında benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-154">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="0d7ac-155">İle başlayarak [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bağlamalar ve davranışları için gerekli değildir bir ada sahip.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-155">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0d7ac-156">Varsayılan yapılandırma ve adsız bağlamaları ve davranışları hakkında daha fazla bilgi için bkz: [Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ac-156">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="0d7ac-157">XML ad alanı bağlamanın belirtir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-157">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="0d7ac-158">Varsayılan değer " http://tempuri.org/Bindings".</span><span class="sxs-lookup"><span data-stu-id="0d7ac-158">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="0d7ac-159">Her bağlama sahip bir `name` ve `namespace` birlikte benzersiz özniteliği hizmetinin meta verilerde tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-159">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="0d7ac-160">A <xref:System.TimeSpan> tamamlamak açık işlem için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="0d7ac-161">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0d7ac-162">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-162">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="0d7ac-163">HTTP proxy adresini içeren bir URI.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-163">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="0d7ac-164">Varsa `useSystemWebProxy` ayarlanır `true`, bu ayar olmalıdır `null`.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-164">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="0d7ac-165">Varsayılan, `null` değeridir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-165">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0d7ac-166">A <xref:System.TimeSpan> tamamlamak alma işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="0d7ac-167">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0d7ac-168">Varsayılan değer 00:10:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-168">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="0d7ac-169">A <xref:System.TimeSpan> tamamlamak bir gönderme işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-169">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0d7ac-170">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-170">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0d7ac-171">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-171">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="0d7ac-172">İletileri bağlamadaki yayma için kullanılacak kodlama karakter kümesini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-172">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="0d7ac-173">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="0d7ac-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0d7ac-174">-BigEndianUnicode: Unicode kodlama BigEndian.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-174">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="0d7ac-175">-Unicode: 16-bit kodlaması.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-175">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="0d7ac-176">-UTF8: 8-bit kodlama</span><span class="sxs-lookup"><span data-stu-id="0d7ac-176">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="0d7ac-177">UTF8 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-177">The default is UTF8.</span></span> <span data-ttu-id="0d7ac-178">Bu öznitelik türünde <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="0d7ac-179">Geçerli bir <xref:System.ServiceModel.TransferMode> iletilerin ara belleğe veya bir istek veya yanıtı belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-179">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="0d7ac-180">Otomatik yapılandırılan HTTP Ara sunucusu sisteminin kullanılması gerekip gerekmediğini, varsa belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-180">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="0d7ac-181">Varsayılan, `true` değeridir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-181">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d7ac-182">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d7ac-182">Child Elements</span></span>  
  
|<span data-ttu-id="0d7ac-183">Öğe</span><span class="sxs-lookup"><span data-stu-id="0d7ac-183">Element</span></span>|<span data-ttu-id="0d7ac-184">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d7ac-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d7ac-185">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="0d7ac-186">Bağlama için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-186">Defines the security settings for the binding.</span></span> <span data-ttu-id="0d7ac-187">Bu öğe türünde <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-187">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="0d7ac-188">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-188">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="0d7ac-189">Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0d7ac-190">Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d7ac-191">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d7ac-191">Parent Elements</span></span>  
  
|<span data-ttu-id="0d7ac-192">Öğe</span><span class="sxs-lookup"><span data-stu-id="0d7ac-192">Element</span></span>|<span data-ttu-id="0d7ac-193">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d7ac-193">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d7ac-194">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-194">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="0d7ac-195">Bu öğe, standart ve özel bağlamalar koleksiyonunu tutar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-195">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d7ac-196">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0d7ac-196">Remarks</span></span>  
 <span data-ttu-id="0d7ac-197">BasicHttpBinding, SOAP 1.1 iletileri göndermek için aktarım olarak HTTP kullanır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-197">The BasicHttpBinding uses HTTP as the transport for sending SOAP 1.1 messages.</span></span> <span data-ttu-id="0d7ac-198">Bir hizmet WS uygun uç noktalarını kullanıma sunmak için bu bağlamayı kullanan-ı BP 1.1 ASMX istemciler tüketen olanlar gibi.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-198">A service can use this binding to expose endpoints that conform to WS-I BP 1.1, such as those that ASMX clients consume.</span></span> <span data-ttu-id="0d7ac-199">Benzer şekilde, istemci BasicHttpBinding WS uygun uç noktaları açığa çıkaran hizmetler ile iletişim kurmak için kullanabilir-ı BP 1.1 ASMX Web Hizmetleri veya BasicHttpBinding ile yapılandırılmış bir hizmeti gibi.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-199">Similarly, a client can use the BasicHttpBinding to communicate with services exposing endpoints that conform to WS-I BP 1.1, such as ASMX Web services or services configured with the BasicHttpBinding.</span></span>  
  
 <span data-ttu-id="0d7ac-200">Güvenlik için varsayılan olarak devre dışıdır, ancak bu mod özniteliği ayarıyla eklenebilir [ \<Güvenlik >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) dışında bir değeri alt öğeye `None`.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-200">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="0d7ac-201">Bir "Metin" İleti kodlama ve UTF-8 metin kodlama varsayılan olarak kullanır.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-201">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d7ac-202">Örnek</span><span class="sxs-lookup"><span data-stu-id="0d7ac-202">Example</span></span>  
 <span data-ttu-id="0d7ac-203">Aşağıdaki örnek, kullanımını gösterir <xref:System.ServiceModel.BasicHttpBinding> , HTTP iletişimi ve en fazla birlikte çalışabilirlik ilk - ve second - generation ile Web hizmetleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-203">The following example demonstrates the use of <xref:System.ServiceModel.BasicHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="0d7ac-204">İstemci ve hizmet yapılandırma dosyalarında bağlama belirtildi.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-204">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="0d7ac-205">Bağlama türü kullanarak belirtilen `binding` özniteliği `<endpoint>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-205">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="0d7ac-206">Temel bağlama yapılandırmak ve bazı ayarlarını değiştirmek istiyorsanız, bir bağlama yapılandırmasını tanımlamak gereklidir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-206">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="0d7ac-207">Uç nokta bağlama yapılandırması adıyla kullanarak başvurmalıdır `bindingConfiguration` özniteliği `<endpoint>` hizmeti için aşağıdaki yapılandırma kodda gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-207">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="basicHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <basicHttpBinding>  
        <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Text"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="0d7ac-208">Örnek</span><span class="sxs-lookup"><span data-stu-id="0d7ac-208">Example</span></span>  
 <span data-ttu-id="0d7ac-209">İle başlayarak [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bağlamalar ve davranışları için gerekli değildir bir ada sahip.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-209">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0d7ac-210">Önceki örnekte işlevselliği, uç nokta adresini ve bağlama adından bindingConfiguration kaldırarak gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-210">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="basicHttpBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <basicHttpBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Text"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0d7ac-211">Varsayılan yapılandırma ve adsız bağlamaları ve davranışları hakkında daha fazla bilgi için bkz: [Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ac-211">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7ac-212">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0d7ac-212">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="0d7ac-213">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="0d7ac-213">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0d7ac-214">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0d7ac-214">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0d7ac-215">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="0d7ac-215">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="0d7ac-216">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="0d7ac-216">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
