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
# <a name="get-c-reference"></a><span data-ttu-id="5be79-102">get (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="5be79-102">get (C# Reference)</span></span>

<span data-ttu-id="5be79-103">`get` Tanımlayan anahtar sözcüğü bir *erişimci* yönteminde bir özellik veya dizin özelliği veya dizin oluşturucu öğenin döndürür.</span><span class="sxs-lookup"><span data-stu-id="5be79-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="5be79-104">Daha fazla bilgi için [özellikleri](../../../csharp/programming-guide/classes-and-structs/properties.md), [Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) ve [dizin oluşturucular](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="5be79-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="5be79-105">Aşağıdaki örnek, her ikisi de tanımlar bir `get` ve `set` adlı bir özellik erişimcisi `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="5be79-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="5be79-106">Adlı bir özel alan kullanan `_seconds` özellik değeri yedeklenir.</span><span class="sxs-lookup"><span data-stu-id="5be79-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="5be79-107">Genellikle, `get` erişimci, önceki örnekte olduğu gibi bir değer döndüren tek bir sistem oluşur.</span><span class="sxs-lookup"><span data-stu-id="5be79-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="5be79-108">C# 7.0 ile başlayarak, uygulayabileceğiniz `get` bir ifade gövdeli üyesi erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="5be79-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="5be79-109">Aşağıdaki örnek her ikisini birden uygular `get` ve `set` ifade gövdeli üyeler olarak erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="5be79-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
<span data-ttu-id="5be79-110">Basit durumlarda için bir özelliğin `get` ve `set` erişimcileri ayarlama veya özel destek alanı bir değer alınırken daha başka bir işlem gerçekleştirme, otomatik uygulanan özellikler için C# Derleyici desteği yararlanabilir.</span><span class="sxs-lookup"><span data-stu-id="5be79-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="5be79-111">Aşağıdaki örnek uygulayan `Hours` otomatik uygulanan bir özellik olarak.</span><span class="sxs-lookup"><span data-stu-id="5be79-111">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5be79-112">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="5be79-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5be79-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5be79-113">See Also</span></span>

- [<span data-ttu-id="5be79-114">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="5be79-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5be79-115">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="5be79-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5be79-116">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="5be79-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="5be79-117">Özellikler</span><span class="sxs-lookup"><span data-stu-id="5be79-117">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
