---
title: "Nasıl yapılır: Uygulama Etki Alanını Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79a05be9b3ddb9ca8aaabe13165efc5d851125a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="74e11-102">Nasıl yapılır: Uygulama Etki Alanını Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e11-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="74e11-103">Ortak dil çalışma zamanı kullanarak yeni bir uygulama etki alanı için yapılandırma bilgilerini sağlayabilir <xref:System.AppDomainSetup> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="74e11-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="74e11-104">Kendi uygulama etki alanları oluştururken en önemli özelliktir <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="74e11-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="74e11-105">Diğer **AppDomainSetup** özellikleri, belirli bir uygulama etki yapılandırmak için çoğunlukla çalışma zamanı ana bilgisayarı tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="74e11-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="74e11-106">**ApplicationBase** özelliği tanımlar uygulaması kök dizini.</span><span class="sxs-lookup"><span data-stu-id="74e11-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="74e11-107">Çalışma zamanı türü isteği karşılamak gerektiğinde tarafından belirtilen dizinde türünü içeren bütünleştirilmiş için yoklamaları **ApplicationBase** özelliği.</span><span class="sxs-lookup"><span data-stu-id="74e11-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74e11-108">Yeni bir uygulama etki alanı yalnızca devralınan **ApplicationBase** Oluşturucusu özelliği.</span><span class="sxs-lookup"><span data-stu-id="74e11-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="74e11-109">Aşağıdaki örnekte bir örneğini oluşturur **AppDomainSetup** sınıfı, yeni bir uygulama etki alanı oluşturmak için bu sınıfı kullanır, bilgileri konsola yazar ve uygulama etki alanı kaldırır.</span><span class="sxs-lookup"><span data-stu-id="74e11-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74e11-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="74e11-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="74e11-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="74e11-111">See Also</span></span>  
 [<span data-ttu-id="74e11-112">Uygulama etki alanları ile programlama</span><span class="sxs-lookup"><span data-stu-id="74e11-112">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="74e11-113">Uygulama etki alanlarını kullanma</span><span class="sxs-lookup"><span data-stu-id="74e11-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)