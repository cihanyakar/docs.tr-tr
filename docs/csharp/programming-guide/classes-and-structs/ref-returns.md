---
title: "Ref dönüş değerleri ve ref Yereller (C# Kılavuzu)"
description: "Ref dönüş ve ref yerel değerleri tanımlayın ve nasıl kullanılacağını öğrenin"
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.openlocfilehash: 1d8fb092b578602b5d4f791a3fd14f47dfae1ba6
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="ef99f-103">Ref döndürür ve ref Yereller</span><span class="sxs-lookup"><span data-stu-id="ef99f-103">Ref returns and ref locals</span></span>

<span data-ttu-id="ef99f-104">C# 7 ile başlayan, C# başvurusu dönüş değerleri (başvuru dönüşleri) destekler.</span><span class="sxs-lookup"><span data-stu-id="ef99f-104">Starting with C# 7, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="ef99f-105">Bir başvuru dönüş değeri bir değer yerine bir nesne başvurusu bir çağırana geri dönmek tek bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="ef99f-105">A reference return value allows a method to return a reference to an object, rather than a value, back to a caller.</span></span> <span data-ttu-id="ef99f-106">Arayan değere veya başvuruya göre döndürülmedi gibi döndürülen döndürülen nesne kabul seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-106">The caller can then choose to treat the returned object returned as if it were returned by value or by reference.</span></span> <span data-ttu-id="ef99f-107">Yerine yerel bir ref değerdir çağıran bir başvuru olarak işleme başvuruya göre bir değer döndürdü.</span><span class="sxs-lookup"><span data-stu-id="ef99f-107">A value returned by reference that the caller handles as a reference rather than a value is a ref local.</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="ef99f-108">Bir başvuru dönüş değeri nedir?</span><span class="sxs-lookup"><span data-stu-id="ef99f-108">What is a reference return value?</span></span>

<span data-ttu-id="ef99f-109">Çoğu geliştirici çağrılan yöntemi için bağımsız değişken geçirme ile bilginiz *başvuruya göre*.</span><span class="sxs-lookup"><span data-stu-id="ef99f-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="ef99f-110">Çağrılan yöntemin bağımsız değişken listesi başvuruya göre geçirilen bir değer ve değerine çağrılan yöntemi tarafından yapılan değişiklikleri içerir çağırana döndürülen.</span><span class="sxs-lookup"><span data-stu-id="ef99f-110">A called method's argument list includes a value passed by reference, and any changes made to its value by the called method are returned to the caller.</span></span> <span data-ttu-id="ef99f-111">A *başvuru dönüş değeri* tersidir:</span><span class="sxs-lookup"><span data-stu-id="ef99f-111">A *reference return value* is the opposite:</span></span>

- <span data-ttu-id="ef99f-112">Çağrılan yöntemin dönüş değeri, bağımsız değişken kendisine geçirilen yerine başvurusudur.</span><span class="sxs-lookup"><span data-stu-id="ef99f-112">The called method's return value, rather than an argument passed to it, is a reference.</span></span>

- <span data-ttu-id="ef99f-113">Çağrılan yöntemin yerine çağıran yöntemi tarafından döndürülen değer değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-113">The caller, rather than the called method, can modify the value returned by the method.</span></span>

- <span data-ttu-id="ef99f-114">Nesne durumda üzerinde çağıran yansıtılır değişikliklerin yerine bağımsız değişkenin, yöntemin dönüş değeri çağıran tarafından yapılan değişiklikler, yöntemi çağrıldı nesne durumda yansıtılır.</span><span class="sxs-lookup"><span data-stu-id="ef99f-114">Instead of modifications to the argument that are reflected in state of the object on the caller, modifications to the method's return value by the caller are reflected in the state of the object whose method was called.</span></span>

<span data-ttu-id="ef99f-115">Başvuru dönüş değerleri daha küçük kod üretmek yanı çağırana ilgi yalnızca tek tek veri öğeleri, bir dizi öğesi gibi göstermek bir nesne izin.</span><span class="sxs-lookup"><span data-stu-id="ef99f-115">Reference return values can produce more compact code, as well as allow an object to expose only the individual data items, such as an array element, that are of interest to the caller.</span></span> <span data-ttu-id="ef99f-116">Bu, çağıran nesnenin durumu yanlışlıkla değiştirecek olasılığını azaltır.</span><span class="sxs-lookup"><span data-stu-id="ef99f-116">This reduces the likelihood that the caller will inadvertently modify the object's state.</span></span>

