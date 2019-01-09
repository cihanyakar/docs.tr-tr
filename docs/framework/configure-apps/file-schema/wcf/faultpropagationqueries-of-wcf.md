---
title: WCF &lt;faultPropagationQueries&gt;
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 77a38f8474b5e2ac8634d6ea91bc80c6044ff3ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144970"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="72254-102">WCF &lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="72254-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="72254-103">Bir etkinlik içinde oluşan hataların işlenmesi izlemek için kullanılan sorguları koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="72254-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="72254-104">Bu olay bir FaultHandler bir hata her işlediğinde oluşur.</span><span class="sxs-lookup"><span data-stu-id="72254-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="72254-105">Bir etkinlik içinde oluşan hataların işlenmesi izlemek için böyle bir sorgu kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="72254-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="72254-106">Sorgu hata yayma kayıtlara abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="72254-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="72254-107">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="72254-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="72254-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="72254-108">\<system.serviceModel></span></span>  
<span data-ttu-id="72254-109">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="72254-109">\<tracking></span></span>  
<span data-ttu-id="72254-110">\<profilleri ></span><span class="sxs-lookup"><span data-stu-id="72254-110">\<profiles></span></span>  
<span data-ttu-id="72254-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="72254-111">\<trackingProfile></span></span>  
<span data-ttu-id="72254-112">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="72254-112">\<workflow></span></span>  
<span data-ttu-id="72254-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="72254-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72254-114">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="72254-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72254-115">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="72254-115">Attributes and elements</span></span>

<span data-ttu-id="72254-116">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="72254-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="72254-117">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="72254-117">Attributes</span></span>

<span data-ttu-id="72254-118">Yok.</span><span class="sxs-lookup"><span data-stu-id="72254-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="72254-119">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="72254-119">Child elements</span></span>

|<span data-ttu-id="72254-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="72254-120">Element</span></span>|<span data-ttu-id="72254-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72254-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72254-122">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="72254-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="72254-123">Bir etkinlik içinde oluşan hataların işlenmesi izlemek için kullanılan sorgu.</span><span class="sxs-lookup"><span data-stu-id="72254-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="72254-124">Bu olay bir FaultHandler bir hata her işlediğinde oluşur.</span><span class="sxs-lookup"><span data-stu-id="72254-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72254-125">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="72254-125">Parent elements</span></span>  
  
|<span data-ttu-id="72254-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="72254-126">Element</span></span>|<span data-ttu-id="72254-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72254-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72254-128">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="72254-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="72254-129">Belirli bir iş akışı tarafından tanımlanan tüm sorgularında içeren bir yapılandırma öğesi `activityDefinitionId` özelliği.</span><span class="sxs-lookup"><span data-stu-id="72254-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72254-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="72254-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="72254-131">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="72254-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="72254-132">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="72254-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
