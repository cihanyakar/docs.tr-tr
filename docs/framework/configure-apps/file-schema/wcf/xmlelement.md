---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 6a197f7aa29645a08a581bcee103eb94c0e20179
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147024"
---
# <a name="ltxmlelementgt"></a>&lt;XmlElement&gt;
İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirtir.  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<wsFederatedBinding >  
\<bağlama >  
\<Güvenlik >  
\<İleti >  
\<tokenRequestParameters >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|xmlElement|İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirten bir dize.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|Belirteç isteği parametreleri koleksiyonu. Her bir XML öğesi parametredir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [Kimlik Doğrulama ile Hizmet Kimliği](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Federasyon ve Verilen Belirteçler](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Özel Bağlamalarla Güvenlik Özellikleri](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Federasyon ve Verilen Belirteçler](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)
