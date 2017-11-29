---
title: "Tek Boyutlu Diziler (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fed9042ba37164927bb8073bc669fafeb5d40598
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="f1693-102">Tek Boyutlu Diziler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="f1693-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="f1693-103">Aşağıdaki örnekte gösterildiği gibi beş tamsayıların tek boyutlu bir dizi bildirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f1693-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 <span data-ttu-id="f1693-104">Bu dizi öğeleri içeren `array[0]` için `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="f1693-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="f1693-105">[Yeni](../../../csharp/language-reference/keywords/new.md) işleci dizi oluşturmak ve dizi öğeleri varsayılan değerlerine başlatmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f1693-105">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="f1693-106">Bu örnekte, tüm dizi öğeleri sıfır olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="f1693-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="f1693-107">Dize öğesi depolayan bir dizi aynı şekilde bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="f1693-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="f1693-108">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="f1693-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="f1693-109">Dizi başlatma</span><span class="sxs-lookup"><span data-stu-id="f1693-109">Array Initialization</span></span>  
 <span data-ttu-id="f1693-110">Bir dizi bildirimi bağlı Initialize mümkündür; bu durumda sıra belirticisi gerekli değildir başlatma listesindeki öğelerin sayısı tarafından zaten sağlanan çünkü.</span><span class="sxs-lookup"><span data-stu-id="f1693-110">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="f1693-111">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="f1693-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 <span data-ttu-id="f1693-112">Bir dize dizisi aynı şekilde başlatılabilir.</span><span class="sxs-lookup"><span data-stu-id="f1693-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="f1693-113">Bir dize dizisi bildirimi her dizi öğesi bir günlük adıyla nerede başlatılır verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="f1693-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 <span data-ttu-id="f1693-114">Bir dizi bildirimi bağlı başlattığınızda aşağıdaki kısayollarını kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f1693-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 <span data-ttu-id="f1693-115">Bir dizi değişkeni başlatma olmadan bildirmek mümkündür, ancak kullanmalısınız `new` Bu değişken için bir dizi atadığınızda işleci.</span><span class="sxs-lookup"><span data-stu-id="f1693-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="f1693-116">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="f1693-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 <span data-ttu-id="f1693-117">C# 3.0 örtük olarak yazılan diziler tanıtır.</span><span class="sxs-lookup"><span data-stu-id="f1693-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="f1693-118">Daha fazla bilgi için bkz: [örtük olarak yazılan diziler](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="f1693-118">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="f1693-119">Değer türü ve başvuru türü diziler</span><span class="sxs-lookup"><span data-stu-id="f1693-119">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="f1693-120">Aşağıdaki dizi bildirimi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="f1693-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 <span data-ttu-id="f1693-121">Bu deyimi sonucunu bağlıdır `SomeType` bir değer türü veya bir başvuru türü.</span><span class="sxs-lookup"><span data-stu-id="f1693-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="f1693-122">Değer türü ise, her birinin türü olan bir dizi 10 öğelerinin deyimi oluşturur `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="f1693-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="f1693-123">Varsa `SomeType` bir başvuru türü deyimi 10 öğelerin her biri için bir null başvuru başlatılır dizisi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="f1693-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="f1693-124">Değer türleri ve başvuru türleri hakkında daha fazla bilgi için bkz: [türleri](../../../csharp/language-reference/keywords/types.md).</span><span class="sxs-lookup"><span data-stu-id="f1693-124">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1693-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f1693-125">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="f1693-126">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="f1693-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f1693-127">Diziler</span><span class="sxs-lookup"><span data-stu-id="f1693-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="f1693-128">Çok boyutlu diziler</span><span class="sxs-lookup"><span data-stu-id="f1693-128">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="f1693-129">Basit diziler</span><span class="sxs-lookup"><span data-stu-id="f1693-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)