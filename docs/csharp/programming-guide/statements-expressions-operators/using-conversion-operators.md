---
title: Dönüşüm işleçleri - kullanma C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 908067c3ad6cae34dd223bd608a74ba1cd7a88a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236877"
---
# <a name="using-conversion-operators-c-programming-guide"></a>Dönüşüm İşleçleri Kullanma (C# Programlama Kılavuzu)
Kullanımı daha kolay olan `implicit` dönüştürme operatörlerini veya kodu okuyan herkese bir türü dönüştürdüğünüzü açıkça gösteren `explicit` dönüştürme operatörlerini kullanabilirsiniz. Bu konuda, her iki dönüştürme operatörü türü gösterilir.  
  
> [!NOTE]
>  Basit tür dönüştürmeleri hakkında daha fazla bilgi için bkz. [nasıl yapılır: Bir dizeyi sayıya dönüştürme](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [nasıl yapılır: Byte dizisini int'e dönüştürme](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [nasıl yapılır: Onaltılık dizeler ve sayısal türler arasında dönüştürme](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), veya <xref:System.Convert>.  
  
## <a name="example"></a>Örnek  
 Bu bir açık bir dönüştürme operatörü örneğidir. Bu operatör, <xref:System.Byte> türünden `Digit` isimli değer türüne dönüştürür. Tüm baytlar bir basamak değerine dönüştürülemediğinden, dönüştürme açıktır; yani `Main` yönteminde gösterildiği gibi bir yayın kullanılması gerektiği anlamına gelir.  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a>Örnek  
 Bu örnek, önceki örnekte yapılanı geri alan bir dönüştürme aracı tanımlayarak kapalı bir dönüştürme aracı gösterir: `Digit` olarak adlandırılan bir değer sınıfını <xref:System.Byte> integral türüne dönüştürür. Herhangi bir rakam bir <xref:System.Byte>'a dönüştürülebilir olduğundan, kullanıcıların dönüştürme hakkında açık olmaya zorlamaya gerek yoktur.  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Dönüştürme İşleçleri](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [is](../../../csharp/language-reference/keywords/is.md)
