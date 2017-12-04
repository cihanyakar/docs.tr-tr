---
title: "&lt;netNamedPipeBinding&gt; &lt;taşıma&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15489d2f5447fc2d3d4fb5173bcc94b5fb68e1c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="dd01b-102">&lt;netNamedPipeBinding&gt; &lt;taşıma&gt;</span><span class="sxs-lookup"><span data-stu-id="dd01b-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="dd01b-103">Bir adlandırılmış kanal taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd01b-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="dd01b-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dd01b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd01b-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="dd01b-105">\<bindings></span></span>  
<span data-ttu-id="dd01b-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="dd01b-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="dd01b-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="dd01b-107">\<binding></span></span>  
<span data-ttu-id="dd01b-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="dd01b-108">\<security></span></span>  
<span data-ttu-id="dd01b-109">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="dd01b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd01b-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dd01b-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd01b-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="dd01b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dd01b-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="dd01b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd01b-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="dd01b-113">Attributes</span></span>  
  
|<span data-ttu-id="dd01b-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="dd01b-114">Attribute</span></span>|<span data-ttu-id="dd01b-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dd01b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd01b-116">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="dd01b-116">protectionLevel</span></span>|<span data-ttu-id="dd01b-117">Adlandırılmış kanal koruma düzeyini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd01b-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="dd01b-118">İletileri imzalama bir üçüncü taraf onu aktarılırken iletiyle oynama riskini azaltır.</span><span class="sxs-lookup"><span data-stu-id="dd01b-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="dd01b-119">Şifreleme, aktarım sırasında veri düzeyi gizliliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd01b-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="dd01b-120">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="dd01b-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dd01b-121">-Hiçbiri: Koruma yok.</span><span class="sxs-lookup"><span data-stu-id="dd01b-121">-   None: No protection.</span></span><br /><span data-ttu-id="dd01b-122">-Oturum: İletileri imzalanmıştır.</span><span class="sxs-lookup"><span data-stu-id="dd01b-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="dd01b-123">-Da EncryptAndSign: İletileri şifrelenmiş ve imzalanmış.</span><span class="sxs-lookup"><span data-stu-id="dd01b-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="dd01b-124">Da EncryptAndSign varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="dd01b-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd01b-125">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="dd01b-125">Child Elements</span></span>  
 <span data-ttu-id="dd01b-126">Yok.</span><span class="sxs-lookup"><span data-stu-id="dd01b-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd01b-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="dd01b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dd01b-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="dd01b-128">Element</span></span>|<span data-ttu-id="dd01b-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dd01b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd01b-130">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="dd01b-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="dd01b-131">Bağlama için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd01b-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd01b-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dd01b-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="dd01b-133">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="dd01b-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="dd01b-134">Bağlamaları</span><span class="sxs-lookup"><span data-stu-id="dd01b-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="dd01b-135">Sistem tarafından sağlanan bağlamaları yapılandırma</span><span class="sxs-lookup"><span data-stu-id="dd01b-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="dd01b-136">Windows Communication Foundation Hizmetleri ve istemcileri yapılandırmak için bağlamaları kullanma</span><span class="sxs-lookup"><span data-stu-id="dd01b-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="dd01b-137">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="dd01b-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)