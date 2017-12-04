---
title: Zaman Uyumsuz Programlama Desenleri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a527824ba11928d59bc700f253c5a4d77056abf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="45e21-102">Zaman Uyumsuz Programlama Desenleri</span><span class="sxs-lookup"><span data-stu-id="45e21-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="45e21-103">.NET Framework zaman uyumsuz işlemleri gerçekleştirmek için üç desenleri sağlar:</span><span class="sxs-lookup"><span data-stu-id="45e21-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="45e21-104">Zaman uyumsuz programlama modeli (APM) deseni (olarak da bilinir <xref:System.IAsyncResult> desen), burada zaman uyumsuz işlemleri gerektirir `Begin` ve `End` yöntemleri (örneğin, `BeginWrite` ve `EndWrite` zaman uyumsuz yazma işlemleri için).</span><span class="sxs-lookup"><span data-stu-id="45e21-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="45e21-105">Bu desen artık yeni geliştirme projeleri için önerilir.</span><span class="sxs-lookup"><span data-stu-id="45e21-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="45e21-106">Daha fazla bilgi için bkz: [zaman uyumsuz programlama modeli (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="45e21-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="45e21-107">Olay tabanlı zaman uyumsuz desen (içeren bir yöntem gerektiren EAP), `Async` sonek ve de gerektiren bir veya daha fazla olaylar, olay işleyici temsilci türleri ve `EventArg`-türetilmiş tür.</span><span class="sxs-lookup"><span data-stu-id="45e21-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="45e21-108">EAP, .NET Framework 2. 0 ' sunulmuştur.</span><span class="sxs-lookup"><span data-stu-id="45e21-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="45e21-109">Artık yeni geliştirme projeleri için önerilir.</span><span class="sxs-lookup"><span data-stu-id="45e21-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="45e21-110">Daha fazla bilgi için bkz: [olay tabanlı zaman uyumsuz desen (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="45e21-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="45e21-111">Görev tabanlı zaman uyumsuz desen (başlatma ve zaman uyumsuz bir işlemin tamamlanmasını temsil etmek için tek bir yöntem kullanan DOKUNUN).</span><span class="sxs-lookup"><span data-stu-id="45e21-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="45e21-112">DOKUNUN .NET Framework 4'te tanıtılan ve .NET Framework önerilen yaklaşım zaman uyumsuz programlama.</span><span class="sxs-lookup"><span data-stu-id="45e21-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="45e21-113">[Zaman uyumsuz](~/docs/csharp/language-reference/keywords/async.md) ve [await](~/docs/csharp/language-reference/keywords/await.md) C# anahtar sözcükleri ve [zaman uyumsuz](~/docs/visual-basic/language-reference/modifiers/async.md) ve [bekleme](~/docs/visual-basic/language-reference/operators/await-operator.md) Visual Basic Dil işleçleri DOKUNUN için dil desteği ekleyin.</span><span class="sxs-lookup"><span data-stu-id="45e21-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="45e21-114">Daha fazla bilgi için bkz: [görev tabanlı zaman uyumsuz desen (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="45e21-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="45e21-115">Desenler karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="45e21-115">Comparing Patterns</span></span>  

<span data-ttu-id="45e21-116">Üç model zaman uyumsuz işlemleri nasıl düzenleri hızlı karşılaştırma için göz önünde bulundurun bir `Read` belirtilen uzaklıkta başlayan sağlanan arabellek içine belirtilen miktarda veri okuyan yöntemi:</span><span class="sxs-lookup"><span data-stu-id="45e21-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="45e21-117">Bu yöntemin APM karşılık gelen kullanılabilmesini `BeginRead` ve `EndRead` yöntemleri:</span><span class="sxs-lookup"><span data-stu-id="45e21-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="45e21-118">EAP karşılık gelen türleri ve üyeleri aşağıdaki kümesini kullanıma:</span><span class="sxs-lookup"><span data-stu-id="45e21-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="45e21-119">DOKUNUN karşılık gelen aşağıdaki tek kullanılabilmesini `ReadAsync` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="45e21-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="45e21-120">DOKUNUN, APM ve EAP kapsamlı bir tartışma için sonraki bölümde sağlanan bağlantılara bakın.</span><span class="sxs-lookup"><span data-stu-id="45e21-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="45e21-121">İlgili konular</span><span class="sxs-lookup"><span data-stu-id="45e21-121">Related topics</span></span>

| <span data-ttu-id="45e21-122">Başlık</span><span class="sxs-lookup"><span data-stu-id="45e21-122">Title</span></span> | <span data-ttu-id="45e21-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="45e21-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="45e21-124">Zaman uyumsuz programlama modeli (APM)</span><span class="sxs-lookup"><span data-stu-id="45e21-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="45e21-125">Kullanan eski modeli açıklayan <xref:System.IAsyncResult> zaman uyumsuz davranışı sağlamak için arabirim.</span><span class="sxs-lookup"><span data-stu-id="45e21-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="45e21-126">Bu model, artık yeni geliştirme projeleri için önerilir.</span><span class="sxs-lookup"><span data-stu-id="45e21-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="45e21-127">Olay tabanlı zaman uyumsuz desen (EAP)</span><span class="sxs-lookup"><span data-stu-id="45e21-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="45e21-128">Zaman uyumsuz davranışı sağlamak için olay tabanlı eski modeli açıklar.</span><span class="sxs-lookup"><span data-stu-id="45e21-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="45e21-129">Bu model, artık yeni geliştirme projeleri için önerilir.</span><span class="sxs-lookup"><span data-stu-id="45e21-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="45e21-130">Görev tabanlı zaman uyumsuz desen (TAP)</span><span class="sxs-lookup"><span data-stu-id="45e21-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="45e21-131">Temel yeni zaman uyumsuz deseni açıklar <xref:System.Threading.Tasks> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="45e21-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="45e21-132">Bu model, .NET Framework 4 ve sonraki sürümlerde zaman uyumsuz programlama için önerilen yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="45e21-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="45e21-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="45e21-133">See also</span></span>

<span data-ttu-id="45e21-134">[C# zaman uyumsuz programlama](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="45e21-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="45e21-135">[F # zaman uyumsuz programlama](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span><span class="sxs-lookup"><span data-stu-id="45e21-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="45e21-136">Zaman uyumsuz programlama ile Async ve Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45e21-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)