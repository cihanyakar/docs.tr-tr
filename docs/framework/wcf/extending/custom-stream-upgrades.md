---
title: "Özel Akış Yükseltmeleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20b061418ee2dc6c3adcde5553d29e680d739582
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-stream-upgrades"></a><span data-ttu-id="a81d0-102">Özel Akış Yükseltmeleri</span><span class="sxs-lookup"><span data-stu-id="a81d0-102">Custom Stream Upgrades</span></span>
<span data-ttu-id="a81d0-103">İstemci ve sunucu arasındaki bayt sürekli bir akış üzerinde akış odaklı taşımaları TCP ve adlandırılmış kanallar gibi çalışır.</span><span class="sxs-lookup"><span data-stu-id="a81d0-103">Stream-oriented transports such as TCP and Named Pipes operate on a continuous stream of bytes between the client and server.</span></span> <span data-ttu-id="a81d0-104">Bu akış tarafından gerçekleştirilen bir <xref:System.IO.Stream> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-104">This stream is realized by a  <xref:System.IO.Stream> object.</span></span> <span data-ttu-id="a81d0-105">Bir akış yükseltme istemci kanal yığına bir isteğe bağlı Protokolü katmanı eklemek ister ve bunu yapmak için iletişim kanalının diğer ucundaki sorar.</span><span class="sxs-lookup"><span data-stu-id="a81d0-105">In a stream upgrade, the client wants to add an optional protocol layer to the channel stack, and asks the other end of the communication channel to do so.</span></span> <span data-ttu-id="a81d0-106">Özgün değiştirme akış yükseltme oluşur <xref:System.IO.Stream> yükseltilmiş bir nesne.</span><span class="sxs-lookup"><span data-stu-id="a81d0-106">The stream upgrade consists in replacing the original <xref:System.IO.Stream> object with an upgraded one.</span></span>  
  
 <span data-ttu-id="a81d0-107">Örneğin, aktarım akışı en üstünde Sıkıştırma akışına oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-107">For example, you can build a compression stream directly on top of the transport stream.</span></span> <span data-ttu-id="a81d0-108">Bu durumda özgün aktarım <xref:System.IO.Stream> sıkıştırma saran bir ile değiştirilir <xref:System.IO.Stream> ilkinin geçici.</span><span class="sxs-lookup"><span data-stu-id="a81d0-108">In this case the original transport <xref:System.IO.Stream> is replaced with one that wraps the compression <xref:System.IO.Stream> around the original one.</span></span>  
  
 <span data-ttu-id="a81d0-109">Birden çok akış yükseltmeleri, her bir kaydırma uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-109">You can apply multiple stream upgrades, each wrapping the preceding one.</span></span>  
  
## <a name="how-stream-upgrades-work"></a><span data-ttu-id="a81d0-110">Akış yükseltme nasıl çalışır</span><span class="sxs-lookup"><span data-stu-id="a81d0-110">How Stream Upgrades Work</span></span>  
 <span data-ttu-id="a81d0-111">Akış yükseltme işlemi dört bileşenleri vardır.</span><span class="sxs-lookup"><span data-stu-id="a81d0-111">There are four components to the stream upgrade process.</span></span>  
  
1.  <span data-ttu-id="a81d0-112">Yükseltme akış *Başlatıcı* işlemi başlar: çalışma zamanında kanal Aktarım katmanı yükseltmek için bir istek diğer sonuna bağlantısını başlatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-112">An upgrade stream *Initiator* begins the process: at run-time it can initiate a request to the other end of its connection to upgrade the channel transport layer.</span></span>  
  
2.  <span data-ttu-id="a81d0-113">Yükseltme akış *Acceptor* yükseltme taşır: çalışma zamanında başka bir makineden yükseltme isteği alır ve mümkünse, yükseltme kabul eder.</span><span class="sxs-lookup"><span data-stu-id="a81d0-113">An upgrade stream *Acceptor* carries out the upgrade: at run-time it receives the upgrade request from the other machine, and if possible, accepts the upgrade.</span></span>  
  
