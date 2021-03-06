---
title: '&lt;oidMap&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: badab8200a4b10fdc13987dfe39ebfebd4d1f7cf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143174"
---
# <a name="ltoidmapgt-element"></a>&lt;oidMap&gt; öğesi
ASN.1 nesne tanımlayıcısını (OID) eşlemeleri için sınıflar içerir.  
  
 \<Yapılandırma >  
\<mscorlib >  
\<cryptographySettings >  
\<oidMap >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<oidEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Kolay ad ASN.1 OID eşler.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`cryptographySettings`|Şifreleme ayarlarını içerir.|  
|`mscorlib`|İçeren `cryptographySettings` öğesi.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir  **\<oidMap >** RIPEMD 160 karma algoritması için bu karma algoritmayı uygulaması için bir OID eşlemesi içerecek şekilde öğesi.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Şifreleme Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
- [Şifreleme Hizmetleri](../../../../../docs/standard/security/cryptographic-services.md)  
- [Şifreleme Sınıflarını Yapılandırma](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
- [Nesne Tanımlayıcılarını Şifreleme Algoritmalarıyla Eşleme](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
