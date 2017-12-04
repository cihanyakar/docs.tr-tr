---
title: "Kimlik Doğrulama için Genişletilmiş Koruma Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d2ceffe-a7bf-4bd9-a5a2-9406423bd7f8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d8dadf09434778bc32bb75c5eff5ff4cb0494373
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="extended-protection-for-authentication-overview"></a><span data-ttu-id="1e3fb-102">Kimlik Doğrulama için Genişletilmiş Koruma Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="1e3fb-102">Extended Protection for Authentication Overview</span></span>
<span data-ttu-id="1e3fb-103">Kimlik doğrulaması için genişletilmiş koruma, bir saldırganın istemci kimlik bilgilerini yakalar ve bunları bir sunucuya iletir man-in--middle (MITM) saldırılarına karşı korunmasına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-103">Extended Protection for Authentication helps protect against man-in-the-middle (MITM) attacks, in which an attacker intercepts a client’s credentials and forwards them to a server.</span></span>  
  
 <span data-ttu-id="1e3fb-104">Üç katılımcılar bir senaryoyu düşünün: bir istemci, sunucu ve saldırgan.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-104">Consider a scenario with three participants: a client, server, and attacker.</span></span> <span data-ttu-id="1e3fb-105">Sunucunun URL'sine sahip `https://server`, saldırgan URL sahipken `https://attacker`.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-105">The server has the URL `https://server`, whereas the attacker has the URL `https://attacker`.</span></span> <span data-ttu-id="1e3fb-106">Saldırgan, sunucunun değilmiş gibi saldırgan erişme içine istemci püf noktaları.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-106">The attacker tricks the client into accessing the attacker as if it were the server.</span></span> <span data-ttu-id="1e3fb-107">Saldırgan sonra sunucuya istek gönderir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-107">The attacker then sends a request to the server.</span></span> <span data-ttu-id="1e3fb-108">Saldırgan güvenli bir kaynağa erişmeye çalıştığında, sunucunun bir WWW-Authenticate üstbilgisi olan saldırgan yanıtlar.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-108">If the attacker is trying to access a secure resource, the server replies to the attacker with a WWW-Authenticate header.</span></span> <span data-ttu-id="1e3fb-109">İstemcide WWW-Authenticate üstbilgisi gönderir şekilde saldırgan kimlik doğrulama bilgileri yok.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-109">The attacker does not have the authentication information, so it sends the WWW-Authenticate header on to the client.</span></span> <span data-ttu-id="1e3fb-110">İstemci yetkilendirme üst bilgisi bir saldırgana gönderir ve saldırgan sunucu üstbilgi gönderir ve istemci kimlik bilgileri kullanılarak güvenli kaynaklara erişim alır.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-110">The client sends the Authorization header to the attacker, and the attacker sends the header on to the server and gets access to the secure resources using the client’s credentials.</span></span>  
  
 <span data-ttu-id="1e3fb-111">Şu anda bir istemci uygulaması kendisini Kerberos, Özet veya HTTPS kullanarak NTLM kullanarak sunucuya doğruladığında bir aktarım düzeyi güvenlik (TLS) kanalı ilk kurulur ve kimlik doğrulaması bu kanalı kullanılarak gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-111">Currently, when a client application authenticates itself to the server using Kerberos, Digest, or NTLM using HTTPS, a Transport Level Security (TLS) channel is first established and authentication takes place using this channel.</span></span> <span data-ttu-id="1e3fb-112">Ancak, Güvenli Yuva Katmanı (SSL) tarafından oluşturulan oturum anahtarı ile kimlik doğrulaması sırasında oluşturulan oturum anahtarı arasındaki hiçbir bağlama yok.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-112">However, there is no binding between the session key generated by Secure Sockets Layer (SSL) and the session key that is generated during authentication.</span></span> <span data-ttu-id="1e3fb-113">Bu nedenle, önceki senaryoda, iletişimin (örneğin, bir HTTPS kanalı), TLS üzerinden yer alıyorsa vardır oluşturulan iki SSL kanalı: bir istemci ve saldırgan ve başka bir saldırgan ve sunucu arasında arasında.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-113">So, in the previous scenario, if the communication takes places over a TLS (such as an HTTPS channel), there are two SSL channels created: one between the client and the attacker, and another between the attacker and the server.</span></span> <span data-ttu-id="1e3fb-114">İstemcinin kimlik bilgileri istemciden sunucuya ilk saldırgan ile istemci arasında SSL kanalı üzerinden ve sonra saldırgan ve sunucu arasında kanal üzerinden gönderilir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-114">The client’s credentials are sent from the client to the server first over the SSL channel between the client and the attacker and then over the channel between the attacker and the server.</span></span> <span data-ttu-id="1e3fb-115">İstemcinin kimlik bilgilerini sunucu ulaştığınızda, sunucu üzerinde bu kimlik bilgilerini gönderilen kanal saldırgan ve istemci ile kaynaklanan algılama olmadan kimlik bilgilerini doğrular.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-115">Once the client’s credentials reach the server, the server verifies the credentials without detecting that the channel over which those credentials were sent originated with the attacker and not the client.</span></span>  
  
 <span data-ttu-id="1e3fb-116">, TLS güvenli bir dış kanal hem de istemci kimlik doğrulaması iç kanal ve bir kanal bağlama belirteci (CBT) sunucusuna iletmek için çözümüdür.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-116">The solution is to use a TLS-secured outer channel and a client-authenticated inner channel, and to pass a Channel Binding Token (CBT) to the server.</span></span> <span data-ttu-id="1e3fb-117">CBT TLS güvenlikli dış kanal bir özelliktir ve istemci kimlik doğrulaması iç kanalı üzerinden bir konuşma dış kanalına bağlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-117">The CBT is a property of the TLS-secured outer channel, and is used to bind the outer channel to a conversation over the client-authenticated inner channel.</span></span>  
  
 <span data-ttu-id="1e3fb-118">Önceki senaryoda, istemci saldırgan TLS kanalı CBT sunucuya gönderilen yetkilendirme bilgilerle birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-118">In the previous scenario, the CBT of the client-attacker TLS channel is merged with the authorization information that is sent to the server.</span></span> <span data-ttu-id="1e3fb-119">CBT algılayan bir sunucu, istemci saldırgan kanala saldırgan sunuculu kanala bağlı CBT karşılık gelen istemci kimlik doğrulaması bilgilerini bulunan CBT karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-119">A CBT-aware server compares the CBT contained in the client authentication information, which corresponds to the client-attacker channel, to the CBT attached to the attacker-server channel.</span></span> <span data-ttu-id="1e3fb-120">Bir CBT bir kanalın hedefe belirli olduğundan istemci-saldırgan CBT saldırgan-sunucu CBT eşleşmiyor.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-120">A CBT is specific to a channel’s destination, so the client-attacker CBT does not match the attacker-server CBT.</span></span> <span data-ttu-id="1e3fb-121">Bu sunucunun MITM saldırı algılama ve kimlik doğrulama isteği reddeder sağlar.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-121">This lets the server detect the MITM attack and refuse the authentication request.</span></span>  
  
 <span data-ttu-id="1e3fb-122">İstemci tarafı herhangi bir yapılandırma ayarı gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-122">The client side does not require any configuration setting.</span></span> <span data-ttu-id="1e3fb-123">İstemci CBT sunucuya geçirmek için güncelleştirilmiş sonra bunu her zaman yapar.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-123">Once the client has been updated to pass the CBT to the server, it always does so.</span></span> <span data-ttu-id="1e3fb-124">Sunucu da güncelleştirildiyse yok sayın veya CBT kullanmak üzere yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-124">If the server has also been updated, it can be configured to use the CBT or ignore it.</span></span> <span data-ttu-id="1e3fb-125">Bunu güncelleştirilmemiş varsa, onu yoksayar.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-125">If it has not been updated, it ignores it.</span></span>  
  
 <span data-ttu-id="1e3fb-126">Sunucunun aşağıdaki koruma düzeylerini sahip olabilir:</span><span class="sxs-lookup"><span data-stu-id="1e3fb-126">The server can have the following levels of protection:</span></span>  
  
