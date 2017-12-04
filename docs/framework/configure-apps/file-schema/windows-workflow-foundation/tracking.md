---
title: "&lt;İzleme&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8147f9d9366d323b551ce2bb8874f6e80fb50b5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="lttrackinggt"></a><span data-ttu-id="c9046-102">&lt;İzleme&gt;</span><span class="sxs-lookup"><span data-stu-id="c9046-102">&lt;tracking&gt;</span></span>
<span data-ttu-id="c9046-103">Bir iş akışı hizmeti izleme ayarlarını tanımlamak için yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="c9046-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="c9046-104">İş akışı izleme ve yapılandırmasını daha fazla bilgi için bkz: [izleme ve izleme iş akışı](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) ve [yapılandırma izleme iş akışı için](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c9046-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="c9046-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c9046-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c9046-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="c9046-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9046-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c9046-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9046-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="c9046-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c9046-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c9046-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9046-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="c9046-110">Attributes</span></span>  
 <span data-ttu-id="c9046-111">Yok.</span><span class="sxs-lookup"><span data-stu-id="c9046-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9046-112">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="c9046-112">Child Elements</span></span>  
  
|<span data-ttu-id="c9046-113">Öğe</span><span class="sxs-lookup"><span data-stu-id="c9046-113">Element</span></span>|<span data-ttu-id="c9046-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c9046-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9046-115">\<Katılımcıları ></span><span class="sxs-lookup"><span data-stu-id="c9046-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="c9046-116">Kayıtları İzleme için abone katılımcılara tanımlama yapılandırma öğeleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="c9046-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="c9046-117">İzleme katılımcıları izleme kayıtları yükü işlemek için mantığı içerir (örneğin, bir dosyaya yazmak tercih ettikleri).</span><span class="sxs-lookup"><span data-stu-id="c9046-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="c9046-118">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c9046-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="c9046-119">Bir iş akışı örneğinden yayılan filtre izleme kayıtları için bir izleme profili.</span><span class="sxs-lookup"><span data-stu-id="c9046-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9046-120">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="c9046-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c9046-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="c9046-121">Element</span></span>|<span data-ttu-id="c9046-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c9046-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9046-123">Sistem.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c9046-123">system.ServiceModel</span></span>|<span data-ttu-id="c9046-124">Tüm iş akışı yapılandırma öğelerinin kök öğe.</span><span class="sxs-lookup"><span data-stu-id="c9046-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9046-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c9046-125">Remarks</span></span>  
 <span data-ttu-id="c9046-126">İzleme, bir iş akışının yürütülmesini inceleyin olanağı sağlar.</span><span class="sxs-lookup"><span data-stu-id="c9046-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="c9046-127">İş akışı izleme altyapısı, bir iş akışı yürütme sırasında anahtar olayları yansıtma kayıtları yayma Instruments.</span><span class="sxs-lookup"><span data-stu-id="c9046-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="c9046-128">Örneğin, bir iş akışı örneği başlatıldığında veya tamamlandıktan izleme kayıtları gösterilen.</span><span class="sxs-lookup"><span data-stu-id="c9046-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="c9046-129">İzleme, iş akışı değişkenleri ile ilişkili iş ilgili veriler ayrıca ayıklayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c9046-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="c9046-130">Örneğin, iş akışı işleme sistemi sipariş temsil ediyorsa düzeni kimliği ile birlikte izleme kaydı ayıklanabilir.</span><span class="sxs-lookup"><span data-stu-id="c9046-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="c9046-131">Genel olarak, izleme WF etkinleştirme Tanılama veya İş analizi bir iş akışının yürütülmesini kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="c9046-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9046-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c9046-132">See Also</span></span>  
 <span data-ttu-id="c9046-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c9046-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c9046-134">İzleme ve izleme iş akışı</span><span class="sxs-lookup"><span data-stu-id="c9046-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)