---
title: "&lt;İssuedtokenparameters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7e96c41348dea40806c2aca331d7f8ca9499a78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="683d8-102">&lt;İssuedtokenparameters&gt;</span><span class="sxs-lookup"><span data-stu-id="683d8-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="683d8-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="683d8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="683d8-104">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="683d8-104">\<bindings></span></span>  
<span data-ttu-id="683d8-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="683d8-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="683d8-106">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="683d8-106">\<binding></span></span>  
<span data-ttu-id="683d8-107">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="683d8-107">\<security></span></span>  
<span data-ttu-id="683d8-108">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="683d8-108">\<message></span></span>  
<span data-ttu-id="683d8-109">\<İssuedtokenparameters ></span><span class="sxs-lookup"><span data-stu-id="683d8-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="683d8-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="683d8-110">Syntax</span></span>  
  
```xml  
<issuerMetadata address=String" >  
   <headers>  
      <add name="String"  
                 namespace="String" />  
   </headers>  
   <identity>  
           <certificate encodedValue="String"/>  
      <certificateReference findValue="String"   
         isChainIncluded="Boolean"  
         storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
         storeLocation="LocalMachine/CurrentUser"  
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuerMetadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="683d8-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="683d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="683d8-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="683d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="683d8-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="683d8-113">Attributes</span></span>  
  
|<span data-ttu-id="683d8-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="683d8-114">Attribute</span></span>|<span data-ttu-id="683d8-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="683d8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="683d8-116">adres</span><span class="sxs-lookup"><span data-stu-id="683d8-116">address</span></span>|<span data-ttu-id="683d8-117">Gerekli `string` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="683d8-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="683d8-118">Uç nokta adresini belirtir.</span><span class="sxs-lookup"><span data-stu-id="683d8-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="683d8-119">Adres bir mutlak URI olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="683d8-119">The address must be an absolute URI.</span></span> <span data-ttu-id="683d8-120">Varsayılan değer boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="683d8-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="683d8-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="683d8-121">Child Elements</span></span>  
  
|<span data-ttu-id="683d8-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="683d8-122">Element</span></span>|<span data-ttu-id="683d8-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="683d8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="683d8-124">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="683d8-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="683d8-125">Adres üstbilgileri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="683d8-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="683d8-126">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="683d8-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="683d8-127">Bir uç nokta onunla ileti değiş tokuşu diğer uç noktaları tarafından kimlik doğrulamasına olanak tanıyan bir kimlik.</span><span class="sxs-lookup"><span data-stu-id="683d8-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="683d8-128">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="683d8-128">Parent Elements</span></span>  
  
|<span data-ttu-id="683d8-129">Öğe</span><span class="sxs-lookup"><span data-stu-id="683d8-129">Element</span></span>|<span data-ttu-id="683d8-130">Açıklama</span><span class="sxs-lookup"><span data-stu-id="683d8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="683d8-131">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="683d8-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="683d8-132">İleti düzeyi güvenlik ayarlarını tanımlar [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="683d8-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="683d8-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="683d8-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="683d8-134">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="683d8-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="683d8-135">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="683d8-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="683d8-136">Özel bağlamalarla güvenlik özellikleri</span><span class="sxs-lookup"><span data-stu-id="683d8-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="683d8-137">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="683d8-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)