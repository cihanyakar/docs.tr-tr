---
title: Bir WPF Uygulamasını Dağıtma (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 800e8a1e8400a11a7eadd0c352f5bfab334c9fbb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511714"
---
# <a name="deploying-a-wpf-application-wpf"></a>Bir WPF Uygulamasını Dağıtma (WPF)
Windows Presentation Foundation (WPF) uygulamaları tasarlandıktan sonra bunların dağıtılması gerekir. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ve .NET Framework çeşitli dağıtım teknolojileri içerir. Dağıtım teknolojisi dağıtmak için kullanılan bir [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulama uygulama türüne bağlıdır. Bu konu, her dağıtım teknolojisi kısa bir genel bakış ve her dağıtım gereksinimleri ile birlikte nasıl kullanıldığını sağlar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulama türü.  
  
   
<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Dağıtım teknolojileri  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ve .NET Framework dahil olmak üzere çeşitli dağıtım teknolojileri şunları içerir:  
  
-   XCopy dağıtım.  
  
-   [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] Dağıtım.  
  
-   [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] Dağıtım.  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>XCopy dağıtım  
 XCopy dağıtım XCopy komut satırı program dosyaları bir konumdan diğerine kopyalamak için kullanımını gösterir. XCopy dağıtım şu durumlarda uygundur:  
  
-   Uygulama kendi içinde bağımsızdır. İstemciyi çalıştırmak için güncelleştirmeniz gerekmez.  
  
-   Uygulama dosyaları taşınması gerekir bir konumdan diğerine gibi bir yapı konumundan (yerel diskte, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] dosya paylaşımı vb.) için bir yayımlama konumu (Web sitesi [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] dosya paylaşımı vb.).  
  
-   Uygulama (Başlat menüsü kısayolundan, Masaüstü simgesi vb.) tümleşik Kabuk gerektirmez.  
  
 XCopy basit dağıtım senaryoları için uygun olsa da, daha karmaşık dağıtım özellikleri gerekli olduğunda sınırlı. Özellikle, genellikle XCopy kullanarak, oluşturma, yürütme ve dağıtım sağlam bir şekilde yönetmek için betikleri sürdürmek için ek yüke neden olur. Ayrıca, sürüm oluşturma, kaldırma veya geri alma Xcopy komutunu desteklemiyor.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] kolayca istemcilere dağıtılan ve müstakil yürütülebilir paketlenmiş uygulamalar sağlar. Ayrıca, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] ile birlikte yüklenen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ve Masaüstü ve Başlat menüsü programları Denetim Masası ile tümleştirme sağlar.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] Yükleme ve kaldırma uygulamalarının kolaylaştırır, ancak yüklü uygulamaları bir sürüm oluşturma açısından güncel kalmasını sağlamaya yönelik olanakları sağlamaz.  
  
 Hakkında daha fazla bilgi için [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], bkz: [Windows Installer dağıtımı](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce dağıtımı  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] Web stili olmayan Web uygulamaları için uygulama dağıtımı sağlar. Uygulamalar için yayımlanan ve Web veya dosya sunucusundan dağıtılan. Ancak [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] tam desteklemez istemci çeşitli özellikleri [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]-yüklü uygulamalar, aşağıdakileri içeren bir alt kümesini destekler:  
  
-   Başlangıç menüsünde ve programları Denetim Masası ile tümleştirme.  
  
-   Sürüm oluşturma, geri alma ve kaldırma.  
  
-   Çevrimiçi yükleme modunu, her zaman bir uygulamanın dağıtım konumuna başlatır.  
  
-   Yeni sürümleri yayımlandığında otomatik güncelleştirme.  
  
