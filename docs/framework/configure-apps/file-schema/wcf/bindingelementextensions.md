---
title: '&lt;bindingElementExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: ee67df95de715f0b21250bbf5739f84b4945d719
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151455"
---
# <a name="ltbindingelementextensionsgt"></a>&lt;bindingElementExtensions&gt;
Bu bölümde bir makineden özel bağlama öğesinin kullanımını etkinleştirir veya uygulama yapılandırma dosyası. Özel bağlama öğesini kullanarak bu koleksiyona ekleyebilirsiniz `add` anahtar sözcüğü ve ayarı `type` bir bağlama öğesi uzantısı için bir öğenin özniteliği hem de `name` özniteliği için özel bir bağlama öğesi.  
  
 Bağlama uzantıları, özel bağlamalar bir parçası olarak kullanmak için kullanıcı tanımlı bağlama öğeleri oluşturmak kullanıcının etkinleştirir. Programlı olarak soyut sınıf uygulayan bir tür bir bağlama uzantısı olan <xref:System.ServiceModel.Channels.BindingElement>. Yapılandırma dosyasında `bindingElementExtensions` bölümü, bir uzantı öğesi tanımlamak için kullanılır.  
  
 Aşağıdaki örnekte `add` öğesi hem de `name` özniteliği bir bağlama uzantının ekleneceği `bindingElementExtensions` yapılandırma dosyasının.  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Yapılandırma yeteneklerini öğesine eklemek için yazmak ve kaydetmek kullanıcı gerekli bir `bindingElementExtensionSection` öğesi. Bunun hakkında daha fazla bilgi için bkz. <xref:System.Configuration> belgeleri.  
  
 Öğesi ve kendi yapılandırma türü tanımlandıktan sonra uzantıyı aşağıdaki örnekte gösterildiği gibi özel bir bağlama bir parçası olarak kullanılabilir.  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [Bağlamaları Genişletme](../../../../../docs/framework/wcf/extending/extending-bindings.md)
