---
title: İle Polly üstel geri alma ile HTTP çağrı yeniden uygulayın
description: Polly ile HttpClientFactory HTTP hatalarını işlemek hakkında bilgi edinin
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/10/2018
ms.openlocfilehash: 78de1440721e83459e455f5c31d10e52a1d3b1b6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143993"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="b3817-103">HttpClientFactory ve Polly üstel geri alma ile HTTP çağrı yeniden uygulayın</span><span class="sxs-lookup"><span data-stu-id="b3817-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="b3817-104">Açık kaynak gibi daha gelişmiş .NET kitaplıkları yararlanmak için üstel geri alma ile yeniden denemeler için önerilen bir yaklaşım olan [Polly kitaplığını](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="b3817-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="b3817-105">Polly esnekliği ve geçici hata işleme özellikleri sağlayan bir .NET Kitaplığı ' dir.</span><span class="sxs-lookup"><span data-stu-id="b3817-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="b3817-106">Bu özellikler, yeniden deneme, devre kesici, bölme perdesi yalıtım, zaman aşımı ve geri dönüş gibi Polly ilkeleri uygulayarak uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b3817-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="b3817-107">Polly hedefleyen .NET 4.x ve .NET Standard kitaplığı (.NET Core destekleyen) 1.0.</span><span class="sxs-lookup"><span data-stu-id="b3817-107">Polly targets .NET 4.x and the .NET Standard Library 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="b3817-108">Ancak, kendi özel kodunuzu içeren HttpClient Polly'nın kitaplığı kullanarak önemli ölçüde karmaşık olabilir.</span><span class="sxs-lookup"><span data-stu-id="b3817-108">However, using Polly’s library with your own custom code with HttpClient can be significantly complex.</span></span> <span data-ttu-id="b3817-109">Hizmetine özgün sürümünde oluştu bir [ResilientHttpClient Yapı Taşı](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) Polly üzerinde temel.</span><span class="sxs-lookup"><span data-stu-id="b3817-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) based on Polly.</span></span> <span data-ttu-id="b3817-110">Ancak, böylece yapı taşı hizmetine kullanım dışı bırakıldı HttpClientFactory'nın yayınlanmasıyla birlikte, Http iletişimi için dayanıklı uygulamak, çok daha kolay olur.</span><span class="sxs-lookup"><span data-stu-id="b3817-110">But with the release of HttpClientFactory, resilient Http communication has become much simpler to implement, so that building-block was deprecated from eShopOnContainers.</span></span> 

<span data-ttu-id="b3817-111">Aşağıdaki adımlar, Http nasıl kullanabileceğinizi gösterir önceki bölümde açıklanan HttpClientFactory, yeniden denemeler Polly ile tümleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b3817-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="b3817-112">**ASP.NET Core 2.1 referans paketleri**</span><span class="sxs-lookup"><span data-stu-id="b3817-112">**Reference the ASP.NET Core 2.1 packages**</span></span>

<span data-ttu-id="b3817-113">NuGet kullanarak ASP.NET Core 2.1 paketleri bitvise projeniz vardır.</span><span class="sxs-lookup"><span data-stu-id="b3817-113">Your project has to be using the ASP.NET Core 2.1 packages from NuGet.</span></span> <span data-ttu-id="b3817-114">Genelde gerekir `AspNetCore` metapackage ve uzantı paketi `Microsoft.Extensions.Http.Polly`.</span><span class="sxs-lookup"><span data-stu-id="b3817-114">You typically need the `AspNetCore` metapackage, and the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="b3817-115">**Polly'nın yeniden deneme ilkesi, başlatma ile istemci yapılandırma**</span><span class="sxs-lookup"><span data-stu-id="b3817-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="b3817-116">Önceki bölümlerde gösterildiği gibi adlandırılmış veya türü belirtilmiş bir istemci HttpClient yapılandırma, standart Startup.ConfigureServices(...) yöntemi tanımlamak gerekir, ancak şimdi, üstel geri alma ile Http yeniden deneme ilkesi olarak belirterek artımlı kod ekleyin Aşağıda:</span><span class="sxs-lookup"><span data-stu-id="b3817-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="b3817-117">**AddPolicyHandler()** yöntemdir hangi ilkeleri ekler `HttpClient` nesnelerini kullanırsınız.</span><span class="sxs-lookup"><span data-stu-id="b3817-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you will use.</span></span> <span data-ttu-id="b3817-118">Bu durumda, bunu Polly'nın ilke Http yeniden deneme için üstel geri alma ile eklemektir.</span><span class="sxs-lookup"><span data-stu-id="b3817-118">In this case, it is adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="b3817-119">Daha modüler bir yaklaşım sahip olmak için Http yeniden deneme ilkesi ConfigureServices() yöntemi içinde ayrı bir yöntem aşağıdaki kodu tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b3817-119">In order to have a more modular approach, the Http Retry Policy can be defined in a separate method within the ConfigureServices() method, as the following code.</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

<span data-ttu-id="b3817-120">Polly ile yeniden denemeler, üstel geri alma yapılandırmasını ve hata günlük kaydı gibi bir HTTP özel durum olduğunda gerçekleştirilecek eylemleri sayısı bir yeniden deneme ilkesi tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b3817-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="b3817-121">Bu durumda, ilke ile iki saniyede bir üstel yeniden deneme altı kat denemek için yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="b3817-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span> 

<span data-ttu-id="b3817-122">Bu nedenle altı kat deneyecek ve her yeniden deneme arasındaki saniye iki saniye cinsinden başlangıç üstel, olacaktır.</span><span class="sxs-lookup"><span data-stu-id="b3817-122">so it will try six times and the seconds between each retry will be exponential, starting on two seconds.</span></span>

### <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="b3817-123">Değişimi stratejisi için yeniden deneme ilkesi ekleme</span><span class="sxs-lookup"><span data-stu-id="b3817-123">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="b3817-124">Normal bir yeniden deneme ilkesi, sisteminizin durumlarda yüksek eşzamanlılık ve ölçeklenebilirlik ve yüksek Çekişme altında etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="b3817-124">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="b3817-125">En yüksek sayılar kısmi kesintiler durumunda birçok istemcilerden gelen benzer bir yeniden deneme aşmak için iyi bir geçici çözüm değişimi stratejisi için yeniden deneme algoritması/İlkesi eklemektir.</span><span class="sxs-lookup"><span data-stu-id="b3817-125">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="b3817-126">Rastgele üstel geri alma için ekleyerek bu uçtan uca sistemin genel performansı artırabilir.</span><span class="sxs-lookup"><span data-stu-id="b3817-126">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="b3817-127">Sorunlar ortaya çıktığında bunu ani değişiklikleri yayar.</span><span class="sxs-lookup"><span data-stu-id="b3817-127">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="b3817-128">Değişimi uygulamak için kodu, düz bir Polly İlkesi kullandığınızda, aşağıdaki örnekteki gibi görünebilir:</span><span class="sxs-lookup"><span data-stu-id="b3817-128">When you use a plain Polly policy, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a><span data-ttu-id="b3817-129">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b3817-129">Additional resources</span></span>

-   <span data-ttu-id="b3817-130">**Yeniden deneme düzeni**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="b3817-130">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="b3817-131">**Polly ve HttpClientFactory**
    [*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span><span class="sxs-lookup"><span data-stu-id="b3817-131">**Polly and HttpClientFactory**
[*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span></span>

-   <span data-ttu-id="b3817-132">**Polly (.NET esnekliği ve geçici hata işleme kitaplığı)**</span><span class="sxs-lookup"><span data-stu-id="b3817-132">**Polly (.NET resilience and transient-fault-handling library)**</span></span>

    [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   <span data-ttu-id="b3817-133">**Marc Brooker. Değişimi: Rastgele olma durumu ile depolanabileceğini şeyler**</span><span class="sxs-lookup"><span data-stu-id="b3817-133">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>

    [*https://brooker.co.za/blog/2015/03/21/backoff.html*](https://brooker.co.za/blog/2015/03/21/backoff.html)

>[!div class="step-by-step"]
><span data-ttu-id="b3817-134">[Önceki](explore-custom-http-call-retries-exponential-backoff.md)
>[İleri](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="b3817-134">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>