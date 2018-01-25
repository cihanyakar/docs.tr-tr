---
title: "Microsoft WCF Web hizmeti başvuru sağlayıcısı aracı"
description: "Microsoft WCF Web hizmeti başvuru sağlayıcısı .NET Core ve ASP.NET Core projeleri, .NET Framework projeleri için hizmet Başvurusu Ekle benzer işlevsellik ekleyen aracı genel bakış."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: e445361f9f4a858f4b34ca1008670fadc62b8b3c
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="859c9-103">Microsoft WCF Web hizmeti başvuru sağlayıcısı aracı</span><span class="sxs-lookup"><span data-stu-id="859c9-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="859c9-104">Yıllar içinde birçok Visual Studio Geliştirici üretkenliği keyif aldığınızı, [ **hizmet Başvurusu Ekle** ](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) web hizmetlerine erişmek .NET Framework projelerini gerektiğinde sağlanan aracı.</span><span class="sxs-lookup"><span data-stu-id="859c9-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="859c9-105">**WCF Web hizmeti başvuru** projeleri .NET Core ve ASP.NET Core için hizmet Başvurusu Ekle işlevleri gibi bir deneyim sağlar bir Visual Studio bağlı hizmet uzantısı araçtır.</span><span class="sxs-lookup"><span data-stu-id="859c9-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="859c9-106">Bu araç, bir web hizmeti geçerli çözümdeki bir ağ konumu veya WSDL dosya meta verileri alır ve web erişmek için kullanabileceğiniz Windows Communication Foundation (WCF) istemci proxy kodu içeren bir .NET Core uyumlu kaynak dosyası oluşturur hizmet.</span><span class="sxs-lookup"><span data-stu-id="859c9-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="859c9-107">Yalnızca güvenilir bir kaynaktan Hizmetleri başvuruda bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="859c9-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="859c9-108">Güvenilmeyen bir kaynaktan başvuruları ekleme, güvenliği tehlikeye atabilir.</span><span class="sxs-lookup"><span data-stu-id="859c9-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="how-to-use-the-extension"></a><span data-ttu-id="859c9-109">Uzantı kullanma</span><span class="sxs-lookup"><span data-stu-id="859c9-109">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="859c9-110">**WCF Web hizmeti başvuru** seçenektir aşağıdaki proje şablonları kullanılarak oluşturulmuş projeler için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="859c9-110">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="859c9-111">**Visual C#** > **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="859c9-111">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="859c9-112">**Visual C#** > **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="859c9-112">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="859c9-113">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span><span class="sxs-lookup"><span data-stu-id="859c9-113">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="859c9-114">Kullanarak **ASP.NET çekirdek Web uygulaması** proje şablonu bir örnek olarak, bu makalede anlatılmaktadır, projeye bir WCF Hizmeti başvuru eklerken size:</span><span class="sxs-lookup"><span data-stu-id="859c9-114">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="859c9-115">Çözüm Gezgini'nde çift tıklayarak **bağlantılı Hizmetler** proje düğümünün (için .NET Core veya .NET standart bir proje üzerinde sağ tıklattığınızda bu seçenek kullanılabilir **bağımlılıkları** düğümü Çözüm Gezgini'nde projeye).</span><span class="sxs-lookup"><span data-stu-id="859c9-115">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="859c9-116">**Bağlantılı Hizmetler** sayfası aşağıdaki görüntüde gösterildiği gibi görünür:</span><span class="sxs-lookup"><span data-stu-id="859c9-116">The **Connected Services** page appears as shown in the following image:</span></span>

