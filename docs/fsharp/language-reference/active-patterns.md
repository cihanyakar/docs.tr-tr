---
title: Etkin Desenler
description: Etkin desenler girdi verileri alt bölümlere adlandırılmış bölümler tanımlamak için kullanmayı öğrenin F# programlama dilidir.
ms.date: 05/16/2016
ms.openlocfilehash: c830011b69809bd399aab0c8a8bc25d40d5c82cc
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612848"
---
# <a name="active-patterns"></a><span data-ttu-id="89de5-103">Etkin Desenler</span><span class="sxs-lookup"><span data-stu-id="89de5-103">Active Patterns</span></span>

<span data-ttu-id="89de5-104">*Etkin desenler* , bir desen eşleme ifadesinde için ayrılmış bir birleşim olduğu gibi bu adlar kullanabilirsiniz, böylece giriş verileri alt bölümlere adlandırılmış bölümler tanımlamanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="89de5-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="89de5-105">Etkin desenler, her bölüm için özelleştirilmiş bir şekilde veri ayırmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89de5-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="89de5-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="89de5-106">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="89de5-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="89de5-107">Remarks</span></span>

<span data-ttu-id="89de5-108">Önceki sözdiziminde, bölümler tarafından temsil edilen giriş verileri için adları tanımlayıcılardır *bağımsız değişkenleri*, veya başka bir deyişle, bağımsız değişkenlerin tüm değerleri kümesi kümelerine adları.</span><span class="sxs-lookup"><span data-stu-id="89de5-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="89de5-109">Bir etkin düzeni tanımında en fazla yedi bölüm olabilir.</span><span class="sxs-lookup"><span data-stu-id="89de5-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="89de5-110">*İfade* , verileri ayırmak forma açıklar.</span><span class="sxs-lookup"><span data-stu-id="89de5-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="89de5-111">Etkin desen tanımı, adlandırılmış bölüm ait bağımsız değişkenler olarak verilen değerlerden belirleyen kuralları tanımlamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89de5-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="89de5-112">(| Ve |) sembolleri denir *Muz klipleri* ve bu tür bir let bağlama tarafından oluşturulan işlev çağrılırsa bir *etkin tanıyıcı*.</span><span class="sxs-lookup"><span data-stu-id="89de5-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="89de5-113">Örneğin, bir bağımsız değişken ile aşağıdaki etkin düzeni göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="89de5-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="89de5-114">Etkin desen bir desen eşleme ifadesinde, aşağıdaki örnekte olduğu gibi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89de5-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="89de5-115">Bu program çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="89de5-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="89de5-116">Başka bir Etkin desenler veri türleri aynı temel alınan verilerin çeşitli olası gösterimleri olduğunda gibi birden çok yolla ayırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89de5-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="89de5-117">Örneğin, bir `Color` nesne ayrılmış bir RGB temsili ya da bir HSB temsili.</span><span class="sxs-lookup"><span data-stu-id="89de5-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="89de5-118">Yukarıdaki program çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="89de5-118">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="89de5-119">Birlikte, Etkin desenler kullanarak bu iki yolu bölüme etkinleştirin ve yalnızca uygun biçime verileri parçalayın ve hesaplama için en uygun biçimde uygun veri uygun hesaplamalar gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="89de5-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="89de5-120">Sonuçta elde edilen desen eşleştirme ifadeleri çok okunabilir, büyük ölçüde basitleştirme bulunabilecek karmaşık dallanma ve veri analizi kodu uygun şekilde yazılacak veriler etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="89de5-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="89de5-121">Kısmi Etkin desenler</span><span class="sxs-lookup"><span data-stu-id="89de5-121">Partial Active Patterns</span></span>

<span data-ttu-id="89de5-122">Bazen, giriş alanı yalnızca bir kısmını bölümlemek gerekir.</span><span class="sxs-lookup"><span data-stu-id="89de5-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="89de5-123">Bu durumda, kısmi desenleri, bazı girişler eşleşen ancak diğer girişler eşleştirilecek başarısız yazın.</span><span class="sxs-lookup"><span data-stu-id="89de5-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="89de5-124">Her zaman bir değer üretmez Etkin desenler çağrılır *kısmi Etkin desenler*; bunlar seçeneği türünde bir dönüş değerine sahip.</span><span class="sxs-lookup"><span data-stu-id="89de5-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="89de5-125">Kısmi bir etkin düzeni tanımlamak için bir joker karakter kullanın. (\_) Muz klipleri içinde Desen listesinin sonunda.</span><span class="sxs-lookup"><span data-stu-id="89de5-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="89de5-126">Aşağıdaki kodu kısmi bir etkin desen kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="89de5-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="89de5-127">Önceki örnek çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="89de5-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="89de5-128">Kısmi Etkin desenler kullanırken bazen tek tek seçimler ayrık veya birbirini dışlayan olabilir, ancak bunlar olmaması.</span><span class="sxs-lookup"><span data-stu-id="89de5-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="89de5-129">Bazı sayılar kareler hem 64 gibi küpler olduğundan aşağıdaki örnekte, deseni kare ve küp deseni ayrık, değildir.</span><span class="sxs-lookup"><span data-stu-id="89de5-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="89de5-130">Aşağıdaki program tüm tamsayıların en fazla kare hem de küp olan 1000000 yazdırır.</span><span class="sxs-lookup"><span data-stu-id="89de5-130">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="89de5-131">Çıktı aşağıdaki şekilde olacaktır:</span><span class="sxs-lookup"><span data-stu-id="89de5-131">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="89de5-132">Parametreli Etkin desenler</span><span class="sxs-lookup"><span data-stu-id="89de5-132">Parameterized Active Patterns</span></span>

<span data-ttu-id="89de5-133">Etkin desenler, eşleştirilen öğesi için en az bir bağımsız değişkeni her zaman alır ancak adı bu durumda da, ek bağımsız değişken alabilir *parametreli etkin desen* uygular.</span><span class="sxs-lookup"><span data-stu-id="89de5-133">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="89de5-134">Ek bağımsız değişkenler özelleştirilmesi için genel bir desen sağlar.</span><span class="sxs-lookup"><span data-stu-id="89de5-134">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="89de5-135">Örneğin, normal ifade ayrıca kısmi etkin deseni kullanan aşağıdaki kod, olduğu gibi ek bir parametre olarak dizeler genellikle ayrıştırmak için normal ifadeleri kullanma Etkin desenler dahil `Integer` önceki kod örneğinde tanımlanan.</span><span class="sxs-lookup"><span data-stu-id="89de5-135">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="89de5-136">Bu örnekte, çeşitli tarih biçimleri için normal ifadeleri kullanma dizeleri genel ParseRegex etkin düzeni özelleştirildiği verilir.</span><span class="sxs-lookup"><span data-stu-id="89de5-136">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="89de5-137">Tamsayı etkin deseni, eşleşen dizeleri DateTime oluşturucuya geçirilen tamsayı dönüştürmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89de5-137">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="89de5-138">Önceki kodun çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="89de5-138">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="89de5-139">Etkin desenler yalnızca eşleşen bir ifade deseni için sınırlı değildir, ayrıca bunları let bağlamaları üzerinde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89de5-139">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="89de5-140">Önceki kodun çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="89de5-140">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="89de5-141">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="89de5-141">See also</span></span>

- [<span data-ttu-id="89de5-142">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="89de5-142">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="89de5-143">Eşleşme İfadeleri</span><span class="sxs-lookup"><span data-stu-id="89de5-143">Match Expressions</span></span>](match-expressions.md)