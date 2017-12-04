---
title: "Özel Durumları İşleme ve Atma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b064dc39f5807b154a1529eebe17493ae84981cf
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2017
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="e288a-102">İşleme ve .NET özel durumları atma</span><span class="sxs-lookup"><span data-stu-id="e288a-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="e288a-103">Uygulamaları tutarlı bir şekilde yürütme sırasında oluşan hataları ele kurabilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="e288a-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="e288a-104">.NET uygulamaları hataların Tekdüzen şekilde bildirmek için bir model sağlar: .NET işlemlerini özel durumları atma hatası belirtin.</span><span class="sxs-lookup"><span data-stu-id="e288a-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="e288a-105">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="e288a-105">Exceptions</span></span>

<span data-ttu-id="e288a-106">Herhangi bir hata koşulu veya çalışan bir program tarafından karşılaşılan beklenmeyen davranışları bir özel durumdur.</span><span class="sxs-lookup"><span data-stu-id="e288a-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="e288a-107">Kodunuzu veya (gibi paylaşılan bir kitaplık) çağıran kodu, kullanılamayan işletim sistem kaynakları, çalışma zamanı (doğrulanamayan kodu gibi) karşılaştığında beklenmeyen koşullar ve benzeri bir hata nedeniyle durumlar.</span><span class="sxs-lookup"><span data-stu-id="e288a-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="e288a-108">Uygulamanızı bazı Bu koşullar, ancak diğer kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e288a-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="e288a-109">Çoğu uygulama özel durumları kurtarabilirsiniz rağmen çoğu çalışma zamanı özel durumları kurtaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="e288a-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="e288a-110">.NET içinde öğesinden devralan bir nesne istisnadır <xref:System.Exception?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e288a-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e288a-111">Bir sorun oluştuğu bir alanından kod bir özel durum oluşur.</span><span class="sxs-lookup"><span data-stu-id="e288a-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="e288a-112">Özel durum yığını uygulama, işleme veya program sonlandırır kadar geçirilir.</span><span class="sxs-lookup"><span data-stu-id="e288a-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="e288a-113">Özel durumlar geleneksel hata işleme yöntemlerini karşılaştırması</span><span class="sxs-lookup"><span data-stu-id="e288a-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="e288a-114">Geleneksel olarak, bir dil hata işleme modeli hataları algılama ve bunlar için işleyiciler bulma dil benzersiz şekilde veya işletim sistemi tarafından sağlanan hata işleme mekanizması dayanıyordu.</span><span class="sxs-lookup"><span data-stu-id="e288a-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="e288a-115">Özel durum işleme .NET uygulayan yol aşağıdaki avantajları sağlar:</span><span class="sxs-lookup"><span data-stu-id="e288a-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="e288a-116">Özel durum atma ve işleme .NET programlama dilleri için aynı şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="e288a-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="e288a-117">Belirli bir dili sözdizimi özel durumları işlemek için gerekli değildir, ancak kendi sözdizimi tanımlamak her bir dilin verir.</span><span class="sxs-lookup"><span data-stu-id="e288a-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="e288a-118">Özel işlem ve hatta makine sınırları içinde durum.</span><span class="sxs-lookup"><span data-stu-id="e288a-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="e288a-119">Özel durum işleme kod program güvenilirliğini artırmak için uygulamaya eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="e288a-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="e288a-120">Özel durumlar hata bildirimi, dönüş kodları gibi diğer yöntemleri avantaj sunar.</span><span class="sxs-lookup"><span data-stu-id="e288a-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="e288a-121">Bir özel durum ve işlemek yok, çalışma zamanı uygulamanızı sona erdiğinden hataları gözden kaçan geçmemektedir.</span><span class="sxs-lookup"><span data-stu-id="e288a-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="e288a-122">Geçersiz değerler denetlemek için bir hata dönüş kodu için başarısız kod sonucunda sistemi aracılığıyla yaymak devam etmeyin.</span><span class="sxs-lookup"><span data-stu-id="e288a-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="e288a-123">Genel özel durumlar</span><span class="sxs-lookup"><span data-stu-id="e288a-123">Common Exceptions</span></span>

