---
title: WS-I Temel Profil 1.1 Birlikte Çalışabilir Hizmetler Oluşturma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: f32308a17e2934b6884140307074f97e6b51f5f9
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982860"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>WS-I Temel Profil 1.1 Birlikte Çalışabilir Hizmetler Oluşturma
Bir WCF Hizmeti uç noktası ile birlikte çalışabilir olacak şekilde yapılandırmak için [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web hizmeti istemcileri:  
  
-   Kullanım <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> türü, hizmet uç noktası için bağlama türü olarak.  
  
-   Geri çağırma ve oturumu sözleşme özellikleri veya hareket davranışları, hizmet uç noktasında kullanmayın  
  
 İsteğe bağlı olarak, HTTPS ve bağlamadaki aktarım düzeyinde istemci kimlik doğrulaması için destek de etkinleştirebilirsiniz.  
  
 Aşağıdaki özellikleri <xref:System.ServiceModel.BasicHttpBinding> sınıfı WS ötesine işlevselliği gerektiren-ı Basic Profile 1.1:  
  
-   İleti, ileti aktarım en iyi duruma getirme mekanizması (MTOM) kodlama denetlenmektedir <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> özelliği. Bu özellik, kendi varsayılan değerde bırakın <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> MTOM kullanmayacak şekilde.  
  
-   İleti tarafından denetlenen güvenlik <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> değeri, WS ile uyumlu olan WS-güvenlik desteği sağlar-ı temel güvenlik profili 1.0. Bu özellik, kendi varsayılan değerde bırakın <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> WS-Security kullanmayı.  
  
 Bir WCF hizmeti için meta veriler kullanılabilir hale getirmek için [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Web hizmeti istemcisi oluşturma araçlarını kullanın: [Web Hizmetleri Açıklama Dili Aracı (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Hizmetleri bulma Aracı (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)ve `Add Web Reference` özellik Visual Studio'da; meta verileri yayını etkinleştirmeniz gerekir. Daha fazla bilgi için [meta veri uç noktalarını yayımlama](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek kod ile uyumlu bir WCF uç noktası ekleme gösterir [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web hizmet istemci kodu ve alternatif olarak, bir yapılandırma dosyası.  
  
### <a name="code"></a>Kod  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET Web Hizmetleri ile Birlikte Çalışabilirlik](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