-   <span data-ttu-id="1e3fb-127">Yok.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-127">None.</span></span> <span data-ttu-id="1e3fb-128">Bir kanal bağlama doğrulama yapılmaz.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-128">No channel binding validation is performed.</span></span> <span data-ttu-id="1e3fb-129">Güncellenmedi tüm sunucuların davranış budur.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-129">This is the behavior of all servers that have not been updated.</span></span>  
  
-   <span data-ttu-id="1e3fb-130">Kısmi.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-130">Partial.</span></span> <span data-ttu-id="1e3fb-131">Güncelleştirilen tüm istemcilerin sunucuya kanal bağlama bilgileri sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-131">All clients that have been updated must provide channel binding information to the server.</span></span> <span data-ttu-id="1e3fb-132">Güncellenmedi istemciler Bunu yapmak gerekmez.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-132">Clients that have not been updated do not have to do so.</span></span> <span data-ttu-id="1e3fb-133">Uygulama uyumluluğu için izin veren bir ara seçenek budur.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-133">This is an intermediate option that allows for application compatibility.</span></span>  
  
-   <span data-ttu-id="1e3fb-134">Tam.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-134">Full.</span></span> <span data-ttu-id="1e3fb-135">Tüm istemcilerin, kanal bağlama bilgileri sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-135">All clients must provide channel binding information.</span></span> <span data-ttu-id="1e3fb-136">Sunucunun bunu yapmayın istemcilerinden gelen kimlik doğrulama istekleri reddeder.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-136">The server rejects authentication requests from clients that do not do so.</span></span>  
  
 <span data-ttu-id="1e3fb-137">Daha fazla bilgi için Win7 CBT/genişletilmiş koruma örneğe bakın.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-137">For more information, see the Win7 CBT/Extended Protection sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3fb-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1e3fb-138">See Also</span></span>  
 [<span data-ttu-id="1e3fb-139">Windows Server App Fabric için güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="1e3fb-139">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)