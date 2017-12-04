---
title: "&lt;issuedTokenParameters&gt; &lt;yayınlayan&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82e73a571ce7179518d380c0c63c9161b2ad5c55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="b420f-102">&lt;issuedTokenParameters&gt; &lt;yayınlayan&gt;</span><span class="sxs-lookup"><span data-stu-id="b420f-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="b420f-103">Güvenlik belirteci hizmeti (güvenlik belirteçleri veren STS) belirtir.</span><span class="sxs-lookup"><span data-stu-id="b420f-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="b420f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b420f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b420f-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="b420f-105">\<bindings></span></span>  
<span data-ttu-id="b420f-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b420f-106">\<customBinding></span></span>  
<span data-ttu-id="b420f-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="b420f-107">\<binding></span></span>  
<span data-ttu-id="b420f-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="b420f-108">\<security></span></span>  
<span data-ttu-id="b420f-109">\<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="b420f-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="b420f-110">\<veren ></span><span class="sxs-lookup"><span data-stu-id="b420f-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b420f-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b420f-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b420f-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b420f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b420f-113">Öznitelikler, alt öğelerini ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="b420f-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b420f-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b420f-114">Attributes</span></span>  
  
|<span data-ttu-id="b420f-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="b420f-115">Attribute</span></span>|<span data-ttu-id="b420f-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b420f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b420f-117">adres</span><span class="sxs-lookup"><span data-stu-id="b420f-117">address</span></span>|<span data-ttu-id="b420f-118">Gerekli dize.</span><span class="sxs-lookup"><span data-stu-id="b420f-118">Required string.</span></span> <span data-ttu-id="b420f-119">STS URL'si.</span><span class="sxs-lookup"><span data-stu-id="b420f-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b420f-120">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b420f-120">Child Elements</span></span>  
  
|<span data-ttu-id="b420f-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="b420f-121">Element</span></span>|<span data-ttu-id="b420f-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b420f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b420f-123">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="b420f-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="b420f-124">Adres üstbilgileri Oluşturucu oluşturabilirsiniz uç noktaları koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="b420f-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="b420f-125">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="b420f-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b420f-126">Verilen bir belirteç kullanırken, sunucu kimlik doğrulaması istemci etkinleştirme ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="b420f-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b420f-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b420f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b420f-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="b420f-128">Element</span></span>|<span data-ttu-id="b420f-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b420f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b420f-130">\<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="b420f-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="b420f-131">Geçerli verilen belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="b420f-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b420f-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b420f-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="b420f-133">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="b420f-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b420f-134">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="b420f-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b420f-135">Özel bağlamalarla güvenlik özellikleri</span><span class="sxs-lookup"><span data-stu-id="b420f-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="b420f-136">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="b420f-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b420f-137">Bağlamaları</span><span class="sxs-lookup"><span data-stu-id="b420f-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b420f-138">Bağlamaları genişletme</span><span class="sxs-lookup"><span data-stu-id="b420f-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b420f-139">Özel bağlamalar</span><span class="sxs-lookup"><span data-stu-id="b420f-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b420f-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b420f-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="b420f-141">Nasıl yapılır: SecurityBindingElement kullanarak özel bağlama oluşturma</span><span class="sxs-lookup"><span data-stu-id="b420f-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="b420f-142">Özel bağlama güvenliği</span><span class="sxs-lookup"><span data-stu-id="b420f-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)