3.  <span data-ttu-id="a81d0-114">Bir yükseltme *sağlayıcı* oluşturur *Başlatıcı* istemcide ve *Acceptor* sunucusunda.</span><span class="sxs-lookup"><span data-stu-id="a81d0-114">An upgrade *Provider* creates the *Initiator* on the client and the *Acceptor* on the server.</span></span>  
  
4.  <span data-ttu-id="a81d0-115">Bir akış yükseltme *bağlama öğesi* hizmet ve istemci bağlantılarına eklenir ve çalışma zamanında sağlayıcısı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a81d0-115">A stream upgrade *Binding Element* is added to the bindings on the service and the client, and creates the provider at runtime.</span></span>  
  
 <span data-ttu-id="a81d0-116">Birden fazla yükseltme söz konusu olduğunda, hangi yükseltme geçişleri her başlatma için geçerli zorlamak için Durum makineleri Acceptor ve Başlatıcı kapsülleyen unutmayın.</span><span class="sxs-lookup"><span data-stu-id="a81d0-116">Note that in the case of multiple upgrades, the Initiator and Acceptor encapsulate state machines to enforce which upgrade transitions are valid for each Initiation.</span></span>  
  
## <a name="how-to-implement-a-stream-upgrade"></a><span data-ttu-id="a81d0-117">Bir akış yükseltme gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="a81d0-117">How to Implement a Stream Upgrade</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a81d0-118">dört sağlar `abstract` , uygulayabileceğiniz sınıfları:</span><span class="sxs-lookup"><span data-stu-id="a81d0-118"> provides four `abstract` classes that you can implement:</span></span>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 <span data-ttu-id="a81d0-119">Özel akış yükseltmeyi uygulamak için aşağıdakileri yapın.</span><span class="sxs-lookup"><span data-stu-id="a81d0-119">To implement a custom stream upgrade, do the following.</span></span> <span data-ttu-id="a81d0-120">Bu yordam istemci ve sunucu makinelerde en az bir akış yükseltme işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="a81d0-120">This procedure implements a minimal stream upgrade process on both the client and server machines.</span></span>  
  
1.  <span data-ttu-id="a81d0-121">Arabirimini uygulayan bir sınıf oluşturun <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-121">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.</span></span>  
  
    1.  <span data-ttu-id="a81d0-122">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> yükseltilmesi ve yükseltilmiş akış dönmek için akışında yapılacak yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-122">Override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> method to take in the stream to be upgraded, and return the upgraded stream.</span></span> <span data-ttu-id="a81d0-123">Bu yöntem, zaman uyumlu olarak çalışır; zaman uyumsuz olarak yükseltme başlatmak için benzer yöntemler vardır.</span><span class="sxs-lookup"><span data-stu-id="a81d0-123">This method works synchronously; there are analogous methods to initiate the upgrade asynchronously.</span></span>  
  
    2.  <span data-ttu-id="a81d0-124">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> yöntemi ek güncelleştirmelerini denetle.</span><span class="sxs-lookup"><span data-stu-id="a81d0-124">Override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> method to check for additional upgrades.</span></span>  
  
2.  <span data-ttu-id="a81d0-125">Arabirimini uygulayan bir sınıf oluşturun <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-125">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.</span></span>  
  
    1.  <span data-ttu-id="a81d0-126">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> yükseltilmesi ve yükseltilmiş akış dönmek için akışında yapılacak yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-126">Override the <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> method to take in the stream to be upgraded, and return the upgraded stream.</span></span> <span data-ttu-id="a81d0-127">Bu yöntem, zaman uyumlu olarak çalışır; Yükseltme zaman uyumsuz olarak kabul etmek için benzer yöntemler vardır.</span><span class="sxs-lookup"><span data-stu-id="a81d0-127">This method works synchronously; there are analogous methods to accept the upgrade asynchronously.</span></span>  
  
    2.  <span data-ttu-id="a81d0-128">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> istenen yükseltme bu yükseltme acceptor bu noktada yükseltme işlemindeki tarafından desteklenip desteklenmediğini belirlemek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="a81d0-128">Override the <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> method to determine if the upgrade requested is supported by this upgrade acceptor at this point in the upgrade process.</span></span>  
  
