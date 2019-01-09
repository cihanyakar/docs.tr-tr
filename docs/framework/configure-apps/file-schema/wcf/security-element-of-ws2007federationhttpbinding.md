---
title: '&lt;ws2007FederationHttpBinding&gt; &lt;güvenlik&gt; öğesi'
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 4ddf963db10656c905220ca22606772625dd7f3c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145724"
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="fd4ee-102">&lt;ws2007FederationHttpBinding&gt; &lt;güvenlik&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="fd4ee-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="fd4ee-103">Güvenlik ayarlarını tanımlar [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="fd4ee-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd4ee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd4ee-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-105">\<bindings></span></span>  
<span data-ttu-id="fd4ee-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="fd4ee-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-107">\<binding></span></span>  
<span data-ttu-id="fd4ee-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd4ee-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fd4ee-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd4ee-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="fd4ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd4ee-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd4ee-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="fd4ee-112">Attributes</span></span>  
  
|<span data-ttu-id="fd4ee-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="fd4ee-113">Attribute</span></span>|<span data-ttu-id="fd4ee-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fd4ee-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="fd4ee-115">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-115">Optional.</span></span> <span data-ttu-id="fd4ee-116">Uygulanan güvenlik türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="fd4ee-117">Varsayılan değer `Message` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-117">The default value is `Message`.</span></span> <span data-ttu-id="fd4ee-118">Bu öznitelik türünde <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fd4ee-119">mod özniteliği</span><span class="sxs-lookup"><span data-stu-id="fd4ee-119">mode Attribute</span></span>  
  
|<span data-ttu-id="fd4ee-120">Değer</span><span class="sxs-lookup"><span data-stu-id="fd4ee-120">Value</span></span>|<span data-ttu-id="fd4ee-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fd4ee-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd4ee-122">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="fd4ee-122">None</span></span>|<span data-ttu-id="fd4ee-123">SOAP ileti aktarım sırasında güvenli değildir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="fd4ee-124">İleti</span><span class="sxs-lookup"><span data-stu-id="fd4ee-124">Message</span></span>|<span data-ttu-id="fd4ee-125">SOAP ileti güveliği kullanarak bütünlüğü, gizlilik, sunucu kimlik doğrulaması ve istemci kimlik doğrulaması sağlanır.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="fd4ee-126">Varsayılan olarak, gövde imzalı ve şifrelenir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="fd4ee-127">Hizmeti bir sertifikayla yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="fd4ee-128">İstemci kimlik doğrulaması güvenlik belirteci hizmeti tarafından istemciye verilen belirtecin temel alır.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="fd4ee-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fd4ee-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="fd4ee-130">Bütünlüğü, gizliliği ve sunucu kimlik doğrulaması HTTPS tarafından sağlanır.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="fd4ee-131">Hizmeti bir sertifikayla yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="fd4ee-132">İstemci kimlik doğrulaması yoluyla SOAP ileti güvenliği sağlanır ve istemciye bir güvenlik belirteci hizmeti tarafından verilen belirtecin dayanır.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd4ee-133">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="fd4ee-133">Child Elements</span></span>  
  
|<span data-ttu-id="fd4ee-134">Öğe</span><span class="sxs-lookup"><span data-stu-id="fd4ee-134">Element</span></span>|<span data-ttu-id="fd4ee-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fd4ee-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd4ee-136">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="fd4ee-137">İleti düzeyi güvenlik ayarları tanımlar.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="fd4ee-138">Bu öğe türünde <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd4ee-139">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="fd4ee-139">Parent Elements</span></span>  
  
|<span data-ttu-id="fd4ee-140">Öğe</span><span class="sxs-lookup"><span data-stu-id="fd4ee-140">Element</span></span>|<span data-ttu-id="fd4ee-141">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fd4ee-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd4ee-142">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fd4ee-143">Tüm bağlama yeteneklerini tanımlar [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fd4ee-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd4ee-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="fd4ee-145">Nasıl yapılır: WSFederationHttpBinding oluşturma</span><span class="sxs-lookup"><span data-stu-id="fd4ee-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="fd4ee-146">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="fd4ee-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fd4ee-147">Kimlik Bilgisi Türü Seçme</span><span class="sxs-lookup"><span data-stu-id="fd4ee-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fd4ee-148">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="fd4ee-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fd4ee-149">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fd4ee-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fd4ee-150">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="fd4ee-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="fd4ee-151">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="fd4ee-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
