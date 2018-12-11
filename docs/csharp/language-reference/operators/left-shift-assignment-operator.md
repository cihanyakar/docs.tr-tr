---
title: '&lt;&lt;= İşleci - C# başvurusu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239179"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;= İşleci (C# Başvurusu)
Sola kaydırma atama işleci.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ifade formu  
  
```csharp  
x <<= y  
```  
  
 olarak değerlendirilir  
  
```csharp  
x = x << y  
```  
  
 dışında `x` yalnızca bir kez değerlendirilir. [<< İşleci](../../../csharp/language-reference/operators/left-shift-operator.md) kaydırır `x` tarafından belirtilen bit sayısı kadar sola `y`.  
  
 `<<=` İşleci aşırı yüklenemez doğrudan, ancak kullanıcı tanımlı türler aşırı yükleme [<< işleci](../../../csharp/language-reference/operators/left-shift-operator.md) (bkz [işleci](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [C# İşleçleri](../../../csharp/language-reference/operators/index.md)
