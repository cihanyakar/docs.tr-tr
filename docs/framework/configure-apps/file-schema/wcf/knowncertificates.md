---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: ed2bd5ec5b3a2a3e7b929b954df1c00be0849d71
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149765"
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="326ab-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="326ab-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="326ab-103">Bir güvenlik belirteci hizmeti (STS) öğesinden verilen güvenlik kimlik bilgilerinin doğrulanması için sağlanan X.509 Sertifika koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="326ab-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="326ab-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="326ab-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="326ab-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="326ab-105">\<behaviors></span></span>  
<span data-ttu-id="326ab-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="326ab-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="326ab-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="326ab-107">\<behavior></span></span>  
<span data-ttu-id="326ab-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="326ab-108">\<serviceCredentials></span></span>  
<span data-ttu-id="326ab-109">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="326ab-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="326ab-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="326ab-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326ab-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="326ab-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="326ab-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="326ab-112">Attributes and Elements</span></span>  
 <span data-ttu-id="326ab-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="326ab-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="326ab-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="326ab-114">Attributes</span></span>  
 <span data-ttu-id="326ab-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="326ab-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="326ab-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="326ab-116">Child Elements</span></span>  
  
|<span data-ttu-id="326ab-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="326ab-117">Element</span></span>|<span data-ttu-id="326ab-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="326ab-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="326ab-119">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="326ab-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="326ab-120">Koleksiyonuna bir X.509 sertifikası ekler.</span><span class="sxs-lookup"><span data-stu-id="326ab-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="326ab-121">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="326ab-121">Parent Elements</span></span>  
  
|<span data-ttu-id="326ab-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="326ab-122">Element</span></span>|<span data-ttu-id="326ab-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="326ab-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="326ab-124">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="326ab-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="326ab-125">Bir hizmet kimlik bilgisi olarak verilen bir belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="326ab-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="326ab-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="326ab-126">Remarks</span></span>  
 <span data-ttu-id="326ab-127">Verilen belirteç senaryo üç aşamadan oluşur.</span><span class="sxs-lookup"><span data-stu-id="326ab-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="326ab-128">Bir istemci bir hizmeti erişmeye ilk aşamada, başvurulan bir *güvenli belirteç hizmeti*.</span><span class="sxs-lookup"><span data-stu-id="326ab-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="326ab-129">Güvenli belirteç hizmeti daha sonra istemci kimliğini doğrular ve bundan sonra istemci genellikle bir güvenlik onaylama işaretleme dili (SAML) belirteci bir belirteç verir.</span><span class="sxs-lookup"><span data-stu-id="326ab-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="326ab-130">İstemci, ardından belirteci ile hizmetine döndürür.</span><span class="sxs-lookup"><span data-stu-id="326ab-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="326ab-131">Belirteç için belirteç ve bu nedenle istemci kimliğini doğrulamak hizmet veren bir veri hizmeti inceler.</span><span class="sxs-lookup"><span data-stu-id="326ab-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="326ab-132">Belirteç kimlik doğrulaması için sertifika hizmete güvenli belirteç hizmeti kullandığı olarak bilinmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="326ab-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="326ab-133">[ \<ServiceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) depo gibi herhangi bir güvenli belirteç hizmeti sertifika için bir öğedir.</span><span class="sxs-lookup"><span data-stu-id="326ab-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="326ab-134">Sertifikaları eklemek için [ \<knownCertificates > öğesi](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="326ab-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="326ab-135">INSERT bir [ \<Ekle >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) aşağıdaki örnekte gösterildiği gibi her sertifika için.</span><span class="sxs-lookup"><span data-stu-id="326ab-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="326ab-136">Varsayılan olarak, sertifikaları güvenli bir belirteci Hizmeti'nden alınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="326ab-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="326ab-137">Bu "sertifikalar, istemciler yalnızca yasal olun bilinen" bir hizmete erişebilir.</span><span class="sxs-lookup"><span data-stu-id="326ab-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="326ab-138">Bu yapılandırma öğesi kullanma hakkında daha fazla bilgi yanı sıra, bir Federasyon Hizmeti tarafından doğrulanması bir istemci için gereken koşulları gözden geçirmek için bkz: [nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="326ab-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="326ab-139">Federasyon senaryoları hakkında daha fazla bilgi için bkz. [Federasyon ve verilen belirteçler](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="326ab-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="326ab-140">Yapılandırma koleksiyonunda doldurmak nasıl gösteren bir örnek için bkz: [ \<Ekle >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="326ab-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326ab-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="326ab-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="326ab-142">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="326ab-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="326ab-143">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="326ab-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="326ab-144">Güvenlik Davranışları</span><span class="sxs-lookup"><span data-stu-id="326ab-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="326ab-145">Nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="326ab-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="326ab-146">Sertifikalarla Çalışma</span><span class="sxs-lookup"><span data-stu-id="326ab-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="326ab-147">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="326ab-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="326ab-148">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="326ab-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="326ab-149">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="326ab-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
