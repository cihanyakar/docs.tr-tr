---
title: '&lt;developmentMode&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982bc04e362f82760226b1cd2b8b3febe9cc7107
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612055"
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;developmentMode&gt; öğesi
Çalışma zamanı derlemeleri DEVPATH ortam değişkeni tarafından belirtilen dizinleri arar olup olmadığını belirtir.  
  
 \<Yapılandırma >  
\<çalışma zamanı >  
\<developmentMode >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**developerInstallation**|Çalışma zamanı derlemeleri DEVPATH ortam değişkeni tarafından belirtilen dizinleri arar olup olmadığını belirtir.|  
  
## <a name="developerinstallation-attribute"></a>developerInstallation özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**true**|Derlemeleri DEVPATH ortam değişkeni tarafından belirtilen dizinleri arar.|  
|**false**|Derlemeler DEVPATH ortam değişkeni tarafından belirtilen dizinlerde arama yapmaz. Varsayılan değer budur.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca geliştirme sırasında bu ayarı kullanın. Çalışma zamanı, tanımlayıcı adlı derlemeler DEVPATH içinde bulunan sürümlerinde denetlemez. Yalnızca bulduğu ilk derlemeyi de kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çalışma zamanı derlemeleri DEVPATH ortam değişkeni tarafından belirtilen dizinlerde arama gösterilmektedir.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- [Çalışma Zamanı Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Nasıl yapılır: DEVPATH kullanarak derlemelerin bulun](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
