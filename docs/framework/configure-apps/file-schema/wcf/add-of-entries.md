---
title: '&lt;giriş&gt; &lt;ekleme&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 5a61aefd92390eefb95d1f3e39236e53fa264990
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151512"
---
# <a name="ltaddgt-of-ltentriesgt"></a>&lt;giriş&gt; &lt;ekleme&gt;
Bu önceden tanımlanmış bir istemci uç noktası için bir filtre eşlemeleri bir yönlendirme girişi temsil eder. Bu filtreyle eşleşen iletileri bu hedefe gönderilir.  
  
 \<system.serviceModel>  
\<Yönlendirme >  
\<filterTables >  
\<filterTable >  
\<Giriş >  
\<Ekle >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|backupList|Yedekleme uç noktaları listesini bir başvuru belirten bir dize.|  
|uç noktası|Bir başvuru tarafından belirtilen filtreyle eşleşen iletileri alacak bir istemci uç noktası belirten bir dize `filterName` özniteliği.|  
|filterName|Bir filtre öğeye başvuru belirten bir dize.|  
|öncelik|Bu giriş önceliğini belirten bir tamsayı.<br /><br /> Yönlendirme tablosundaki girdileri en düşük önceliği olan 0 ile önceliğine bağlı olarak değerlendirilir. Tüm girişleri belirli bir öncelik için eşzamanlı olarak değerlendirilir, hiçbir eşleşen girişi bulundu geçerli öncelik için öncelik düzeye değerlendirilir.<br /><br /> Bu değer isteğe bağlıdır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Yönlendirme >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Yönlendirme eşleme girişleri içeren bir yapılandırma bölümü.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
