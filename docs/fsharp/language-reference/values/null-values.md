---
title: "Boş Değerler (F#)"
description: "Nasıl null değer F # programlama dili kullanılır öğrenin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 68ebd261-51cf-4582-b2dc-44c84d1c2500
ms.openlocfilehash: 01c14de00eb5efd0952145ffc8aabe69d65a3a48
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="null-values"></a><span data-ttu-id="91b3f-104">Boş Değerler</span><span class="sxs-lookup"><span data-stu-id="91b3f-104">Null Values</span></span>

<span data-ttu-id="91b3f-105">Bu konuda nasıl null değer F #'ta kullanıldığını açıklar.</span><span class="sxs-lookup"><span data-stu-id="91b3f-105">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="91b3f-106">Null değer</span><span class="sxs-lookup"><span data-stu-id="91b3f-106">Null Value</span></span>
<span data-ttu-id="91b3f-107">Null değer normal olarak F #'ta değerler veya değişkenler için kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="91b3f-107">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="91b3f-108">Ancak, bazı durumlarda normal olmayan bir değer olarak null görünür.</span><span class="sxs-lookup"><span data-stu-id="91b3f-108">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="91b3f-109">Bir tür F #'ta tanımlanmışsa, null normal bir değeri sürece izin verilmiyor [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) öznitelik türü için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="91b3f-109">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="91b3f-110">Bir tür bazı diğer .NET dilinde tanımlandı, olası bir değer null ise ve bu tür türleri ile birlikte, F # kodunuzu null değerler karşılaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="91b3f-110">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="91b3f-111">F #'de tanımlanan ve kesinlikle kullanılan F #'türü için F # kitaplığı kullanarak doğrudan bir null değer oluşturmak için tek yolu kullanmaktır [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) veya [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span><span class="sxs-lookup"><span data-stu-id="91b3f-111">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="91b3f-112">Ancak, diğer .NET dillerinden kullanılan bir F # türü veya F #, .NET Framework gibi yazılmaz bir API ile türü kullanıyorsanız, null değerler ortaya çıkabilir.</span><span class="sxs-lookup"><span data-stu-id="91b3f-112">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="91b3f-113">Kullanabileceğiniz `option` F başka bir .NET dilinde olası null değerine sahip bir başvuru değişken kullanmak isteyeceğiniz durumların # türü.</span><span class="sxs-lookup"><span data-stu-id="91b3f-113">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="91b3f-114">Null ile bir F # yerine `option` türü, seçenek değeri kullanmak `None` nesnesi yok ise.</span><span class="sxs-lookup"><span data-stu-id="91b3f-114">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="91b3f-115">Seçenek değeri kullanmak `Some(obj)` bir nesneyle `obj` bir nesne olduğunda.</span><span class="sxs-lookup"><span data-stu-id="91b3f-115">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="91b3f-116">Daha fazla bilgi için bkz: [seçenekleri](../options.md).</span><span class="sxs-lookup"><span data-stu-id="91b3f-116">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="91b3f-117">`null` F # dilinde geçerli bir anahtar sözcüktür ve .NET Framework API'ları veya başka bir .NET dilinde yazılmış diğer API'leri ile çalışırken kullanmak zorunda.</span><span class="sxs-lookup"><span data-stu-id="91b3f-117">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="91b3f-118">Bir null değer gerekebilecek iki .NET API çağrısı ve bağımsız değişken olarak bir null değer geçirmek ve dönüş değeri veya çıktı parametresi .NET yöntemi çağrısından yorumlama durumlardır.</span><span class="sxs-lookup"><span data-stu-id="91b3f-118">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="91b3f-119">Bir .NET yöntem boş bir değer geçirmek için yalnızca kullanmak `null` arama koddaki anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="91b3f-119">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="91b3f-120">Aşağıdaki kod örneği bunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="91b3f-120">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="91b3f-121">Bir .NET yönteminden elde bir null değer yorumlamaya yapabiliyorsanız desen eşleştirme kullanın.</span><span class="sxs-lookup"><span data-stu-id="91b3f-121">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="91b3f-122">Aşağıdaki kod örneğinde desen eşleştirme sunucudan döndürülen değerin null yorumlamak için nasıl kullanılacağını gösterir `ReadLine` zaman çalışır sonunun ötesinde Giriş akışı okunamıyor.</span><span class="sxs-lookup"><span data-stu-id="91b3f-122">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="91b3f-123">F # türleri için null değerler de oluşturulabilir kullandığınızda gibi diğer yollarla `Array.zeroCreate`, çağıran `Unchecked.defaultof`.</span><span class="sxs-lookup"><span data-stu-id="91b3f-123">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="91b3f-124">Kapsüllenmiş null değerleri tutmak için bu kodla dikkatli olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="91b3f-124">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="91b3f-125">Yalnızca F # için amaçlanan bir kitaplıkta her işlevde null değerler olup olmadığını denetlemek yok.</span><span class="sxs-lookup"><span data-stu-id="91b3f-125">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="91b3f-126">Diğer .NET dilleri ile birlikte çalışma için bir kitaplık yazıyorsanız, null denetimlerinin giriş parametreleri ve durum eklemeniz gerekebilir bir `ArgumentNullException`, C# veya Visual Basic kodunda yaptığınız gibi.</span><span class="sxs-lookup"><span data-stu-id="91b3f-126">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="91b3f-127">Rastgele bir değerin boş olup olmadığını denetlemek için aşağıdaki kodu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="91b3f-127">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="91b3f-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="91b3f-128">See Also</span></span>
[<span data-ttu-id="91b3f-129">Değerleri</span><span class="sxs-lookup"><span data-stu-id="91b3f-129">Values</span></span>](index.md)

[<span data-ttu-id="91b3f-130">Eşleşme ifadeleri</span><span class="sxs-lookup"><span data-stu-id="91b3f-130">Match Expressions</span></span>](../match-expressions.md)