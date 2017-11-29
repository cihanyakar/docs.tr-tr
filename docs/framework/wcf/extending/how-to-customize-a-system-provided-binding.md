---
title: "Nasıl yapılır: Sistem Tarafından Sağlanan Bir Bağlamayı Özelleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68a6feffcb4925a20e128c2bc9f06e20ea90a678
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="e6a0a-102">Nasıl yapılır: Sistem Tarafından Sağlanan Bir Bağlamayı Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="e6a0a-102">How to: Customize a System-Provided Binding</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="e6a0a-103">temel bağlama öğeleri özelliklerden bazıları, ancak tüm özellikleri yapılandırmanıza olanak tanıyan çeşitli sistem tarafından sağlanan bağlamaları içerir.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-103"> includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="e6a0a-104">Bu konu, özelliklerin özel bağlama oluşturma için bağlama öğeleri nasıl ayarlanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e6a0a-105">doğrudan oluşturmak ve bağlama öğeleri sistem tarafından sağlanan bağlamalar kullanmadan yapılandırmak bkz: nasıl [özel bağlamaları](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="e6a0a-105"> how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e6a0a-106">bkz: oluşturma ve özel bağlamaları genişletme [bağlamaları genişletme](../../../../docs/framework/wcf/extending/extending-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="e6a0a-106"> creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="e6a0a-107">İçinde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tüm bağlamaları, oluşur *bağlama öğeleri*.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="e6a0a-108">Her bağlama öğesi türetilen <xref:System.ServiceModel.Channels.BindingElement> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="e6a0a-109">Sistem tarafından sağlanan bağlamalar gibi <xref:System.ServiceModel.BasicHttpBinding> oluşturun ve kendi bağlama öğeleri yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="e6a0a-110">Bu konu erişmek ve doğrudan bağlamada sunulmaz Bu bağlama öğeleri özelliklerini değiştirmek nasıl gösterir; Özellikle, <xref:System.ServiceModel.BasicHttpBinding> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="e6a0a-111">Tek tek bağlama öğeleri tarafından temsil edilen bir koleksiyonda bulunan <xref:System.ServiceModel.Channels.BindingElementCollection> sınıfı ve bu sırada eklenir: işlem akış, güvenilir oturum, güvenlik, bileşik çift yönlü, tek yönlü, akış güvenliği, ileti kodlama ve taşıma.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="e6a0a-112">Listelenen tüm bağlama öğeleri her bağlama gerekli olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="e6a0a-113">Kullanıcı tanımlı bağlama öğeleri bu bağlama öğesi koleksiyonda da görüntülenebilir ve daha önce açıklandığı gibi aynı sırada görünmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="e6a0a-114">Örneğin, kullanıcı tanımlı bir aktarım bağlama öğesi koleksiyonun son öğesi olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="e6a0a-115"><xref:System.ServiceModel.BasicHttpBinding> Sınıfı üç bağlama öğeleri içerir:</span><span class="sxs-lookup"><span data-stu-id="e6a0a-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="e6a0a-116">Ya da bağlama öğesi, isteğe bağlı bir güvenlik <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> HTTP taşıma (ileti düzeyi güvenlik) ile kullanılan sınıf veya <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> Aktarım Katmanı Güvenliği de HTTPS aktarımı durumda sağladığında kullanılan sınıfı kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="e6a0a-117">Bağlama öğesi, ya da gerekli ileti Kodlayıcı <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> veya <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="e6a0a-118">Bağlama öğesi, ya da gerekli bir aktarım <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, veya <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="e6a0a-119">Bu örnekte biz bağlama örneği oluşturun, oluşturun bir *özel bağlama* kendisinden özel bağlama bağlama öğeleri inceleyin ve biz HTTP bağlama öğesi bulduğunuzda ayarlarız kendi `KeepAliveEnabled` özelliğine`false`.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="e6a0a-120">`KeepAliveEnabled` Doğrudan özellik gösterilmez `BasicHttpBinding`, bağlama öğesi aşağı gidin ve bu özelliği ayarlamak için özel bağlama oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="e6a0a-121">Sistem tarafından sağlanan bir bağlamayı değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="e6a0a-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="e6a0a-122">Bir örneğini oluşturmak <xref:System.ServiceModel.BasicHttpBinding> sınıfı ve ileti düzeyi kendi güvenlik modunu ayarlama.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="e6a0a-123">Özel bağlama bağlamayı ve oluşturun bir <xref:System.ServiceModel.Channels.BindingElementCollection> özel bağlamanın özelliklerinden biri sınıfından.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="e6a0a-124">Döngü <xref:System.ServiceModel.Channels.BindingElementCollection> sınıfı ve ne zaman bulduğunuz <xref:System.ServiceModel.Channels.HttpTransportBindingElement> sınıfı, Ayarla kendi <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a0a-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e6a0a-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e6a0a-126">Özel bağlamalar</span><span class="sxs-lookup"><span data-stu-id="e6a0a-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)