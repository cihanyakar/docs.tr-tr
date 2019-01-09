---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: c79c8e8db2a4ea4526000bcbe336d1e664f9c4c2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150961"
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="b49fa-102">&lt;DataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="b49fa-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="b49fa-103">İçin yapılandırma verilerini içeren <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b49fa-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="b49fa-104">Bu öğe, iki farklı hiyerarşilere gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="b49fa-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="b49fa-105">Bir listelenir aşağıdaki şema hiyerarşisini bölümü ve diğer açıklamalar bölümünde listelenir.</span><span class="sxs-lookup"><span data-stu-id="b49fa-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="b49fa-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b49fa-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="b49fa-107">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="b49fa-107">\<behaviors></span></span>  
<span data-ttu-id="b49fa-108">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b49fa-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="b49fa-109">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="b49fa-109">\<behavior></span></span>  
<span data-ttu-id="b49fa-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b49fa-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49fa-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b49fa-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b49fa-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b49fa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b49fa-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b49fa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b49fa-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b49fa-114">Attributes</span></span>  
  
|<span data-ttu-id="b49fa-115">Öğe</span><span class="sxs-lookup"><span data-stu-id="b49fa-115">Element</span></span>|<span data-ttu-id="b49fa-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b49fa-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b49fa-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="b49fa-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="b49fa-118">Bunu edilirken bitiş noktası tarafından sağlanan veri yoksay belirten bir Boole değeri serileştirilecek veya serisi.</span><span class="sxs-lookup"><span data-stu-id="b49fa-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="b49fa-119">Bu öznitelik yalnızca ayarlanabilir `<dataContractSerializer>` altında `<behavior>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="b49fa-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="b49fa-120">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="b49fa-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="b49fa-121">Serileştirmek veya seri durumdan çıkarılacak öğeleri maksimum sayısını belirten bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="b49fa-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="b49fa-122">Bu öznitelik 65536'dır.</span><span class="sxs-lookup"><span data-stu-id="b49fa-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b49fa-123">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b49fa-123">Child Elements</span></span>  
 <span data-ttu-id="b49fa-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="b49fa-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b49fa-125">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b49fa-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b49fa-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="b49fa-126">Element</span></span>|<span data-ttu-id="b49fa-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b49fa-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b49fa-128">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="b49fa-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="b49fa-129">Bir koleksiyon için bir hizmet davranışını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b49fa-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="b49fa-130">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="b49fa-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="b49fa-131">İçin olan kök öğesini temsil eden <xref:System.Runtime.Serialization> ad uzayı bölümü ve seçeneklerini ayarlamak için öğeleri içeren <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b49fa-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b49fa-132">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b49fa-132">Remarks</span></span>  
 <span data-ttu-id="b49fa-133">Bu konunun giriş belirtildiği gibi ikinci hiyerarşide budur \<X509Extension > öğesi oluşur.</span><span class="sxs-lookup"><span data-stu-id="b49fa-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="b49fa-134">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="b49fa-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="b49fa-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b49fa-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="b49fa-136">Bilinen türler hakkında daha fazla bilgi için bkz: <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b49fa-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49fa-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b49fa-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="b49fa-138">Veri Anlaşması Bilinen Türler</span><span class="sxs-lookup"><span data-stu-id="b49fa-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="b49fa-139">Veri Aktarma ve Seri Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="b49fa-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