<span data-ttu-id="ef99f-117">Bir yöntem başvuru dönüş değeri olarak döndürebilir değeri bazı kısıtlamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="ef99f-117">There are some restrictions on the value that a method can return as a reference return value.</span></span> <span data-ttu-id="ef99f-118">Bu güncelleştirmeler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="ef99f-118">These include:</span></span>

- <span data-ttu-id="ef99f-119">Dönüş değeri olamaz `void`.</span><span class="sxs-lookup"><span data-stu-id="ef99f-119">The return value cannot be `void`.</span></span> <span data-ttu-id="ef99f-120">Bir yöntemi tanımlamak çalışan bir `void` başvuru dönüş değeri derleyici hatası CS1547 oluşturur, "Anahtar sözcüğü 'void' Bu bağlamda kullanılamaz."</span><span class="sxs-lookup"><span data-stu-id="ef99f-120">Attempting to define a method with a `void` reference return value generates compiler error CS1547, "Keyword 'void' cannot be used in this context."</span></span>
 
- <span data-ttu-id="ef99f-121">Dönüş değeri döndürdüğü yöntemi yerel bir değişkende olamaz; döndürdüğü yöntemi dışında bir kapsamı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ef99f-121">The return value cannot be a local variable in the method that returns it; it must have a scope that is outside the method that returns it.</span></span> <span data-ttu-id="ef99f-122">Bu yönteme geçirilen bağımsız değişken olabilir veya bir örneği veya sınıfının statik alanı olabilir.</span><span class="sxs-lookup"><span data-stu-id="ef99f-122">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="ef99f-123">Derleyici Hatası CS8168, yerel bir değişken oluşturur dönüş çalışılırken "döndüremiyor yerel 'obj' başvuruya göre yerel bir ref olmadığından."</span><span class="sxs-lookup"><span data-stu-id="ef99f-123">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="ef99f-124">Dönüş değeri olamaz bir `null`.</span><span class="sxs-lookup"><span data-stu-id="ef99f-124">The return value cannot be a `null`.</span></span> <span data-ttu-id="ef99f-125">Döndürülecek çalışırken `null` derleyici hatası "bir ifade başvuruya göre döndürülemez olduğundan bu bağlamda kullanılamaz." CS8156 oluşturur</span><span class="sxs-lookup"><span data-stu-id="ef99f-125">Attempting to return `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="ef99f-126">Ref dönüş yöntemiyle bir null değer döndürmesi gerekiyorsa, bir başvuru türü null (örneklendirilmemiş) değerini ya da döndürebilir ya da bir [boş değer atanabilir tür](../nullable-types/index.md) değer türü.</span><span class="sxs-lookup"><span data-stu-id="ef99f-126">If a method with a ref return needs to return a null value, you can either return a null (uninstantiated) value for a reference type or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="ef99f-127">Dönüş değeri bir sabit, bir numaralandırma üyesi veya bir özelliği olamaz bir `class` veya `struct`.</span><span class="sxs-lookup"><span data-stu-id="ef99f-127">The return value cannot be a constant, an enumeration member, or a property of a `class` or `struct`.</span></span> <span data-ttu-id="ef99f-128">Derleyici Hatası CS8156 "bir ifade başvuruya göre döndürülemez olduğundan bu bağlamda kullanılamaz.", bunlar döndürülecek çalışırken oluşturur</span><span class="sxs-lookup"><span data-stu-id="ef99f-128">Attempting to return these generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="ef99f-129">Dönüş değerini bilinmeyen hala durumdayken yürütme bitmeden önce zaman uyumsuz bir yöntem döndürebilir olduğundan, ayrıca, başvuru dönüş değerleri zaman uyumsuz yöntemleri izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="ef99f-129">In addition, because an asynchronous method may return before it has finished execution, while its return value is still unknown, reference return values are not allowed on async methods.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="ef99f-130">Ref dönüş değeri tanımlama</span><span class="sxs-lookup"><span data-stu-id="ef99f-130">Defining a ref return value</span></span>

