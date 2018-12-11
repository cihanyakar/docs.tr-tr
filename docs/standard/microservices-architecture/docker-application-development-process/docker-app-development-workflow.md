---
title: Docker uygulamaları için geliştirme iş akışı
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Docker uygulamaları için geliştirme iş akışı
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/05/2018
ms.openlocfilehash: bc6b1796ed7b12a04affc521ac2efee515c48ae2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150556"
---
# <a name="development-workflow-for-docker-apps"></a>Docker uygulamaları için geliştirme iş akışı

Burada geliştirici kendi tercih edilen dili kullanarak uygulama kodları ve yerel olarak test her geliştiricinin makine uygulama geliştirme yaşam döngüsü başlatır. Hangi dil, çerçeve ve geliştirici seçer, bu iş akışı ile platform ne olursa olsun Geliştirici her zaman geliştirme ve test Docker kapsayıcıları, ancak bunun yerel olarak yapılması.

Her kapsayıcı (bir Docker görüntüsü örneği), aşağıdaki bileşenleri içerir:

- Bir işletim sistemi seçimi olduğu (örneğin, bir Linux dağıtımı, Windows Nano sunucu veya Windows Server Core).

- Geliştirici (uygulama ikilileri, vb.) tarafından eklenen dosyalar.

- Yapılandırma bilgileri (ortam ayarlarını ve bağımlılıklarını).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Docker kapsayıcı tabanlı uygulamaları geliştirmek için iş akışı

Bu bölümde açıklanmaktadır *iç döngü* Docker kapsayıcı tabanlı uygulamaları için geliştirme iş akışı. İç döngü iş akışı, daha geniş DevOps iş akışını dikkate alarak değildir ve yalnızca geliştiricinin bilgisayarında geliştirme çalışmanın odaklanır anlamına gelir. Ortamı ayarlamak için ilk adımlarında bu yalnızca bir kez gerçekleştirilir dahil değildir.

Uygulamanın kendi Hizmetleri ve ek kitaplıklar (bağımlılıklar) karakterlerinden oluşur. Aşağıda, genellikle bir Docker uygulaması oluştururken Şekil 5-1'de gösterildiği gibi temel adımlar verilmiştir.

![Docker kapsayıcı uygulamaları grafik geliştirmek için adım adım iş akışı](./media/image1.png)

**Şekil 5-1.** Kapsayıcılı Docker uygulamaları geliştirmeye yönelik adım adım iş akışı

Bu kılavuzdaki tüm bu işlemi ayrıntılı olarak verilmiştir ve önemli adım her bir Visual Studio ortamında odaklanarak açıklanmıştır.

