---
title: Al - C# başvurusu
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: e3cd4779b4f865c4c9bb46d4f25819c863de8bc2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240044"
---
# <a name="get-c-reference"></a>get (C# Başvurusu)

`get` Tanımlayan anahtar sözcüğü bir *erişimci* yönteminde bir özellik veya dizin özelliği veya dizin oluşturucu öğenin döndürür. Daha fazla bilgi için [özellikleri](../../../csharp/programming-guide/classes-and-structs/properties.md), [Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) ve [dizin oluşturucular](../../../csharp/programming-guide/indexers/index.md).  
  
Aşağıdaki örnek, her ikisi de tanımlar bir `get` ve `set` adlı bir özellik erişimcisi `Seconds`. Adlı bir özel alan kullanan `_seconds` özellik değeri yedeklenir.  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Genellikle, `get` erişimci, önceki örnekte olduğu gibi bir değer döndüren tek bir sistem oluşur. C# 7.0 ile başlayarak, uygulayabileceğiniz `get` bir ifade gövdeli üyesi erişimcisi. Aşağıdaki örnek her ikisini birden uygular `get` ve `set` ifade gövdeli üyeler olarak erişimcisi.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
Basit durumlarda için bir özelliğin `get` ve `set` erişimcileri ayarlama veya özel destek alanı bir değer alınırken daha başka bir işlem gerçekleştirme, otomatik uygulanan özellikler için C# Derleyici desteği yararlanabilir. Aşağıdaki örnek uygulayan `Hours` otomatik uygulanan bir özellik olarak. 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)
- [Özellikler](../../../csharp/programming-guide/classes-and-structs/properties.md)
