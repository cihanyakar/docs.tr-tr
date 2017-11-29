---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 428dbdc65a4f66e5632e4ded7d7ded0d10b7c9d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="d1270-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="d1270-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="d1270-103">Eş sertifikanın bir ileti gönderen tarafından kullanılan kimlik doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1270-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="d1270-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d1270-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1270-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="d1270-105">\<behaviors></span></span>  
<span data-ttu-id="d1270-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d1270-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d1270-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="d1270-107">\<behavior></span></span>  
<span data-ttu-id="d1270-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d1270-108">\<serviceCredentials></span></span>  
<span data-ttu-id="d1270-109">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="d1270-109">\<peer></span></span>  
<span data-ttu-id="d1270-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d1270-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1270-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d1270-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1270-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="d1270-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1270-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="d1270-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1270-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="d1270-114">Attributes</span></span>  
  
|<span data-ttu-id="d1270-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="d1270-115">Attribute</span></span>|<span data-ttu-id="d1270-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d1270-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="d1270-117">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="d1270-117">Optional enumeration.</span></span> <span data-ttu-id="d1270-118">Kimlik bilgilerini doğrulamak için kullanılan beş modlarından birini belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1270-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="d1270-119">Bu öznitelik türünde <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="d1270-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="d1270-120">Varsa kümesine `Custom`, sonra bir `customCertificateValidator` de sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d1270-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="d1270-121">İsteğe bağlı dize.</span><span class="sxs-lookup"><span data-stu-id="d1270-121">Optional string.</span></span> <span data-ttu-id="d1270-122">Bir türü ve bir özel tür doğrulamak için kullanılan derleme belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1270-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="d1270-123">Bu öznitelik ne zaman ayarlanmalıdır `certificateValidationMode` ayarlanır `Custom`.</span><span class="sxs-lookup"><span data-stu-id="d1270-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="d1270-124">Bu öznitelik türünde <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="d1270-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="d1270-125">Varsayılan eş eş sertifikayı güvenilir kişiler deposunda karşı doğrular sertifika Doğrulayıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="d1270-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="d1270-126">Sertifika geçerli bir kök zincir olduğunu doğrular.</span><span class="sxs-lookup"><span data-stu-id="d1270-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="d1270-127">Farklı bir davranışı belirtmek ve bu öznitelik için özel Doğrulayıcı işaret edecek şekilde kullanmak için özel bir doğrulayıcı uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d1270-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="d1270-128">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="d1270-128">Optional enumeration.</span></span> <span data-ttu-id="d1270-129">Sertifika iptal modunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1270-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="d1270-130">Bu öznitelik türünde <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="d1270-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="d1270-131">Sistem eş sertifika tarafından iptal edildi olduğunu doğrular iptal edilen sertifika listesinde bakan.</span><span class="sxs-lookup"><span data-stu-id="d1270-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="d1270-132">Bu onay çevrimiçi denetleyerek ya da bir önbelleğe alınan iptal listesi karşı gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="d1270-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="d1270-133">İptal denetimi NoCheck için bu öznitelik ayarlayarak kapatılabilir.</span><span class="sxs-lookup"><span data-stu-id="d1270-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="d1270-134">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="d1270-134">Optional enumeration.</span></span> <span data-ttu-id="d1270-135">Burada eş sertifika doğrulanmış tarafından güvenilen depolama konumu belirtir [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] güvenlik sistemi.</span><span class="sxs-lookup"><span data-stu-id="d1270-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="d1270-136">Bu öznitelik türünde <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="d1270-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1270-137">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="d1270-137">Child Elements</span></span>  
 <span data-ttu-id="d1270-138">Yok.</span><span class="sxs-lookup"><span data-stu-id="d1270-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1270-139">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="d1270-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d1270-140">Öğe</span><span class="sxs-lookup"><span data-stu-id="d1270-140">Element</span></span>|<span data-ttu-id="d1270-141">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d1270-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1270-142">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="d1270-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="d1270-143">Eş düğüm için geçerli kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1270-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1270-144">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d1270-144">Remarks</span></span>  
 <span data-ttu-id="d1270-145">Bu öğe, ileti kimlik doğrulaması seçilirse yapılandırılmış olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d1270-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="d1270-146">Çıktı kanallar için her ileti tarafından sağlanan sertifika kullanılarak imzalanmıştır [ \<sertifika >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="d1270-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="d1270-147">Tüm iletiler, uygulamaya teslim önce tarafından belirtilen Doğrulayıcı kullanarak ileti kimlik bilgileri karşı denetlenir `customCertificateValidatorType` bu öğesinin özniteliği.</span><span class="sxs-lookup"><span data-stu-id="d1270-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="d1270-148">Doğrulayıcı kabul edin veya kimlik bilgisi reddedin.</span><span class="sxs-lookup"><span data-stu-id="d1270-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1270-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d1270-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="d1270-150">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="d1270-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d1270-151">Eşler arası ağ</span><span class="sxs-lookup"><span data-stu-id="d1270-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="d1270-152">Eş kanal ileti kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="d1270-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="d1270-153">Eş kanal özel kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="d1270-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="d1270-154">Eş kanalı uygulamalarını güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="d1270-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)