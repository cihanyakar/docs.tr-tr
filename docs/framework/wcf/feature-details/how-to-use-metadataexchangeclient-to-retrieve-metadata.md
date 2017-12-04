---
title: "Nasıl yapılır: Meta Verileri Almak için MetadataExchangeClient Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cccbf343acc74b3e0da0f55e497f19ca15e27892
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="663da-102">Nasıl yapılır: Meta Verileri Almak için MetadataExchangeClient Kullanma</span><span class="sxs-lookup"><span data-stu-id="663da-102">How to: Use MetadataExchangeClient to Retrieve Metadata</span></span>
<span data-ttu-id="663da-103">Kullanım <xref:System.ServiceModel.Description.MetadataExchangeClient> sınıfı WS-MetadataExchange (MEX) protokolünü kullanarak meta verileri indirir.</span><span class="sxs-lookup"><span data-stu-id="663da-103">Use the <xref:System.ServiceModel.Description.MetadataExchangeClient> class to download metadata using the WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="663da-104">Alınan meta veri dosyaları verilir bir <xref:System.ServiceModel.Description.MetadataSet> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="663da-104">The retrieved metadata files are returned as a <xref:System.ServiceModel.Description.MetadataSet> object.</span></span> <span data-ttu-id="663da-105">Döndürülen <xref:System.ServiceModel.Description.MetadataSet> nesnesini içeren koleksiyonu <xref:System.ServiceModel.Description.MetadataSection> nesneleri, her biri içeren belirli meta veriler dialect ve bir tanımlayıcı.</span><span class="sxs-lookup"><span data-stu-id="663da-105">The returned <xref:System.ServiceModel.Description.MetadataSet> object contains a collection of <xref:System.ServiceModel.Description.MetadataSection> objects, each of which contains a specific metadata dialect and an identifier.</span></span> <span data-ttu-id="663da-106">Döndürülen meta veri dosyaları için yazabilir veya Web Hizmetleri Açıklama Dili (WSDL) belgeleri döndürülen meta veri içeriyorsa, meta verileri kullanarak içeri aktarabilirsiniz <xref:System.ServiceModel.Description.WsdlImporter>.</span><span class="sxs-lookup"><span data-stu-id="663da-106">You can write the returned metadata to files or, if the returned metadata contains Web Services Description Language (WSDL) documents, you can import the metadata using the <xref:System.ServiceModel.Description.WsdlImporter>.</span></span>  
  
 <span data-ttu-id="663da-107"><xref:System.ServiceModel.Description.MetadataExchangeClient> Bir adresi alın oluşturucular kullandığınıza bağlama <xref:System.ServiceModel.Description.MetadataExchangeBindings> adresinin Tekdüzen Kaynak Tanımlayıcısı (URI) şemasını eşleşen statik sınıf.</span><span class="sxs-lookup"><span data-stu-id="663da-107">The <xref:System.ServiceModel.Description.MetadataExchangeClient> constructors that take an address use the binding on the <xref:System.ServiceModel.Description.MetadataExchangeBindings> static class that matches the Uniform Resource Identifier (URI) scheme of the address.</span></span> <span data-ttu-id="663da-108">Alternatif olarak kullanabileceğiniz <xref:System.ServiceModel.Description.MetadataExchangeClient> açıkça kullanılacak bağlama belirtmenize olanak tanır Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="663da-108">You can alternatively use the <xref:System.ServiceModel.Description.MetadataExchangeClient> constructor that allows you to explicitly specify the binding to use.</span></span> <span data-ttu-id="663da-109">Belirtilen bağlama tüm meta veri başvurularını çözmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="663da-109">The specified binding is used to resolve all metadata references.</span></span>  
  
 <span data-ttu-id="663da-110">Olduğu gibi diğer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] istemci, <xref:System.ServiceModel.Description.MetadataExchangeClient> türü, istemci uç noktası yapılandırmaları uç nokta Yapılandırması adı kullanarak yüklemek için bir oluşturucu sağlar.</span><span class="sxs-lookup"><span data-stu-id="663da-110">Just like any other [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client, the <xref:System.ServiceModel.Description.MetadataExchangeClient> type provides a constructor for loading client endpoint configurations using the endpoint configuration name.</span></span> <span data-ttu-id="663da-111">Belirtilen uç nokta yapılandırması belirtmelisiniz <xref:System.ServiceModel.Description.IMetadataExchange> sözleşme.</span><span class="sxs-lookup"><span data-stu-id="663da-111">The specified endpoint configuration must specify the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="663da-112">Aşağıdakilerden birini kullanmanız gerekir böylece uç nokta yapılandırması adresi, yüklü değil <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> bir adresi alın aşırı.</span><span class="sxs-lookup"><span data-stu-id="663da-112">The address in the endpoint configuration is not loaded, so you must use one of the <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> overloads that take an address.</span></span> <span data-ttu-id="663da-113">Meta veri adresi kullanarak belirttiğinizde bir <xref:System.ServiceModel.EndpointAddress> örneği <xref:System.ServiceModel.Description.MetadataExchangeClient> adresi bir MEX uç noktaya işaret varsayar.</span><span class="sxs-lookup"><span data-stu-id="663da-113">When you specify the metadata address using an <xref:System.ServiceModel.EndpointAddress> instance, the <xref:System.ServiceModel.Description.MetadataExchangeClient> assumes that the address points to a MEX endpoint.</span></span> <span data-ttu-id="663da-114">Meta veri adresi bir URL olarak belirttiğiniz sonra da belirtmek gereken <xref:System.ServiceModel.Description.MetadataExchangeClientMode> kullanmak için MEX veya HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="663da-114">If you specify the metadata address as a URL, then you need to also specify which <xref:System.ServiceModel.Description.MetadataExchangeClientMode> to use, MEX or HTTP GET.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="663da-115">Varsayılan olarak, <xref:System.ServiceModel.Description.MetadataExchangeClient> tüm başvuruları sizin için çözümler WSDL ve XML Şeması dahil olmak üzere içeri aktarır ve da içerir.</span><span class="sxs-lookup"><span data-stu-id="663da-115">By default, the <xref:System.ServiceModel.Description.MetadataExchangeClient> resolves all references for you, including WSDL and XML Schema imports and includes.</span></span> <span data-ttu-id="663da-116">Ayarlayarak bu işlev devre dışı bırakabilirsiniz <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="663da-116">You can disable this functionality by setting the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `false`.</span></span> <span data-ttu-id="663da-117">Kullanarak çözümlemek için referans maksimum sayısını kontrol edebilirsiniz <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="663da-117">You can control the maximum number of references to resolve using the <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> property.</span></span> <span data-ttu-id="663da-118">Bu özellik ile birlikte kullanabileceğiniz `MaxReceivedMessageSize` ne kadar meta verileri alınır denetlemek için bağlama özelliği.</span><span class="sxs-lookup"><span data-stu-id="663da-118">You can use this property in conjunction with the `MaxReceivedMessageSize` property on the binding to control how much metadata is retrieved.</span></span>  
  
### <a name="to-use-metadataexchangeclient-to-obtain-metadata"></a><span data-ttu-id="663da-119">Meta veri elde etmek üzere MetadataExchangeClient kullanma</span><span class="sxs-lookup"><span data-stu-id="663da-119">To use MetadataExchangeClient to obtain metadata</span></span>  
  
1.  <span data-ttu-id="663da-120">Yeni bir <xref:System.ServiceModel.Description.MetadataExchangeClient> belirterek açıkça bağlama, bir uç nokta yapılandırması adını veya adresini meta veri nesnesi.</span><span class="sxs-lookup"><span data-stu-id="663da-120">Create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> object by explicitly specifying a binding, an endpoint configuration name, or the address of the metadata.</span></span>  
  
2.  <span data-ttu-id="663da-121">Yapılandırma <xref:System.ServiceModel.Description.MetadataExchangeClient> gereksinimlerinize uygun olarak.</span><span class="sxs-lookup"><span data-stu-id="663da-121">Configure the <xref:System.ServiceModel.Description.MetadataExchangeClient> to suit your needs.</span></span> <span data-ttu-id="663da-122">Örneğin, meta veriler bulunurken kullanın, nasıl meta veri başvurularını çözümlendi, ayarlayın ve denetlemek için kimlik bilgileri belirtebilirsiniz <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A> ne kadar zaman aşımına uğramadan önce dönmek meta veri isteği olduğunu denetleme özelliği.</span><span class="sxs-lookup"><span data-stu-id="663da-122">For example, you can specify credentials to use when requesting metadata, control how metadata references are resolved, and set the <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A> property to control how long the metadata request has to return before it times out.</span></span>  
  
3.  <span data-ttu-id="663da-123">Elde <xref:System.ServiceModel.Description.MetadataSet> birini çağırarak alınan meta verileri içeren nesne <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="663da-123">Obtain the <xref:System.ServiceModel.Description.MetadataSet> object that contains the retrieved metadata by calling one of the <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> methods.</span></span> <span data-ttu-id="663da-124">Yalnızca kullanabilirsiniz Not <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> açıkça bir adresi oluşturulurken belirttiyseniz bağımsız değişken almayan aşırı <xref:System.ServiceModel.Description.MetadataExchangeClient>.</span><span class="sxs-lookup"><span data-stu-id="663da-124">Note that you can only use the <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> overload that takes no arguments if you explicitly specified an address when constructing the <xref:System.ServiceModel.Description.MetadataExchangeClient>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="663da-125">Örnek</span><span class="sxs-lookup"><span data-stu-id="663da-125">Example</span></span>  
 <span data-ttu-id="663da-126">Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir <xref:System.ServiceModel.Description.MetadataExchangeClient> karşıdan yüklenir ve meta veri dosyaları numaralandırma.</span><span class="sxs-lookup"><span data-stu-id="663da-126">The following code example shows how to use <xref:System.ServiceModel.Description.MetadataExchangeClient> to download and enumerate metadata files.</span></span>  

 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  

## <a name="compiling-the-code"></a><span data-ttu-id="663da-127">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="663da-127">Compiling the Code</span></span>  
 <span data-ttu-id="663da-128">Bu kod örneği derlemek için System.ServiceModel.dll derleme başvurusu ve alma <xref:System.ServiceModel.Description> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="663da-128">To compile this code example, you must reference the System.ServiceModel.dll assembly and import the <xref:System.ServiceModel.Description> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663da-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="663da-129">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataResolver>  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>  
 <xref:System.ServiceModel.Description.WsdlImporter>