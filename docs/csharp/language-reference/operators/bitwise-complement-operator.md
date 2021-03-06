---
title: ~ İşleci - C# başvurusu
ms.custom: seodec18
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 57e5baee423c0b5d9292d0ad4cbf909646eb3a38
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235731"
---
# <a name="-operator-c-reference"></a>~ İşleci (C# Başvurusu)

Bit düzeyinde tamamlama işleci `~` bir bit düzeyinde tamamlayıcı işlenenin her bitini ters çevirerek üreten bir birli işleç. Tüm tamsayı türlerini destekleyen `~` işleci.

> [!NOTE]
> `~` Simgesi sonlandırıcılar bildirmek için de kullanılır. Daha fazla bilgi için [sonlandırıcılar](../../programming-guide/classes-and-structs/destructors.md).

Aşağıdaki örnek, kullanımını gösterir. `~` işleci:

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> İkili sabit dizeler önceki örnekte [sunulan C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) ve [içinde Gelişmiş C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

## <a name="operator-overloadability"></a>İşleç overloadability

Kullanıcı tanımlı türler için [aşırı](../keywords/operator.md) `~` işleci.

## <a name="c-language-specification"></a>C# dili belirtimi

Daha fazla bilgi için [bit düzeyinde tamamlama işleci](~/_csharplang/spec/expressions.md#bitwise-complement-operator) bölümünü [ C# dil belirtimi](../language-specification/index.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# İşleçleri](index.md)
- [Sonlandırıcılar](../../programming-guide/classes-and-structs/destructors.md)
- [& işleci](and-operator.md)
- [| işleci](or-operator.md)
- [^ işleci](xor-operator.md)
