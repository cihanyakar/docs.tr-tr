---
title: "Internet kimlik doğrulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f44bef7804e9101b2d1bc50ba53f3fc7a5fa90ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="internet-authentication"></a><span data-ttu-id="e4a42-102">Internet kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="e4a42-102">Internet Authentication</span></span>
<span data-ttu-id="e4a42-103"><xref:System.Net> Sınıflarını istemci kimlik doğrulaması mekanizmaları, temel standart Internet kimlik doğrulama yöntemleri de dahil olmak üzere çeşitli destek, Özet, NTLM, negotiate ve Kerberos kimlik doğrulaması, yanı sıra oluşturabileceğiniz özel yöntemler.</span><span class="sxs-lookup"><span data-stu-id="e4a42-103">The <xref:System.Net> classes support a variety of client authentication mechanisms, including the standard Internet authentication methods basic, digest, negotiate, NTLM, and Kerberos authentication, as well as custom methods that you can create.</span></span>  
  
 <span data-ttu-id="e4a42-104">İçinde depolanan kimlik doğrulama kimlik bilgileri <xref:System.Net.NetworkCredential> ve <xref:System.Net.CredentialCache> sınıfları, uygulayan <xref:System.Net.ICredentials> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e4a42-104">Authentication credentials are stored in the <xref:System.Net.NetworkCredential> and <xref:System.Net.CredentialCache> classes, which implement the <xref:System.Net.ICredentials> interface.</span></span> <span data-ttu-id="e4a42-105">Bu sınıfların biri için kimlik bilgileri sorgulandığında örneğini döndürür **NetworkCredential** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e4a42-105">When one of these classes is queried for credentials, it returns an instance of the **NetworkCredential** class.</span></span> <span data-ttu-id="e4a42-106">Kimlik doğrulama işlemi tarafından yönetilen <xref:System.Net.AuthenticationManager> sınıfı ve gerçek kimlik doğrulama işlemi uygulayan bir kimlik doğrulama modülü sınıfı tarafından gerçekleştirilen <xref:System.Net.IAuthenticationModule> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e4a42-106">The authentication process is managed by the <xref:System.Net.AuthenticationManager> class, and the actual authentication process is performed by an authentication module class that implements the <xref:System.Net.IAuthenticationModule> interface.</span></span> <span data-ttu-id="e4a42-107">Özel kimlik doğrulama modülü ile kaydetmeniz gerekir **bulunan** kullanılabilmesi için önce; modülleri temel, Özet için anlaşma, NTLM ve Kerberos kimlik doğrulama yöntemleri varsayılan olarak kayıtlı.</span><span class="sxs-lookup"><span data-stu-id="e4a42-107">You must register a custom authentication module with the **AuthenticationManager** before it can be used; modules for the basic, digest, negotiate, NTLM, and Kerberos authentication methods are registered by default.</span></span>  
  
 <span data-ttu-id="e4a42-108">**NetworkCredential** bir URI tarafından tanımlanan tek bir Internet kaynağına ile ilişkili kimlik bilgileri kümesi depolar ve bunları herhangi çağrısının yanıtı döndürür <xref:System.Net.NetworkCredential.GetCredential%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e4a42-108">**NetworkCredential** stores a set of credentials associated with a single Internet resource identified by a URI and returns them in response to any call to the <xref:System.Net.NetworkCredential.GetCredential%2A> method.</span></span> <span data-ttu-id="e4a42-109">**NetworkCredential** sınıf sınırlı sayıda Internet kaynaklarına erişen uygulamalar veya tüm durumlarda aynı kimlik bilgileri kümesi kullanan uygulamaları tarafından genellikle kullanılan.</span><span class="sxs-lookup"><span data-stu-id="e4a42-109">The **NetworkCredential** class is typically used by applications that access a limited number of Internet resources or by applications that use the same set of credentials in all cases.</span></span>  
  
 <span data-ttu-id="e4a42-110">**CredentialCache** sınıfı bir koleksiyon çeşitli Web kaynakları için kimlik bilgileri depolar.</span><span class="sxs-lookup"><span data-stu-id="e4a42-110">The **CredentialCache** class stores a collection of credentials for various Web resources.</span></span> <span data-ttu-id="e4a42-111">Zaman <xref:System.Net.CredentialCache.GetCredential%2A> yöntemi çağrıldığında, **CredentialCache** Web kaynağına ve istenen kimlik doğrulama şeması URI'si tarafından belirlenen kimlik bilgileri, uygun kümesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e4a42-111">When the <xref:System.Net.CredentialCache.GetCredential%2A> method is called, **CredentialCache** returns the proper set of credentials, as determined by the URI of the Web resource and the requested authentication scheme.</span></span> <span data-ttu-id="e4a42-112">Farklı kimlik doğrulama şemasını ile Internet kaynakların çeşitli kullanan uygulamalar yararlı kullanımından **CredentialCache** sınıfının tüm kimlik bilgilerini depolar ve istenen şekilde sağlar.</span><span class="sxs-lookup"><span data-stu-id="e4a42-112">Applications that use a variety of Internet resources with different authentication schemes benefit from using the **CredentialCache** class, since it stores all the credentials and provides them as requested.</span></span>  
  
 <span data-ttu-id="e4a42-113">Bir Internet kaynağına kimlik doğrulaması istediğinde <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> yöntemi gönderir <xref:System.Net.WebRequest> için **bulunan** istek için kimlik bilgileri ile birlikte.</span><span class="sxs-lookup"><span data-stu-id="e4a42-113">When an Internet resource requests authentication, the <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> method sends the <xref:System.Net.WebRequest> to the **AuthenticationManager** along with the request for credentials.</span></span> <span data-ttu-id="e4a42-114">İsteği daha sonra şu işlem göre kimlik doğrulaması:</span><span class="sxs-lookup"><span data-stu-id="e4a42-114">The request is then authenticated according to the following process:</span></span>  
  