<span data-ttu-id="ef99f-131">Ref dönüş değeri ekleyerek tanımlarsınız [ref](../../language-reference/keywords/ref.md) yöntem imzası dönüş türü için anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="ef99f-131">You define a ref return value by adding the [ref](../../language-reference/keywords/ref.md) keyword to the return type of the method signature.</span></span> <span data-ttu-id="ef99f-132">Örneğin, aşağıdaki imzası belirten `GetContactInformation` özelliği bir başvuru döndürür bir `Person` çağıran nesneye:</span><span class="sxs-lookup"><span data-stu-id="ef99f-132">For example, the following signature indicates that the `GetContactInformation` property returns a reference to a `Person` object to the caller:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

<span data-ttu-id="ef99f-133">Ayrıca, nesnenin adını döndürülen her tarafından [dönmek](../../language-reference/keywords/return.md) yöntem gövdesi deyiminde öncesinde, tarafından [ref](../../language-reference/keywords/ref.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="ef99f-133">In addition, the name of the object returned by each [return](../../language-reference/keywords/return.md) statement in the method body must be preceded by the [ref](../../language-reference/keywords/ref.md) keyword.</span></span> <span data-ttu-id="ef99f-134">Örneğin, aşağıdaki `return` deyiminin döndüreceği bir `Person` adlı nesne `p` başvuruya göre:</span><span class="sxs-lookup"><span data-stu-id="ef99f-134">For example, the following `return` statement returns a `Person` object named `p` by reference:</span></span>

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="ef99f-135">Ref dönüş değeri kullanma</span><span class="sxs-lookup"><span data-stu-id="ef99f-135">Consuming a ref return value</span></span>

<span data-ttu-id="ef99f-136">Çağıran bir ref dönüş değeri iki yoldan biriyle işleyebilir:</span><span class="sxs-lookup"><span data-stu-id="ef99f-136">A caller can handle a ref return value in either of two ways:</span></span>

- <span data-ttu-id="ef99f-137">Değere göre bir yönteminden döndürülen sıradan bir değer.</span><span class="sxs-lookup"><span data-stu-id="ef99f-137">As an ordinary value returned by value from a method.</span></span> <span data-ttu-id="ef99f-138">Çağıran, dönüş değeri bir başvuru dönüş değeri olduğunu göz ardı etmeyi seçebilir.</span><span class="sxs-lookup"><span data-stu-id="ef99f-138">The caller can choose to ignore that the return value is a reference return value.</span></span> <span data-ttu-id="ef99f-139">Bu durumda, yöntem çağrısı tarafından döndürülen değer yapılan değişiklikler çağrılan türü durumda yansıtılmaz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-139">In this case, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span> <span data-ttu-id="ef99f-140">Döndürülen değeri bir değer türü ise, yöntem çağrısı tarafından döndürülen değer yapılan değişiklikler çağrılan türü durumda yansıtılmaz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-140">If the returned value is a value type, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span>

- <span data-ttu-id="ef99f-141">Bir başvuru olarak değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ef99f-141">As a reference return value.</span></span> <span data-ttu-id="ef99f-142">Arayan için başvuru dönüş değeri olarak atanır değişkeni tanımlamanız gerekir bir [ref yerel](#ref-local), ve yöntem çağrısı tarafından döndürülen değer değişiklikleri çağrılan türü durumda yansıtılır.</span><span class="sxs-lookup"><span data-stu-id="ef99f-142">The caller must define the variable to which the reference return value is assigned as a [ref local](#ref-local), and any changes to the value returned by the method call are reflected in the state of the called type.</span></span> 

## <a name="ref-locals"></a><span data-ttu-id="ef99f-143">Ref Yereller</span><span class="sxs-lookup"><span data-stu-id="ef99f-143">Ref locals</span></span>

<span data-ttu-id="ef99f-144">Başvuru dönüş değeri bir başvuru olarak işlemek için arayan bir değere bildirmelidir bir *ref yerel* kullanarak `ref` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="ef99f-144">To handle the reference return value as a reference, the caller must declare the value to be a *ref local* by using the `ref` keyword.</span></span> <span data-ttu-id="ef99f-145">Örneğin tarafından döndürülen değer, `Person.GetContactInfomation` yöntemi bir değer yerine bir başvuru olarak kullanılması, yöntem çağrısı gibi görünür:</span><span class="sxs-lookup"><span data-stu-id="ef99f-145">For example, if the value returned by the `Person.GetContactInfomation` method is to be consumed as a reference rather than a value, the method call appears as:</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="ef99f-146">Unutmayın `ref` anahtar sözcüğü kullanılır hem yerel değişken bildirimi önce *ve* yöntemi çağırmadan önce.</span><span class="sxs-lookup"><span data-stu-id="ef99f-146">Note that the `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> <span data-ttu-id="ef99f-147">Her ikisi de dahil etmek için hata `ref` Değişken bildiriminde anahtar sözcükleri ve atama sonuçları derleyici hatası CS8172, "başlatamıyor bir başvuru tarafından değere sahip bir değişken."</span><span class="sxs-lookup"><span data-stu-id="ef99f-147">Failure to include both `ref` keywords in the variable declaration and assignment results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
<span data-ttu-id="ef99f-148">Sonraki değişiklikler `Person` yöntemi tarafından döndürülen nesne yansıtılır `contacts` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="ef99f-148">Subsequent changes to the `Person` object returned by the method are reflected in the `contacts` object.</span></span>

<span data-ttu-id="ef99f-149">Varsa `p` ref yerel kullanarak tanımlı değil `ref` anahtar sözcüğü, yapılan değişiklikleri `p` çağıran tarafından yansıtılmaz `contacts` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="ef99f-149">If `p` is not defined as a ref local by using the `ref` keyword, any changes made to `p` by the caller are not reflected in the `contacts` object.</span></span>
 
## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="ef99f-150">Ref döndürür ve ref Yereller: örneği</span><span class="sxs-lookup"><span data-stu-id="ef99f-150">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="ef99f-151">Aşağıdaki örnek tanımlayan bir `NumberStore` tamsayı değerleri dizisi depolayan sınıf.</span><span class="sxs-lookup"><span data-stu-id="ef99f-151">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="ef99f-152">`FindNumber` Yöntemi büyük veya eşit bir bağımsız değişken olarak geçirilen ilk sayı başvuruya göre döndürür.</span><span class="sxs-lookup"><span data-stu-id="ef99f-152">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="ef99f-153">Büyük veya ona eşit bağımsız değişkeni için herhangi bir sayı ise, yöntem dizin 0 döndürür.</span><span class="sxs-lookup"><span data-stu-id="ef99f-153">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

<span data-ttu-id="ef99f-154">Aşağıdaki örnek çağrıları `NumberStore.FindNumber` 16 eşit veya daha büyük olan ilk değer alma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ef99f-154">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="ef99f-155">Arayan yöntemi tarafından döndürülen değer sonra iki katına çıkar.</span><span class="sxs-lookup"><span data-stu-id="ef99f-155">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="ef99f-156">Örneğin çıktısını gösterildiği gibi bu değişikliği dizi öğelerinin değeri yansıtılır `NumberStore` örneği.</span><span class="sxs-lookup"><span data-stu-id="ef99f-156">As the output from the example shows, this change is reflected in the value of the array elements of the `NumberStore` instance.</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

<span data-ttu-id="ef99f-157">Başvuru dönüş değerleri desteği, böyle bir işlem dizin değerini birlikte dizi öğesinin döndürerek genellikle gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="ef99f-157">Without support for reference return values, such an operation is usually performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="ef99f-158">Çağıran, ayrı bir yöntem çağrısı değeri değiştirmek için bu dizini sonra kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-158">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="ef99f-159">Ancak, çağıran erişmek ve büyük olasılıkla diğer dizi değerlerini değiştirmek için dizini de değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-159">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="ef99f-160">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ef99f-160">See also</span></span>

[<span data-ttu-id="ef99f-161">ref anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="ef99f-161">ref keyword</span></span>](../../language-reference/keywords/ref.md)