---
title: using deyimi - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 9569b04e4d4f7bfca90390bfd803cdd02b3f3632
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244602"
---
# <a name="using-statement-c-reference"></a>using Deyimi (C# Başvurusu)
Doğru kullanımını güvence altına kullanışlı bir söz dizimi sağlar <xref:System.IDisposable> nesneleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `using` deyimi.  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Açıklamalar  
 <xref:System.IO.File> ve <xref:System.Drawing.Font> (içinde bu durum dosya tanıtıcıları ve cihaz bağlamları) yönetilmeyen kaynaklara erişen Yönetilen türlerin örnekleridir. Yönetilmeyen kaynakları bunları kapsayan sınıf kitaplığı türleri ve diğer birçok tür vardır. Tüm türleri uygulamalıdır <xref:System.IDisposable> arabirimi.  
  
Zaman ömrünü bir `IDisposable` nesne tek bir yöntem sınırlıdır, bildirme ve içinde örneği `using` deyimi. `using` Deyim aramaları <xref:System.IDisposable.Dispose%2A> doğru bir şekilde ve (daha önce gösterildiği gibi kullandığınız zaman) nesnesi üzerinde yöntemi de neden nesne kapsam dışına çıkmadan kendisine hemen sonra <xref:System.IDisposable.Dispose%2A> çağrılır. İçinde `using` blok, nesne, salt okunur ve yeniden atandığında veya değiştirilemez.  
  
 `using` Bildirimi sağlar <xref:System.IDisposable.Dispose%2A> bile içinde özel bir durum oluştuğunda çağrılır `using` blok. Nesnenin içine koyarak aynı sonucu elde edebileceğiniz bir `try` blok ve ardından arama <xref:System.IDisposable.Dispose%2A> içinde bir `finally` engelle; aslında bu, nasıl `using` deyimi, derleyici tarafından çevrilir. Kod örneği, daha önce aşağıdaki kodu derleme zamanında genişletir (nesne için sınırlı kapsamı oluşturmak için ek küme ayracı unutmayın):  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
 
 Hakkında daha fazla bilgi için `try` - `finally` deyimi bkz [try-finally](try-finally.md) konu.
  
 Birden fazla örneğini bir tür içinde bildirilebilir `using` aşağıdaki örnekte gösterildiği gibi deyimi:  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Kaynak nesne örneği oluşturun ve ardından değişkenine geçirin `using` deyimi değildir, ancak bu en iyi uygulama. Bu durumda, sonra Denetim leaves `using` engellemek, kapsam içinde nesne kalır ancak büyük olasılıkla kendi yönetilmeyen kaynaklara erişim yok. Diğer bir deyişle, tam olarak artık başlatılır. Nesne dışında kullanmayı denerseniz `using` bir özel durum oluşturulmasına neden risk engelleyin. Bu nedenle, nesneyi oluşturmak genellikle daha iyi `using` deyimi ve sınırlandırmak için kapsamı `using` blok.  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
Atma hakkında daha fazla bilgi için `IDisposable` nesneleri bkz [IDisposable uygulayan nesneler kullanma](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)  
- [using Yönergesi](../../../csharp/language-reference/keywords/using-directive.md)  
- [Atık Toplama](../../../standard/garbage-collection/index.md)  
- [IDisposable uygulayan nesneler kullanma](../../../standard/garbage-collection/using-objects.md)  
- [IDisposable arabirimi](xref:System.IDisposable)