<span data-ttu-id="e288a-124">Aşağıdaki tabloda ortak bazı özel durumlar ne bunlara neden olabilecek örnekleri ile listeler.</span><span class="sxs-lookup"><span data-stu-id="e288a-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="e288a-125">Özel durum türü</span><span class="sxs-lookup"><span data-stu-id="e288a-125">Exception type</span></span> | <span data-ttu-id="e288a-126">Temel tür</span><span class="sxs-lookup"><span data-stu-id="e288a-126">Base type</span></span> | <span data-ttu-id="e288a-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e288a-127">Description</span></span> | <span data-ttu-id="e288a-128">Örnek</span><span class="sxs-lookup"><span data-stu-id="e288a-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| <xref:System.Exception> | <xref:System.Object> | <span data-ttu-id="e288a-129">Tüm özel durumlar için temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="e288a-129">Base class for all exceptions.</span></span> | <span data-ttu-id="e288a-130">Hiçbiri (Bu özel durumun türetilmiş bir sınıf kullanın).</span><span class="sxs-lookup"><span data-stu-id="e288a-130">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="e288a-131">Çalışma zamanı tarafından yalnızca bir dizi yanlış sıralandığında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e288a-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="e288a-132">Geçerli aralığın dışında bir dizi dizin oluşturma:`arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="e288a-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| <xref:System.NullReferenceException> | <xref:System.Exception> | <span data-ttu-id="e288a-133">Çalışma zamanı tarafından yalnızca null bir nesne başvurulduğunda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e288a-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| <xref:System.InvalidOperationException> | <xref:System.Exception> | <span data-ttu-id="e288a-134">Geçersiz bir durumda olduğunda yöntemler tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e288a-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="e288a-135">Çağırma `Enumerator.GetNext()` bir öğe temel alınan koleksiyonundan kaldırdıktan sonra.</span><span class="sxs-lookup"><span data-stu-id="e288a-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <xref:System.Exception> | <span data-ttu-id="e288a-136">Tüm bağımsız değişken özel durumlar için temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="e288a-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="e288a-137">Hiçbiri (Bu özel durumun türetilmiş bir sınıf kullanın).</span><span class="sxs-lookup"><span data-stu-id="e288a-137">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <xref:System.Exception> | <span data-ttu-id="e288a-138">Bir bağımsız değişken boş olmasına izin verme yöntemler tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e288a-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| <xref:System.ArgumentOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="e288a-139">Bağımsız değişkenler aralıktan doğrulayın yöntemler tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e288a-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="e288a-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e288a-140">See Also</span></span>

* [<span data-ttu-id="e288a-141">Özel durum sınıfı ve özellikleri</span><span class="sxs-lookup"><span data-stu-id="e288a-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="e288a-142">Nasıl yapılır: özel durumları yakalamak için Try-Catch bloğu kullanın</span><span class="sxs-lookup"><span data-stu-id="e288a-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="e288a-143">Nasıl yapılır: bir Catch bloğunda belirli özel durumların kullanın</span><span class="sxs-lookup"><span data-stu-id="e288a-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="e288a-144">Nasıl yapılır: açıkça özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="e288a-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="e288a-145">Nasıl yapılır: kullanıcı tanımlı özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="e288a-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="e288a-146">Kullanıcı tarafından filtrelenmiş özel durum işleyicilerini kullanma</span><span class="sxs-lookup"><span data-stu-id="e288a-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="e288a-147">Nasıl yapılır: Finally bloklarını kullanma</span><span class="sxs-lookup"><span data-stu-id="e288a-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="e288a-148">COM birlikte çalışma özel durumları işleme</span><span class="sxs-lookup"><span data-stu-id="e288a-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="e288a-149">Özel durumlar için en iyi yöntemler</span><span class="sxs-lookup"><span data-stu-id="e288a-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="e288a-150">Özel durumları .NET içinde nasıl çalıştığı hakkında daha fazla bilgi için bkz: [ne her geliştirme gereken bilmeniz hakkında özel durumlara çalışma zamanında](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="e288a-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>