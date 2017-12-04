---
title: '&lt;udpDiscoveryEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b82102fdd1e906df504aa9c29b3eb2d0080e0a3e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltudpdiscoveryendpointgt"></a><span data-ttu-id="0d0d6-102">&lt;udpDiscoveryEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="0d0d6-102">&lt;udpDiscoveryEndpoint&gt;</span></span>
<span data-ttu-id="0d0d6-103">Bu yapılandırma öğesi UDP üzerinden bulma işlemleri için önceden yapılandırılmış olan standart bir uç nokta tanımlayan çok noktaya yayın bağlama.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-103">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="0d0d6-104">Bu uç noktaya sabit bir sözleşme var ve iki WS bulma protokolünü sürümlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-104">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="0d0d6-105">Ayrıca, sabit bir UDP bağlama ve WS-bulma belirtimleri (WS-bulma Nisan 2005 veya WS-bulma V1.1) belirtildiği gibi varsayılan bir adresi olan...</span><span class="sxs-lookup"><span data-stu-id="0d0d6-105">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1)..</span></span>  
  
 <span data-ttu-id="0d0d6-106">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0d0d6-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="0d0d6-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0d0d6-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d0d6-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0d0d6-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <discoveryEndpoint>           <standardEndpoint                  discoveryMode="Adhoc/Managed"                  discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"                  maxResponseDelay="Timespan"                  multicastAddress="Uri"                   name="String" />       </discoveryEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d0d6-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d0d6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0d0d6-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d0d6-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0d0d6-111">Attributes</span></span>  
  
|<span data-ttu-id="0d0d6-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="0d0d6-112">Attribute</span></span>|<span data-ttu-id="0d0d6-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d0d6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d0d6-114">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="0d0d6-114">discoveryMode</span></span>|<span data-ttu-id="0d0d6-115">Keşif Protokolü modu belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-115">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="0d0d6-116">Geçerli değerler "Geçici" ve "Yönetilen" dir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-116">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="0d0d6-117">Yönetilen modunda bulunabilirlik Hizmetleri depo olarak davranan bir keşif proxy'si, protokolünü kullanır.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-117">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="0d0d6-118">Adhoc modu, UDP kullanılacak protokolü gerektirir kullanılabilir hizmetler bulmak için çok noktaya yayın mekanizması.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-118">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="0d0d6-119">Bu değer türünde <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-119">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="0d0d6-120">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="0d0d6-120">discoveryVersion</span></span>|<span data-ttu-id="0d0d6-121">WS bulma protokolünü iki sürümü birini belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-121">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="0d0d6-122">Geçerli değerler WSDiscovery11 ve WSDiscoveryApril2005 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-122">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="0d0d6-123">Bu değer türünde <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-123">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="0d0d6-124">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="0d0d6-124">maxResponseDelay</span></span>|<span data-ttu-id="0d0d6-125">Keşif Protokolü gecikme için maksimum değeri belirten bir Timespan değerine araştırma eşleşme veya eşleşme çözmek gibi belirli iletileri göndermeden önce bekler.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-125">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="0d0d6-126">Aynı anda tüm ProbeMatches gönderirse ağ storm neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-126">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="0d0d6-127">Bu oluşmasını önlemek için her ProbeMatch arasında rastgele bir gecikme ile ProbeMatches gönderilir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-127">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="0d0d6-128">Bu öznitelik tarafından ayarlanan değer için 0 aralığı rastgele gecikmeyi kullanılıyor.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-128">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="0d0d6-129">Bu öznitelik 0 olarak ayarlanırsa, ProbeMatches iletileri sıkı bir döngü herhangi bir gecikme olmadan gönderilir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-129">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="0d0d6-130">Aksi takdirde, tüm ProbeMatches iletileri göndermek için geçen toplam süre maxResponseDelay aşmadığından emin ProbeMatches iletileri bazı rastgele gecikme ile gönderilir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-130">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="0d0d6-131">Bu değer yalnızca Hizmetleri için geçerlidir, istemciler tarafından kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-131">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="0d0d6-132">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="0d0d6-132">multicastAddress</span></span>|<span data-ttu-id="0d0d6-133">Bulma ileti alma ve gönderme için kullanılacak bir çok noktaya yayın adresini belirtir URI.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-133">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="0d0d6-134">Varsayılan değer uyumluluğunu protokolü belirtimi için çok noktaya yayın adresi gibidir.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-134">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="0d0d6-135">Standart uç noktasının yapılandırma adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-135">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="0d0d6-136">Adı kullanılıyor `endpointConfiguration` yapılandırmasına standart bir uç noktasını bağlamak için hizmet uç noktası özniteliği.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-136">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d0d6-137">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d0d6-137">Child Elements</span></span>  
  
|<span data-ttu-id="0d0d6-138">Öğe</span><span class="sxs-lookup"><span data-stu-id="0d0d6-138">Element</span></span>|<span data-ttu-id="0d0d6-139">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d0d6-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d0d6-140">\<Udpannouncementendpoint ></span><span class="sxs-lookup"><span data-stu-id="0d0d6-140">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="0d0d6-141">UDP taşıma UDP uç noktası için yapılandırmanıza olanak tanıyan ayarlar koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-141">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d0d6-142">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0d0d6-142">Parent Elements</span></span>  
  
|<span data-ttu-id="0d0d6-143">Öğe</span><span class="sxs-lookup"><span data-stu-id="0d0d6-143">Element</span></span>|<span data-ttu-id="0d0d6-144">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0d0d6-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d0d6-145">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0d0d6-145">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="0d0d6-146">Standart uç noktalar koleksiyonu uç noktaları biriyle önceden tanımlanmış veya bunların özelliklerinin (adresi, bağlama, sözleşme) daha fazla sabit.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-146">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0d0d6-147">Örnek</span><span class="sxs-lookup"><span data-stu-id="0d0d6-147">Example</span></span>  
 <span data-ttu-id="0d0d6-148">Aşağıdaki örnek, bir UDP üzerinden bulma iletiler için dinleme hizmeti gösterir çok noktaya yayın taşıma.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-148">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <endpoint binding="basicHttpBinding"   
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="DiscoveryEndpoint"  
              kind="udpDiscoveryEndpoint" />  
  </service>  
  <standardEndpoints>  
    <udpDiscoveryEndpoint>  
      <standardEndpoint name="DiscoveryEndpoint"                         
                        version="WSDiscoveryApril2005" />  
    </udpDiscoveryEndpoint>  
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="0d0d6-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-149">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>