---
title: C#işleçleri
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 6380fa4ec99f598be0d01db1061900520e94d5f1
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333414"
---
# <a name="c-operators"></a>C#işleçleri

C# (matematik, dizin oluşturma, işlev çağrısı, vb.) bir ifadede gerçekleştirilecek işlemleri belirten simgelerdir birçok işleçleri sağlar. Yapabilecekleriniz [aşırı](../../programming-guide/statements-expressions-operators/overloadable-operators.md) işleçlerinin çoğu kullanıcı tanımlı bir türe başvurulduğunda anlamının değiştirin.

Tamsayı türlerinde işlemler (gibi `==`, `!=`, `<`, `>`, `&`, `|`) genellikle numaralandırma üzerinde izin verilir (`enum`) türleri.

Aşağıdaki bölümlerde, en yüksek önceliğe düşüğe başlayarak C# işleçleri listeler. Her bölüm içerisindeki işleçler aynı öncelik düzeyine paylaşın.

## <a name="primary-operators"></a>Birincil operatörler

En yüksek öncelik işleçleri şunlardır.

[x.y](member-access-operator.md) – üye erişimi.

[x? y](null-conditional-operators.md) – null koşullu üye erişimi. Döndürür `null` sol işlenen değerlendirilirse `null`.

[x? [y] ](null-conditional-operators.md) -null koşullu dizin erişim. Döndürür `null` sol işlenen değerlendirilirse `null`.

[f(x)](invocation-operator.md) – işlev çağırma.