Bir düzenleyici/CLI geliştirme yaklaşımını (örneğin, Visual Studio Code ve Docker CLI'yı MacOS ya da Windows) kullandığınızda, her adım genellikle Visual Studio kullanıyorsanız, daha ayrıntılı biçimde bilmeniz gerekir. E-kitabı CLI ortamda çalışma hakkında daha fazla bilgi için bkz. [Microsoft Platforms ve araçlarla kapsayıcılı Docker uygulaması yaşam döngüsü](https://aka.ms/dockerlifecycleebook/).

Visual Studio kullanıyorsanız, bu adımların çoğunu sizin yerinize üretkenliğinizi önemli ölçüde artıran işlenir. Visual Studio 2017 kullanılarak ve çok kapsayıcılı uygulamaları hedefleyen bu özellikle doğrudur. Örneğin, Visual Studio yalnızca tek bir tıklatmayla ekler *Dockerfile* ve *docker-compose.yml* uygulamanız için dosyaları projelerinize yapılandırmasına sahip. Visual Studio'da uygulamayı çalıştırdığınızda, Docker görüntüsünü oluşturur ve çok kapsayıcılı bir uygulama doğrudan Docker'da çalıştırılır. Bile aynı anda birden fazla kapsayıcılar ayıklamanızı sağlar. Bu özellikler, geliştirme hızını artırın.

Aşağıdaki kılavuzda, "perde" Docker ile neler olduğunu açıklar.

![1. adım - uygulama grafiği kod](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Adım 1. Kodlamaya başlayın ve ilk uygulama veya hizmet taban çizgisi oluşturma

Docker uygulaması geliştirmek, Docker olmadan uygulama geliştirme şekilde benzerdir. Docker için geliştirmeye devam ederken, dağıtan ve uygulamanızı veya yerel ortamınızda Docker kapsayıcıları içinde çalışan hizmetleri test etme, farktır. Kapsayıcı, bir Linux kapsayıcı ya da bir Windows kapsayıcı olabilir.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Visual Studio ile yerel ortamınızı ayarlayın

Başlamak için sahip olduğunuzdan emin olun [Docker Community Edition'ı (CE)](https://www.docker.com/community-edition) aşağıdaki yönergelerinde açıklandığı gibi yüklü Windows için:

[İçin Docker CE Windows ile çalışmaya başlama](https://docs.docker.com/docker-for-windows/)

Visual Studio 2017 ile buna ihtiyacınız **.NET Core çoklu platform geliştirme** yüklüyse, Şekil 5-2'de gösterildiği gibi iş yükü.

![](./media/image3.png)

**Şekil 5-2**. Seçme **.NET Core ve Docker** Visual Studio 2017 Kurulum sırasında iş yükü

Uygulamanızda Docker'ı etkinleştirme ve Docker sınama dağıtımı önce (genellikle, .NET Core kapsayıcıları kullanmayı planlıyorsanız) düz .NET uygulamanızda kodlamaya başlayabilirsiniz. Ancak, üzerinde Docker olabildiğince çabuk, çünkü gerçek ortam olacak ve sorunları olabildiğince çabuk bulunabileceğini çalışma başlangıç önerilir. Visual Studio, bu nedenle, neredeyse saydam hissettiği Docker'la çalışmak kolaylaştırır çünkü bu teşvik edilir — çok kapsayıcılı uygulamalar Visual Studio'dan hata ayıklama sırasında en iyi örnek.

### <a name="additional-resources"></a>Ek kaynaklar

- **İçin Docker CE Windows ile çalışmaya başlama**

   [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- **Visual Studio 2017**

   [*https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![2. adım - dockerfile'ları grafik yazma](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Adım 2. Mevcut bir .NET temel görüntü için ilgili bir Dockerfile'ı oluşturma

Derlemek istediğiniz her özel görüntü için bir Dockerfile ihtiyacınız; Ayrıca Visual Studio veya el ile Docker CLI'yı kullanarak otomatik olarak dağıtıp dağıtmamak dağıtılması için her kapsayıcı için bir Dockerfile gerekir (docker run ve docker-compose komutları). Uygulamanızda tek bir özel hizmet varsa, tek bir Dockerfile gerekir. Uygulamanız birden çok hizmeti (olduğu gibi bir mikro hizmetler mimarisinde) içeriyorsa, her hizmet için bir Dockerfile gerekir.

Dockerfile, uygulamanızın veya hizmetinizin kök klasöründe yer alır. Bu, Docker ayarlama ve bir kapsayıcıdaki uygulama veya hizmetinizin çalıştırma bildiririz komutlar içerir. El ile bir Dockerfile içinde kod oluşturma ve birlikte .NET bağımlılıklarınızı projenize ekleyin.

Docker için Visual Studio Araçları sayesinde, bu görevi yalnızca birkaç tıklamayla gerektirir. Visual Studio 2017'de yeni bir proje oluşturduğunuzda, adlı bir seçenek yoktur **Docker desteğini etkinleştir**Şekil 5-3'te gösterildiği gibi.

![Visual Studio 2017'de yeni bir proje oluştururken, Docker desteğini etkinleştirme](./media/image5.png)

**Şekil 5-3**. Visual Studio 2017'de yeni bir proje oluştururken, Docker desteğini etkinleştirme

Projeye sağ tıklayarak mevcut bir .NET Core web uygulaması projesini Docker desteğini de etkinleştirebilirsiniz **Çözüm Gezgini** seçerek **Ekle** > **Docker desteği** Şekil 5-4'te gösterildiği gibi.

![Visual Studio'da Docker desteği menü seçeneği ekleyin](./media/add-docker-support.png)

**Şekil 5-4**. Mevcut bir Visual Studio 2017 projesinde Docker desteğini etkinleştirme

Bu eylem ekler bir *Dockerfile* gerekli yapılandırmayla projeye ve yalnızca .NET Core web uygulaması projelerinde kullanılabilir.

Eklemek için bir *docker-compose.yml* bölümünde projeye sağ tıklayın, tüm çözüm için dosya **Çözüm Gezgini** seçip **Ekle**  >   **Kapsayıcı Düzenleyicisi desteği**Şekil 5-5'te gösterildiği gibi.

![Visual Studio'da kapsayıcı orchestrator destek menü seçeneği ekleyin](./media/add-container-orchestrator-support.png)

**Şekil 5-5**. Visual Studio 2017'de var olan bir projeye eklenirken kapsayıcı Düzenleyicisi desteği.

Aşağıdaki bölümlerde, biz bu dosyaların her giden bilgiler açıklanmaktadır. Visual Studio bu işi sizin yerinize bunları yapar, ancak bir Dockerfile içinde unsurları anlamak kullanışlıdır.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Seçenek A: Var olan resmi .NET Docker görüntüsünü kullanarak bir proje oluşturma

Genellikle resmi bir depodan alabilirsiniz bir temel görüntünün üstüne kapsayıcınızın özel bir görüntü oluşturun [Docker Hub](https://hub.docker.com/) kayıt defteri. Visual Studio'da Docker desteğini etkinleştirmek ne olacağını perde tam olarak olmasıdır. Dockerfile, var olan bir aspnetcore görüntüsü kullanır.

Daha önce hangi Docker görüntülerini ve seçtiğiniz işletim sistemi ve framework bağlı olarak kullanabilirsiniz depoları açıklanmıştır. Örneğin, ASP.NET Core (Linux veya Windows) kullanmak istiyorsanız, kullanılacak görüntüyü microsoft, / aspnetcore:2.0. Bu nedenle, kapsayıcınız için kullanacağınız hangi temel Docker görüntüsüne belirtmeniz yeterlidir. Microsoft'tan ekleyerek bunu / Dockerfile için aspnetcore:2.0. Bu Visual Studio tarafından otomatik olarak gerçekleştirilir, ancak sürüm olsaydı, bu değeri güncelleştirin.

Bir sürüm numarası ile Docker Hub resmi bir .NET görüntü deposundan kullanarak aynı dil özellikleri (geliştirme, test ve üretim dahil) tüm makinelerde kullanılabilir olmasını sağlar.

Aşağıdaki örnek bir ASP.NET Core kapsayıcı için bir örnek Dockerfile gösterir.

```Dockerfile
FROM microsoft/aspnetcore:2.0

ARG source

WORKDIR /app

EXPOSE 80

COPY ${source:-obj/Docker/publish} .

ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

Bu durumda, kapsayıcı resmi ASP.NET Core Docker görüntü (Linux ve Windows için çok arch) 2.0 sürümünü temel alır. Ayar budur `FROM microsoft/aspnetcore:2.0`. (Bu temel görüntü hakkında daha fazla bilgi için bkz: [ASP.NET Core, Docker görüntüsü](https://hub.docker.com/r/microsoft/aspnetcore/) sayfası ve [.NET Core, Docker görüntüsü](https://hub.docker.com/r/microsoft/dotnet/) sayfası.) Dockerfile içinde ayrıca isteyin (Bu durumda, SUNMAYA ayarı ile yapılandırılmış olarak 80 numaralı bağlantı noktası) çalışma zamanında kullanacağınız TCP bağlantı noktasında dinlemek için Docker gerekir.

Dil ve çerçeve kullanmakta olduğunuz bağlı olarak bir Dockerfile içinde ek yapılandırma ayarları belirtebilirsiniz. Örneğin, giriş noktası satırla \["dotnet", "MySingleContainerWebApp.dll"\] bir .NET Core uygulamasını çalıştırmak için Docker söyler. .NET uygulaması derleme ve çalıştırma için SDK ve .NET Core CLI (dotnet CLI) kullanıyorsanız, bu ayar farklı olacaktır. ENTRYPOINT satır ve diğer ayarları uygulamanız için seçtiğiniz dile ve platforma bağlı olarak farklı olacaktır alt çizgidir.

### <a name="additional-resources"></a>Ek kaynaklar

- **.NET Core Uygulamaları için Docker Görüntülerinizi Derleme**

   [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- **Kendi görüntünüzü**. Resmi Docker belgelerinde.

   [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Çok yay görüntü depolarını kullanarak

Tek bir depoda bir Linux görüntüsü ve bir Windows görüntüsünü gibi platformu çeşitleri içerebilir. Bu özellik, (yani Linux ve Windows) birden çok platform karşılamak için tek depo oluşturmak Microsoft (temel Görüntü Oluşturucu) gibi satıcıları sağlar. Örneğin, [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Docker Hub kayıt defterinde depo aynı depo adını kullanarak Linux ve Windows Nano sunucu için destek sağlar.

Açık bir platformu hedefleyen bir etiket belirtirseniz, aşağıdaki durumlarda ister:

- **Microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux

- **Microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Ancak ve belirtirseniz bu yeni mid-2017 itibarıyla, hatta aynı etiketi ile aynı görüntü adı, yeni çok yay görüntülerini (gibi çok arch destekler aspnetcore görüntüsü) bağlı dağıttığınız Docker ana bilgisayar işletim sistemi olarak Linux veya Windows sürümü kullanır , aşağıdaki örnekte gösterildiği gibi:

- **Microsoft / aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

Windows konaktan görüntü çekme bu şekilde, Windows değişken çeker ve bir Linux ana bilgisayarından görüntü adının aynısını çekme Linux değişken çeker.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Seçenek B: Temel görüntünüzü sıfırdan oluşturma

Kendi Docker temel görüntüsünde sıfırdan oluşturabilirsiniz. Bu senaryo için Docker ile başlayan bir kişinin önerilmez, ancak kendi temel görüntü belirli bitlerini ayarlamak istiyorsanız, bunu yapabilirsiniz.

### <a name="additional-resources"></a>Ek kaynaklar

- **.NET Core görüntüleri çok yay**.

   https://github.com/dotnet/announcements/issues/14

- **Temel görüntü oluşturma**. Resmi Docker belgeleri.

   [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![3. adım - görüntü grafiğini oluşturun](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Adım 3. Özel Docker görüntülerinizi oluşturmak ve uygulamanızın veya hizmetinizin bunları ekleme

Uygulamanızdaki her hizmet için ilgili görüntü oluşturmanız gerekir. Uygulamanızı bir tek bir hizmeti veya web uygulaması oluşur, tek bir görüntü yeterlidir.

Docker görüntülerini otomatik olarak sizin için Visual Studio'da yerleşiktir. Aşağıdaki adımlar yalnızca Düzenleyici/CLI iş akışı için gereken ve altında olabilecekler açıklık için açıklanmıştır.

Geliştirme ve yerel olarak bir tamamlanmış itinceye kadar test için geliştirici olarak, ihtiyaç duyduğunuz, özelliği veya kaynak denetim sisteminize (örneğin GitHub) değiştirin. Bu, Docker görüntüleri oluşturun ve kapsayıcıları yerel Docker konağı için (Windows veya Linux VM) dağıtın ve çalıştırın, test ve yerel kapsayıcıların karşı hata ayıklama gerektiği anlamına gelir.

Özel bir görüntü yerel ortamınızda Docker CLI ve Dockerfile'ı kullanarak oluşturmak için docker oluşturma komutu, Şekil 5-5'olduğu gibi kullanabilirsiniz.

![Özel bir Docker görüntüsü oluşturma](./media/image8.png)

**Şekil 5-5**. Özel bir Docker görüntüsü oluşturma

İsteğe bağlı olarak, doğrudan docker derleme proje klasöründen çalıştırmak, yerine, önce gerekli .NET kitaplıkları ile dağıtılabilir bir klasör oluşturabilirsiniz ve dotnet çalıştırarak ikili dosyaları yayımlayın ve ardından docker derleme komutunu kullanın.

Bu ada sahip bir Docker görüntüsü oluşturacak **cesardl/netcore-webapı-mikro hizmet-docker: ilk**. Bu durumda: öncelikle, belirli bir sürümü temsil eden bir etiketi olan. Oluşturulmuş Docker uygulamanız için oluşturmak için gereken her özel bir görüntü için bu adımı yineleyebilirsiniz.

Bir uygulama birden çok kapsayıcılardan yapılan ne zaman (diğer bir deyişle, çok kapsayıcılı bir uygulama olduğu), ayrıca docker compose up--ilgili kullanıma sunulan meta verileri kullanarak tek bir komutla ilgili tüm görüntüleri oluşturmak için yapı komutu docker-compose.yml dosyaları.

Var olan görüntülerden yerel deponuzda docker'ı kullanarak görüntü komutu, Şekil 5-6'da gösterildiği gibi bulabilirsiniz.

![Docker görüntüleri komutunu kullanarak var olan görüntüleri görüntüleme](./media/image9.png)

**Şekil 5-6.** Docker görüntüleri komutunu kullanarak var olan görüntüleri görüntüleme

### <a name="creating-docker-images-with-visual-studio"></a>Visual Studio ile Docker görüntüleri oluşturma

Docker desteği bir proje oluşturmak için Visual Studio kullandığınızda, bir görüntü açıkça oluşturmayın. Bastığınızda bunun yerine, görüntünün sizin için oluşturulan **F5** dockerized uygulamaya veya hizmete çalıştırılacak. Bu adım Visual Studio'da otomatik olarak yapılır ve durum göremezsiniz ancak neler olduğunu bilmeniz önemlidir üzerinde underneath.

![4. adım - services grafiği tanımlayın](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>4. adımı. Çok kapsayıcılı Docker uygulaması oluştururken, docker-compose.yml hizmetlerinizi tanımlayın

[Docker-compose.yml](https://docs.docker.com/compose/compose-file/) dosya dağıtım komutları ile oluşturulmuş bir uygulama olarak dağıtılması için ilgili bir hizmetler kümesi tanımlamanıza olanak sağlar.

Docker-compose.yml dosyası kullanmak için aşağıdaki örnekte benzer içeriğe sahip ana dosyasında veya kök Çözüm klasörü'ı oluşturmanız gerekir:

```yml
version: '3'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

Bu docker-compose.yml dosyası basit ve birleştirilmiş bir sürümüdür. Bu, her zaman, bağlantı dizesi gibi dağıtım ortamı bağımlı olabileceği yapılandırma bilgilerini artı uygulanan her bir kapsayıcı (adı gibi özel görüntü), statik yapılandırma verilerini içerir. Sonraki bölümlerde, docker-compose.yml yapılandırmanın birden çok nasıl bölebilirsiniz öğreneceksiniz docker compose dosyaları ve geçersiz kılma değerleri (hata ayıklama veya sürüm) ortamını ve yürütme türüne bağlı olarak.

Docker-compose.yml dosyası örneği dört hizmet tanımlar: webmvc service (web uygulaması), (catalog.api ve ordering.api) iki mikro hizmet ve kapsayıcı olarak çalışan Linux SQL Server tabanlı bir veri kaynağı kapsayıcı, sql.data,. Her biri için gerekli bir Docker görüntüsü, bu nedenle, her hizmetin bir kapsayıcı olarak dağıtılır.

Docker-compose.yml dosyası, yalnızca kapsayıcıların ne kullanılır, ancak ayrı ayrı yapılandırmaya belirtir. Örneğin, webmvc kapsayıcısı tanımında .yml dosyası:

- Önceden oluşturulmuş bir elektronik mağaza kullanan / web: son görüntü. Ancak, aynı zamanda bir parçası olarak oluşturulacak görüntünün yapılandırabilirsiniz docker-compose temelli bir derleme üzerinde yürütme ek bir yapılandırma: docker-compose dosyasındaki bölümü.

- İki ortam değişkenlerini (katalog URL'si ve OrderingUrl) başlatır.

- Konak makinedeki dış bağlantı noktası 80 kapsayıcı üzerindeki 80 kullanıma sunulan bağlantı noktası iletir.

- Web uygulaması katalog ve sıralama hizmetiyle bağlantı bağlıdır\_ayarı. Bu hizmet, bu hizmetleri yeniden başlatılana kadar beklenecek neden olur.

Mikro hizmetler ve çok kapsayıcılı uygulamalar uygulamak nasıl ele, biz bir sonraki bölümde docker-compose.yml dosyası yeniden ziyaret.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Visual Studio 2017'de docker-compose.yml ile çalışma

Şekil 5-7'de gösterildiği gibi bir web uygulaması projesine kapsayıcı Düzenleyicisi desteği eklediğinizde, Visual Studio bir hizmet bölümü (Proje) docker-compose.yml dosyasını içeren çözüme ekler. Bu, bir çoklu kapsayıcı çözümü düzenlemeye başlamanın kolay bir yoludur.

![Visual Studio'da kapsayıcı orchestrator destek menü öğesi ekleme](./media/add-container-orchestrator-support.png)

**Şekil 5-7**. Bir ASP.NET Core projesi sağ tıklayarak Visual Studio 2017'de Docker desteği ekleme

Kapsayıcı Düzenleyicisi desteği ekleme (zaten yoksa) Dockerfile, projenize ekler. Ayrıca çözüm düzeyinde bir genel docker-compose.yml dosyası için yapılandırma bilgilerini ekler. Yeni bir proje düğümünü göreceksiniz ( *docker compose.dcproj* proje dosyası) içinde **Çözüm Gezgini** Şekil 5-8'de gösterildiği gibi docker-compose.yml dosyasını içeren.

![Çözüm Gezgininde docker-compose](./media/docker-compose-files.png)

**Şekil 5-8**. **Docker-compose** Visual Studio 2017 Çözüm Gezgini'nde eklenen ağaç düğümü

Ardından, docker-compose.yml dosyasını açın ve ek özellikler ile güncelleştirin.

Kullanarak bir docker-compose.yml dosyası ile çok kapsayıcılı bir uygulama dağıtabilirsiniz `docker-compose up` komutu.

![Adım 5 - çalışma uygulama grafiği](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>5. adımı. Kendi Docker uygulaması derleme ve çalıştırma

Uygulamanız yalnızca tek bir kapsayıcıya sahip değilse, Docker Konağı (VM veya fiziksel sunucu) dağıtarak çalıştırabilirsiniz. Uygulamanız birden fazla hizmet içeriyor, ancak bunu oluşan bir uygulama olarak ya da tek bir CLI komutu kullanarak dağıtabilirsiniz (docker-compose ayarlama), veya Visual Studio ile bu komut aslında altında kullanacak. Farklı seçenekleri göz atalım.

### <a name="option-a-run-a-single-container-app"></a>Seçenek A: Tek kapsayıcı uygulamasını çalıştırma

#### <a name="docker-cli"></a>Docker CLI

Şekil 5-9'olduğu gibi komutu çalıştırın: docker kullanarak Docker kapsayıcısı çalıştırabilirsiniz:

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![Komutu çalıştırarak docker kullanarak Docker kapsayıcı çalıştırma](./media/image13.png)

**Şekil 5-9**. Komutu çalıştırarak docker kullanarak Docker kapsayıcı çalıştırma

Bu durumda, komut kapsayıcının iç bağlantı noktası 5000 ana makinenin 80 numaralı bağlantı noktasına bağlar. Bu konak 80 numaralı bağlantı noktasında dinleme ve kapsayıcıda genericread 5000 numaralı bağlantı noktasına ileten anlamına gelir.

#### <a name="visual-studio"></a>Visual Studio

Kapsayıcı Düzenleyicisi desteği eklemediyseniz, ayrıca bir çoklu kapsayıcı uygulaması Visual Studio'da tuşlarına basarak çalıştırabileceğiniz **F5**. Kapsayıcı, docker run kullanarak yerel olarak çalışır.

### <a name="option-b-run-a-multi-container-app"></a>Seçenek B: Bir çoklu kapsayıcı uygulaması

Çoğu Kurumsal senaryolarda, Docker uygulaması birden çok Hizmetleri, Şekil 5-10'da gösterildiği gibi çok kapsayıcılı bir uygulama çalıştırmak gereken yani oluşacaktır.

![VM ile dağıtılan Docker kapsayıcılarının gösteren grafik](./media/image14.png)

**Şekil 5-10**. Dağıtılmış Docker kapsayıcıları ile VM

#### <a name="docker-cli"></a>Docker CLI

Docker CLI ile çok kapsayıcılı bir uygulama çalıştırmak için docker çalıştırabilirsiniz-compose komutu. Bu komut kullandığı docker-compose.yml dosyası çok kapsayıcılı bir uygulama dağıtmak için çözüm düzeyinde olması. Şekil 5-11 komut docker-compose.yml dosyasını içeren ana proje dizininden çalıştırılırken sonuçları gösterilmektedir.

![Örnek sonuçları çalıştırırken docker-compose komutu](./media/image15.png)

**Şekil 5-11**. Örnek sonuçları çalıştırırken docker-compose komutu

Sonra docker-compose komutu çalıştırmaları, uygulama ve onun ilişkili kapsayıcılar, Docker ana bilgisayara dağıtılır.

#### <a name="visual-studio"></a>Visual Studio

Visual Studio 2017'yi kullanarak çok kapsayıcılı bir uygulama çalıştıran basit bir işlemdir. Yalnızca, çok kapsayıcılı bir uygulama çalıştırabilirsiniz, ancak doğrudan Visual Studio'dan tüm kapsayıcıları ayarı tarafından normal kesme noktaları hata ayıklamanız mümkün.

Her bir çözüm içinde bir proje için kapsayıcı Düzenleyicisi desteği eklemeden önce belirtildiği gibi proje çalıştırın veya çözümün tamamının aynı anda hata ayıklama olanak sağlayan genel (Çözüm düzeyinde) docker-compose.yml dosyasında yapılandırılır. Visual Studio Docker çözümü desteği etkin olan her proje için bir kapsayıcı başlatın ve iç tüm adımları gerçekleştirdiğiniz (dotnet yayımlama, docker derleme, vs.).

Burada önemli olan nokta Şekil 5-12'de gösterildiği gibi Visual Studio 2017'de, ek bir yoktur **Docker** komutunu **F5** anahtar eylem. Bu seçenek çalıştırın ya da docker-compose.yml dosyaları çözüm düzeyinde tanımlanan tüm kapsayıcıları çalıştırarak çok kapsayıcılı bir uygulama hata ayıklama sağlar. Birden çok kapsayıcı çözümleri hata ayıklama özelliği (kapsayıcı) farklı bir projede birkaç kesme noktaları, her bir kesme noktası ayarlayın ve Visual Studio'dan hata ayıklama sırasında farklı projelerde tanımlanan ve çalıştırılan kesme noktalarında durdurur anlamına gelir. farklı kapsayıcılar.

![Visual Studio 2017'de çalışan çok kapsayıcılı uygulamalar](./media/image16.png)

**Şekil 5-12**. Visual Studio 2017'de çalışan çok kapsayıcılı uygulamalar

### <a name="additional-resources"></a>Ek kaynaklar

-  **ASP.NET kapsayıcısını uzak Docker konağı için dağıtma**

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Test etme ve dağıtma düzenleyicilerle hakkında bir Not

Docker compose up ve docker run komutları (veya çalışan ve kapsayıcıları Visual Studio'da hata ayıklama) kapsayıcıları geliştirme ortamınızda test etmek için yeterli. Ancak, bu yaklaşım Docker kümeleri hedefleniyorsa ve Docker Swarm, Mesosphere DC/OS veya Kubernetes düzenleyicileri gibi kullanmamanız gerekir. Gibi bir küme kullanıyorsanız [Docker Swarm modu](https://docs.docker.com/engine/swarm/) dağıtmak ve test gibi ek komutlar gerekir (kullanılabilir için Docker CE Windows ve Mac sürümü 1.12 itibaren), [docker hizmeti oluşturulur](https://docs.docker.com/engine/reference/commandline/service_create/) için tek hizmetler. Birden çok kapsayıcılardan oluşan bir uygulama dağıtıyorsanız, kullandığınız [docker compose paket](https://docs.docker.com/compose/reference/bundle/) ve [docker dağıtma myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) olarak oluşturulan uygulamayı dağıtmak için bir *Yığını*. Daha fazla bilgi için bkz. blog gönderisine [giriş Deneysel dağıtılmış uygulama paketleri](https://blog.docker.com/2016/06/docker-app-bundle/) Docker belgelerinde. Docker sitesi.

İçin [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) ve [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) farklı dağıtım komutları ve komut dosyaları da kullanmanız gerekir.

![6. adım grafiği](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>6. adım. Kullanarak yerel bir Docker ana bilgisayarınızda Docker uygulamanızı test edin

Bu adım, uygulamanızın yapılması bağlı olarak değişir. Tek kapsayıcı veya hizmet olarak dağıtılan bir basit .NET Core Web uygulamasında, Docker konağı üzerinde bir tarayıcı açıp bu siteye gezinme, Şekil 5-13'te gösterildiği gibi hizmete erişebilir. (Dockerfile içinde yapılandırma kapsayıcı 80 dışında her şey, konağa bağlantı noktasına eşler. ana bilgisayar bağlantı noktası URL'ye dahil edin.)

![Örneği yerel olarak localhost kullanarak Docker uygulamanızı test etme](./media/image18.png)

**Şekil 5-13**. Örneği yerel olarak localhost kullanarak Docker uygulamanızı test etme

Docker için localhost işaret etmiyorsa IP ana bilgisayar (Bu varsayılan Docker CE kullanırken, gerekir), hizmetinize gidin ve makinenizin Ağ kartının IP adresini kullanın.

Bu URL tarayıcıda tartışılan belirli bir kapsayıcı örneği için 80 numaralı bağlantı noktasını kullanır. Nasıl bu komutu çalıştırın: docker ile bir önceki adımda açıklandığı gibi dağıtılmış olduğu için ancak, dahili olarak istekleri 5000, bağlantı noktası için Rehbere yönlendiriliyorsunuz.

Ayrıca, Şekil 5-14'te gösterildiği gibi terminalden curl kullanarak uygulamayı test edebilirsiniz. Bir Docker yüklemesinde Windows üzerindeki Docker ana bilgisayar IP her zaman 10.0.75.1 makinenizin gerçek IP adresinin yanı sıra varsayılandır.

![Docker uygulamanızı yerel olarak curl kullanarak test etme örneği](./media/image19.png)

**Şekil 5-14**. Docker uygulamanızı yerel olarak curl kullanarak test etme örneği

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Test ve hata ayıklama Visual Studio 2017 ile kapsayıcıları

Çalışan kapsayıcılar, olduğu gibi çalışan kapsayıcılar Visual Studio 2017 ile hata ayıklama, .NET uygulama kadar aynı şekilde ayıklayabilirsiniz.

### <a name="testing-and-debugging-without-visual-studio"></a>Test ve hata ayıklama Visual Studio

Düzenleyici/CLI yaklaşımı kullanarak geliştiriyorsanız kapsayıcılarında hata ayıklama daha zordur ve izlemeleri oluşturarak hata ayıklama isteyeceksiniz.

### <a name="additional-resources"></a>Ek kaynaklar

- **Yerel bir Docker kapsayıcısı uygulamalarında hata ayıklama**

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- **Steve Lasker. Derleme, hata ayıklama, Docker ile ASP.NET Core uygulamaları dağıtın.** Video.

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Visual Studio ile kapsayıcıları geliştirirken basitleştirilmiş bir iş akışı

Etkili bir şekilde, Visual Studio kullanarak iş akışı Düzenleyicisi'ni / CLI yaklaşımı kullanırsanız, çok daha kolay olacaktır. Docker tarafından gerekli adımların çoğu için Dockerfile ilgili ve gizli ya da Visual Studio tarafından Şekil 5-15'te gösterildiği gibi Basitleştirilmiş docker-compose.yml dosyaları.

![Visual Studio ile geliştirirken basitleştirilmiş bir iş akışı](./media/image20.png)

**Şekil 5-15**. Visual Studio ile geliştirirken basitleştirilmiş bir iş akışı

Ayrıca, yalnızca bir kez (Docker desteği ekleme projelerinize) 2. adım gerçekleştirmeniz gerekir. Bu nedenle, iş akışı herhangi bir geliştirme için .NET kullanarak normal geliştirme görevlerine benzer şekildedir. Kapsar (görüntü oluşturma işlemi, hangi kullandığınız temel görüntüleri, kapsayıcılar, vb. dağıtımını) altında ve bazen de davranışları özelleştirmek için Dockerfile veya docker-compose.yml dosyasını düzenlemeniz gerekir neler olduğunu bilmeniz gerekir. Ancak işin çoğunu, çok daha üretken hale Visual Studio kullanılarak büyük ölçüde basitleştirilir.

### <a name="additional-resources"></a>Ek kaynaklar

- **Steve Lasker. Visual Studio 2017 ile .NET docker geliştirme**

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

- **Jeffrey t Fritz. Visual Studio için bir kapsayıcı yeni Docker araçları ile .NET Core uygulaması yerleştirin**

   [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Windows kapsayıcıları ayarlamak için bir Dockerfile içinde PowerShell komutlarını kullanarak

[Windows kapsayıcıları](/virtualization/windowscontainers/about/) mevcut Windows uygulamalarınızı Docker görüntüleri olarak dönüştürmek ve Docker ekosistemi sayesinde geri kalanı gibi aynı araçları ile dağıtmaya olanak sağlar. Windows kapsayıcıları kullanmak için aşağıdaki örnekte gösterildiği gibi bir Dockerfile içinde PowerShell komutlarını çalıştırın:

```Dockerfile
FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]
```

Bu durumda, biz bir Windows Server Core temel görüntüyü (FROM ayar) kullanarak ve bir (çalışma ayarı) PowerShell komutuyla IIS'yi yükleme. Benzer şekilde, ASP.NET 4.x, .NET 4.6 veya herhangi bir Windows yazılımı gibi ek bileşenler ayarlamak için PowerShell komutlarını kullanabilirsiniz. Örneğin, aşağıdaki komut bir Dockerfile içinde ASP.NET 4.5 ' ayarlar:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Ek kaynaklar

- **aspnet-docker/Dockerfile.** Windows özellikleri içerecek şekilde dockerfile'ları için örnek Powershell komutları.

   [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
>[Önceki](index.md)
>[İleri](../multi-container-microservice-net-applications/index.md)
