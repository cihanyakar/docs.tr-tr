---
title: '&lt;baseAddressPrefixFilter&gt; &lt;ekleme&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: ece3178c48c84c609ab959a5cfc426062de9255f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145607"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a>&lt;baseAddressPrefixFilter&gt; &lt;ekleme&gt;
IIS içinde bir Windows Communication Foundation (WCF) uygulaması uygun Internet Information Services (IIS) bağlamalarını seçmek için bir mekanizma sağlayan doğrudan bir filtre belirtir bir yapılandırma öğesini temsil eder.  
  
 \<system.ServiceModel>  
\<serviceHostingEnvironment >  
\<baseAddressPrefixFilters >  
\<Ekle >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Ön eki|Temel adres bir kısmen eşleştirmek için kullanılan URI.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|IIS içinde bir Windows Communication Foundation (WCF) uygulaması uygun IIS bağlamalarını seçmek için bir mekanizma sağlar doğrudan filtreleri belirten yapılandırma öğelerinin koleksiyonu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Önek filtresi, hangi bir URI'leri olan hizmet tarafından kullanılmak üzere belirtmek paylaşılan barındırma sağlayıcıları için bir yol sağlar. Bu, birden çok uygulama ile aynı sitede aynı düzeni için farklı temel adresler barındırmak için paylaşılan ana bilgisayarları etkinleştirir.  
  
 IIS Web siteleri, sanal dizinler içeren sanal uygulamalar için kapsayıcılardır. Uygulama bir sitedeki bir veya daha fazla IIS bağlama aracılığıyla erişilebilir. IIS bağlamaları, iki bilgi parçasını sağlar: bağlama protokolü ve bağlama bilgileri. İletişim oluştuğu Düzen Protokolü (örneğin, HTTP) bağlama tanımlar ve bağlama bilgileri (örneğin, IP adresi, bağlantı noktası, AnaBilgisayarÜstbilgisi) siteye erişmek için kullanılan verileri içerir.  
  
 IIS, her şeması için birden çok taban adresi sonuçlanır her site için birden fazla IIS bağlamaları belirtme destekler. Bir site altında barındırılan bir WCF hizmeti yalnızca bir temel adres bir bağlamayı her şeması için izin verdiğinden, barındırılan hizmetin gerekli temel adresini seçmek için önek filtreleme özelliğini kullanabilirsiniz. IIS tarafından sağlanan gelen temel adresler, isteğe bağlı bir ön ek listesi filtre göre filtrelenir.  
  
 Örneğin, siteniz aşağıdaki temel adresler içerebilir.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Uygulama etki alanı düzeyinde bir önek filtre belirtmek için aşağıdaki yapılandırma dosyası kullanabilirsiniz.  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 Bu örnekte, `net.tcp://test1.fabrikam.com:8000` ve `http://test2.fabrikam.com:9000` doğrudan geçiş yapılacak izin, kendi şemaları için yalnızca temel adresleridir.  
  
 Öneki belirtilmediğinde, varsayılan olarak, tüm adresleri üzerinden geçirilir. Önek belirleyerek eşleşen temel adresini doğrudan geçiş yapılacak bu şema için yalnızca sağlar.  
  
> [!NOTE]
>  Filtre, herhangi bir joker karakterleri desteklemiyor. Ayrıca, IIS tarafından sağlanan baseAddresses adresleri yok diğer düzenleri bağlı olabilir `baseAddressPrefixFilters` listesi. Bu adresleri filtrelenir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Barındırma](../../../../../docs/framework/wcf/feature-details/hosting.md)
