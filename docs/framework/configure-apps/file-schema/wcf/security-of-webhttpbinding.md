---
title: '&lt;webHttpBinding&gt; &lt;güvenliği&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 12477c36c2771621e5f8b88ce245746c6f5ec120
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145412"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a>&lt;webHttpBinding&gt; &lt;güvenliği&gt;
Yapılandırılmış uç noktaya ilişkin güvenlik gereksinimlerini belirleyen bir [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<webHttpBinding>  
\<bağlama >  
\<Güvenlik >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|mod|Aktarım düzeyi güvenlik veya hiçbir güvenlik bir uç noktası tarafından kullanılıp kullanılmayacağını belirtir. Varsayılan, `None` değeridir. Bu öznitelik türünde <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>mod özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|Hiçbiri|Güvenlik devre dışı bırakıldı.|  
|Taşıma|HTTPS kullanarak güvenliği sağlanır. Hizmet SSL sertifikaları ile yapılandırılması gerekir. İleti tamamen HTTPS kullanan güvenli ve hizmet hizmet SSL sertifikasını kullanarak istemci tarafından doğrulanır. İstemci kimlik doğrulaması aracılığıyla denetlenir `ClientCredentialType` özniteliği [ \<aktarım >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Bu mod, ileti bütünlüğü ve gizliliği sağlamaz. Bu, HTTP tabanlı istemci kimlik doğrulaması sağlar. Bu mod, dikkatli kullanılmalıdır. Burada aktarım güvenliği (IPSec gibi) diğer yollarla sağlanmaktadır ve yalnızca istemci kimlik doğrulaması WCF altyapısı tarafından sağlanan ortamlarda kullanılmalıdır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<taşıma >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|Taşıma güvenlik ayarlarını tanımlar. Bu öğe için karşılık gelen <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> türü.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Bu SOAP iletileri yerine HTTP isteklerine yanıt Windows Communication Foundation (WCF) Web Hizmetleri için uç noktaları yapılandırmak için kullanılan bir bağlama öğesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Kimlik Bilgisi Türü Seçme](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)  
 [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<bağlama >](../../../../../docs/framework/misc/binding.md)  
 [WCF Web HTTP Programlama Modeli](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