![Bağlı hizmetler sekmesi](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="859c9-118">Üzerinde **bağlantılı Hizmetler** sayfasında, **Microsoft WCF Web hizmeti başvuru sağlayıcısı**.</span><span class="sxs-lookup"><span data-stu-id="859c9-118">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="859c9-119">Bu işlem sonrasında **yapılandırma WCF Web hizmeti başvuru** Sihirbazı:</span><span class="sxs-lookup"><span data-stu-id="859c9-119">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![Hizmet uç noktası sekmesi](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="859c9-121">Bir hizmeti seçin.</span><span class="sxs-lookup"><span data-stu-id="859c9-121">Select a service.</span></span>

    <span data-ttu-id="859c9-122">3a.</span><span class="sxs-lookup"><span data-stu-id="859c9-122">3a.</span></span> <span data-ttu-id="859c9-123">Çeşitli hizmetler arama seçenekleri içinde kullanılabilir **yapılandırma WCF Web hizmeti başvuru** Sihirbazı:</span><span class="sxs-lookup"><span data-stu-id="859c9-123">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="859c9-124">Geçerli çözümde tanımlanan Hizmetleri aramak için tıklatın **bulma** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="859c9-124">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="859c9-125">Belirtilen bir adres barındırılan hizmetleri aramak için bir hizmet URL'si girin **adresi** kutusuna ve tıklatın **Git** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="859c9-125">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="859c9-126">Web hizmeti meta veri bilgileri içeren bir WSDL dosya seçmek için tıklatın **Gözat** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="859c9-126">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="859c9-127">3b.</span><span class="sxs-lookup"><span data-stu-id="859c9-127">3b.</span></span> <span data-ttu-id="859c9-128">Arama sonuçları listesinden hizmeti seçin **Hizmetleri** kutusu.</span><span class="sxs-lookup"><span data-stu-id="859c9-128">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="859c9-129">Gerekirse, karşılık gelen üretilen kod için ad alanı girin **Namespace** metin kutusu.</span><span class="sxs-lookup"><span data-stu-id="859c9-129">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="859c9-130">3c.</span><span class="sxs-lookup"><span data-stu-id="859c9-130">3c.</span></span> <span data-ttu-id="859c9-131">Tıklatın **sonraki** açmak için düğmeye **veri türü seçenekleri** ve **istemci seçenekleri** sayfaları.</span><span class="sxs-lookup"><span data-stu-id="859c9-131">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="859c9-132">Alternatif olarak, **son** düğmesi varsayılan seçenekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="859c9-132">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="859c9-133">**Veri türü seçenekleri** form oluşturulan hizmet başvurusu yapılandırma ayarlarını İyileştir olanak sağlar:</span><span class="sxs-lookup"><span data-stu-id="859c9-133">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![Veri türü Seçenekler sekmesi](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="859c9-135">**Yeniden başvurulan derlemelerin türlerinde** onay kutusu seçeneği, hizmet başvurusu kod oluşturma için gerekli veri türleri, projenizin başvurulan derlemelerin birinde tanımlandığında yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="859c9-135">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="859c9-136">Derleme zamanı tür çakışmasından veya çalışma zamanı sorunlarını önlemek için bu var olan veri türleri yeniden önemlidir.</span><span class="sxs-lookup"><span data-stu-id="859c9-136">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="859c9-137">Tür bilgileri, proje bağımlılıklarını sayısı ve diğer sistem performans etkenlere bağlı olarak yüklenirken bir gecikme olabilir.</span><span class="sxs-lookup"><span data-stu-id="859c9-137">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="859c9-138">**Son** düğmesi devre dışı sürece yükleme sırasında **yeniden başvurulan derlemelerin türlerinde** onay kutusunun işaretli olduğundan.</span><span class="sxs-lookup"><span data-stu-id="859c9-138">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="859c9-139">Tıklatın **son** işiniz bittiğinde.</span><span class="sxs-lookup"><span data-stu-id="859c9-139">Click **Finish** when you are done.</span></span>


<span data-ttu-id="859c9-140">İlerleme durumunu, aracı görüntüleme oluştu:</span><span class="sxs-lookup"><span data-stu-id="859c9-140">While displaying progress, the tool:</span></span>

* <span data-ttu-id="859c9-141">WCF hizmetinden meta verileri indirir.</span><span class="sxs-lookup"><span data-stu-id="859c9-141">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="859c9-142">Hizmet başvurusu kod adındaki bir dosyada oluşturur *reference.cs*ve altında projenize ekler **bağlantılı Hizmetler** düğümü.</span><span class="sxs-lookup"><span data-stu-id="859c9-142">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="859c9-143">NuGet paket başvurularıyla derlemek ve hedef platformu üzerinde çalıştırmak için gerekli proje dosyası (.csproj) güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="859c9-143">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![İlerleme penceresi](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="859c9-145">Bu işlemleri tamamladığınızda, oluşturulan WCF istemci türünün bir örneği oluşturun ve hizmet işlemlerini çağırma.</span><span class="sxs-lookup"><span data-stu-id="859c9-145">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="859c9-146">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="859c9-146">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="859c9-147">Geri bildirim & sorular</span><span class="sxs-lookup"><span data-stu-id="859c9-147">Feedback & questions</span></span>
<span data-ttu-id="859c9-148">Sorularınız veya geri bildirim, varsa [github'da bir sorun açın](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="859c9-148">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="859c9-149">Herhangi bir varolan sorular veya sorunlar gözden geçirebilirsiniz [WCF bağlantıların github'da adresindeki](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="859c9-149">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="859c9-150">Sürüm notları</span><span class="sxs-lookup"><span data-stu-id="859c9-150">Release notes</span></span>
* <span data-ttu-id="859c9-151">Başvurmak [sürüm notları](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) güncelleştirilmiş sürüm bilgileri için bilinen sorunlar da dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="859c9-151">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 