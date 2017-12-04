---
title: "Nasıl yapılır: WorkflowServiceHost ile İş Akışı Tarafından İşlenmeyen Özel Durum Davranışını Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e85f8010528d18133ccd9d98de8479ea0de343d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="301e8-102">Nasıl yapılır: WorkflowServiceHost ile İş Akışı Tarafından İşlenmeyen Özel Durum Davranışını Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="301e8-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="301e8-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> Barındırılan bir iş akışı içinde işlenmeyen bir özel durum oluşursa, gerçekleştirilecek eylemi belirtmenize olanak tanıyan bir davranıştır <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="301e8-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="301e8-104">Bu konuda, bir yapılandırma dosyasında bu davranışı yapılandırmak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="301e8-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="301e8-105">WorkflowUnhandledExceptionBehavior yapılandırmak için</span><span class="sxs-lookup"><span data-stu-id="301e8-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="301e8-106">Ekleme bir <`workflowUnhandledException`> öğesinde bir <`behavior`> öğesi içinde bir <`serviceBehaviors`> öğesini kullanarak `action` özniteliği aşağıdaki örnekte gösterildiği gibi işlenmeyen bir özel durum meydana geldiğinde eylemi belirtin.</span><span class="sxs-lookup"><span data-stu-id="301e8-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="301e8-107">Önceki yapılandırma örneği Basitleştirilmiş yapılandırma kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="301e8-107">The preceding configuration sample is using simplified configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="301e8-108">[Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="301e8-108"> [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="301e8-109">Bu davranış, aşağıdaki örnekte gösterildiği gibi kodda yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="301e8-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="301e8-110">`action` Özniteliği <`workflowUnhandledException`> öğesi aşağıdaki değerlerden birine ayarlanabilir:</span><span class="sxs-lookup"><span data-stu-id="301e8-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="301e8-111">**İptal Et**</span><span class="sxs-lookup"><span data-stu-id="301e8-111">**abandon**</span></span>  
     <span data-ttu-id="301e8-112">(Bu son kalan noktasına geri olan) kalıcı örneği durumu dokunmadan bellek örneğinde durdurur.</span><span class="sxs-lookup"><span data-stu-id="301e8-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="301e8-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="301e8-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="301e8-114">Bellek örneğinde durdurur ve askıya alınmasına kalıcı örneğini güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="301e8-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="301e8-115">**İptal**</span><span class="sxs-lookup"><span data-stu-id="301e8-115">**cancel**</span></span>  
     <span data-ttu-id="301e8-116">İptal işleyicileri için örneği çağırır ve ayrıca örneği Mağazası'ndan kaldırabilir bellek örneğinde tamamlar</span><span class="sxs-lookup"><span data-stu-id="301e8-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="301e8-117">**sonlandırma**</span><span class="sxs-lookup"><span data-stu-id="301e8-117">**terminate**</span></span>  
     <span data-ttu-id="301e8-118">Bellek örneğinde tamamlanır ve örnek deposundan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="301e8-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="301e8-119"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, bkz: [iş akışı hizmeti konak genişletilebilirliği](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="301e8-119"> <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301e8-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="301e8-120">See Also</span></span>  
 [<span data-ttu-id="301e8-121">İş akışı hizmeti konak genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="301e8-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="301e8-122">İş akışı Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="301e8-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)