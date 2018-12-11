---
title: Çok boyutlu diziler - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: d5663062815f0c85772aa0e30f5edeac654431b8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242223"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="a6913-102">Çok Boyutlu Diziler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="a6913-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="a6913-103">Diziler, birden fazla boyuta sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="a6913-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="a6913-104">Örneğin, aşağıdaki bildirimi dört satır ve iki sütunlu iki boyutlu bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a6913-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 <span data-ttu-id="a6913-105">Aşağıdaki bildirim üç bir dizi oluşturur boyutları, 4, 2 ve 3.</span><span class="sxs-lookup"><span data-stu-id="a6913-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="a6913-106">Dizi başlatma</span><span class="sxs-lookup"><span data-stu-id="a6913-106">Array Initialization</span></span>

 <span data-ttu-id="a6913-107">Aşağıdaki örnekte gösterildiği gibi dizi bildirimi üzerine başlatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a6913-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 <span data-ttu-id="a6913-108">Dizi boyut belirtilmeden de başlatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a6913-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 <span data-ttu-id="a6913-109">Bir dizi değişkeni başlatma olmadan belirtmek isterseniz, kullanmalısınız `new` dizi değişkenine atamak için işleç.</span><span class="sxs-lookup"><span data-stu-id="a6913-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="a6913-110">Kullanımını `new` aşağıdaki örnekte gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="a6913-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 <span data-ttu-id="a6913-111">Aşağıdaki örnek, belirli bir dizi öğesine bir değer atar.</span><span class="sxs-lookup"><span data-stu-id="a6913-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 <span data-ttu-id="a6913-112">Benzer şekilde, aşağıdaki örnekte belirli bir dizi öğenin değerini alır ve değişkenine atar `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="a6913-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 <span data-ttu-id="a6913-113">Aşağıdaki kod örneği, dizi öğeleri (hariç basit Diziler) varsayılan değerlerine başlatır.</span><span class="sxs-lookup"><span data-stu-id="a6913-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a6913-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a6913-114">See Also</span></span>

- [<span data-ttu-id="a6913-115">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a6913-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a6913-116">Diziler</span><span class="sxs-lookup"><span data-stu-id="a6913-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="a6913-117">Tek Boyutlu Diziler</span><span class="sxs-lookup"><span data-stu-id="a6913-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="a6913-118">Düzensiz Diziler</span><span class="sxs-lookup"><span data-stu-id="a6913-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
