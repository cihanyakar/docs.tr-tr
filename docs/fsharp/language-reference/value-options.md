---
title: 'Değer seçenekleri (F #)'
description: 'Seçenek türü bir yapı sürümü F # değer seçeneği türü hakkında bilgi edinin.'
ms.date: 06/16/2018
ms.openlocfilehash: 4c255cbbcfd9cb480230de09cd370a401c87343a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936212"
---
# <a name="value-options"></a>Değer seçenekleri

Aşağıdaki iki koşul tuttuğunuzda değeri seçenek türünün F # kullanılır:

1. Bir senaryo için uygun olan bir [F # seçeneği](options.md).
2. Bir yapı kullanarak sizin senaryonuzda bu performans artar.

Tüm performans açısından duyarlı senaryoları "yapılar kullanarak çözülen". Bunları başvuru türleri yerine kullanırken kopyalama ek maliyeti dikkate almanız gerekir. Ancak, çünkü yapılar bazen daha iyi bir program ömrü boyunca genel performansı sağlayabilir büyük F # programları genellikle etkin yolları akış birçok isteğe bağlı tür örneği.

## <a name="definition"></a>Tanım

Değer seçeneği olarak tanımlanmış olan bir [ayırt edici birleşim](discriminated-unions.md#struct-discriminated-unions) olan başvuru seçeneği türüne benzerdir:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpValueOption`1")>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone: 'T voption
    | ValueSome: 'T -> 'T voption

    member Value : 'T

and 'T voption = ValueOption<'T>
```

Değer seçeneği yapısal eşitlik ve karşılaştırma için uygundur. İkisi arasındaki temel fark, derlenmiş ad, tür adı ve büyük/küçük harf adları, bir değer türü olduğunu belirtmek ' dir.

## <a name="using-value-options"></a>Değer seçeneklerini kullanma

Değer seçenekleri gibi kullanılır [seçenekleri](options.md). `ValueSome` bir değerin mevcut olduğunu belirtmek için kullanılır ve `ValueNone` bir değer mevcut olmadığında kullanılır:

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

Olduğu gibi [seçenekleri](options.md), döndüren bir işlev için adlandırma kuralı `ValueOption` ile ön ek için `try`.

## <a name="value-option-properties-and-methods"></a>Değer seçeneği özellikleri ve yöntemleri

Şu anda bir özellik için değer seçenekleri mevcuttur: `Value`. Bir <xref:System.InvalidOperationException> hiçbir değer yoksa, bu özelliğin çağırılır olması durumunda tetiklenir.

## <a name="value-option-functions"></a>Değer seçeneği işlevleri

Şu anda bir modül bağlı işlev değer seçenekleri için olan `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Olduğu gibi `defaultArg` işlevi `defaultValueArg` belirli değer seçeneği temel değerini döndürür var; Aksi takdirde, varsayılan değeri döndürür.

Şu anda hiç bir modül bağlı işlevi değer seçenekleri için vardır.

## <a name="see-also"></a>Ayrıca bkz.

[Seçenekler](options.md)