---
title: 'Nasıl Yapılır: -İşaretçi değişkeninin değerini edinme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: b20642344b34b5426512ef64bde2ab33d55136b9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236641"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="d467e-102">Nasıl Yapılır: İşaretçi değişkeninin değerini edinme (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="d467e-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="d467e-103">İşaretçi yöneltme işleci için bir işaretçi tarafından işaret edilen konumda bir değişkeni almak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="d467e-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="d467e-104">İfade, aşağıdaki biçimi alır burada `p` bir işaretçi türü:</span><span class="sxs-lookup"><span data-stu-id="d467e-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="d467e-105">İşaretçi türünün dışındaki herhangi bir türde bir ifade üzerinde birli yöneltme işlecini kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="d467e-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="d467e-106">Ayrıca, kendisine uygulanamıyor bir [void](../../../csharp/language-reference/keywords/void.md) işaretçi.</span><span class="sxs-lookup"><span data-stu-id="d467e-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="d467e-107">Yöneltme işleci uygulandığında bir [null](../../../csharp/language-reference/keywords/null.md) işaretçisi sonucu uygulamasına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="d467e-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d467e-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="d467e-108">Example</span></span>  
 <span data-ttu-id="d467e-109">Aşağıdaki örnekte, türünde bir değişken `char` farklı türlerde işaretçiler kullanılarak erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="d467e-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="d467e-110">Unutmayın adresini `theChar` gelen çalıştıracak çalışma için bir değişkene ayrılan fiziksel adresi geçebileceğiniz farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="d467e-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
<span data-ttu-id="d467e-111">**TheChar değerini Z =**
**theChar adresini 12F718 =**
**pChar değerini Z =**
**pInt değerini 90 =**</span><span class="sxs-lookup"><span data-stu-id="d467e-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span></span>

## <a name="see-also"></a><span data-ttu-id="d467e-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d467e-112">See Also</span></span>

- [<span data-ttu-id="d467e-113">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d467e-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d467e-114">İşaretçi İfadeleri</span><span class="sxs-lookup"><span data-stu-id="d467e-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="d467e-115">İşaretçi türleri</span><span class="sxs-lookup"><span data-stu-id="d467e-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="d467e-116">Türler</span><span class="sxs-lookup"><span data-stu-id="d467e-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="d467e-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="d467e-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="d467e-118">fixed Deyimi</span><span class="sxs-lookup"><span data-stu-id="d467e-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="d467e-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d467e-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
