---
title: Mimari yaklaşımları - sunucusuz uygulamalar
description: Giriş mimarisi, N katmanlı mimariler için sunucusuz bulut tabanlı kurumsal uygulamalar oluşturmaya yönelik yaklaşıyor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 04ad383586f974bb2dccc4623a9a254f5668dab4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126751"
---
# <a name="architecture-approaches"></a><span data-ttu-id="e81fc-103">Mimari yaklaşımları</span><span class="sxs-lookup"><span data-stu-id="e81fc-103">Architecture approaches</span></span>

<span data-ttu-id="e81fc-104">Kurumsal uygulamaları tasarlamak için varolan yaklaşımlara anlama yardımcı tarafından sunucusuz oynadığı rol açıklayın.</span><span class="sxs-lookup"><span data-stu-id="e81fc-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="e81fc-105">Birçok yaklaşımlar ve yazılım geliştirme yıllardır içinde gelişerek desenleri vardır ve tüm kendi Artıları ve eksileri vardır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="e81fc-106">Çoğu durumda, bir çözüm üzerinde tek bir yaklaşım karar gerektirebilir değil, ancak çeşitli yaklaşımlar tümleştirme.</span><span class="sxs-lookup"><span data-stu-id="e81fc-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="e81fc-107">Geçiş senaryoları, genellikle bir mimari yaklaşımı, karma bir yaklaşım aracılığıyla başka bir kaydırma içerir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="e81fc-108">Bu bölümde, kurumsal uygulamalar için her iki mantıksal ve fiziksel mimari desenleri için genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="e81fc-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="e81fc-109">Mimari desenleri</span><span class="sxs-lookup"><span data-stu-id="e81fc-109">Architecture patterns</span></span>

<span data-ttu-id="e81fc-110">Modern iş uygulamaları mimarisi desenleri çeşitli izleyin.</span><span class="sxs-lookup"><span data-stu-id="e81fc-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="e81fc-111">Bu bölümde genel desenleri araştırma temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e81fc-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="e81fc-112">Burada listelenen desenleri mutlaka tüm en iyi değildir, ancak farklı bir yaklaşım gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="e81fc-113">Daha fazla bilgi için [Azure Uygulama Mimarisi Kılavuzu](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="e81fc-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="e81fc-114">Hamleye olanak</span><span class="sxs-lookup"><span data-stu-id="e81fc-114">Monoliths</span></span>

<span data-ttu-id="e81fc-115">Birçok iş uygulaması tek deseni izler.</span><span class="sxs-lookup"><span data-stu-id="e81fc-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="e81fc-116">Eski uygulamaları genellikle hamleye olanak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="e81fc-117">Tek düzende, tüm uygulama sorunları tek bir dağıtımda yer alır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="e81fc-118">Her şeyi veritabanı çağrıları için kullanıcı arabirimi, aynı kod temelinde dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Tek mimarisi](./media/monolith-architecture.png)

<span data-ttu-id="e81fc-120">Tek yaklaşım için çeşitli avantajları vardır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="e81fc-121">Genellikle, tek bir kod tabanının çekmek ve çalışmaya başlamak çok kolaydır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="e81fc-122">Gelişim süresini daha az olabilir ve test ortamları oluşturmayı sağlayan yeni bir kopya olarak kadar kolaydır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="e81fc-123">Tek birden çok bileşenler ve uygulamalar dahil etmek için tasarlanmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="e81fc-124">Ne yazık ki, tek düzen ölçekte bölünme eğilimindedir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="e81fc-125">Tek yaklaşım ana dezavantajları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e81fc-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="e81fc-126">Aynı kod tabanını paralel çalışma zordur.</span><span class="sxs-lookup"><span data-stu-id="e81fc-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="e81fc-127">Nasıl Önemsiz fark etmeksizin herhangi bir değişiklik, uygulamanın tamamı yeni bir sürümünü gerektirir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="e81fc-128">Potansiyel olarak yeniden düzenleme, uygulamanın tamamını etkiler.</span><span class="sxs-lookup"><span data-stu-id="e81fc-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="e81fc-129">Genellikle ölçeklendirmek için tek bir çözüm birden çok oluşturmaktır yoğun kaynak tek kopyası.</span><span class="sxs-lookup"><span data-stu-id="e81fc-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="e81fc-130">Sistemleri genişletin veya diğer sistemlere elde edilen tümleştirme zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="e81fc-131">Tüm tek yapılandırmaya gerek nedeniyle test etmek zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="e81fc-132">Kod yeniden kullanımını zordur ve genellikle kendi kod kopyaları olan diğer uygulamaları edersiniz.</span><span class="sxs-lookup"><span data-stu-id="e81fc-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="e81fc-133">Birçok işletme, tek uygulamaları geçirme ve aynı anda daha fazla kullanılabilir desenleri için bunları yeniden düzenleme için bir fırsat olarak buluta arayın.</span><span class="sxs-lookup"><span data-stu-id="e81fc-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="e81fc-134">Korunan, dağıtılan ve ayrı olarak ölçeği izin vermek üzere tek tek uygulamalar ve bileşenler kesmek için yaygındır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="e81fc-135">N katmanlı uygulamalar</span><span class="sxs-lookup"><span data-stu-id="e81fc-135">N-Layer applications</span></span>

<span data-ttu-id="e81fc-136">N katmanlı uygulama bölüm belirli katmanlara uygulama mantığı.</span><span class="sxs-lookup"><span data-stu-id="e81fc-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="e81fc-137">En yaygın Katmanlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e81fc-137">The most common layers include:</span></span>

