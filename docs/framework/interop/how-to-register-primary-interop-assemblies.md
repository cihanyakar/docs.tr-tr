---
title: 'Nasıl yapılır: Birincil Birlikte Çalışma Derlemelerini Kaydetme'
ms.date: 03/30/2017
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9017e8dc50914bbffbcea52192e6ec10fbc7a6df
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840829"
---
# <a name="how-to-register-primary-interop-assemblies"></a>Nasıl yapılır: Birincil Birlikte Çalışma Derlemelerini Kaydetme

Sınıflar yalnızca COM birlikte çalışma tarafından sıralanabilir ve her zaman arabirimleri olarak sıralanmış. Bazı durumlarda, sınıf hazırlamak için kullanılan arabirimi sınıf arabirimi bilinir. Tercih ettiğiniz bir arabirime sahip sınıf arabirimi geçersiz kılma hakkında daha fazla bilgi için bkz: [COM çağrılabilir sarmalayıcısı](../../../docs/framework/interop/com-callable-wrapper.md).

 Bir .NET Framework uygulamasından COM türlerini kullanmak isteyen herhangi bir geliştirici birlikte çalışma derlemesi oluşturabilirsiniz ancak bunun yapılması, bu nedenle bir sorun oluşturur. Her bir geliştirici alır ve geliştirici olanlar içeri aktarılıp başka bir geliştirici tarafından imzalanmış uyumlu benzersiz türleri kümesi oluşturan bir COM tür kitaplığı imzalar. Her geliştirici için satıcı tarafından sağlanan ve imzalı birincil birlikte çalışma derlemesi elde etmek bu tür uyumsuzluk sorun çözümüdür.

 Diğer uygulamalar için üçüncü taraf COM türleri açığa planlıyorsanız, her zaman aynı yayımcının tanımlar tür kitaplığı tarafından sağlanan birincil birlikte çalışma derlemesi kullanın. Kesin tür uyumluluğu sağlamaya ek olarak, birincil birlikte çalışma derlemelerini genellikle birlikte çalışabilirlik geliştirmek için satıcı tarafından özelleştirilir.

 Birincil birlikte çalışma derlemesi kullanarak, üçüncü taraf COM türleri kullanıma sunmak planlamıyorsanız olsa bile, COM bileşenleriyle birlikte görevini kolaylaştırabilir. Ancak, bu strateji satıcı birincil birlikte çalışma bütünleştirilmiş kodu içerisinde tanımlanmış türler için yapabileceğiniz değişikliklere karşı hiçbir yalıtımı sağlar. Uygulamanızın gerektirdiği gibi yalıtımı olduğunda, birincil birlikte çalışma derlemesi kullanmak yerine kendi birlikte çalışma derlemesi oluşturur.

 Visual Studio ile başvuru önce tüm alınan birincil birlikte çalışma derlemelerini geliştirme bilgisayarınızda uygulamanızı kaydetmeniz gerekir. Visual Studio arar ve bir birincil birlikte çalışma derlemesi ilk kez bir COM tür kitaplığından bir tür başvurusu kullanır. Visual Studio tür kitaplığı ile ilişkilendirilmiş birincil birlikte çalışma derlemesi bulamazsanız, almak isteyip istemediğinizi sorar veya bunun yerine bir birlikte çalışma derlemesi oluşturmak sunar. Benzer şekilde, [tür kitaplığı alma programı (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) de birincil birlikte çalışma derlemelerini bulmak için kayıt kullanır.

 Visual Studio kullanmayı düşünmüyorsanız, birincil birlikte çalışma derlemelerini kaydetmek gerekli olmamasına karşın, kaydı iki avantaj sağlar:

-   Özgün tür kitaplığının kayıt defteri anahtarı altında kayıtlı birincil birlikte çalışma derlemesine açıkça işaretlenmiştir. Kayıt, bilgisayarınızda bir birincil birlikte çalışma derlemesi bulmak en iyi yoludur.

-   Yanlışlıkla oluşturma ve bir süre sonra gelecekte, kaydı birincil birlikte çalışma derlemesi olan bir tür başvurmak için Visual Studio kullanıyorsanız, yeni bir birlikte çalışma derlemesi kullanarak önleyebilirsiniz.

Kullanım [derleme Kayıt Aracı (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) birincil birlikte çalışma derlemesi kaydedilecek.

## <a name="to-register-a-primary-interop-assembly"></a>Birincil birlikte çalışma derlemesi kaydetmek için

1.  Komut isteminde, şunları yazın:

     **RegAsm** *assemblyname*

     Bu komutta *assemblyname* kayıtlı derlemenin dosya adı. RegAsm.exe özgün tür kitaplığıyla aynı kayıt defteri anahtarı altında birincil birlikte çalışma derlemesi için bir giriş ekler.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kaydeder `CompanyA.UtilLib.dll` birincil birlikte çalışma derlemesi.

```console
regasm CompanyA.UtilLib.dll
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Birincil birlikte çalışma derlemeleriyle programlama](https://msdn.microsoft.com/library/306fa1d6-0703-4004-9e93-d0a57f1be81e(v=vs.100))
- [Birincil birlikte çalışma derlemelerini konumlandırma](https://msdn.microsoft.com/library/d6768e4b-cd80-414d-a4f8-05d979eb393b(v=vs.100))
- [Birincil birlikte çalışma derlemelerini yeniden dağıtma](https://msdn.microsoft.com/library/e76384f0-d631-474c-bdbd-13884cba0265(v=vs.100))