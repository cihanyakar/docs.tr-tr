---
title: "&lt;issuerChannelBehaviors&gt; Öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73d090aa47e18792d313b3d086e7a667e74bb08
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="dade6-102">&lt;issuerChannelBehaviors&gt; Öğesi</span><span class="sxs-lookup"><span data-stu-id="dade6-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="dade6-103">Bir koleksiyonu içerir [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (yapılandırmasında tanımlanmış) istemci uç nokta davranışları belirtilen hizmet belirteci Hizmetleri ile iletişim kurarken kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="dade6-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="dade6-104">Tanımlı davranışları herhangi içeremez [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) öğeleri.</span><span class="sxs-lookup"><span data-stu-id="dade6-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="dade6-105">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dade6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="dade6-106">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="dade6-106">\<behaviors></span></span>  
<span data-ttu-id="dade6-107">endpointBehaviors bölümü</span><span class="sxs-lookup"><span data-stu-id="dade6-107">endpointBehaviors section</span></span>  
<span data-ttu-id="dade6-108">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="dade6-108">\<behavior></span></span>  
<span data-ttu-id="dade6-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="dade6-109">\<clientCredentials></span></span>  
<span data-ttu-id="dade6-110">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="dade6-110">\<issuedToken></span></span>  
<span data-ttu-id="dade6-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dade6-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dade6-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dade6-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dade6-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="dade6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dade6-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="dade6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dade6-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="dade6-115">Attributes</span></span>  
 <span data-ttu-id="dade6-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="dade6-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dade6-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="dade6-117">Child Elements</span></span>  
  
|<span data-ttu-id="dade6-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="dade6-118">Element</span></span>|<span data-ttu-id="dade6-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dade6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dade6-120">\<ekleme ></span><span class="sxs-lookup"><span data-stu-id="dade6-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="dade6-121">Bir davranış koleksiyona ekler.</span><span class="sxs-lookup"><span data-stu-id="dade6-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dade6-122">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="dade6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dade6-123">Öğe</span><span class="sxs-lookup"><span data-stu-id="dade6-123">Element</span></span>|<span data-ttu-id="dade6-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dade6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dade6-125">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="dade6-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="dade6-126">Bir hizmet için bir istemci kimlik doğrulaması için kullanılan özel bir belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="dade6-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dade6-127">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dade6-127">Remarks</span></span>  
 <span data-ttu-id="dade6-128">Herhangi bir zaman bu öğeyi kullanın davranışları (dahil davranışları dışında `<clientCredentials>` öğeleri) hizmet ile iletişim kurmak için kullanılan gerekir.</span><span class="sxs-lookup"><span data-stu-id="dade6-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="dade6-129">Örneğin, bir [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) davranışı öğesi dahil edilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="dade6-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dade6-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dade6-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="dade6-131">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="dade6-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="dade6-132">Güvenlik davranışları</span><span class="sxs-lookup"><span data-stu-id="dade6-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="dade6-133">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="dade6-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="dade6-134">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="dade6-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="dade6-135">İstemcilerinin güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="dade6-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="dade6-136">Nasıl yapılır: federe istemci oluşturma</span><span class="sxs-lookup"><span data-stu-id="dade6-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="dade6-137">Nasıl yapılır: yerel yayımlayan yapılandırma</span><span class="sxs-lookup"><span data-stu-id="dade6-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="dade6-138">Federasyon ve verilen belirteçler</span><span class="sxs-lookup"><span data-stu-id="dade6-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)