-   Dosya uzantıları kaydı.  
  
 Hakkında daha fazla bilgi için [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], bkz: [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>WPF Uygulamalarını Dağıtma  
 Dağıtım seçenekleri bir [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulama, uygulama türüne bağlıdır. Bir dağıtım perspektifinden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] üç önemli uygulama türü vardır:  
  
-   Tek başına uygulamalar.  
  
-   Yalnızca işaretleme [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] uygulamalar.  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Tek başına uygulamaları dağıtma  
 Tek başına uygulamalar kullanılarak dağıtılır [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] veya [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Her iki durumda da, tek başına uygulamalar çalıştırmak için tam güven gerektirir. Tam güven olduğundan otomatik olarak verilen kullanılarak dağıtılan tek başına uygulamalar [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Kullanılarak dağıtılan uygulamalara [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] otomatik olarak tam güven izni yok. Bunun yerine, [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] güvenlik iletişim kutusu, kullanıcıların bir tek başına uygulama yüklenmeden önce kabul etmesi gerekir uyarı görüntüler. Kabul tek başına uygulama yüklenir ve tam güven izni. Aksi durumda, tek başına uygulama yüklü değil.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Yalnızca XAML uygulamaları dağıtma  
 Yalnızca işaretleme [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfaları genellikle yayımlanır Web sunucularına gibi [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] sayfaları ve görüntülenebilir [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]. Yalnızca işaretleme [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfaları, Internet bölgesi izin kümesi tarafından tanımlanan bir kısıtlama olmadan bir kısmi güven güvenliği korumalı alan içinde çalıştırın. Bu bir eşdeğer güvenlik sandbox sağlar [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]-tabanlı Web uygulamaları.  
  
 İçin güvenlik hakkında daha fazla bilgi için [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulamaları, [güvenlik](../../../../docs/framework/wpf/security-wpf.md).  
  
 Yalnızca işaretleme [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfaları yüklenebilir yerel dosya sistemine XCopy kullanarak veya [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Bu sayfaları kullanarak görüntülenebilir [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] ya da Windows Explorer.  
  
 XAML hakkında daha fazla bilgi için bkz: [XAML genel bakış (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>XAML tarayıcı uygulamaları dağıtma  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] Dağıtılacak aşağıdaki üç dosyayı gerektiren derlenmiş uygulamalar şunlardır:  
  
-   *ApplicationName*.exe: çalıştırılabilir derlemesinin uygulama dosyası.  
  
-   *ApplicationName*.xbap: dağıtım bildirimi.  
  
-   *ApplicationName*. exe.manifest: uygulama bildirimi.  
  
> [!NOTE]
>  Dağıtım ve uygulama bildirimleri hakkında daha fazla bilgi için bkz: [WPF uygulaması oluşturma](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Bu dosyalar üretilen olduğunda bir [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] oluşturulmuştur. Daha fazla bilgi için [nasıl yapılır: yeni bir WPF tarayıcı uygulaması projesi oluşturma](https://msdn.microsoft.com/library/72ef4d90-e163-42a1-8df0-ea7ccfd1901f). Yalnızca biçimlendirme gibi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfaları [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] kullanılarak görüntülenmesi ve genellikle bir Web sunucusuna yayımlanan [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] dağıtım tekniklerden birini kullanarak istemcilere dağıtılabilir. Ancak, [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] önerilir çünkü aşağıdaki özellikleri sağlar:  
  
1.  Yeni bir sürümü yayımlandığında otomatik güncelleştirmeler.  
  
2.  Ayrıcalıklar yükseltme [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] tam güven ile çalışıyor.  
  
 Varsayılan olarak, ClickOnce .deploy uzantısını uygulama dosyalarıyla yayımlar. Bu sorunlara neden olabilir, ancak devre dışı bırakılabilir. Daha fazla bilgi için [sunucu ve istemci yapılandırma sorunları ClickOnce Dağıtımları içinde](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Dağıtma hakkında daha fazla bilgi için [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], bkz: [WPF XAML tarayıcı uygulamalarına genel bakış](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>.NET Framework2ü yükleme  
 Çalıştırılacak bir [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulama, Microsoft .NET Framework, istemcide yüklü olması gerekir. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] istemciler ile .NET Framework yüklü olup olmadığını otomatik olarak algılar, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tarayıcıda tutulan uygulamalar görüntülendiğinde. .NET Framework yüklü değilse [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] yüklemek için kullanıcıların ister.  
  
 .NET Framework yüklü olup olmadığını algılamak için [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] geri dönüş olarak kayıtlı bir önyükleyici uygulaması içerir [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] Aşağıdaki uzantılara sahip içerik dosyaları için işleyici: .xaml, .xps .xbap ve .application. Şu dosya türlerini gidin ve .NET Framework istemcide yüklü değil, önyükleyici uygulama yüklemek için izin ister. İzin verilmez, .NET Framework ne uygulama yüklenir.  
  
 İzin verilirse, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] indirir ve yükler .NET Framework kullanarak [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. .NET Framework'ün başarılı yüklemeden sonra başlangıçta istenen dosya yeni bir tarayıcı penceresinde açılır.  
  
 .NET framework otomatik algılamayı edinilebilir [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)], ve [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] olan istemciler [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] veya sonraki bir sürümü yüklü.  
  
 Daha fazla bilgi için [.NET Framework ve uygulamaları dağıtma](../../../../docs/framework/deployment/index.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF Uygulaması Derleme](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Güvenlik](../../../../docs/framework/wpf/security-wpf.md)
