---
title: 'Nasıl yapılır: işaretçiyle - bir dizi öğesine erişme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 59765dbcad6c28cf2ad9f3df2052df19cafd08f1
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307285"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="33aab-102">Nasıl yapılır: işaretçiyle bir dizi öğesine erişme (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="33aab-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="33aab-103">Güvenli olmayan bir bağlamda, bir öğedeki bir bellek işaretçi öğe erişimi, kullanarak aşağıdaki örnekte gösterildiği gibi erişebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="33aab-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="33aab-104">Köşeli ayraç ifadesi örtük olarak dönüştürülebilir olmalıdır `int`, `uint`, `long`, veya `ulong`.</span><span class="sxs-lookup"><span data-stu-id="33aab-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="33aab-105">İşlemi `p[e]` eşdeğerdir `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="33aab-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="33aab-106">C ve C++ gibi işaretçi öğe erişimi işlemleri denetlemez hataları.</span><span class="sxs-lookup"><span data-stu-id="33aab-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="33aab-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="33aab-107">Example</span></span>

<span data-ttu-id="33aab-108">Bu örnekte, bir karakter dizisine 123 bellek konumları ayrılır `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="33aab-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="33aab-109">Dizi küçük harfler ve büyük harfler iki görüntülemek için kullanılan [için](../../../csharp/language-reference/keywords/for.md) döngüleri.</span><span class="sxs-lookup"><span data-stu-id="33aab-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="33aab-110">Dikkat ifade `charPointer[i]` ifadesine eşdeğerdir `*(charPointer + i)`, ve iki ifadeden birini kullanarak aynı sonucu elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="33aab-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="33aab-111">**Büyük harfler:**</span><span class="sxs-lookup"><span data-stu-id="33aab-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="33aab-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="33aab-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="33aab-113">**Küçük harfler:**</span><span class="sxs-lookup"><span data-stu-id="33aab-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="33aab-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="33aab-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="33aab-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="33aab-115">See also</span></span>

- [<span data-ttu-id="33aab-116">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="33aab-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="33aab-117">İşaretçi İfadeleri</span><span class="sxs-lookup"><span data-stu-id="33aab-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="33aab-118">İşaretçi türleri</span><span class="sxs-lookup"><span data-stu-id="33aab-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="33aab-119">Türler</span><span class="sxs-lookup"><span data-stu-id="33aab-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="33aab-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="33aab-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="33aab-121">fixed Deyimi</span><span class="sxs-lookup"><span data-stu-id="33aab-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="33aab-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="33aab-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
