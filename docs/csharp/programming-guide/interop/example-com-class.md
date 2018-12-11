---
title: Örnek COM sınıfı - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: b2e9e94f75b048dbe4ce3430c7a590f9be156e1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242496"
---
# <a name="example-com-class-c-programming-guide"></a>Örnek COM Sınıfı (C# Programlama Kılavuzu)
Bir sınıfın, bir COM nesnesi olarak kullanıma bir örnek verilmiştir. Bu kod bir .cs dosyasına yerleştirilir ve projenize eklenir sonra ayarlayın **kaydetme COM birlikte çalışması için** özelliğini **True**. Daha fazla bilgi için [nasıl yapılır: COM birlikte çalışması için bir bileşeni kayıt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).
  
 COM Visual C# nesnelerini gösterme, bir sınıf arabirimi, gerekirse olayları arabirim ve sınıf bildirme gerektirir. Sınıf üyeleri için COM görünür olmasını şu kurallara uymalıdır:  
  
-   Sınıfı, ortak olmalıdır.  
  
-   Özellikleri, yöntemleri ve olayların ortak olması gerekir.  
  
-   Özellikler ve yöntemler sınıf arabirimi bildirilmelidir.  
  
-   Olayları olay arabirimi bildirilmesi gerekir.  
  
 Bu arabirimleri bildirilmemiş olan diğer genel sınıf üyeleri için COM görünür durumda değildir, ancak diğer .NET Framework nesneleri için görünür olur.  
  
 Özellikler ve yöntemler com göstermek için bunları sınıf arabirimi bildirmek ve bunları ile işaretleyin bir `DispId` özniteliği ve bunları sınıfında uygulama. Üyeleri bir arabirimde bildirilen siparişi için COM vtable kullanılan sırasıdır.  
  
 Sizin sınıfınızdan olaylar oluşturmak için bunları olayları arabirimi bildirme ve bunlarla işaretlemek bir `DispId` özniteliği. Sınıf bu arabirim uygulamamalıdır.  
  
 Sınıfı, sınıf arabirimi uygular; Daha fazla arabirim uygulayabilir, ancak ilk uygulama varsayılan sınıf arabirimi olacaktır. Burada com'a özellikleri ve yöntemleri uygulayın. Bunlar genel olarak işaretlenmelidir ve sınıf arabirimi bildirimlerinde eşleşmelidir. Ayrıca, burada sınıfı tarafından tetiklenen olayları bildirin. Bunlar genel olarak işaretlenmelidir ve olayları arabirimi bildirimlerinde eşleşmelidir.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Birlikte çalışabilirlik](../../../csharp/programming-guide/interop/index.md)  
- [Derleme Sayfası, Proje Tasarımcısı (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)
