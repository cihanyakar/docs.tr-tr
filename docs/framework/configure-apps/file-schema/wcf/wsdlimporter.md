---
title: '&lt;WsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 43c1a50c740cd9c75ee641e4ac4d0fa8ea3ca36b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144996"
---
# <a name="ltwsdlimportergt"></a>&lt;WsdlImporter&gt;
WS-Policy ekli Web Hizmetleri Açıklama Dili (WSDL) 1.1 meta verileri içe aktaran tüm WSDL ımporters belirtir.  
  
\<system.ServiceModel>  
\<İstemci >  
\<meta veri >  
\<wsdlImporters >  
\<WsdlImporter >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`type`|Bu öğenin türü.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<wsdlImporters >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|WS-Policy ekli Web Hizmetleri Açıklama Dili (WSDL) 1.1 meta verileri içe aktaran tüm WSDL ımporters belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir WSDL içeri Aktarıcı yanı sıra meta veri alma, bu sözleşmeyi temsil eden çeşitli sınıf bilgilerini ve uç nokta bilgileri dönüştürmek için kullanılır. Sözleşmeyi ve uç nokta bilgilerini ve kullanıma alma hataları ve içeri aktarma ve dönüştürme işlemi için uygun tür bilgilerini kabul özellikleri seçerek alabilirsiniz. İçeri aktarma bağlama bilgileri ve ilke belgeleri, WSDL belgeleri, WSDL uzantıları ve XML Şeması belgeleri için erişim sağlayan özellikleri de destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [WCF İstemci Yapılandırması](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [İstemciler](../../../../../docs/framework/wcf/feature-details/clients.md)