1.  <span data-ttu-id="e4a42-115">**Bulunan** çağrıları <xref:System.Net.IAuthenticationModule.Authenticate%2A> her kayıtlı sırayla kayıtlı kimlik doğrulama modülleri yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e4a42-115">The **AuthenticationManager** calls the <xref:System.Net.IAuthenticationModule.Authenticate%2A> method on each of the registered authentication modules in the order they were registered.</span></span> <span data-ttu-id="e4a42-116">**Bulunan** döndürmez ilk modülünü kullanan **null** kimlik doğrulama işlemini gerçekleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="e4a42-116">The **AuthenticationManager** uses the first module that does not return **null** to carry out the authentication process.</span></span> <span data-ttu-id="e4a42-117">İşleminin ayrıntılarını dahil edilen kimlik doğrulama modülü türüne bağlı olarak farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="e4a42-117">The details of the process vary depending on the type of authentication module involved.</span></span>  
  
2.  <span data-ttu-id="e4a42-118">Kimlik doğrulama işlemi tamamlandığında, kimlik doğrulama modülü döndüren bir <xref:System.Net.Authorization> için **WebRequest** Internet kaynağa erişmek için gerekli bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="e4a42-118">When the authentication process is complete, the authentication module returns an <xref:System.Net.Authorization> to the **WebRequest** that contains the information needed to access the Internet resource.</span></span>  
  
 <span data-ttu-id="e4a42-119">Bazı kimlik doğrulama şemasını bir kullanıcı, bir kaynak için bir istek yapmadan doğrulayabilir.</span><span class="sxs-lookup"><span data-stu-id="e4a42-119">Some authentication schemes can authenticate a user without first making a request for a resource.</span></span> <span data-ttu-id="e4a42-120">Bir uygulama, böylece en az bir gidiş dönüş sunucuya ortadan kaldırılır kullanıcıyla kaynak preauthenticating tarafından zamandan tasarruf edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4a42-120">An application can save time by preauthenticating the user with the resource, thus eliminating at least one round trip to the server.</span></span> <span data-ttu-id="e4a42-121">Ya da daha sonra kullanıcıya daha iyi yanıt olması için program başlatma sırasında kimlik doğrulaması gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="e4a42-121">Or, it can perform authentication during program startup in order to be more responsive to the user later.</span></span> <span data-ttu-id="e4a42-122">Ön kimlik doğrulaması kümesi kullanan kimlik doğrulama şemasını <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> özelliğine **doğru**.</span><span class="sxs-lookup"><span data-stu-id="e4a42-122">Authentication schemes that can use preauthentication set the <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> property to **true**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a42-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e4a42-123">See Also</span></span>  
 [<span data-ttu-id="e4a42-124">Temel ve Özet kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="e4a42-124">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="e4a42-125">NTLM ve Kerberos kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="e4a42-125">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="e4a42-126">Güvenlik ağ programlama</span><span class="sxs-lookup"><span data-stu-id="e4a42-126">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)