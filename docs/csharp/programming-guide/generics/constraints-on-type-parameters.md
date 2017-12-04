---
title: "Tür Parametrelerindeki Kısıtlamalar (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: "41"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f5382b0050b81ed3bb1a075a042bdc4034a3975d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a><span data-ttu-id="533e6-102">Tür Parametrelerindeki Kısıtlamalar (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="533e6-102">Constraints on Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="533e6-103">Genel bir sınıf tanımladığınızda, sınıfını başlattığında, istemci kodu tür bağımsız değişkenleri için kullanabileceğiniz türü tür kısıtlamaları uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="533e6-103">When you define a generic class, you can apply restrictions to the kinds of types that client code can use for type arguments when it instantiates your class.</span></span> <span data-ttu-id="533e6-104">İstemci kodu kısıtlaması tarafından izin verilmeyen bir türünü kullanarak, sınıfının örneği çalışırsa, bir derleme zamanı hatası sonucudur.</span><span class="sxs-lookup"><span data-stu-id="533e6-104">If client code tries to instantiate your class by using a type that is not allowed by a constraint, the result is a compile-time error.</span></span> <span data-ttu-id="533e6-105">Bu kısıtlamalar kısıtlamaları denir.</span><span class="sxs-lookup"><span data-stu-id="533e6-105">These restrictions are called constraints.</span></span> <span data-ttu-id="533e6-106">Kısıtlamaları belirtilen kullanarak `where` bağlamsal anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="533e6-106">Constraints are specified by using the `where` contextual keyword.</span></span> <span data-ttu-id="533e6-107">Aşağıdaki tabloda kısıtlamaları altı türlerini listeler:</span><span class="sxs-lookup"><span data-stu-id="533e6-107">The following table lists the six types of constraints:</span></span>  
  
|<span data-ttu-id="533e6-108">Kısıtlama</span><span class="sxs-lookup"><span data-stu-id="533e6-108">Constraint</span></span>|<span data-ttu-id="533e6-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="533e6-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="533e6-110">Burada T: yapısı</span><span class="sxs-lookup"><span data-stu-id="533e6-110">where T: struct</span></span>|<span data-ttu-id="533e6-111">Tür bağımsız değişkeni bir değer türü olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="533e6-111">The type argument must be a value type.</span></span> <span data-ttu-id="533e6-112">Herhangi bir değer türü dışında <xref:System.Nullable> belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-112">Any value type except <xref:System.Nullable> can be specified.</span></span> <span data-ttu-id="533e6-113">Bkz: [kullanarak boş değer atanabilir türler](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="533e6-113">See [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) for more information.</span></span>|  
|<span data-ttu-id="533e6-114">Burada T: sınıfı</span><span class="sxs-lookup"><span data-stu-id="533e6-114">where T : class</span></span>|<span data-ttu-id="533e6-115">Tür bağımsız değişkeni bir başvuru türü olmalıdır; Bu aynı zamanda herhangi sınıfı, arabirim, temsilci veya dizi türü için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="533e6-115">The type argument must be a reference type; this applies also to any class, interface, delegate, or array type.</span></span>|  
|<span data-ttu-id="533e6-116">Burada T: new()</span><span class="sxs-lookup"><span data-stu-id="533e6-116">where T : new()</span></span>|<span data-ttu-id="533e6-117">Tür bağımsız değişkeni genel bir parametresiz oluşturucuya sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="533e6-117">The type argument must have a public parameterless constructor.</span></span> <span data-ttu-id="533e6-118">Diğer kısıtlamalar ile birlikte kullanıldığında `new()` kısıtlaması son belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="533e6-118">When used together with other constraints, the `new()` constraint must be specified last.</span></span>|  
|<span data-ttu-id="533e6-119">Burada T: \<temel sınıf adı ></span><span class="sxs-lookup"><span data-stu-id="533e6-119">where T : \<base class name></span></span>|<span data-ttu-id="533e6-120">Tür bağımsız değişkeni, olabilir veya belirtilen temel sınıfından türetilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-120">The type argument must be or derive from the specified base class.</span></span>|  
|<span data-ttu-id="533e6-121">Burada T: \<arabirim adı ></span><span class="sxs-lookup"><span data-stu-id="533e6-121">where T : \<interface name></span></span>|<span data-ttu-id="533e6-122">Tür bağımsız değişkeni olabilir veya belirtilen arabirimini uygulaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="533e6-122">The type argument must be or implement the specified interface.</span></span> <span data-ttu-id="533e6-123">Birden çok arabirim kısıtlamaları belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-123">Multiple interface constraints can be specified.</span></span> <span data-ttu-id="533e6-124">Kısıtlayan arabirimi genel olabilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-124">The constraining interface can also be generic.</span></span>|  
|<span data-ttu-id="533e6-125">Burada T: U</span><span class="sxs-lookup"><span data-stu-id="533e6-125">where T : U</span></span>|<span data-ttu-id="533e6-126">T olması veya u için sağlanan bağımsız değişken öğesinden türetilen için sağlanan tür bağımsız değişkeni</span><span class="sxs-lookup"><span data-stu-id="533e6-126">The type argument supplied for T must be or derive from the argument supplied for U.</span></span>|  
  
