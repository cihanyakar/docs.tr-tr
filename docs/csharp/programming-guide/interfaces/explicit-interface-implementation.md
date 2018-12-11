---
title: Açık arabirim uygulaması - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: e985da878ca4160938f29911d4313ee6cd731aeb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244836"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="12769-102">Açık Arabirim Uygulaması (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="12769-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="12769-103">Varsa bir [sınıfı](../../../csharp/language-reference/keywords/class.md) üyenin sınıf üzerinde uygulama, bu üye, geliştirdikleri kullanılacak iki arabirim neden olmaz ve aynı imzaya sahip bir üye içeren iki arabirimlerini uygular.</span><span class="sxs-lookup"><span data-stu-id="12769-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="12769-104">Aşağıdaki örnekte, tüm çağrıları `Paint` aynı yöntemini çağırır.</span><span class="sxs-lookup"><span data-stu-id="12769-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="12769-105">İki [arabirimi](../../../csharp/language-reference/keywords/interface.md) üyeleri aynı işlev gerçekleştirmez, ancak bu birini veya her ikisini arabirimler yanlış bir uygulanmasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="12769-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="12769-106">Arabirim üyesini açık olarak uygulanması mümkün — bir sınıf üyesinin oluşturma yalnızca arabirimi aracılığıyla çağrılır ve bu arabirim için özgüdür.</span><span class="sxs-lookup"><span data-stu-id="12769-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="12769-107">Bu sınıf üyesinin adını arabirimi ve nokta ile adlandırma tarafından gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="12769-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="12769-108">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="12769-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="12769-109">Sınıf üyesi `IControl.Paint` aracılığıyla yalnızca kullanılabilir `IControl` arabirimi ve `ISurface.Paint` aracılığıyla yalnızca kullanılabilir `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="12769-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="12769-110">Her iki yöntem uygulamaları ayrıdır ve hiçbiri doğrudan sınıfta kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="12769-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="12769-111">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="12769-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="12769-112">Açık uygulama, iki arabirim üyeleri aynı adlı bir özelliği ve yöntemi gibi farklı yeri bildirin durumları çözümlemek için de kullanılır:</span><span class="sxs-lookup"><span data-stu-id="12769-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="12769-113">İki arabirim uygulamak için açık uygulama P özellik veya yöntemin P için veya her ikisi de bir derleyici hatası önlemek bir sınıf vardır.</span><span class="sxs-lookup"><span data-stu-id="12769-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="12769-114">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="12769-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="12769-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="12769-115">See Also</span></span>

- [<span data-ttu-id="12769-116">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="12769-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="12769-117">Sınıflar ve Yapılar</span><span class="sxs-lookup"><span data-stu-id="12769-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="12769-118">Arabirimler</span><span class="sxs-lookup"><span data-stu-id="12769-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="12769-119">Devralma</span><span class="sxs-lookup"><span data-stu-id="12769-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