3.  <span data-ttu-id="a81d0-129">Uygulayan bir sınıf oluşturun <xref:System.ServiceModel.Channels.StreamUpgradeProvider>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-129">Create a class the implements <xref:System.ServiceModel.Channels.StreamUpgradeProvider>.</span></span> <span data-ttu-id="a81d0-130">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> ve <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> acceptor ve 2. ve 1. adımda tanımlanan Başlatıcı örnekleri döndürülecek yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="a81d0-130">Override the <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> and the <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> methods to return instances of the acceptor and initiator defined in steps 2 and 1.</span></span>  
  
4.  <span data-ttu-id="a81d0-131">Arabirimini uygulayan bir sınıf oluşturun <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-131">Create a class that implements <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.</span></span>  
  
    1.  <span data-ttu-id="a81d0-132">Geçersiz kılma <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> istemcide yöntemi ve <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> hizmette yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-132">Override the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> method on the client and the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> method on the service.</span></span>  
  
    2.  <span data-ttu-id="a81d0-133">Geçersiz kılma <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> istemcide yöntemi ve <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> yükseltme bağlama öğesine eklemek için hizmetinde yöntemini <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-133">Override the <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> method on the client and the <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> method on the service to add the upgrade Binding Element to <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>.</span></span>  
  
5.  <span data-ttu-id="a81d0-134">Sunucu ve istemci makineleri bağlamaları yeni akış yükseltme bağlama öğesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a81d0-134">Add the new stream upgrade binding element to bindings on the server and client machines.</span></span>  
  
## <a name="security-upgrades"></a><span data-ttu-id="a81d0-135">Güvenlik yükseltmeleri</span><span class="sxs-lookup"><span data-stu-id="a81d0-135">Security Upgrades</span></span>  
 <span data-ttu-id="a81d0-136">Bir güvenlik yükseltmesi ekleme, genel akış yükseltme işlemi özelleştirilmiş bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="a81d0-136">Adding a security upgrade is a specialized version of the general stream upgrade process.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a81d0-137">zaten Akış Güvenliği yükseltmek için iki bağlama öğeleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="a81d0-137"> already provides two binding elements for upgrading stream security.</span></span> <span data-ttu-id="a81d0-138">Aktarım düzeyinde güvenlik yapılandırmasını yalıtılan <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> ve <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement> hangi yapılandırılabilir ve özel bağlama için eklendi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-138">The configuration of transport-level security is encapsulated by the <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> and the <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement> which can be configured and added to a custom binding.</span></span> <span data-ttu-id="a81d0-139">Bu bağlama öğelerini genişletmek <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> yükseltme sağlayıcıları istemci ve sunucu akış derlemeler sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a81d0-139">These binding elements extend the <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> class that builds the client and server stream upgrade providers.</span></span> <span data-ttu-id="a81d0-140">Bu bağlama öğeleri Uzman güvenlik akış olmayan yükseltme sağlayıcısı sınıfları oluşturma yöntemleri sahip `public`, bu iki için tüm yapmanız gereken durumda bağlamaya bağlama öğesi eklemek için.</span><span class="sxs-lookup"><span data-stu-id="a81d0-140">These binding elements have methods that create the specialized security stream upgrade provider classes, which are not `public`, so for these two cases all you need to do is to add the binding element to the binding.</span></span>  
  
 <span data-ttu-id="a81d0-141">Yukarıdaki iki bağlama öğeleri tarafından üç güvenlikle ilgili karşılanmadı güvenlik senaryoları için `abstract` sınıfları yukarıdaki Başlatıcı, acceptor ve sağlayıcı temel sınıflardan türetilmiş:</span><span class="sxs-lookup"><span data-stu-id="a81d0-141">For security scenarios not met by the above two binding elements, three security-related `abstract` classes are derived from the above initiator, acceptor and provider base classes:</span></span>  
  