## <a name="why-use-constraints"></a><span data-ttu-id="533e6-127">Kısıtlamaları neden kullanılır?</span><span class="sxs-lookup"><span data-stu-id="533e6-127">Why Use Constraints</span></span>  
 <span data-ttu-id="533e6-128">Geçerli olup olmadığını belirlemek için veya başka bir öğe karşılaştırmak için genel bir listedeki bir öğe incelemek isterseniz, derleyicinin bazı istemci ortak tarafından belirtilen tür bağımsız değişkeni tarafından işleci veya yöntem çağrılacak olan desteklenecek garanti olmalıdır de.</span><span class="sxs-lookup"><span data-stu-id="533e6-128">If you want to examine an item in a generic list to determine whether it is valid or to compare it to some other item, the compiler must have some guarantee that the operator or method it has to call will be supported by any type argument that might be specified by client code.</span></span> <span data-ttu-id="533e6-129">Bu garantisi, genel bir sınıf tanımı için bir veya daha fazla kısıtlamaları uygulayarak elde edilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-129">This guarantee is obtained by applying one or more constraints to your generic class definition.</span></span> <span data-ttu-id="533e6-130">Örneğin, taban sınıf kısıtlaması bu tür nesneler yalnızca derleyici söyler veya öğesinden türetilmiş türü tür bağımsız değişkenleri kullanılır.</span><span class="sxs-lookup"><span data-stu-id="533e6-130">For example, the base class constraint tells the compiler that only objects of this type or derived from this type will be used as type arguments.</span></span> <span data-ttu-id="533e6-131">Derleyici bu garantisi sonra genel sınıfında çağrılacak türü yöntemleri izin verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="533e6-131">Once the compiler has this guarantee, it can allow methods of that type to be called in the generic class.</span></span> <span data-ttu-id="533e6-132">Bağlamsal anahtar sözcüğünü kullanarak kısıtlamalar uygulanır `where`.</span><span class="sxs-lookup"><span data-stu-id="533e6-132">Constraints are applied by using the contextual keyword `where`.</span></span> <span data-ttu-id="533e6-133">Aşağıdaki kod örneği için ekleyebilirsiniz biz işlevini gösterir `GenericList<T>` sınıfı (içinde [genel türlere giriş](../../../csharp/programming-guide/generics/introduction-to-generics.md)) bir taban sınıf kısıtlaması uygulayarak.</span><span class="sxs-lookup"><span data-stu-id="533e6-133">The following code example demonstrates the functionality we can add to the `GenericList<T>` class (in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)) by applying a base class constraint.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 <span data-ttu-id="533e6-134">Kullanmak genel bir sınıf kısıtlaması etkinleştirir `Employee.Name` özelliği tüm öğeleri T türü ya da olması garanti çünkü bir `Employee` veya öğesinden devralınan bir nesneyi `Employee`.</span><span class="sxs-lookup"><span data-stu-id="533e6-134">The constraint enables the generic class to use the `Employee.Name` property because all items of type T are guaranteed to be either an `Employee` object or an object that inherits from `Employee`.</span></span>  
  
 <span data-ttu-id="533e6-135">Aynı tür parametresi birden çok kısıtlama uygulanabilir ve kısıtlamaları kendilerini genel türleri, aşağıdaki gibi olabilir:</span><span class="sxs-lookup"><span data-stu-id="533e6-135">Multiple constraints can be applied to the same type parameter, and the constraints themselves can be generic types, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 <span data-ttu-id="533e6-136">Tür parametresi kısıtlayarak, izin verilen işlemler ve kısıtlama türü ve devralma hiyerarşisi içindeki tüm türler tarafından desteklenen yöntem çağrılarını sayısını artırın.</span><span class="sxs-lookup"><span data-stu-id="533e6-136">By constraining the type parameter, you increase the number of allowable operations and method calls to those supported by the constraining type and all types in its inheritance hierarchy.</span></span> <span data-ttu-id="533e6-137">Bu nedenle, tasarlarken genel sınıfları veya yöntemleri, basit atama ötesinde Genel üyeler üzerinde herhangi bir işlemi gerçekleştirme veya kaldırılacak tarafından desteklenmeyen herhangi bir yöntem çağırma varsa `System.Object`, tür parametresi kısıtlamaları uygulamak gerekir.</span><span class="sxs-lookup"><span data-stu-id="533e6-137">Therefore, when you design generic classes or methods, if you will be performing any operation on the generic members beyond simple assignment or calling any methods not supported by `System.Object`, you will have to apply constraints to the type parameter.</span></span>  
  
 <span data-ttu-id="533e6-138">Uygularken `where T : class` kısıtlaması, kaçının `==` ve `!=` tür parametresi işleçlerini çünkü bu işleçlere yalnızca başvuru kimliği olmayan değer eşitlik için test.</span><span class="sxs-lookup"><span data-stu-id="533e6-138">When applying the `where T : class` constraint, avoid the `==` and `!=` operators on the type parameter because these operators will test for reference identity only, not for value equality.</span></span> <span data-ttu-id="533e6-139">Bağımsız değişken olarak kullanılan bir türdeki Bu işleçleri aşırı yüklenmiş olsa bile bu geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="533e6-139">This is the case even if these operators are overloaded in a type that is used as an argument.</span></span> <span data-ttu-id="533e6-140">Aşağıdaki kod bu noktayı gösterir; Çıktı halde false şeklindedir <xref:System.String> sınıf aşırı `==` işleci.</span><span class="sxs-lookup"><span data-stu-id="533e6-140">The following code illustrates this point; the output is false even though the <xref:System.String> class overloads the `==` operator.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 <span data-ttu-id="533e6-141">Bu davranış derleme zamanında Derleyici yalnızca T bir başvuru türü ve dolayısıyla tüm başvuru türleri için geçerli varsayılan işleçleri kullanması gerekir bilir, nedeni.</span><span class="sxs-lookup"><span data-stu-id="533e6-141">The reason for this behavior is that, at compile time, the compiler only knows that T is a reference type, and therefore must use the default operators that are valid for all reference types.</span></span> <span data-ttu-id="533e6-142">Değer eşitlik için test etmeniz gerekir, önerilen yöntem de uygulamak için ise `where T : IComparable<T>` kısıtlaması ve genel bir sınıf oluşturmak için kullanılan herhangi bir sınıf arabirimi uygulayın.</span><span class="sxs-lookup"><span data-stu-id="533e6-142">If you must test for value equality, the recommended way is to also apply the `where T : IComparable<T>` constraint and implement that interface in any class that will be used to construct the generic class.</span></span>  
  
