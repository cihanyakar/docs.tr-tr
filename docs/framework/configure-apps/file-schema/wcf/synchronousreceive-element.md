---
title: '&lt;synchronousReceive&gt; öğesi'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: bc89470900e50e4d3e522682b39b20e21a66b284
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147388"
---
# <a name="ltsynchronousreceivegt-element"></a>&lt;synchronousReceive&gt; öğesi
Bu yapılandırma öğesi, bir hizmet veya istemci uygulamasında ileti alma için çalışma zamanı davranışını belirtmek için kullanılır. Herhangi bir öznitelik veya alt öğe yok.  
  
 \<system.ServiceModel>  
\<davranışlar >  
\<endpointBehaviors >  
\<davranışı >  
\<synchronousReceive >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<davranışı >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Bir uç nokta davranışı belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eş zamanlı alma kullanmak yerine varsayılan olarak zaman uyumsuz kanal dinleyicisi istemek için bu davranışı kullanın. Windows Communication Foundation (WCF) pompa kabul edilen her kanal için yeni bir iş parçacığı verir. Çok sayıda kanalları varsa, çalışan iş parçacığı dışında olasılığı yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
