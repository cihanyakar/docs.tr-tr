---
title: '&lt;Connectionpoolsettings&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: bf9229411143345847247f36de07b5c014d3f259
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149606"
---
# <a name="ltnamedpipetransportgt"></a>&lt;Connectionpoolsettings&gt;
Özel bir bağlamaya dahil olduğunda Adlandırılmış kanalları kullanarak ileti aktarılması bir kanal neden olan bir taşıma tanımlar.  
  
\<system.serviceModel>  
\<bağlamaları >  
\<customBinding >  
\<bağlama >  
\<namePipeTransport >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|ChannelInitializationTimeout|Alır veya ayarlar bir <xref:System.TimeSpan> kesilmeden önce bir kanal başlatma durumu olabilir en uzun süreyi belirler.|  
|ConnectionBufferSize|Alır veya ayarlar istemci veya hizmet serileştirilmiş ileti öbeğini iletmek için kullanılan arabellek boyutu.|  
|hostNameComparisonMode|Alır veya ayarlar üzerinde URI'yi eşleştirirken hizmete erişmek için ana bilgisayar adının kullanılıp kullanılmadığını gösteren bir değer.|  
|manualAddressing|Alır veya iletinin el ile adresleme gerekli olup olmadığını gösteren bir değer ayarlar.|  
|maxBufferPoolSize|Alır veya taşıma tarafından kullanılan herhangi bir arabellek havuzu bayt cinsinden en büyük boyutunu ayarlar.|  
|maxBufferSize|Alır veya kullanılacak arabelleğin en büyük boyutunu ayarlar. Akış iletileri için bu değer, arabelleğe alınmış modda okuma ait ileti üstbilgilerini olası en büyük boyutunu en az olmalıdır.|  
|MaxOutputDelay|Alır veya gönderilmeden önce ileti veya tam bir ileti bir öbek bellekte arabelleğe alınan kalabileceği süreyi en uzun aralığı ayarlar.|  
|maxPendingAccepts|Alır veya ayarlar hizmetine gelen bağlantıları işlemek için bir Dinleyicide bekleyen bir hizmetin olabilir kanal sayısı üst sınırı.|  
|maxPendingConnections|Alır veya ayarlar gönderme hizmetinde bekleyen bağlantıları sayısı.|  
|maxReceivedMessageSize|Alır ve izin verilen maksimum ileti boyutu, alınan bayt cinsinden ayarlar.|  
|transferMode|Alır veya iletileri ara belleğe veya akışa ile bağlantı sağlamaya yönelik aktarım gösteren bir değer ayarlar.|  
|[\<Tcptransport >, \<Connectionpoolsettings >](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Adlandırılmış kanal bağlama için ek bağlantı havuzu ayarlarını belirtir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<bağlama >](../../../../../docs/framework/misc/binding.md)|Özel bağlama tüm bağlama yeteneklerini tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
Bu aktarım "net.pipe://hostname/path" biçiminin bir URI'leri kullanır. Diğer URI bileşenlerini isteğe bağlıdır.  
  
`namedPipeTransport` Öğesi, başlangıç noktası adlandırılmış Aktarım Protokolü uygulayan özel bağlamayı oluşturmak için. Bu aktarım için makinede Windows Communication Foundation (WCF) - to - WCF iletişim kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
[Taşımalar](../../../../../docs/framework/wcf/feature-details/transports.md)   
[Taşıma seçme](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
[Bağlamaları](../../../../../docs/framework/wcf/bindings.md)   
[Bağlamaları genişletme](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
[Özel bağlamalar](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
[\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
