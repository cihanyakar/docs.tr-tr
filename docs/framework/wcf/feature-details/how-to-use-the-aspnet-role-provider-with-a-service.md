---
title: "Nasıl yapılır: ASP.NET Rol Sağlayıcısını Bir Hizmetle Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb5adec17f834687038b729a475fbcc0e2311c01
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="0b8ae-102">Nasıl yapılır: ASP.NET Rol Sağlayıcısını Bir Hizmetle Kullanma</span><span class="sxs-lookup"><span data-stu-id="0b8ae-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="0b8ae-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Rol sağlayıcısı (birlikte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] üyelik sağlayıcısı) sağlayan bir özelliktir [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] bir hesabı olan bir site oluşturmak için ve yetkilendirme için rolleri atanan kullanıcıların Web siteleri oluşturmak için geliştiriciler amaçlar.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="0b8ae-104">Bu özellik, herhangi bir kullanıcı sitesi olan bir hesap oluşturun ve site ve hizmetlerini özel erişim için oturum açın.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="0b8ae-105">Kullanıcıların bir Windows etki alanında hesaplarına sahip olmasını gerektiren Windows güvenliği aksine budur.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="0b8ae-106">Bunun yerine, kendi kimlik bilgilerini (kullanıcı adı/parola birleşimini) sağlayan herhangi bir kullanıcı site ve hizmetlerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="0b8ae-107">Örnek bir uygulama için bkz: [üyelik ve rol sağlayıcısı](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0b8ae-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0b8ae-108">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] üyelik sağlayıcısı özelliği, bkz: [nasıl yapılır: ASP.NET üyelik sağlayıcıyı kullanacak](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0b8ae-108"> the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="0b8ae-109">Rol sağlayıcı özelliği, kullanıcı bilgilerini depolamak için bir SQL Server veritabanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-109">The role provider feature uses a SQL Server database to store user information.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="0b8ae-110">Geliştiriciler güvenlik amacıyla bu özelliklerden yararlanabilir.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-110"> developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="0b8ae-111">Tümleşik olduğunda bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulama, kullanıcıların gerekir sağlamak için bir kullanıcı adı/parola birleşimini [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] istemci uygulaması.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-111">When integrated into a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="0b8ae-112">Etkinleştirmek için [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] veritabanını kullanmak için bir örneğini oluşturun <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> sınıfı, Ayarla kendi <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> özelliğine <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>ve örnek olarak koleksiyonuna ekleyin <xref:System.ServiceModel.ServiceHost> hizmet barındırma.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-112">To enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="0b8ae-113">Rol sağlayıcısı yapılandırmak için</span><span class="sxs-lookup"><span data-stu-id="0b8ae-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="0b8ae-114">Web.config dosyasında altında <`system.web`> öğesi ekleme bir <`roleManager`> öğesi ve kümesi kendi `enabled` özniteliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="0b8ae-115">Ayarlama `defaultProvider` özniteliğini `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="0b8ae-116">Alt öğesi olarak <`roleManager`> öğesi ekleme bir <`providers`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="0b8ae-117">Alt öğesi olarak <`providers`> öğesi ekleme bir <`add`> öğesi aşağıdaki özniteliklerle uygun değerlere ayarlayın: `name`, `type`, `connectionStringName`, ve `applicationName`, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="0b8ae-118">Hizmetini rol sağlayıcıyı kullanacak şekilde yapılandırmak için</span><span class="sxs-lookup"><span data-stu-id="0b8ae-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="0b8ae-119">Web.config dosyasına ekleyerek bir [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="0b8ae-120">Ekleme bir [ \<davranışları >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) öğesine <`system.ServiceModel`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="0b8ae-121">Ekleme bir [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) için <`behaviors`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="0b8ae-122">Ekleme bir [ \<davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) öğesi ve kümesi `name` öznitelik için uygun bir değer.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="0b8ae-123">Ekleme bir [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) için <`behavior`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="0b8ae-124">Ayarlama `principalPermissionMode` özniteliğini `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="0b8ae-125">Ayarlama `roleProviderName` özniteliğini `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="0b8ae-126">Aşağıdaki örnek, bir parça yapılandırmasının gösterir.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0b8ae-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0b8ae-127">See Also</span></span>  
 [<span data-ttu-id="0b8ae-128">Üyelik ve rol sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="0b8ae-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="0b8ae-129">Nasıl yapılır: ASP.NET üyelik sağlayıcısı kullanın</span><span class="sxs-lookup"><span data-stu-id="0b8ae-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)