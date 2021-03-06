---
title: Değer türleri - C# başvurusu
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 77aed78e7822e06b3b1e6c48b07790d93e09559c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612731"
---
# <a name="value-types-c-reference"></a>Değer türleri (C# Başvurusu)

Değer türlerinin iki tür vardır:

- [Yapılar](struct.md)

- [Sabit Listeleri](enum.md)

## <a name="main-features-of-value-types"></a>Değer türleri'larının temel özellikleri

Bir değer türünde bir değişken türünde bir değer içerir. Örneğin, bir değişken `int` türü, değer içerebilir `42`. Bu, bir başvuru türü olarak da bilinen bir nesne örneği içeren bir başvuru türünün bir değişkeni farklıdır. Bu değer, bir değişkene bir değer türü yeni bir değer atadığınızda, kopyalanır. Başvuru türünde bir değişken için yeni bir değer atadığınızda, başvuru kopyalanır, nesnenin kendisini değil.

Tüm değer türleri örtülü olarak türetilmiş <xref:System.ValueType?displayProperty=nameWithType>.

Farklı başvuru türleri ile yeni bir tür bir değer türünden türetilemez. Ancak, başvuru türleri, ister yapılar, arabirimler uygulayabilirsiniz.

Değer türü değişkenler olamaz `null` varsayılan olarak. Ancak, karşılık gelen değişkenleri [boş değer atanabilir türler](../../../csharp/programming-guide/nullable-types/index.md) olabilir `null`.

Her değer türü varsayılan değer türü başlatan örtülü varsayılan bir oluşturucuya sahiptir. Değer türleri varsayılan değerler hakkında daha fazla bilgi için bkz. [varsayılan değerler tablosu](default-values-table.md).

## <a name="simple-types"></a>Basit türler

*Basit türler* bir dizi önceden tanımlanmış bir yapı türü tarafından sağlanan C# ve aşağıdaki türleri oluşturan:

- [Tam sayı türleri](integral-types-table.md): tamsayı sayısal türleri ve [char](char.md) türü
- [Kayan nokta türleri](floating-point-types-table.md)
- [bool](bool.md)

Basit türler anahtar sözcükleri tanımlanır, ancak bu anahtar sözcükler yalnızca önceden tanımlanmış bir yapı türleri için diğer adlar <xref:System> ad alanı. Örneğin, [int](int.md) bir diğer adıdır <xref:System.Int32?displayProperty=nameWithType>. Diğer adlar tam bir listesi için bkz. [yerleşik türler tablosu](built-in-types-table.md).

Basit türler, bazı ek işlemler izin vermek, diğer yapı türlerden farklılık gösterir:

- Basit türler, değişmez değerleri kullanılarak başlatılabilir. Örneğin, `'A'` bir sabit değer türü olan `char` ve `2001` bir sabit değer türü olan `int`.

- Sabitler ile basit türler bildirebilirsiniz [const](const.md) anahtar sözcüğü. Diğer yapı tür sabitleri mümkün değildir.

- Sabit ifadeler, işlenenleri tüm basit tür sabit değerlerdir, derleme zamanında değerlendirilir.

Daha fazla bilgi için [basit türler](~/_csharplang/spec/types.md#simple-types) bölümünü [ C# dil belirtimi](../language-specification/index.md).

## <a name="initializing-value-types"></a>Değer türleri başlatma

C# dilinde yerel değişkenler, kullanılmadan önce başlatılmalıdır. Örneğin, aşağıdaki örnekte olduğu gibi başlatma olmadan yerel bir değişken bildirmeniz:

```csharp
int myInt;
```

Bunu başlatılmadan önce kullanamazsınız. Aşağıdaki deyimi kullanarak başlatabilirsiniz:

```csharp
myInt = new int();  // Invoke default constructor for int type.
```

Bu ifade, aşağıdaki deyime eşdeğerdir:

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

Elbette, bildirim ve başlatma aşağıdaki örneklerde gösterildiği gibi aynı deyimde olabilir:

```csharp
int myInt = new int();
```

– veya –

```csharp
int myInt = 0;
```

Kullanarak [yeni](new.md) işleci belirli türdeki varsayılan oluşturucuyu çağırır ve varsayılan değer değişkenine atar. Önceki örnekte, varsayılan oluşturucu değer atanmış `0` için `myInt`. Varsayılan Oluşturucu çağırarak atanan değerler hakkında daha fazla bilgi için bkz: [varsayılan değerler tablosu](default-values-table.md).

Kullanıcı tanımlı türler ile kullanın [yeni](new.md) varsayılan oluşturucuyu çağırmak için. Örneğin, aşağıdaki deyim olan varsayılan oluşturucusunu çağırır `Point` yapısı:

```csharp
Point p = new Point(); // Invoke default constructor for the struct.
```

Bu çağrıdan sonra kesinlikle atanacak yapı olarak kabul edilir; diğer bir deyişle, tüm üyeleri varsayılan değerlerine başlatılır.

Hakkında daha fazla bilgi için `new` işleci bkz [yeni](new.md).

Sayısal türlerin çıktı biçimlendirme hakkında daha fazla bilgi için bkz: [sayısal sonuçlar tablosunu biçimlendirme](formatting-numeric-results-table.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Türler](types.md)
- [Türler için başvuru tabloları](reference-tables-for-types.md)
- [Başvuru Türleri](reference-types.md)
- [Boş değer atanabilir türler](../../programming-guide/nullable-types/index.md)