[bir&#91;x&#93; ](index-operator.md) – toplama nesnesi dizin oluşturma.

[x ++](increment-operator.md) – sonek artırma. X değerini döndürür ve ardından depolama konumu büyük bir x değeri ile güncelleştirir (genellikle 1 tamsayı ekler).

[x--](decrement-operator.md) – son ek azaltma. X değerini döndürür ve ardından depolama konumu bir daha az x değeri ile güncelleştirir (genellikle 1 tamsayı çıkarır).

[Yeni](../keywords/new-operator.md) – oluşturmada yazın.

[typeof](../keywords/typeof.md) – döndürür <xref:System.Type> işlenen temsil eden nesne.

[işaretli](../keywords/checked.md) – taşma denetimi için tamsayı işlemleri sağlar.

[denetlenmeyen](../keywords/unchecked.md) – taşma tamsayı işlemlerinde denetimini devre dışı bırakır. Varsayılan derleyici davranışı budur.

[Default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – t türü varsayılan değerini üretir

[Temsilci](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – bildirir ve temsilci örneği döndürür.

[sizeof](../keywords/sizeof.md) -türü işlenen bayt cinsinden boyutunu döndürür.

[->](dereference-operator.md) – Birleştirilmiş üye erişimi ile işaretçiye başvuruluyor.

## <a name="unary-operators"></a>Birli işleçler

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[+ x](addition-operator.md) – x değerini döndürür.

[-x](subtraction-operator.md) – sayısal olumsuzlama.

[\!x](logical-negation-operator.md) – mantıksal olumsuzlama.

[~ x](bitwise-complement-operator.md) – bit düzeyinde tamamlayıcı.

[++ x](increment-operator.md) – önek artırma. Depolama konumu bir x değeriyle güncelleştirdikten sonra x değerini büyük döndürür (genellikle 1 tamsayı ekler).

[--x](decrement-operator.md) – önek azaltma. Depolama konumu daha az bir x değeriyle güncelleştirdikten sonra x değeri döndürür (genelde tam sayı 1 çıkarır).

[(T) x](invocation-operator.md) – atama yazın.

[await](../keywords/await.md) – bekler bir `Task`.

[& x](and-operator.md) – adresidir.

[* x](multiplication-operator.md) – başvurusunu kaldırma.

## <a name="multiplicative-operators"></a>Çarpma işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x * y](multiplication-operator.md) – çarpma.

[x / y](division-operator.md) – bölme. İşlenenler tamsayılar, sonuç sıfıra yakınsayarak kesilmiş bir tamsayıdır (örneğin, `-7 / 2 is -3`).

[% y x](remainder-operator.md) – kalan. İşlenen tamsayılar olursa bu y bölme x geri kalanı döndürür.  Varsa `q = x / y` ve `r = x % y`, ardından `x = q * y + r`.

## <a name="additive-operators"></a>Toplama işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x + y](addition-operator.md) – ekleme.

[x-y](subtraction-operator.md) – çıkarma.

## <a name="shift-operators"></a>Kaydırma işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x <\< y](left-shift-operator.md) – bitlerini sola kaydırma ve sağ taraftaki sıfır ile doldurun.

[x >> y](right-shift-operator.md) – sağ shift bitleri. Sol işlenen ise `int` veya `long`, sonra da sol bit imza biti ile doldurulur. Sol işlenen ise `uint` veya `ulong`, sonra da sol bitler sıfır ile doldurulur.

## <a name="relational-and-type-testing-operators"></a>İlişkisel ve tür testi işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x \< y](less-than-operator.md) – (x, y değerinden ise true) küçüktür.

[x > y](greater-than-operator.md) – büyük (x, y büyükse true).

[x \<y =](less-than-equal-operator.md) – küçük veya eşittir.

[x > y =](greater-than-equal-operator.md) – büyüktür veya eşittir.

[olan](../keywords/is.md) – uyumluluk yazın. Değerlendirilen sol işlenen sağ işlenen (statik türü) belirtilen türe dönüştürülebilir ise true döndürür.

[olarak](../keywords/as.md) – dönüştürmesi yazın. (Bir statik türü), sağ işlenen tarafından belirtilen tür için sol işlenen döndürür ancak `as` döndürür `null` burada `(T)x` bir özel durum oluşturması.

## <a name="equality-operators"></a>Eşitlik işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x == y](equality-comparison-operator.md) – eşitlik. Varsayılan olarak, başvuru için türleri dışındaki `string`, bu başvuru eşitliği (kimlik test) döndürür. Ancak, türleri aşırı yüklenebilir `==`, amacınız kimliğini test etmek için ise kullanmak en iyisidir `ReferenceEquals` metodunda `object`.

[x! = y](not-equal-operator.md) – eşit değil. Açıklama için bkz. `==`. Bir tür aşırı `==`, aşırı gerekir sonra `!=`.

## <a name="logical-and-operator"></a>Mantıksal AND işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x ve y](and-operator.md) – mantıksal ve bit düzeyinde and Bu genellikle tamsayı türleri ile kullanabilirsiniz ve `enum` türleri.

## <a name="logical-xor-operator"></a>Mantıksal XOR işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x ^ y](xor-operator.md) – mantıksal ve bit düzeyinde XOR. Bu genellikle tamsayı türleri ile kullanabilirsiniz ve `enum` türleri.

## <a name="logical-or-operator"></a>Mantıksal OR işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x &#124; y](or-operator.md) – mantıksal ve bit düzeyinde OR. Bu genellikle tamsayı türleri ile kullanabilirsiniz ve `enum` türleri.

## <a name="conditional-and-operator"></a>Koşullu AND işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x & & y](conditional-and-operator.md) – mantıksal and İlk işlenen false olarak değerlendirilirse, ardından C# ikinci işlenenin değerlendirmez.

## <a name="conditional-or-operator"></a>Koşullu OR işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x &#124; &#124; y](conditional-or-operator.md) – mantıksal OR. İlk işlenen true olarak değerlendirilirse, ardından C# ikinci işlenenin değerlendirmez.

## <a name="null-coalescing-operator"></a>Null birleşim işleci

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[x?? y](null-coalescing-operator.md) – döndürür `x` olmayan ise`null`; Aksi halde döndürür `y`.

## <a name="conditional-operator"></a>Koşullu işleç

Bu işleç, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahiptir.

[t? x: y](conditional-operator.md) – test `t` true, ardından değerlendirilip döndürülecek değerlendirir `x`; Aksi takdirde, değerlendirilip döndürülecek `y`.

## <a name="assignment-and-lambda-operators"></a>Atama ve Lambda işleçleri

Bu işleçler, sonraki bölümde daha yüksek bir önceliğe ve önceki bölümde daha düşük önceliğe sahip.

[x = y](assignment-operator.md) – atama.

[x += y](addition-assignment-operator.md) – artırma. Değerini ekleme `y` değerine `x`, sonuçta depolamak `x`ve yeni bir değer. Varsa `x` atayan bir `event`, ardından `y` C# bir olay işleyicisi ekler uygun bir işlev olmalıdır.

[x-= y](subtraction-assignment-operator.md) – azaltma. Değerini çıkarma `y` değerinden `x`, sonuçta depolamak `x`ve yeni bir değer. Varsa `x` atayan bir `event`, ardından `y` C# kaldıran bir olay işleyicisi uygun bir işlev olmalıdır

[x * y =](multiplication-assignment-operator.md) – çarpma atama. Çarp değeri `y` değerine `x`, sonuçta depolamak `x`ve yeni bir değer.

[x / y =](division-assignment-operator.md) – bölme ataması. Değerini ayırmak `x` değeriyle `y`, sonuçta depolamak `x`ve yeni bir değer.

[%x y =](remainder-assignment-operator.md) – kalanını atama. Değerini ayırmak `x` değeriyle `y`, kalanı depolamak `x`ve yeni bir değer.

[x & y =](and-assignment-operator.md) – ve atama. DEĞERİ `y` değeriyle `x`, sonuçta depolamak `x`ve yeni bir değer.

[x &#124;y =](or-assignment-operator.md) – OR ataması. YA da değerini `y` değeriyle `x`, sonuçta depolamak `x`ve yeni bir değer.

[x ^ y =](xor-assignment-operator.md) – XOR atama. XOR değeri, `y` değeriyle `x`, sonuçta depolamak `x`ve yeni bir değer.

[x << y =](left-shift-assignment-operator.md) – sola kaydırma ataması. Değerini kaydırma `x` sol tarafından `y` yerde depolamak sonucunda `x`ve yeni bir değer.

[x >> y =](right-shift-assignment-operator.md) – sağa kaydırma ataması. Değerini kaydırma `x` sağa `y` yerde depolamak sonucunda `x`ve yeni bir değer.

[=>](lambda-operator.md) – lambda bildirimi.

## <a name="arithmetic-overflow"></a>Aritmetik Taşma

Aritmetik işleçler ([+](addition-operator.md), [ - ](subtraction-operator.md), [ * ](multiplication-operator.md), [ / ](division-operator.md)) can sayısal tür için olası değerler aralığının dışında olan sonuçlar üretir. Ayrıntılar için ancak genel olarak belirli bir işlecin bölümüne bakabilir:

- Tamsayı aritmetik taşma da bir <xref:System.OverflowException> ya da sonucun en önemli bitlerini atar. Sıfır ile tamsayı bölme her zaman oluşturur bir <xref:System.DivideByZeroException>.

   Tamsayı taşması oluştuğunda olabilen yürütme bağlamında ne olacağı bağlıdır [işaretli veya işaretsiz](../keywords/checked-and-unchecked.md). Denetlenen bir bağlamda bir <xref:System.OverflowException> oluşturulur. İşaretlenmemiş bir bağlamda, sonucun en önemli bitleri atılır ve yürütme devam eder. Bu nedenle, C#, işleme veya taşmayı yoksayma seçmenizi sağlar. Varsayılan olarak, aritmetik işlemler oluşan bir *denetlenmeyen* bağlamı.

   Aritmetik işlemler ek olarak, integral türünden integral türü atamaları taşmaya neden olabilir (olduğunda cast gibi'bir [uzun](../keywords/long.md) için bir [int](../keywords/int.md)) ve işaretli veya işaretsiz yürütme tabidir. Ancak, bit düzeyinde işleçler ve kaydırma işleçleri asla taşmaya neden olmaz.

- Kayan nokta aritmetik taşma ya da sıfıra bölme hiçbir zaman bir özel durum oluşturur, kayan nokta türleri IEEE 754 ve bunu temel aldığından, sonsuzluk ve NaN (sayı değil) temsil eden hükümlerine vardır.

- [Ondalık](../keywords/decimal.md) aritmetik taşma her zaman oluşturur bir <xref:System.OverflowException>. Sıfır ile ondalık bölme her zaman oluşturur bir <xref:System.DivideByZeroException>.

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C#](../../index.md)
- [Aşırı Yüklenebilir İşleçler](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [C# Anahtar Sözcükleri](../keywords/index.md)