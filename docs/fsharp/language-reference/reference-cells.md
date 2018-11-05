---
title: Başvuru Hücreleri (F#)
description: F# başvuru hücreleri başvuru semantiğiyle değişebilir değerler oluşturmanıza olanak tanıyan depolama konumları nasıl olduğunu öğrenin.
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2018
ms.locfileid: "44192284"
---
# <a name="reference-cells"></a><span data-ttu-id="d8962-103">Başvuru Hücreleri</span><span class="sxs-lookup"><span data-stu-id="d8962-103">Reference Cells</span></span>

<span data-ttu-id="d8962-104">*Başvuru hücreleri* , başvuru semantiğiyle değişebilir değerler oluşturmanıza olanak sağlayan depolama yerleridir.</span><span class="sxs-lookup"><span data-stu-id="d8962-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8962-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d8962-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="d8962-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d8962-106">Remarks</span></span>

<span data-ttu-id="d8962-107">Kullandığınız `ref` değeri kapsülleyen yeni bir başvuru hücresi oluşturmak için bir değer önce işleci.</span><span class="sxs-lookup"><span data-stu-id="d8962-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="d8962-108">Ardından, temeldeki değer değişebilir olduğundan değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8962-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="d8962-109">Başvuru hücresi gerçek bir değer taşır; yalnızca adres değildir.</span><span class="sxs-lookup"><span data-stu-id="d8962-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="d8962-110">Kullanarak bir başvuru hücresi oluşturduğunuzda `ref` işleci, kapsüllenmiş bir değişmez değer olarak temeldeki değerin bir kopyasını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d8962-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="d8962-111">Kullanarak bir başvuru hücresi başvuru `!` (bang) işlecini.</span><span class="sxs-lookup"><span data-stu-id="d8962-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="d8962-112">Aşağıdaki kod örneği başvuru hücrelerinin bildirim ve kullanımını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="d8962-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="d8962-113">Çıktı `50`.</span><span class="sxs-lookup"><span data-stu-id="d8962-113">The output is `50`.</span></span>

<span data-ttu-id="d8962-114">Başvuru hücreleri örnekleridir `Ref` genel kayıt türü, şu şekilde bildirilir.</span><span class="sxs-lookup"><span data-stu-id="d8962-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="d8962-115">Türü `'a ref` eşanlamlıdır `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="d8962-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="d8962-116">Derleyici ve IDE içindeki IntelliSense, bu tür için ilkini görüntüler fakat temeldeki tanım ikincisidir.</span><span class="sxs-lookup"><span data-stu-id="d8962-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="d8962-117">`ref` İşleci yeni bir başvuru hücresi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d8962-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="d8962-118">Aşağıdaki kod bildirimidir `ref` işleci.</span><span class="sxs-lookup"><span data-stu-id="d8962-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="d8962-119">Aşağıdaki tablo başvuru hücresindeki mevcut özellikleri göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="d8962-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="d8962-120">İşleç, üye veya alan</span><span class="sxs-lookup"><span data-stu-id="d8962-120">Operator, member, or field</span></span>|<span data-ttu-id="d8962-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d8962-121">Description</span></span>|<span data-ttu-id="d8962-122">Tür</span><span class="sxs-lookup"><span data-stu-id="d8962-122">Type</span></span>|<span data-ttu-id="d8962-123">Tanım</span><span class="sxs-lookup"><span data-stu-id="d8962-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="d8962-124">`!` (başvuru işleci)</span><span class="sxs-lookup"><span data-stu-id="d8962-124">`!` (dereference operator)</span></span>|<span data-ttu-id="d8962-125">Temeldeki değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="d8962-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="d8962-126">`:=` (atama işleci)</span><span class="sxs-lookup"><span data-stu-id="d8962-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="d8962-127">Temeldeki değeri değiştirir.</span><span class="sxs-lookup"><span data-stu-id="d8962-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="d8962-128">`ref` (işleç)</span><span class="sxs-lookup"><span data-stu-id="d8962-128">`ref` (operator)</span></span>|<span data-ttu-id="d8962-129">Yeni bir başvuru hücresine bir değer kapsüller.</span><span class="sxs-lookup"><span data-stu-id="d8962-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="d8962-130">`Value` (özelliği)</span><span class="sxs-lookup"><span data-stu-id="d8962-130">`Value` (property)</span></span>|<span data-ttu-id="d8962-131">Temeldeki değeri alır veya ayarlar.</span><span class="sxs-lookup"><span data-stu-id="d8962-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="d8962-132">`contents` (kayıt alanı)</span><span class="sxs-lookup"><span data-stu-id="d8962-132">`contents` (record field)</span></span>|<span data-ttu-id="d8962-133">Temeldeki değeri alır veya ayarlar.</span><span class="sxs-lookup"><span data-stu-id="d8962-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="d8962-134">Temeldeki değere erişmek için çeşitli yollar vardır.</span><span class="sxs-lookup"><span data-stu-id="d8962-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="d8962-135">Başvuru işleci tarafından döndürülen değer (`!`) atanabilir bir değer değil.</span><span class="sxs-lookup"><span data-stu-id="d8962-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="d8962-136">Bu nedenle, temeldeki değeri değiştiriyorsanız, atama işlecini kullanmanız gerekir (`:=`) bunun yerine.</span><span class="sxs-lookup"><span data-stu-id="d8962-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="d8962-137">Her iki `Value` özelliği ve `contents` alanı atanabilir değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="d8962-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="d8962-138">Bu nedenle, bunları temeldeki değere ulaşmak ya da onu değiştirmek için aşağıdaki kodda gösterildiği gibi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8962-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="d8962-139">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="d8962-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="d8962-140">Alan `contents` diğer ML sürümleriyle uyumluluk için sağlanır ve derleme sırasında bir uyarı üretecektir.</span><span class="sxs-lookup"><span data-stu-id="d8962-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="d8962-141">Uyarı devre dışı bırakmak için `--mlcompatibility` derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="d8962-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="d8962-142">Daha fazla bilgi için [derleyici seçenekleri](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="d8962-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="d8962-143">C# programcıları, bilmeniz `ref` C# ile aynı şeydir değil `ref` F#.</span><span class="sxs-lookup"><span data-stu-id="d8962-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="d8962-144">F#'de eşdeğer bir yapıdır [zkratka](byrefs.md), başvuru hücrelerinin'dan farklı bir kavram olan.</span><span class="sxs-lookup"><span data-stu-id="d8962-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="d8962-145">Değerleri olarak işaretlenmiş `mutable`için otomatik olarak yükseltilebilir `'a ref` kapanım; tarafından yakalanan olup [değerleri](values/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8962-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8962-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d8962-146">See also</span></span>

- [<span data-ttu-id="d8962-147">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="d8962-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d8962-148">Parametreler ve Bağımsız Değişkenler</span><span class="sxs-lookup"><span data-stu-id="d8962-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="d8962-149">Simge ve İşleç Başvurusu</span><span class="sxs-lookup"><span data-stu-id="d8962-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="d8962-150">Değerler</span><span class="sxs-lookup"><span data-stu-id="d8962-150">Values</span></span>](values/index.md)