1.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 <span data-ttu-id="a81d0-142">Güvenlik akış yükseltme uygulama işlemi boyunca önce bu üç sınıflardan türetin fark ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="a81d0-142">The process of implementing a security stream upgrade is the same as before, with the difference that you would derive from these three classes.</span></span> <span data-ttu-id="a81d0-143">Çalışma zamanı için güvenlik bilgileri sağlamak için bu sınıfları, ek özellikler geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="a81d0-143">Override the additional properties in these classes to supply security information to the runtime.</span></span>  
  
## <a name="multiple-upgrades"></a><span data-ttu-id="a81d0-144">Birden fazla yükseltme</span><span class="sxs-lookup"><span data-stu-id="a81d0-144">Multiple Upgrades</span></span>  
 <span data-ttu-id="a81d0-145">Yükseltme istekleri ek oluşturmak için yukarıdaki işlemi tekrarlayın: ek uzantıları oluşturma <xref:System.ServiceModel.Channels.StreamUpgradeProvider> ve bağlama öğeleri.</span><span class="sxs-lookup"><span data-stu-id="a81d0-145">To create additional upgrade requests repeat the above process: create additional extensions of <xref:System.ServiceModel.Channels.StreamUpgradeProvider> and binding elements.</span></span> <span data-ttu-id="a81d0-146">Bağlamaya ait bağlama öğelerini ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a81d0-146">Add the binding elements to the binding.</span></span> <span data-ttu-id="a81d0-147">Ek bağlama öğeleri bağlamaya eklenen ilk bağlama öğesi ile başlayan ardışık olarak işlenir.</span><span class="sxs-lookup"><span data-stu-id="a81d0-147">The additional binding elements are processed sequentially, starting with the first binding element added to the binding.</span></span> <span data-ttu-id="a81d0-148">İçinde <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> ve <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> her yükseltme sağlayıcı kendisini parametreleri bağlama önceden varolan yükseltme sonrasında katman nasıl belirleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-148">In <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> and <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> each upgrade provider can determine how to layer itself on any pre-existing upgrade binding parameters.</span></span> <span data-ttu-id="a81d0-149">Ardından yeni bir birleşik yükseltme bağlama parametresi parametresiyle bağlama varolan yükseltme değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="a81d0-149">It should then replace the existing upgrade binding parameter with a new composite upgrade binding parameter.</span></span>  
  
 <span data-ttu-id="a81d0-150">Alternatif olarak, bir yükseltme sağlayıcı birden fazla yükseltme destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="a81d0-150">Alternatively, one upgrade provider can support multiple upgrades.</span></span> <span data-ttu-id="a81d0-151">Örneğin, güvenlik ve sıkıştırma destekleyen bir özel akış yükseltme sağlayıcı uygulamak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-151">For example, you might want to implement a custom stream upgrade provider that supports both security and compression.</span></span> <span data-ttu-id="a81d0-152">Aşağıdaki adımları uygulayın:</span><span class="sxs-lookup"><span data-stu-id="a81d0-152">Do the following steps:</span></span>  
  
1.  <span data-ttu-id="a81d0-153">Bir alt <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> Acceptor ve Başlatıcı oluşturur sağlayıcı sınıfı yazmak için.</span><span class="sxs-lookup"><span data-stu-id="a81d0-153">Subclass <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> to write the provider class that creates the Initiator and Acceptor.</span></span>  
  
2.  <span data-ttu-id="a81d0-154">Bir alt <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> geçersiz kılmak emin <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> Sıkıştırma akışına ve güvenli akış için içerik türleri sırayla döndürülecek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-154">Subclass the <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> making sure to override the <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> method to return the content types for the compression stream and the secure stream in order.</span></span>  
  
3.  <span data-ttu-id="a81d0-155">Bir alt <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> özel içerik türlerinde anlar kendi <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a81d0-155">Subclass the <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> that understands the custom content types in its <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> method.</span></span>  
  
4.  <span data-ttu-id="a81d0-156">Akış her çağrı sonra yükseltilecek <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> ve <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.</span><span class="sxs-lookup"><span data-stu-id="a81d0-156">The stream will be upgraded after each call to <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> and <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81d0-157">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a81d0-157">See Also</span></span>  
 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>