* <span data-ttu-id="e81fc-138">Kullanıcı arabirimi</span><span class="sxs-lookup"><span data-stu-id="e81fc-138">User interface</span></span>
* <span data-ttu-id="e81fc-139">İş mantığı</span><span class="sxs-lookup"><span data-stu-id="e81fc-139">Business logic</span></span>
* <span data-ttu-id="e81fc-140">Veri erişimi</span><span class="sxs-lookup"><span data-stu-id="e81fc-140">Data access</span></span>

<span data-ttu-id="e81fc-141">Diğer Katmanlar, ara yazılım ve toplu işlem API'si içerebilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="e81fc-142">Katmanları mantıksal olduğuna dikkat edin önemlidir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="e81fc-143">Yalıtılmış olarak geliştirilen olsa da, bunların tümü aynı hedef platformu için dağıtılabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N katmanlı mimari](./media/n-layer-architecture.png)

<span data-ttu-id="e81fc-145">N katmanlı yaklaşımın çeşitli avantajları vardır dahil olmak üzere:</span><span class="sxs-lookup"><span data-stu-id="e81fc-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="e81fc-146">Yeniden düzenleme, bir katman için ayrı tutulur.</span><span class="sxs-lookup"><span data-stu-id="e81fc-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="e81fc-147">Takımların bağımsız olarak derleme, test, dağıtabilir ve ayrı katmanlar korumak.</span><span class="sxs-lookup"><span data-stu-id="e81fc-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="e81fc-148">Katmanlar takas edilebilir, UI yerleşiminde değişikliğe gerek kalmadan veri katmanı birden çok veritabanı örneğin erişebilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="e81fc-149">Sunucusuz bir veya daha fazla katmanı uygulamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="e81fc-150">Mikro hizmetler</span><span class="sxs-lookup"><span data-stu-id="e81fc-150">Microservices</span></span>

<span data-ttu-id="e81fc-151">**[Mikro Hizmetler](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  mimarileri içeren ortak özellikleri içerir:</span><span class="sxs-lookup"><span data-stu-id="e81fc-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="e81fc-152">Uygulamaları birkaç küçük hizmetlerini oluşur.</span><span class="sxs-lookup"><span data-stu-id="e81fc-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="e81fc-153">Her hizmet kendi işleminde çalışır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="e81fc-154">Hizmetleri iş etki alanı hizalanır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="e81fc-155">Hizmetler, genellikle HTTP aktarım olarak kullanarak basit API'ler üzerinden iletişim kurar.</span><span class="sxs-lookup"><span data-stu-id="e81fc-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="e81fc-156">Hizmetleri, dağıtılmış ve bağımsız olarak yükseltildi.</span><span class="sxs-lookup"><span data-stu-id="e81fc-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="e81fc-157">Hizmetleri bir tek veri deposuna bağımlı değildir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="e81fc-158">Sistem hatası düşünülerek tasarlanmıştır ve bile belirli hizmetleri başarısız olduğunda uygulama çalışmaya devam.</span><span class="sxs-lookup"><span data-stu-id="e81fc-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="e81fc-159">Mikro hizmetler, diğer mimari yaklaşımları birbirini dışlayan olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e81fc-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="e81fc-160">Örneğin, N katmanlı bir mimari, mikro hizmetler için orta katman kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="e81fc-161">Mikro hizmetler çeşitli yollarla, kapsayıcılar için IIS konaklardaki sanal dizinlerden uygulamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="e81fc-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="e81fc-162">Mikro hizmet özelliklerini bunları sunucusuz uygulamalar için özellikle ideal hale getirir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Mikro hizmet mimarisi](./media/microservices-architecture.png)

<span data-ttu-id="e81fc-164">Mikro hizmet mimarileri profesyoneller şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e81fc-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="e81fc-165">Yeniden düzenleme genellikle tek bir hizmet için ayrı tutulur.</span><span class="sxs-lookup"><span data-stu-id="e81fc-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="e81fc-166">Hizmetleri birbirinden yükseltilebilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="e81fc-167">Tek başına hizmetlerinden gereksinimlerini karşılamak için ayarlanabilecek, dayanıklılık ve esneklik.</span><span class="sxs-lookup"><span data-stu-id="e81fc-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="e81fc-168">Geliştirme paralel olarak birbirinden farklı ekipler ve platformlar arasında gerçekleşebilir.</span><span class="sxs-lookup"><span data-stu-id="e81fc-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="e81fc-169">Yalıtılmış Hizmetleri için kapsamlı testler yazmak daha kolaydır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="e81fc-170">Mikro hizmetler de dahil olmak üzere kendi zorluklar getirir:</span><span class="sxs-lookup"><span data-stu-id="e81fc-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="e81fc-171">Hangi hizmetlerin kullanılabileceğini ve bunları nasıl belirleme.</span><span class="sxs-lookup"><span data-stu-id="e81fc-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="e81fc-172">Yaşam döngüsü Hizmetleri yönetme.</span><span class="sxs-lookup"><span data-stu-id="e81fc-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="e81fc-173">Hizmetleri genel uygulama birbirine nasıl uyduğunu anlama.</span><span class="sxs-lookup"><span data-stu-id="e81fc-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="e81fc-174">Farklı hizmet arasında yapılan çağrılar tam sistem testi.</span><span class="sxs-lookup"><span data-stu-id="e81fc-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="e81fc-175">Sonuç olarak tüm daha sonra açıklanan avantajları sunucusuz olarak dahil olmak üzere, bu sorunları ele almak için çözümleri vardır.</span><span class="sxs-lookup"><span data-stu-id="e81fc-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e81fc-176">[Önceki](index.md)
>[İleri](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="e81fc-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>