---
title: Hata İletileri (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
ms.openlocfilehash: c326b781222429d68ec4385d95507a6ba99eafcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590140"
---
# <a name="error-messages-visual-basic"></a>Hata İletileri (Visual Basic)
Yazma, derleme veya Visual Basic uygulama çalıştırdığınızda aşağıdaki tür hataları oluşabilir:  
  
1.  Visual Studio'da bir uygulama yazdığınızda ortaya tasarım zamanı hataları.  
  
2.  Visual Studio'da veya bir komut isteminde bir uygulamayı derlediğinizde ortaya derleme zamanı hataları.  
  
3.  Visual Studio'da veya tek başına yürütülebilir bir dosya olarak bir uygulamayı çalıştırdığınızda ortaya çalışma zamanı hataları.  
  
 Belirli bir hata ile ilgili sorunları giderme hakkında daha fazla bilgi için bkz: [Visual Basic programcıları için ek kaynaklar](../../../visual-basic/getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Çalıştırma zamanı hataları  
 Visual Basic uygulama sistem yürütülemiyor bir eylem gerçekleştirmek üzere çalışırsa, bir çalışma zamanı hatası oluşur ve Visual Basic oluşturur bir `Exception` nesnesi. Visual Basic, özel hatalar tüm verilerin üretebilir yazın, dahil olmak üzere `Exception` kullanarak nesneleri, `Throw` deyimi. Bir uygulama hatası hata numarası ve yakalanan özel durum iletisi görüntüleyerek belirleyebilirsiniz. Bir hata belirledi değil, uygulama sona erer.  
  
 Kod yakalamak ve çalışma zamanı hataları inceleyin. Hatayı üreten kodu alın, bir `Try` bloğu, eşleşen bir içindeki tüm atılmış hata yakalayabilir `Catch` bloğu. Çalışma zamanında hataları yakalar ve bunları kodunuzda yanıt hakkında daha fazla bilgi için bkz: [deneyin... Catch... Finally ifadesi](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Derleme zamanı hataları  
 Visual Basic derleyici kodundaki bir sorunla karşılaşırsa, derleme zamanı hata oluşur. Kod Düzenleyicisi'nde dalgalı bir çizgi kod satırını altında göründüğünden hangi satırlık bir kod hataya kolayca tanımlayabilirsiniz. Dalgalı alt çizgi veya açık ya da işaret hata iletisi görüntülenir **hata listesi**, diğer iletileri de gösterir.  
  
 Dalgalı alt çizgi bir tanımlayıcısı varsa ve kısa çizgi en sağdaki karakterin altında görünür, sınıf, oluşturucusu, yöntemi, özelliği, alan veya numaralandırma için bir saplama oluşturabilir. Daha fazla bilgi için bkz: [kullanımından Oluştur](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 Visual Basic derleyici gelen uyarıları çözümleme göre daha hızlı çalışır ve daha az hataları olan kod yazmayı mümkün olabilir. Bu uyarılar uygulamayı çalıştırdığınızda, hatalara neden olabilecek kodunu belirleyin. Örneğin, derleyici, bir atanmamış nesne değişkeni üyesi çağrılacak çalışırsanız dönüş değeri ayarlamadan bir işlevinden dönmek, ya yürütme konusunda sizi uyarır bir `Try` bloğu özel durumları yakalamak için mantığı hatalı. Açma ve kapatma, devre dışı bırakma dahil olmak üzere uyarılar hakkında daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](/visualstudio/ide/configuring-warnings-in-visual-basic).
