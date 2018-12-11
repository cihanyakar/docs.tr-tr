---
title: .NET Core Kılavuzu
description: .NET core Windows, Linux ve Mac uygulamaları oluşturmak için .NET, modüler, yüksek performanslı bir uygulama olan. Başlamak için .NET Core hakkında bilgi edinin.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: ffa58600bea1f5514b25c18aa00e6d36679f2fd9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170284"
---
# <a name="net-core-guide"></a><span data-ttu-id="3fd11-104">.NET Core Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="3fd11-104">.NET Core Guide</span></span>

<span data-ttu-id="3fd11-105">[.NET core](about.md) olduğu bir [açık kaynaklı](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), genel amaçlı bir geliştirme platformu üzerinde Microsoft ve .NET topluluk tarafından tutulan [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="3fd11-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="3fd11-106">Bu platformlar arası (Windows, macOS ve Linux destekliyor) ve cihaz, Bulut ve IOT uygulamaları oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3fd11-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="3fd11-107">Bkz: [.NET Core hakkında](about.md) özellikleri, desteklenen diller ve çerçeveler ve API anahtarını dahil olmak üzere, .NET Core hakkında daha fazla bilgi edinmek için.</span><span class="sxs-lookup"><span data-stu-id="3fd11-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="3fd11-108">Kullanıma [.NET Core öğreticilerini](tutorials/index.md) basit bir .NET Core uygulaması oluşturmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="3fd11-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="3fd11-109">Yalnızca ilk uygulamanızı çalıştırmaya başlayın birkaç dakika sürer.</span><span class="sxs-lookup"><span data-stu-id="3fd11-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="3fd11-110">.NET Core tarayıcınızda denemek istiyorsanız, bakmak [içindeki numaralandırır C# ](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) çevrimiçi öğretici.</span><span class="sxs-lookup"><span data-stu-id="3fd11-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core-21"></a><span data-ttu-id="3fd11-111">.NET Core 2.1 indirme</span><span class="sxs-lookup"><span data-stu-id="3fd11-111">Download .NET Core 2.1</span></span>

<span data-ttu-id="3fd11-112">İndirme [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) .NET Core Windows, macOS veya Linux makinenizde denemek için.</span><span class="sxs-lookup"><span data-stu-id="3fd11-112">Download the [.NET Core  2.1 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="3fd11-113">Ziyaret [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) Docker kapsayıcılarını kullanmayı tercih ederseniz.</span><span class="sxs-lookup"><span data-stu-id="3fd11-113">Visit [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="3fd11-114">Tüm .NET Core sürümleri kullanılabilir [.NET Core indirir](https://www.microsoft.com/net/download/archives) için başka bir .NET Core sürümünün düşürmek istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="3fd11-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="3fd11-115">.NET core 2.1</span><span class="sxs-lookup"><span data-stu-id="3fd11-115">.NET Core 2.1</span></span>

<span data-ttu-id="3fd11-116">En son sürüm [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="3fd11-116">The latest version is [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span></span> <span data-ttu-id="3fd11-117">Yeni özellikler içerir: Genel araçları, yüksek performanslı API'leri (gibi <xref:System.Span%601?displayProperty=nameWithType>), katmanlı JIT derlemesi [derleme](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) ve [çalışma zamanı performans iyileştirmeleri](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), için ve Destek Alpine ve ARM32.</span><span class="sxs-lookup"><span data-stu-id="3fd11-117">New features include: global tools, high-performance APIs (such as <xref:System.Span%601?displayProperty=nameWithType>), tiered JIT compilation, [build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and [runtime performance improvements](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), and support for Alpine and ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="3fd11-118">İlk uygulamanızı oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fd11-118">Create your first application</span></span>

<span data-ttu-id="3fd11-119">.NET Core SDK'yı yükledikten sonra bir komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="3fd11-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="3fd11-120">Aşağıdaki komutu yazın `dotnet` oluşturma ve C# uygulama çalıştırma için komutları.</span><span class="sxs-lookup"><span data-stu-id="3fd11-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="3fd11-121">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="3fd11-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="3fd11-122">Destek</span><span class="sxs-lookup"><span data-stu-id="3fd11-122">Support</span></span>

<span data-ttu-id="3fd11-123">.NET Core [Microsoft tarafından desteklenen](https://www.microsoft.com/net/support/policy), Windows, macOS ve Linux'ta.</span><span class="sxs-lookup"><span data-stu-id="3fd11-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="3fd11-124">Güvenlik ve kalite testinden yılda birkaç kez, genellikle aylık güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3fd11-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="3fd11-125">.NET core ikili dağıtımları oluşturulan ve azure'da Microsoft korunan sunucularda test edilmiş ve yalnızca tüm Microsoft Ürün gibi desteklenen.</span><span class="sxs-lookup"><span data-stu-id="3fd11-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="3fd11-126">[Red Hat destekleyen .NET Core](http://redhatloves.net/) Red Hat Enterprise Linux (RHEL) üzerinde.</span><span class="sxs-lookup"><span data-stu-id="3fd11-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="3fd11-127">Red Hat kaynaktan .NET Core oluşturur ve kullanılabilir hale getirir [Red Hat yazılımı koleksiyonları](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="3fd11-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="3fd11-128">Red Hat ve Microsoft .NET Core iyi RHEL üzerinde çalıştığından emin olmak üzere işbirliği yapıyor.</span><span class="sxs-lookup"><span data-stu-id="3fd11-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
