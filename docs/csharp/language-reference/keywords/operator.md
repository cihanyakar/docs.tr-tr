---
title: işleç anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
description: Yerleşik bir C# İşleç aşırı yüklemesi hakkında bilgi edinin
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: cdc052da4457a59cc66848780e944ccf203acf39
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235610"
---
# <a name="operator-c-reference"></a><span data-ttu-id="9acb6-103">operator (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="9acb6-103">operator (C# Reference)</span></span>

<span data-ttu-id="9acb6-104">Kullanım `operator` anahtar sözcük yerleşik bir işleç aşırı yüklemesi veya bir kullanıcı tanımlı dönüştürme bir class veya struct bildiriminde sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="9acb6-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="9acb6-105">Özel bir sınıf ya da yapı üzerinde operatör aşırı yükleme için karşılık gelen türü bir işleç bildirimi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="9acb6-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="9acb6-106">Yerleşik bir C# işleci aşırı işleç bildirimi, aşağıdaki kurallar karşılamanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="9acb6-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="9acb6-107">Her ikisini de içeren bir `public` ve `static` değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="9acb6-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="9acb6-108">İçerdiği `operator X` burada `X` adı ya da sembol aşırı işleci.</span><span class="sxs-lookup"><span data-stu-id="9acb6-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="9acb6-109">Birli işleçler bir parametreye sahip ve ikili işleçler iki parametreye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="9acb6-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="9acb6-110">Her durumda sınıfın veya yapının işleci bildiren aynı türde en az bir parametresi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9acb6-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="9acb6-111">Dönüştürme işleçleri tanımlama hakkında daha fazla bilgi için bkz: [açık](explicit.md) ve [örtük](implicit.md) anahtar sözcüğü makaleler.</span><span class="sxs-lookup"><span data-stu-id="9acb6-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="9acb6-112">Aşırı yüklenebilir C# işleçleri genel bir bakış için bkz: [fazla yüklenebilir işleçler](../../programming-guide/statements-expressions-operators/overloadable-operators.md) makalesi.</span><span class="sxs-lookup"><span data-stu-id="9acb6-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="9acb6-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="9acb6-113">Example</span></span>

<span data-ttu-id="9acb6-114">Aşağıdaki örnekte tanımlayan bir `Fraction` kesirli sayılar temsil eden tür.</span><span class="sxs-lookup"><span data-stu-id="9acb6-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="9acb6-115">Aşırı `+` ve `*` kesirli toplama ve çarpma gerçekleştirmek için işleçler ve ayrıca bir dönüştürme işleci bu dönüştürür sağlar bir `Fraction` için yazın bir `double` türü.</span><span class="sxs-lookup"><span data-stu-id="9acb6-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="9acb6-116">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="9acb6-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9acb6-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9acb6-117">See also</span></span>

- [<span data-ttu-id="9acb6-118">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="9acb6-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9acb6-119">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9acb6-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9acb6-120">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="9acb6-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9acb6-121">implicit</span><span class="sxs-lookup"><span data-stu-id="9acb6-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="9acb6-122">explicit</span><span class="sxs-lookup"><span data-stu-id="9acb6-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="9acb6-123">Fazla yüklenebilir işleçler</span><span class="sxs-lookup"><span data-stu-id="9acb6-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="9acb6-124">Nasıl yapılır: Yapılar arasında kullanıcı tanımlı Dönüşümler Uygulama</span><span class="sxs-lookup"><span data-stu-id="9acb6-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