## <a name="constraining-multiple-parameters"></a><span data-ttu-id="533e6-143">Birden çok parametre sınırlama</span><span class="sxs-lookup"><span data-stu-id="533e6-143">Constraining Multiple Parameters</span></span>  
 <span data-ttu-id="533e6-144">Aşağıdaki örnekte gösterildiği gibi birden çok parametre ve tek bir parametre için birden çok kısıtlama kısıtlamaları uygulayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="533e6-144">You can apply constraints to multiple parameters, and multiple constraints to a single parameter, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a><span data-ttu-id="533e6-145">Sınırsız tür parametreleri</span><span class="sxs-lookup"><span data-stu-id="533e6-145">Unbounded Type Parameters</span></span>  
 <span data-ttu-id="533e6-146">Tür ortak sınıfı T gibi herhangi bir kısıtlama söz konusu parametrelerindeki `SampleClass<T>{}`, sınırsız tür parametreleri olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="533e6-146">Type parameters that have no constraints, such as T in public class `SampleClass<T>{}`, are called unbounded type parameters.</span></span> <span data-ttu-id="533e6-147">Sınırsız tür parametreleri aşağıdaki kurallar vardır:</span><span class="sxs-lookup"><span data-stu-id="533e6-147">Unbounded type parameters have the following rules:</span></span>  
  
