---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 9ba54dc1744751efe4efad04f829cccce1244e0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145685"
---
# <a name="ltwebhttpgt"></a>&lt;webHttp&gt;
Bu öğeyi belirten <xref:System.ServiceModel.Description.WebHttpBehavior> yapılandırma yoluyla bir uç noktada. İle birlikte kullanıldığında bu davranışı [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standart bağlama için bir Windows Communication Foundation (WCF) hizmeti Web programlama modeli sağlar.  
  
 \<system.ServiceModel>  
\<davranışlar >  
\<endpointBehaviors >  
\<davranışı >  
\<webHttp >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Bu özelliği ayarlandığında `true`, WCF altyapısı kullanılacak en iyi biçimi belirler. Otomatik Biçim Seçimi varsayılan olarak devre dışıdır için geriye dönük uyumluluk. Otomatik Biçim Seçimi program aracılığıyla veya yapılandırma yoluyla etkinleştirilebilir.|  
|defaultBodyStyle|Döndürülen iletilerin varsayılan gövde stilini belirtir. Daha fazla bilgi için <xref:System.ServiceModel.Web.WebMessageBodyStyle> ve [WCF Web HTTP biçimlendirme](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|İletiler için varsayılan giden yanıt biçimini belirtir. Daha fazla bilgi için [WCF Web HTTP biçimlendirme](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Bir iç sunucu hatası bir FaultException oluşturulup oluşturulmayacağını belirten bayrağı alır veya ayarlar (HTTP durum kodu: 500) oluşur.|  
|helpEnabled|Alır veya Yardım sayfasının etkinleştirilip etkinleştirilmediğini belirleyen bir değer ayarlar.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<davranışı >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Uç nokta davranışları kümesini belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [AJAX Tümleştirme ve JSON Desteği](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
