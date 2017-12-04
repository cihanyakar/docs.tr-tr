---
title: "&lt;eş&gt; &lt;sertifikası&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8bf8cb80201f2501fb60df7c9abb5039d688dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="32ab3-102">&lt;eş&gt; &lt;sertifikası&gt;</span><span class="sxs-lookup"><span data-stu-id="32ab3-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="32ab3-103">Bir eş tarafından kullanılan bir sertifika belirtir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="32ab3-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="32ab3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="32ab3-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="32ab3-105">\<behaviors></span></span>  
<span data-ttu-id="32ab3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="32ab3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="32ab3-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="32ab3-107">\<behavior></span></span>  
<span data-ttu-id="32ab3-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="32ab3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="32ab3-109">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="32ab3-109">\<peer></span></span>  
<span data-ttu-id="32ab3-110">\<Sertifika ></span><span class="sxs-lookup"><span data-stu-id="32ab3-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32ab3-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="32ab3-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32ab3-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="32ab3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="32ab3-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="32ab3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32ab3-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="32ab3-114">Attributes</span></span>  
  
|<span data-ttu-id="32ab3-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="32ab3-115">Attribute</span></span>|<span data-ttu-id="32ab3-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="32ab3-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="32ab3-117">X.509 sertifika deposunda arama için değer içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="32ab3-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="32ab3-118">Özniteliğinde bulunan türü belirtilen gereksinimleri karşılaması gerekir `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="32ab3-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="32ab3-119">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="32ab3-120">İstemcinin karşı eşin sertifikasını doğrulamak için kullandığı X.509 sertifika depolama konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="32ab3-121">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="32ab3-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="32ab3-122">-LocalMachine: Yerel Makine sertifika deposuna.</span><span class="sxs-lookup"><span data-stu-id="32ab3-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="32ab3-123">-Currentuser'a: sertifika deposuna geçerli kullanıcıya atanmış.</span><span class="sxs-lookup"><span data-stu-id="32ab3-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="32ab3-124">LocalMachine varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="32ab3-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="32ab3-125">Açmak için X.509 Sertifika deposu adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="32ab3-126">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="32ab3-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="32ab3-127">-Adres Defteri: Diğer kullanıcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="32ab3-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="32ab3-128">-AuthRoot: sertifika deposunu üçüncü taraf sertifika yetkilileri (CA'lar) için.</span><span class="sxs-lookup"><span data-stu-id="32ab3-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="32ab3-129">-CertificateAuthority: Ara sertifika yetkilileri (CA) sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="32ab3-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="32ab3-130">-İzin verilmeyen: mağaza iptal edilen sertifikaları için sertifika.</span><span class="sxs-lookup"><span data-stu-id="32ab3-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="32ab3-131">-My: Sertifika deposunda kişisel sertifikalar için.</span><span class="sxs-lookup"><span data-stu-id="32ab3-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="32ab3-132">-Kök: Güvenilen kök sertifika yetkilileri (CA'lar) sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="32ab3-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="32ab3-133">-TrustedPeople: Doğrudan-güvenilir kişiler ve kaynaklar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="32ab3-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="32ab3-134">-TrustedPublisher: Doğrudan-Güvenilen Yayımcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="32ab3-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="32ab3-135">Varsayılan değer My.</span><span class="sxs-lookup"><span data-stu-id="32ab3-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="32ab3-136">Yürütülecek X.509 arama türünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="32ab3-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="32ab3-137">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="32ab3-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="32ab3-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="32ab3-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="32ab3-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="32ab3-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="32ab3-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="32ab3-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="32ab3-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="32ab3-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="32ab3-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="32ab3-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="32ab3-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="32ab3-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="32ab3-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="32ab3-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="32ab3-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="32ab3-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="32ab3-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="32ab3-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="32ab3-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="32ab3-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="32ab3-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="32ab3-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="32ab3-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="32ab3-149">-   FindByExtension</span></span><br /><span data-ttu-id="32ab3-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="32ab3-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="32ab3-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="32ab3-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="32ab3-152">İçinde yer alan türü `findValue` özniteliği belirtilen gereksinimleri karşılaması gerekir `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="32ab3-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="32ab3-153">FindBySubjectDistinguishedName varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32ab3-154">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="32ab3-154">Child Elements</span></span>  
 <span data-ttu-id="32ab3-155">Yok.</span><span class="sxs-lookup"><span data-stu-id="32ab3-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32ab3-156">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="32ab3-156">Parent Elements</span></span>  
  
|<span data-ttu-id="32ab3-157">Öğe</span><span class="sxs-lookup"><span data-stu-id="32ab3-157">Element</span></span>|<span data-ttu-id="32ab3-158">Açıklama</span><span class="sxs-lookup"><span data-stu-id="32ab3-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32ab3-159">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="32ab3-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="32ab3-160">Eş düğüm için geçerli kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="32ab3-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32ab3-161">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="32ab3-161">Remarks</span></span>  
 <span data-ttu-id="32ab3-162">Bu yapılandırma öğesi içeren bir `X509Certificate2` eş kafes Komşuları doğrulanırken kullanılan örnek.</span><span class="sxs-lookup"><span data-stu-id="32ab3-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="32ab3-163">Eşler arası programlama hakkında daha fazla bilgi için bkz: [eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="32ab3-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ab3-164">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="32ab3-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="32ab3-165">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="32ab3-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="32ab3-166">Eşler arası ağ</span><span class="sxs-lookup"><span data-stu-id="32ab3-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="32ab3-167">Eş kanal ileti kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="32ab3-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="32ab3-168">Eş kanal özel kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="32ab3-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="32ab3-169">Eş kanalı uygulamalarını güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="32ab3-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="32ab3-170">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="32ab3-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)