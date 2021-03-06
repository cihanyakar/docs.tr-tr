---
title: Diziler - örtük C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 9c235b6084238917c2cb3f2cd745aef0264f82ce
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238279"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Türü Örtük Olarak Belirlenmiş Diziler (C# Programlama Kılavuzu)

Türü örtük olarak belirlenmiş dizi örneği türü çıkarımı yapılan bir dizi belirtilen dizi başlatıcısında öğeleri oluşturabilirsiniz. Örtük olarak yazılmış bir değişken için kuralları, örtük olarak yazılan diziler için de geçerlidir. Daha fazla bilgi için [örtük olarak yazılan yerel değişkenler](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Türü örtük olarak belirlenmiş diziler, genellikle anonim türler ve nesne ve koleksiyon başlatıcıları birlikte sorgu ifadelerinde kullanılır.  
  
 Aşağıdaki örnekler, türü örtük olarak belirlenmiş dizi oluşturma işlemini gösterir:  
  
 [!code-csharp[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 Önceki örnekte, örtük olarak yazılan diziler ile hiçbir köşeli parantez başlatma ifadesinin sol tarafında kullanılan dikkat edin. Basit diziler kullanılarak başlatılır unutmayın `new []` olduğu, tek boyutlu diziler gibi.  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a>Nesne başlatıcılarda örtük olarak yazılan diziler

 Dizi içeren bir anonim tür oluşturduğunuzda, dizi türü nesne başlatıcı içinde örtük olarak yazılmalıdır. Aşağıdaki örnekte, `contacts` her biri adında bir dizi içeren bir örtük olarak anonim türler dizisidir `PhoneNumbers`. Unutmayın `var` anahtar sözcüğünü nesne başlatıcılarda içinde kullanılmaz.  
  
 [!code-csharp[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Örtülü Olarak Yazılan Yerel Değişkenler](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)  
- [Diziler](../../../csharp/programming-guide/arrays/index.md)  
- [Anonim Tipler](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
- [Nesne ve Koleksiyon Başlatıcıları](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
- [var](../../../csharp/language-reference/keywords/var.md)  
- [LINQ Sorgu ifadeleri](../../../csharp/programming-guide/linq-query-expressions/index.md)
