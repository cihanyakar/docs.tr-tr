---
title: '&lt;Usesmallınternalthreadstacks&gt; öğesi'
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23a38297526090f1df35f8541026accd5a5cb9bc
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613797"
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;Usesmallınternalthreadstacks&gt; öğesi
Ortak dil çalışma zamanı (CLR) bellek miktarını azaltmak istekleri, dahili olarak, bu iş parçacıkları için varsayılan yığın boyutu kullanmak yerine kullanan belirli iş parçacıklarını oluşturduğunda açık yığın boyutlarını belirterek kullanır.  
  
 \<Yapılandırma > öğesi  
\<çalışma zamanı > öğesi  
\<Usesmallınternalthreadstacks > öğesi  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Etkin|Gerekli öznitelik.<br /><br /> Dahili olarak kullandığı belirli bir iş parçacığı oluşturur CLR kullanın açık yığın boyutu varsayılan yığın boyutu yerine, istenip istenmeyeceğini belirtir. Açık yığın boyutu varsayılan yığın boyutu 1 MB küçüktür.|  
  
## <a name="enabled-attribute"></a>etkin Öznitelik  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|true|Açık yığın boyutlarını isteyin.|  
|false|Varsayılan yığın boyutunu kullanın. İçin varsayılan [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstek dikkate alınır, iç iş parçacıkları için CLR kullanan açık bir iş parçacığı boyutları varsayılan boyuttan daha küçük olduğundan, bu yapılandırma öğesi, bir işlemde daha az sanal bellek kullanımı istemek için kullanılır.  
  
> [!IMPORTANT]
>  Bu yapılandırma öğesi, mutlak bir gereksinim yerine CLR isteğidir. İçinde [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], isteğin yalnızca x86 için geçerli olur mimarisi. Bu öğe CLR'ın gelecek sürümlerinde tamamen yoksayıldı ya da seçili iç iş parçacıkları için kullanılan her zaman açık yığın boyutlarını değiştirilmiştir.  
  
 CLR, isteği kabul eder, daha küçük yığın boyutlarını yığın olası hale getirebilecek çünkü bu yapılandırma öğesi daha küçük sanal bellek kullanımı için güvenilirlik arasında denge kurar belirterek büyük olasılıkla taşıyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, CLR kullanım açık yığın belirli dahili olarak kullandığı iş parçacıklarının boyutları istek gösterilmiştir.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- [Çalışma Zamanı Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)
