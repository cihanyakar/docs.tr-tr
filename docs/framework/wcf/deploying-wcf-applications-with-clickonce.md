---
title: "ClickOnce ile WCF Uygulamaları Dağıtma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714e8341c58e5337d8e45bf61b48137d33fa51b9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="07b3d-102">ClickOnce ile WCF Uygulamaları Dağıtma</span><span class="sxs-lookup"><span data-stu-id="07b3d-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="07b3d-103">Kullanan istemci uygulamalar [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ClickOnce teknolojisini kullanarak dağıtılmış.</span><span class="sxs-lookup"><span data-stu-id="07b3d-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="07b3d-104">Bu teknoloji güvenilir bir sertifika ile dijital olarak imzalanmış olması koşuluyla çalışma zamanı kod erişim güvenliği tarafından sağlanan güvenlik korumaları yararlanmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="07b3d-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="07b3d-105">ClickOnce uygulamayı imzalamak için kullanılan sertifikanın güvenilir yayımcı depoda bulunmalıdır ve istemci makinesinde yerel güvenlik ilkesi publisher'ın sertifikayla imzalanan uygulamaların tam güven izinleri vermek için yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="07b3d-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="07b3d-106">ClickOnce uygulamaları ve güvenilen yayımcılar yapılandırma hakkında daha fazla bilgi için bkz: [ClickOnce Güvenilen Yayımcılar yapılandırma](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="07b3d-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b3d-107">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="07b3d-107">See Also</span></span>  
 [<span data-ttu-id="07b3d-108">Güvenilir Uygulama dağıtımına genel bakış</span><span class="sxs-lookup"><span data-stu-id="07b3d-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="07b3d-109">ClickOnce dağıtımı Windows Forms uygulamaları</span><span class="sxs-lookup"><span data-stu-id="07b3d-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)