---
title: 'Nasıl Yapılır: (Kimlik) - başvuru eşitliği testi C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 6aa3aebdc03fc54233ac1cc027241fcb36cc8535
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237057"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a>Nasıl Yapılır: (Kimlik) başvuru eşitliği testi (C# Programlama Kılavuzu)
Referans eşitlik karşılaştırmaları, türlerini desteklemek için tüm özel mantığı uygulamanız gerekmez. Bu işlev tarafından statik tüm türleri için sağlanan <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> yöntemi.  
  
 Aşağıdaki örnek, iki değişken sahip olup olmadığını belirlemek gösterilmektedir *eşitlik*, bellekte aynı nesneye başvuruda bulunan anlamına gelir.  
  
 Örnek ayrıca neden gösterir <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> her zaman döndürür `false` değer türleri ve neden kullanmamalısınız <xref:System.Object.ReferenceEquals%2A> dize eşitliğini belirlemek için.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 Uygulamasını `Equals` içinde <xref:System.Object?displayProperty=nameWithType> Evrensel temel sınıfı da bir referans eşitlik kontrolüne gerçekleştirir, ancak beklediğiniz sonuçları bir sınıf yöntemini geçersiz kılmak için devre dışı durumda olmayabileceğinden, bu kullanmak en iyisidir. Aynı true `==` ve `!=` işleçleri. Türleri başvuru üzerinde ne zaman işletim, varsayılan davranışını `==` ve `!=` referans eşitlik kontrolüne gerçekleştirmektir. Ancak, türetilen sınıfların bir değer eşitliği denetimi gerçekleştirmek için işleç aşırı yüklenebilir. Hata olasılığını en aza indirmek için her zaman kullanmak en iyisidir <xref:System.Object.ReferenceEquals%2A> varsa iki nesne başvuru eşitliğine sahip olup olmadığını belirlemek.  
  
 Her zaman aynı bütünleştirilmiş kod içinde sabit dizelerini çalışma zamanı tarafından interned. Diğer bir deyişle, her benzersiz bir değişmez değer dize yalnızca bir örneğini korunur. Ancak, çalışma zamanı dizeleri çalışma zamanında oluşturulan interned veya iki eşit sabit dizelerini farklı derlemelerde interned olduğunu garanti etmez garanti etmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [Eşitlik Karşılaştırmaları](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)
