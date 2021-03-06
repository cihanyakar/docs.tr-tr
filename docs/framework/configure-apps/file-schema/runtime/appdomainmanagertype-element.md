---
title: '&lt;appDomainManagerType&gt; öğesi'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e7f37fd652ce98e24d2e2e99edcd3d59a0e597b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610439"
---
# <a name="ltappdomainmanagertypegt-element"></a>&lt;appDomainManagerType&gt; öğesi
Varsayılan uygulama etki alanı için uygulama etki alanı yöneticisi olarak görev yapan türünü belirtir.  
  
 \<Yapılandırma >  
\<çalışma zamanı >  
\<appDomainManagerType >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`value`|Gerekli öznitelik. İşlem varsayılan uygulama etki alanı için uygulama etki alanı yöneticisi olarak görev yapan ad alanı dahil türünün adını belirtir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulama etki alanı yöneticisi türünü belirtmek için bu iki öğe belirtmeniz gerekir ve [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) öğesi. Diğer, bu öğelerden herhangi birini belirtilmezse, yoksayılır.  
  
 Varsayılan uygulama etki alanına yüklendiğinde <xref:System.TypeLoadException> belirtilen türü tarafından belirtilen derlemede mevcut değilse oluşturulur [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) öğesi; ve için işlem başarısız başlatın.  
  
 Varsayılan uygulama etki alanı için uygulama etki alanı yöneticisi türü belirttiğinizde, uygulama etki alanı yöneticisi türü oluşturulan varsayılan uygulama etki alanından diğer uygulama etki alanları devralır. Kullanım <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> ve <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> özellikler farklı uygulama etki alanı yöneticisi türü için yeni bir uygulama etki alanı belirtin.  
  
 Uygulama etki alanı yöneticisi türünü belirtme, uygulama tam güven gerektirir. (Örneğin, masaüstünde çalışan bir uygulama tam güven yok.) Uygulama tam güven yoksa bir <xref:System.TypeLoadException> oluşturulur.  
  
 Tür ve ad alanı için kullanılan aynı biçimdir <xref:System.Type.FullName%2A?displayProperty=nameWithType> özelliği.  
  
 Bu yapılandırma öğesi yalnızca [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] ve daha sonra.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, uygulama etki alanı yöneticisi varsayılan uygulama etki alanı için bir işlem olduğunu belirtmek gösterilmektedir `MyMgr` yazın `AdMgrExample` derleme.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
- [\<appDomainManagerAssembly > öğesi](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
- [Çalışma Zamanı Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [SetAppDomainManagerType Yöntemi](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
