---
title: '&lt;ServiceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b9e32509a5e182301455eaf0e602a03c51fbc23a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150779"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="865a6-102">&lt;ServiceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="865a6-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="865a6-103">Hizmet ve istemci kimlik doğrulama ile ilgili ayarlarda kullanılan kimlik bilgisini belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="865a6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="865a6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="865a6-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="865a6-105">\<behaviors></span></span>  
<span data-ttu-id="865a6-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="865a6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="865a6-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="865a6-107">\<behavior></span></span>  
<span data-ttu-id="865a6-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="865a6-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865a6-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="865a6-109">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="865a6-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="865a6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="865a6-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="865a6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="865a6-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="865a6-112">Attributes</span></span>  
  
|<span data-ttu-id="865a6-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="865a6-113">Attribute</span></span>|<span data-ttu-id="865a6-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="865a6-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="865a6-115">Bu yapılandırma öğesi türünü belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="865a6-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="865a6-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="865a6-116">Child Elements</span></span>  
  
|<span data-ttu-id="865a6-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="865a6-117">Element</span></span>|<span data-ttu-id="865a6-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="865a6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="865a6-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="865a6-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="865a6-120">İstemci sertifikası yok-bant olduğunda kullanılacak sertifikayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="865a6-121">Bu öğe ayrıca istemci sertifika doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="865a6-122">Bu öğe türünde <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="865a6-123">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="865a6-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="865a6-124">Bu hizmet için geçerli verilen belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="865a6-125">Bu öğe türünde <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="865a6-126">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="865a6-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="865a6-127">Bir eşdüzey düğüm için geçerli kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="865a6-128">Bu öğe türünde <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="865a6-129">\<Servicecredential ></span><span class="sxs-lookup"><span data-stu-id="865a6-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="865a6-130">Geçerli bir güvenli konuşma kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="865a6-131">Bu öğe türünde <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="865a6-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="865a6-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="865a6-133">Kendisini tanımlamak için bir hizmet tarafından kullanılan sertifikayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="865a6-134">Bu öğe türünde <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="865a6-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="865a6-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="865a6-136">Kullanıcı adı parola doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="865a6-137">Bu öğe türünde <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="865a6-138">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="865a6-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="865a6-139">Windows kimlik doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="865a6-140">Bu öğe türünde <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="865a6-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="865a6-141">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="865a6-141">Parent Elements</span></span>  
  
|<span data-ttu-id="865a6-142">Öğe</span><span class="sxs-lookup"><span data-stu-id="865a6-142">Element</span></span>|<span data-ttu-id="865a6-143">Açıklama</span><span class="sxs-lookup"><span data-stu-id="865a6-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="865a6-144">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="865a6-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="865a6-145">Bir davranış öğesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="865a6-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="865a6-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="865a6-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="865a6-147">Güvenlik Davranışları</span><span class="sxs-lookup"><span data-stu-id="865a6-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
