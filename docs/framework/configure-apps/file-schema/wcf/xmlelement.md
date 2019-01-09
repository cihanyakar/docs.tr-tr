---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 6a197f7aa29645a08a581bcee103eb94c0e20179
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147024"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="72818-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="72818-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="72818-103">İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="72818-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="72818-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="72818-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="72818-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="72818-105">\<bindings></span></span>  
<span data-ttu-id="72818-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="72818-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="72818-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="72818-107">\<binding></span></span>  
<span data-ttu-id="72818-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="72818-108">\<security></span></span>  
<span data-ttu-id="72818-109">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="72818-109">\<message></span></span>  
<span data-ttu-id="72818-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="72818-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72818-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="72818-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72818-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="72818-112">Attributes and Elements</span></span>  
 <span data-ttu-id="72818-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="72818-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72818-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="72818-114">Attributes</span></span>  
  
|<span data-ttu-id="72818-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="72818-115">Attribute</span></span>|<span data-ttu-id="72818-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72818-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72818-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="72818-117">xmlElement</span></span>|<span data-ttu-id="72818-118">İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="72818-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72818-119">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="72818-119">Child Elements</span></span>  
 <span data-ttu-id="72818-120">Yok.</span><span class="sxs-lookup"><span data-stu-id="72818-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72818-121">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="72818-121">Parent Elements</span></span>  
  
|<span data-ttu-id="72818-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="72818-122">Element</span></span>|<span data-ttu-id="72818-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72818-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72818-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="72818-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="72818-125">Belirteç isteği parametreleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="72818-125">A collection of token request parameters.</span></span> <span data-ttu-id="72818-126">Her bir XML öğesi parametredir.</span><span class="sxs-lookup"><span data-stu-id="72818-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72818-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="72818-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="72818-128">Kimlik Doğrulama ile Hizmet Kimliği</span><span class="sxs-lookup"><span data-stu-id="72818-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="72818-129">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="72818-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="72818-130">Özel Bağlamalarla Güvenlik Özellikleri</span><span class="sxs-lookup"><span data-stu-id="72818-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="72818-131">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="72818-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="72818-132">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="72818-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