-   <span data-ttu-id="533e6-148">`!=` Ve `==` somut tür bağımsız değişkeni bu işleçlere destekleyecek garanti olduğundan işleçleri kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="533e6-148">The `!=` and `==` operators cannot be used because there is no guarantee that the concrete type argument will support these operators.</span></span>  
  
-   <span data-ttu-id="533e6-149">Ve ondan dönüştürülebilir `System.Object` veya herhangi bir arabirim türü açıkça dönüştürülebilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-149">They can be converted to and from `System.Object` or explicitly converted to any interface type.</span></span>  
  
-   <span data-ttu-id="533e6-150">' Karşılaştırabilirsiniz [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="533e6-150">You can compare to [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="533e6-151">Sınırsız bir parametre karşılaştırılır varsa `null`, karşılaştırma her zaman tür bağımsız değişkeni bir değer türü ise false döndürür.</span><span class="sxs-lookup"><span data-stu-id="533e6-151">If an unbounded parameter is compared to `null`, the comparison will always return false if the type argument is a value type.</span></span>  
  
## <a name="type-parameters-as-constraints"></a><span data-ttu-id="533e6-152">Tür parametreleri kısıtlamaları olarak</span><span class="sxs-lookup"><span data-stu-id="533e6-152">Type Parameters as Constraints</span></span>  
 <span data-ttu-id="533e6-153">Bir kısıtlama yararlı üye işlevi kendi tür parametresi ile olduğu gibi aşağıdaki örnekte gösterildiği gibi kapsayan tür tür parametresi bu parametreye sınırlamak bir genel tür parametresi kullanımını sahiptir:</span><span class="sxs-lookup"><span data-stu-id="533e6-153">The use of a generic type parameter as a constraint is useful when a member function with its own type parameter has to constrain that parameter to the type parameter of the containing type, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 <span data-ttu-id="533e6-154">Önceki örnekte, `T` türü kısıtlaması bağlamında `Add` yöntemi ve sınırsız tür parametresi bağlamında `List` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="533e6-154">In the previous example, `T` is a type constraint in the context of the `Add` method, and an unbounded type parameter in the context of the `List` class.</span></span>  
  
 <span data-ttu-id="533e6-155">Tür parametreleri, genel bir sınıf tanımları kısıtlamalar olarak da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="533e6-155">Type parameters can also be used as constraints in generic class definitions.</span></span> <span data-ttu-id="533e6-156">Tür parametresi herhangi bir tür parametre birlikte köşeli ayraç içinde bildirilmelidir dikkat edin:</span><span class="sxs-lookup"><span data-stu-id="533e6-156">Note that the type parameter must be declared within the angle brackets together with any other type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 <span data-ttu-id="533e6-157">Tür parametreleri yararlılığını Genel sınıflar kısıtlamalarıyla olarak den türemesi dışında derleyici tür parametresi hakkında hiçbir şey kabul edilebilir olduğundan çok sınırlı `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="533e6-157">The usefulness of type parameters as constraints with generic classes is very limited because the compiler can assume nothing about the type parameter except that it derives from `System.Object`.</span></span> <span data-ttu-id="533e6-158">Genel sınıflar, iki tür parametreleri arasında bir devralma ilişkisi uygulamak istediğiniz senaryolarda kısıtlamalar olarak tür parametreleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="533e6-158">Use type parameters as constraints on generic classes in scenarios in which you want to enforce an inheritance relationship between two type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533e6-159">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="533e6-159">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="533e6-160">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="533e6-160">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="533e6-161">Genel türlere giriş</span><span class="sxs-lookup"><span data-stu-id="533e6-161">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="533e6-162">Genel sınıflar</span><span class="sxs-lookup"><span data-stu-id="533e6-162">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
 [<span data-ttu-id="533e6-163">New kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="533e6-163">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)