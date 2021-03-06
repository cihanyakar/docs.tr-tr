---
title: 'Nasıl yapılır: Birden Fazla Dosya Derleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3072be4e870b64edcea32bb7159db8c64c50d840
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183106"
---
# <a name="how-to-build-a-multifile-assembly"></a>Nasıl yapılır: Birden Fazla Dosya Derleme
Bu makalede, bir çoklu dosya derlemesi oluşturmak nasıl açıklanır ve yordamdaki her adımı gösteren kod sağlar.  
  
> [!NOTE]
>  Visual Studio IDE için C# ve Visual Basic yalnızca tek dosya derlemeleri oluşturmak için kullanılabilir. Çok dosyalı derlemeler oluşturmak istiyorsanız, Visual C++ ile komut satırı derleyicilerini veya Visual Studio kullanmanız gerekir.  
  
### <a name="to-create-a-multifile-assembly"></a>Bir çoklu dosya derlemesi oluşturmak için  
  
1.  Derlemede kod modülleriyle bütünleştirilmiş diğer modüller tarafından başvurulan ad alanlarını içeren tüm dosyaları derleyin. Modüllerin varsayılan uzantısı .netmodule'dür.  
  
     Örneğin, diyelim `Stringer` dosya adlı bir ad alanına sahip `myStringer`, adında bir sınıf içeren `Stringer`. `Stringer` Sınıf adında bir yöntem içerir `StringerMethod` , konsola tek satır yazar.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     Bu kodu derlemek için aşağıdaki komutu kullanın:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     Belirtme *Modülü* parametresiyle **/t:** derleyici seçeneği, dosyanın bir derleme olarak değil bir modül olarak derlenmesi gerektiğini gösterir. Derleyici adlı bir modül oluşturur `Stringer.netmodule`, derleyiciye eklenebilecek.  
  
2.  Kodda başvurulan diğer modülleri göstermek için gerekli derleyici seçeneklerini kullanarak tüm diğer modülleri derleyin. Bu adımı kullanan **/addmodule** derleyici seçeneği.  
  
     Aşağıdaki örnekte adlı kod modülünde `Client` Giriş noktasında, `Main` bir yönteme başvuran yöntemi `Stringer.dll` 1. adımda oluşturduğunuz modülü.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     Bu kodu derlemek için aşağıdaki komutu kullanın:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     Belirtin **/t:module** olacağından bu modül gelecekteki bir adımda bir derlemeye eklenir. Belirtin **/addmodule** seçeneğini kodda `Client` kod tarafından oluşturulan bir ad alanına başvurduğundan `Stringer.netmodule`. Derleyici adlı bir modül oluşturur `Client.netmodule` başka bir modül için bir başvuru içeren `Stringer.netmodule`.  
  
    > [!NOTE]
    >  C# Ve Visual Basic derleyicileri, aşağıdaki iki farklı sözdizimini kullanan çok dosyalı derlemeleri doğrudan oluşturmayı destekler.  
    >   
    >  -   İki dosyalı bir derleme oluşturun:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   Tek bir derleme iki dosyalı bir derleme oluşturur:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  Kullanım [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) derleme bildirimini içeren çıktı dosyasını oluşturmak için. Bu dosya, tüm modüller veya derlemenin parçası olan kaynaklar için başvuru bilgileri içerir.  
  
     Komut satırında, aşağıdaki komutu yazın:  
  
     **Al** \< *modül adı*> \<*modül adı*>... **/ main:**\<*yöntem adı*> **/out:**\<*dosya adı*>   **/target :**\<*derleme dosya türü*>  
  
     Bu komutta *modül adı* bağımsız değişkenleri derlemeye eklenecek her modülün adını belirtin. **/Main:** seçeneği derlemenin giriş noktası olan yöntem adını belirtir. **/Out:** seçeneği, derleme meta verilerini içeren çıktı dosyasının adını belirtir. **/Target:** seçeneği derlemenin bir konsol uygulaması yürütülebilir (.exe) dosyası, bir Windows çalıştırılabilir (.win) dosyası veya bir kitaplık (.lib) dosyası olduğunu belirtir.  
  
     Aşağıdaki örnekte, Al.exe adlı yürütülebilir bir konsol uygulaması olan derleme oluşturur. `myAssembly.exe`. Uygulama adlı iki modülden oluşur `Client.netmodule` ve `Stringer.netmodule`, ve yürütülebilir dosyanın adı `myAssembly.exe,` yalnızca birleştirme metaverilerini içerir. Derlemenin giriş noktası `Main` sınıfında yöntemi `MainClientApp`, bulunan `Client.dll`.  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     Kullanabileceğiniz [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) bir derlemenin içeriğini incelemek için ya da bir dosyanın bir derleme veya modül olup olmadığını belirlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
- [Bütünleştirilmiş Kodlar Oluşturma](../../../docs/framework/app-domains/create-assemblies.md)  
- [Nasıl yapılır: Bütünleştirilmiş Kod İçeriklerini Görüntüleme](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
- [Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
- [Çok Dosyalı Bütünleştirilmiş Kodlar](../../../docs/framework/app-domains/multifile-assemblies.md)
