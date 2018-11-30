---
title: string (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: 66b1729363878f69f868b8b8fd6e9e7011426f27
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672010"
---
# <a name="string-c-reference"></a><span data-ttu-id="fa31d-102">string (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="fa31d-102">string (C# Reference)</span></span>

<span data-ttu-id="fa31d-103">`string` Türü bir dizi sıfır veya daha fazla Unicode karakteri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="fa31d-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="fa31d-104">`string` için bir diğer addır <xref:System.String> .NET içinde.</span><span class="sxs-lookup"><span data-stu-id="fa31d-104">`string` is an alias for <xref:System.String> in .NET.</span></span>

<span data-ttu-id="fa31d-105">Ancak `string` bir başvuru türü eşitlik işleçleri (`==` ve `!=`) değerlerini karşılaştırmak için tanımlanan `string` nesnelerine, başvuruda değil.</span><span class="sxs-lookup"><span data-stu-id="fa31d-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="fa31d-106">Bu, daha sezgisel dizeyi eşitlik için sınama yapar.</span><span class="sxs-lookup"><span data-stu-id="fa31d-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="fa31d-107">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="fa31d-107">For example:</span></span>

```csharp
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine((object)a == (object)b);
```

<span data-ttu-id="fa31d-108">Bu "True" görüntüler ve ardından "False" eşdeğer dizeler içeriğini çünkü ancak `a` ve `b` aynı dize örneğine işaret etmiyor.</span><span class="sxs-lookup"><span data-stu-id="fa31d-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="fa31d-109">+ İşleci dizeleri birleştirir:</span><span class="sxs-lookup"><span data-stu-id="fa31d-109">The + operator concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="fa31d-110">Bu, "Günaydın" içeren bir dize nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="fa31d-110">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="fa31d-111">Dizelerdir *değişmez*--bir dize nesnesi, içeriğini nesne oluşturulduktan sonra değiştirilemez, söz dizimi sağlar ancak görünür Bunu yapmak gibi.</span><span class="sxs-lookup"><span data-stu-id="fa31d-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="fa31d-112">Örneğin, bu kod yazdığınızda, derleyici, gerçekte yeni dizi karakteri tutmak için yeni bir dize nesnesi oluşturur ve yeni nesne b atanır.</span><span class="sxs-lookup"><span data-stu-id="fa31d-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="fa31d-113">"H" dizesi, ardından çöp toplama için uygundur.</span><span class="sxs-lookup"><span data-stu-id="fa31d-113">The string "h" is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="fa31d-114">[] İşleci karakterlerin tek tek salt okunur erişim için kullanılan bir `string`:</span><span class="sxs-lookup"><span data-stu-id="fa31d-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="fa31d-115">Dize değişmez değerleri, tür `string` ve teklif iki biçimde yazılır ve @-quoted.</span><span class="sxs-lookup"><span data-stu-id="fa31d-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="fa31d-116">Dize değişmez değerleri çift tırnak işaretleri (") içine alınan Teklif:</span><span class="sxs-lookup"><span data-stu-id="fa31d-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="fa31d-117">Dize değişmez değerleri, sabit değer herhangi bir karakter içerebilir.</span><span class="sxs-lookup"><span data-stu-id="fa31d-117">String literals can contain any character literal.</span></span> <span data-ttu-id="fa31d-118">Kaçış dizileri dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="fa31d-118">Escape sequences are included.</span></span> <span data-ttu-id="fa31d-119">Aşağıdaki örnekte çıkış dizisi `\\` eğik için `\u0066` harfi f, için ve `\n` için yeni satır.</span><span class="sxs-lookup"><span data-stu-id="fa31d-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp
string a = "\\\u0066\n";
Console.WriteLine(a);
```

> [!NOTE]
> <span data-ttu-id="fa31d-120">Çıkış kodu `\udddd` (burada `dddd` bir dört basamaklı sayıdır) U + Unicode karakteri temsil eden`dddd`.</span><span class="sxs-lookup"><span data-stu-id="fa31d-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="fa31d-121">Sekiz basamağı Unicode atlatma kodları da tanınan: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="fa31d-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="fa31d-122">Verbatim dize değişmez değerleri ile başlayıp `@` ve ayrıca çift tırnak işaretleri içine alınır.</span><span class="sxs-lookup"><span data-stu-id="fa31d-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="fa31d-123">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="fa31d-123">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="fa31d-124">Kaçış dizileri: avantajlarındandır harfi harfine dizeler *değil* işlenen, hangi kolaylaştırır, örneğin, tam olarak nitelenmiş dosya adını yazın:</span><span class="sxs-lookup"><span data-stu-id="fa31d-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="fa31d-125">Çift tırnak işareti eklemek için bir @-quoted , çift, dize:</span><span class="sxs-lookup"><span data-stu-id="fa31d-125">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

<span data-ttu-id="fa31d-126">Diğer kullanımları için `@` özel karakter bkz [@--tam tanımlayıcı](../tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="fa31d-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>

<span data-ttu-id="fa31d-127">C# dizeleri hakkında daha fazla bilgi için bkz. [dizeleri](../../programming-guide/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa31d-127">For more information about strings in C#, see [Strings](../../programming-guide/strings/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="fa31d-128">Örnek</span><span class="sxs-lookup"><span data-stu-id="fa31d-128">Example</span></span>

[!code-csharp[csrefKeywordsTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#17)]  

## <a name="c-language-specification"></a><span data-ttu-id="fa31d-129">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="fa31d-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fa31d-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fa31d-130">See also</span></span>

- [<span data-ttu-id="fa31d-131">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="fa31d-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fa31d-132">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="fa31d-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fa31d-133">Dizeleri Kullanmak için En İyi Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="fa31d-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="fa31d-134">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="fa31d-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fa31d-135">Başvuru Türleri</span><span class="sxs-lookup"><span data-stu-id="fa31d-135">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="fa31d-136">Değer Türleri</span><span class="sxs-lookup"><span data-stu-id="fa31d-136">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="fa31d-137">Temel Dize İşlemleri</span><span class="sxs-lookup"><span data-stu-id="fa31d-137">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="fa31d-138">Yeni Dizeler Oluşturma</span><span class="sxs-lookup"><span data-stu-id="fa31d-138">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="fa31d-139">Sayısal Sonuçlar Tablosunu Biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="fa31d-139">Formatting Numeric Results Table</span></span>](formatting-numeric-results-table.md)
