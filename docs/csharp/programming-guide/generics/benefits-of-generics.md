---
title: Genel türlerin yararları - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
ms.openlocfilehash: f97d3ce7a67638719d02c31879c00679405118bc
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245018"
---
# <a name="benefits-of-generics-c-programming-guide"></a>Genel Türlerin Yararları (C# Programlama Kılavuzu)
Genel türler ortak dil çalışma zamanı ve C# dili içinde Genelleştirme gerçekleştirilir atama türleri için ve evrensel temel türe göre önceki sürümlerinde bir sınırlama çözümü sağlamak <xref:System.Object>. Genel sınıf oluşturarak, tür kullanımı uyumlu bir koleksiyon oluşturabilirsiniz derleme zamanında.  
  
 Genel olmayan koleksiyon sınıfları kullanma sınırlamaları kullanan kısa bir program yazarak gösterilen <xref:System.Collections.ArrayList> .NET sınıf kitaplığı'ndan koleksiyon sınıfı. Örneği <xref:System.Collections.ArrayList> sınıfı, herhangi bir başvuru veya değer türü depolayabilir.  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 Ancak, bu kullanışlı bir maliyetle birlikte gelir. Eklenen herhangi bir başvuru veya değer türü bir <xref:System.Collections.ArrayList> örtük olarak başvurmanıza olduğu <xref:System.Object>. Öğeleri değer türleri ise listeye eklenir ve bunlar alınırken kutudan olduğunda bunlar paketlenmelidir. Hem atama hem de kutulama ve kutudan çıkarma işlemlerinin performansını düşürebilir; kutulama ve kutudan çıkarma etkisini nerede büyük koleksiyonlarında gezinmek gereken senaryolarda çok önemli olabilir.  
  
 Diğer derleme zamanı tür denetimini eksiklik sınırlamadır; çünkü bir <xref:System.Collections.ArrayList> her şeye bıraktığı <xref:System.Object>, istemci kodu, bunun gibi bir şeyler yapmasını önlemek için derleme zamanında bir yolu yoktur:  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 Edilebilir ve heterojen bir koleksiyon oluşturuyorsanız bazen kasıtlı rağmen dizeleri birleştiren ve `ints` tek bir <xref:System.Collections.ArrayList> büyük olasılıkla bir programlama hatası olması ve bu hata çalışma zamanına kadar algılanmaz.  
  
 1.0 ve 1.1 C# dilinin sürümlerinde, yalnızca kendi tür belirli koleksiyonlar yazarak genelleştirilmiş kodda .NET Framework temel sınıf kitaplığı koleksiyon sınıfları tehlikeleri önlemek. Elbette, böyle bir sınıfın birden fazla veri türü için yeniden kullanılabilir olmadığından, Genelleştirme avantajlarını kaybedersiniz ve depolanacak her türü için sınıfı yeniden gerekir.  
  
 Hangi <xref:System.Collections.ArrayList> ve diğer benzer sınıflar kurmalıdır, örnek başına temelinde, kullanmak istediğiniz belirli bir veri türü belirtmek istemci kodu için bir yoldur. Yukarı çevrim için gereksinimini ortadan <xref:System.Object> ve ayrıca bu derleyicinin tür denetimi olası hale getirir. Diğer bir deyişle, <xref:System.Collections.ArrayList> bir tür parametresi gerekiyor. Tam olarak neler genel türler sağlar olmasıdır. Genel olarak <xref:System.Collections.Generic.List%601> koleksiyonu içinde <xref:System.Collections.Generic> ad alanı, aynı koleksiyona öğe ekleme işlemi bu benzer:  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 İçin istemci kodu, yalnızca eklenen söz dizimiyle <xref:System.Collections.Generic.List%601> karşılaştırıldığında <xref:System.Collections.ArrayList> bağımsız değişken türü bildirimi ve örnek oluşturma. Bu biraz daha kodlama karmaşıklığı tanıtmanın karşılığında, yalnızca daha güvenli olmayan bir liste oluşturabilirsiniz <xref:System.Collections.ArrayList>, ancak Ayrıca önemli ölçüde daha hızlı, özellikle liste öğeleri değer türleri olduğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.

- <xref:System.Collections.Generic>  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Genel Türlere Giriş](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [Kutulama ve Kutudan Çıkarma](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
- [Genel Koleksiyonlar Ne Zaman Kullanılır?](../../../standard/collections/when-to-use-generic-collections.md)  
- [Koleksiyonlar için yönergeler](../../../standard/design-guidelines/guidelines-for-collections.md)   
