---
title: '&lt;trackingProfile&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 939aa89fd236df34b59dca18d45ccb23fc8049d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="lttrackingprofilegt"></a><span data-ttu-id="72adc-102">&lt;trackingProfile&gt;</span><span class="sxs-lookup"><span data-stu-id="72adc-102">&lt;trackingProfile&gt;</span></span>
<span data-ttu-id="72adc-103">İş akışı izleme katılımcı kayıtlarında izleme için bir abonelik oluşturmak için yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="72adc-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="72adc-104">İzleme profili çalışma zamanında bir iş akışı örneğinin durumu değiştiğinde, gösterilen iş akışı olayları abone olmak için izleme katılımcı izin izleme sorgularını içerir.</span><span class="sxs-lookup"><span data-stu-id="72adc-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="72adc-105">Tanımlanan sorguları izleme profilinde bölüm abonelik tarafından döndürülen olayları türlerini tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="72adc-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="72adc-106">İş akışı izleme ve yapılandırmasını daha fazla bilgi için bkz: [izleme ve izleme iş akışı](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) ve [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="72adc-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="72adc-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="72adc-107">\<system.serviceModel></span></span>  
<span data-ttu-id="72adc-108">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="72adc-108">\<tracking></span></span>  
<span data-ttu-id="72adc-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="72adc-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72adc-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="72adc-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72adc-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="72adc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="72adc-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="72adc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72adc-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="72adc-113">Attributes</span></span>  
  
|<span data-ttu-id="72adc-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="72adc-114">Attribute</span></span>|<span data-ttu-id="72adc-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72adc-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72adc-116">name</span><span class="sxs-lookup"><span data-stu-id="72adc-116">name</span></span>|<span data-ttu-id="72adc-117">İzleme profili adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="72adc-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72adc-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="72adc-118">Child Elements</span></span>  
  
|<span data-ttu-id="72adc-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="72adc-119">Element</span></span>|<span data-ttu-id="72adc-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72adc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72adc-121">\<Katılımcıları ></span><span class="sxs-lookup"><span data-stu-id="72adc-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="72adc-122">Tüm sorgular tarafından tanımlanan belirli bir iş akışı için içeren bir yapılandırma öğesi **HYPERLINK "http://msdn.microsoft.com/en-us/library/ System.ServiceModel.Activities.Tracking.Configuration.profileworkflowelement.activitydefinitionid (VS.100) .aspx "ctivityDefinitionId** özelliği.</span><span class="sxs-lookup"><span data-stu-id="72adc-122">A configuration element that contains all queries for a specific workflow identified by the **a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx"ctivityDefinitionId** property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72adc-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="72adc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="72adc-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="72adc-124">Element</span></span>|<span data-ttu-id="72adc-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72adc-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72adc-126">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="72adc-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="72adc-127">Bir iş akışı hizmeti izleme ayarlarını tanımlamak için yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="72adc-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72adc-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="72adc-128">Remarks</span></span>  
 <span data-ttu-id="72adc-129">Profilleri izleme çalışma zamanında bir iş akışı örneğinin durumu değiştiğinde, gösterilen iş akışı olayları abone olmak için izleme katılımcı izin izleme sorgularını içerir.</span><span class="sxs-lookup"><span data-stu-id="72adc-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="72adc-130">Çok kaba bir profili yazabilirsiniz izleme gereksinimlerinize bağlı olarak, bir iş akışı üzerinde üst düzey durum değişikliklerini küçük bir kümesi için abone olur.</span><span class="sxs-lookup"><span data-stu-id="72adc-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="72adc-131">Buna karşılık, sonuçta ortaya çıkan, olayları ayrıntılı yürütme akışı daha sonra yeniden oluşturmak için zengin çok belirli bir profil oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="72adc-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="72adc-132">İzleme profilleri belirli izleme kayıtları için iş akışı çalışma zamanı sorgu izin kayıtları izleme için bildirim temelli abonelikler olarak yapılandırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="72adc-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="72adc-133">Köprü "http://msdn.microsoft.com/en-us/library/system.activities.tracking.trackingrecord (VS.100).aspx" TrackingRecord nesnelerin farklı sınıflara abone izin sorgu türleri sayıda vardır.</span><span class="sxs-lookup"><span data-stu-id="72adc-133">There are a handful of query types that allow you subscribe to different classes of  HYPERLINK "http://msdn.microsoft.com/en-us/library/system.activities.tracking.trackingrecord(VS.100).aspx" TrackingRecord objects.</span></span> <span data-ttu-id="72adc-134">Sorgu tam bir listesi için bkz: [ \<katılımcıları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) ve [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="72adc-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="72adc-135">Aşağıdaki örnek, bir izleme profili abone olmak izleme katılımcı izin veren bir yapılandırma dosyası gösterir `Started` ve `Completed` iş akışı olayları.</span><span class="sxs-lookup"><span data-stu-id="72adc-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72adc-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="72adc-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="72adc-137">İzleme ve izleme iş akışı</span><span class="sxs-lookup"><span data-stu-id="72adc-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="72adc-138">Profillerini izleme</span><span class="sxs-lookup"><span data-stu-id="72adc-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)