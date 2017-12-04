---
title: "&lt;scopedCertificates&gt; Öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cb1d536d25186dd2d75cec962143b16cdd45260
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltscopedcertificatesgt-element"></a><span data-ttu-id="0f396-102">&lt;scopedCertificates&gt; Öğesi</span><span class="sxs-lookup"><span data-stu-id="0f396-102">&lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="0f396-103">X.509 sertifikaları (kimlik doğrulaması için kapsamlı) belirli hizmetleri tarafından sağlanan bir koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="0f396-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="0f396-104">Bu koleksiyon, genellikle bir Federasyon senaryosunda için güvenlik belirteci Hizmetleri hizmet sertifikalarını belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0f396-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="0f396-105">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0f396-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f396-106">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="0f396-106">\<behaviors></span></span>  
<span data-ttu-id="0f396-107">endpointBehaviors bölümü</span><span class="sxs-lookup"><span data-stu-id="0f396-107">endpointBehaviors section</span></span>  
<span data-ttu-id="0f396-108">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="0f396-108">\<behavior></span></span>  
<span data-ttu-id="0f396-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0f396-109">\<clientCredentials></span></span>  
<span data-ttu-id="0f396-110">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0f396-110">\<serviceCertificate></span></span>  
<span data-ttu-id="0f396-111">\<scopedCertificates > öğesi</span><span class="sxs-lookup"><span data-stu-id="0f396-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="0f396-112">\<Ekle > öğesi için \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="0f396-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f396-113">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0f396-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f396-114">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0f396-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0f396-115">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0f396-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f396-116">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0f396-116">Attributes</span></span>  
 <span data-ttu-id="0f396-117">Yok.</span><span class="sxs-lookup"><span data-stu-id="0f396-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f396-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0f396-118">Child Elements</span></span>  
  
|<span data-ttu-id="0f396-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="0f396-119">Element</span></span>|<span data-ttu-id="0f396-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0f396-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f396-121">\<ekleme ></span><span class="sxs-lookup"><span data-stu-id="0f396-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="0f396-122">Bir X.509 sertifikası kapsamlı sertifikaları koleksiyonuna ekler.</span><span class="sxs-lookup"><span data-stu-id="0f396-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f396-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0f396-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0f396-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="0f396-124">Element</span></span>|<span data-ttu-id="0f396-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0f396-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f396-126">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0f396-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0f396-127">İstemci bir hizmete kimlik doğrulanırken kullanılacak bir sertifika belirtir.</span><span class="sxs-lookup"><span data-stu-id="0f396-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f396-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0f396-128">Remarks</span></span>  
 <span data-ttu-id="0f396-129">Bu koleksiyon kurduğu hizmetinin URL'sini göre kullanmak için hizmet sertifikalarını yapılandırmak istemci sağlar.</span><span class="sxs-lookup"><span data-stu-id="0f396-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="0f396-130">Bu, özellikle bir istemci birden fazla hizmet için (son hizmet yanı sıra Ara güvenlik belirteci Hizmetleri) burada iletişim verilen belirteç senaryolarda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="0f396-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="0f396-131">Bu sertifika, sertifika tabanlı ileti güvenliği kullanan bağlamaları için hizmet iletileri şifrelemek için kullanılan ve istemci yanıtlar imzalama hizmeti tarafından kullanılacak beklenen.</span><span class="sxs-lookup"><span data-stu-id="0f396-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="0f396-132">Bir bağlama hizmeti ve URL ScopedCertificates bulunan hizmet için belirli bir sertifika için bir sertifika gerektiriyorsa, varsayılan sertifika kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0f396-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="0f396-133">Daha fazla bilgi için "Sertifikalar kapsamlı" bölümüne bakın [nasıl yapılır: federe istemci oluşturma](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="0f396-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f396-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="0f396-134">Example</span></span>  
 <span data-ttu-id="0f396-135">Aşağıdaki örnek istemcinin etki alanı adı HTTP protokolü üzerinden http://www.contoso.com olan uç noktaları ile iletişim kurarken kullanması bir hizmet sertifikası belirtir.</span><span class="sxs-lookup"><span data-stu-id="0f396-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is http://www.contoso.com over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f396-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0f396-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="0f396-137">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="0f396-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="0f396-138">Nasıl yapılır: federe istemci oluşturma</span><span class="sxs-lookup"><span data-stu-id="0f396-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="0f396-139">\<ekleme ></span><span class="sxs-lookup"><span data-stu-id="0f396-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [<span data-ttu-id="0f396-140">İstemcilerinin güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="0f396-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0f396-141">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="0f396-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)