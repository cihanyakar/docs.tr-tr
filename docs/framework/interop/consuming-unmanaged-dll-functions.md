---
title: Yönetilmeyen DLL İşlevlerini Kullanma
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f2dc9fccf6718c4edebc26efcdda71b41873a3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195248"
---
# <a name="consuming-unmanaged-dll-functions"></a>Yönetilmeyen DLL İşlevlerini Kullanma
Platform çağırma etkinleştirir Win32 API olanlar gibi dinamik bağlantı kitaplıklarını (DLL'ler) uygulanan yönetilmeyen işlevleri çağırmak için kod yönetilen bir hizmettir. Dışarı aktarılan bir işlevi çağırır bulur ve bağımsız değişkenlerinden (tamsayı, dizeler, diziler, yapılar ve benzeri) gerektiği gibi birlikte çalışabilirlik sınırında sürekliliğe devreder.  
  
 Bu bölümde, yönetilmeyen DLL işlevlerini kullanma ile ilgili görevleri tanıtır ve çağırma platformu hakkında daha fazla bilgi sağlar. Aşağıdaki görevlerin yanı sıra genel önemli noktalar ve ek bilgiler ve örnekler sağlayan bir bağlantı vardır.  
  
#### <a name="to-consume-exported-dll-functions"></a>Dışa aktarılan DLL işlevleri kullanmak için  
  
1.  [DLL'lerde işlevleri tanımlama](../../../docs/framework/interop/identifying-functions-in-dlls.md).  
  
     En düşük düzeyde, işlevin adını ve içerdiği DLL'in adı belirtmeniz gerekir.  
  
2.  [DLL işlevleri için bir sınıf oluşturmanız](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).  
  
     Varolan bir sınıfı kullanın, yönetilmeyen her işlev için bağımsız bir sınıf oluşturun veya ilgili yönetilmeyen işlevler bir dizi içeren bir sınıf oluşturun.  
  
3.  [Yönetilen kodda prototipler oluşturma](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
     [Visual Basic] Kullanım **Declare** deyimiyle **işlevi** ve **LIB** anahtar sözcükleri. Bazı nadir durumlarda, kullandığınız **DllImportAttribute** ile **paylaşılan işlevi** anahtar sözcükleri. Bu gibi durumlarda, daha sonra bu bölümde açıklanmıştır.  
  
     [C#] Kullanımı **DllImportAttribute** işlevi ve DLL tanımlamak için. Yöntemi işaretlemek **statik** ve **extern** değiştiriciler.  
  
     [C++] Kullanım **DllImportAttribute** işlevi ve DLL tanımlamak için. Sarmalayıcı yöntemini işaretlemek veya işlevini **extern "C"**.  
  
4.  [Bir DLL işlevini çağırmak](../../../docs/framework/interop/calling-a-dll-function.md).  
  
     Yönetilen herhangi bir yöntemi gibi yönetilen sınıfınıza yöntemi çağırın. [Yapıları geçirme](../../../docs/framework/interop/passing-structures.md) ve [geri çağırma işlevlerini uygulama](../../../docs/framework/interop/callback-functions.md) özel durumları olan.  
  
 Nasıl oluşturulacağını gösteren örnekler için. NET tabanlı bildirimler platformuyla kullanılacak çağırmak için bkz: [Platform Çağırma ile veri hazırlama](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="a-closer-look-at-platform-invoke"></a>Yakından platform çağırma  
 Platform çağırma dışarı aktarılan işlevleri bulun ve bunların bağımsız değişkenleri, çalışma zamanında hazırlamak için meta verileri kullanır. Aşağıdaki çizim bu süreci göstermektedir.  
  
 ![Platform Çağırma](../../../docs/framework/interop/media/pinvoke.gif "PInvoke")  
Bir platform çağırma yönetilmeyen DLL işlev çağrısı  
  
 Yönetilmeyen bir işlev çağırır olduğunda platform çağırma aşağıdaki eylemler dizisini gerçekleştirir:  
  
1.  İşlevi içeren DLL bulur.  
  
2.  DLL belleğine yükler.  
  
3.  Bellekte bir işlevin adresini bulur ve bağımsız olarak gerekli veri hazırlama yığına iter.  
  
    > [!NOTE]
    >  İşlev yalnızca ilk çağrıda işlevin adresini bellekte bulma bulma ve DLL yüklenirken oluşur.  
  
4.  Yönetilmeyen işlev denetimine aktarımlarına.  
  
 Platform çağırma yönetilen çağırana yönetilmeyen işlevi tarafından oluşturulan oluşturur özel durumlar.

## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen Kod ile Birlikte Çalışma](../../../docs/framework/interop/index.md)  
 [Platform Çağırma Örnekleri](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Birlikte Çalışma için Hazırlama](../../../docs/framework/interop/interop-marshaling.md)  
