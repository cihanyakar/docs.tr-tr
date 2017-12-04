---
title: "Nasıl yapılır: bir iş akışı yan yana birden fazla sürümünü ana bilgisayar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f6fa267e6400672328714f016a5823d8f1311aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="46460-102">Nasıl yapılır: bir iş akışı yan yana birden fazla sürümünü ana bilgisayar</span><span class="sxs-lookup"><span data-stu-id="46460-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="46460-103">`WorkflowIdentity`bir adı ve sürümü bir iş akışı tanımı ile ilişkilendirmek iş akışı uygulama geliştiricilerinin ve kalıcı iş akışı örneği ile ilişkili olması için bu bilgileri için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="46460-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="46460-104">Bu kimlik bilgileri, iş akışı uygulama geliştiriciler tarafından birden çok iş akışı tanımı sürümlerinin yan yana yürütme gibi senaryoları etkinleştirmek için kullanılabilir ve dinamik güncelleştirme gibi diğer işlevleri için dönüm sağlar.</span><span class="sxs-lookup"><span data-stu-id="46460-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="46460-105">Bu adım öğreticide nasıl kullanılacağını göstermektedir `WorkflowIdentity` aynı anda birden çok iş akışı sürümü barındırmak için.</span><span class="sxs-lookup"><span data-stu-id="46460-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46460-106">Tamamlanmış sürümü indirme veya videosu öğreticinin görüntülemek için bkz: [Windows Workflow Foundation (WF45) - başlangıç Öğreticisi](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="46460-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="46460-107">Bu konuda</span><span class="sxs-lookup"><span data-stu-id="46460-107">In this topic</span></span>  
 <span data-ttu-id="46460-108">Öğreticinin bu adımında `WriteLine` iş akışı etkinlikleri ek bilgi ve yeni bir sağlamak için değiştirildiğinde `WriteLine` etkinlik eklenir.</span><span class="sxs-lookup"><span data-stu-id="46460-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="46460-109">Özgün iş akışı derleme kopyası saklanır ve onu özgün ve güncelleştirilmiş iş akışları aynı anda çalıştırabilmeniz için ana bilgisayar uygulamasını güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="46460-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="46460-110">NumberGuessWorkflowActivities proje bir kopyasını oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="46460-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="46460-111">İş akışları güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="46460-112">Durum makinesi iş akışını güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="46460-113">Akış iş akışı güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="46460-114">Sıralı iş akışı güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="46460-115">İş akışı önceki içerecek şekilde WorkflowVersionMap güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="46460-116">Derleme ve uygulamayı çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="46460-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="46460-117">Bu konudaki adımları izleyerek önce uygulamayı çalıştırmak, her tür çeşitli iş akışlarını başlatmak ve her biri için bir veya iki tahmin yapma.</span><span class="sxs-lookup"><span data-stu-id="46460-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="46460-118">Bu adım ve aşağıdaki adımı kalıcı bu iş akışları kullanılan [nasıl yapılır: iş akışı örneği çalışma tanım güncelleştirme](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="46460-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46460-119">Başlarken Öğreticisi her adımı için önceki adımları değişir.</span><span class="sxs-lookup"><span data-stu-id="46460-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="46460-120">Önceki adımları tamamlanmadıysa tamamen tamamlanmış bir sürümünü yükleyebilirsiniz [Windows Workflow Foundation (WF45) - başlangıç Öğreticisi](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="46460-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <span data-ttu-id="46460-121"><a name="BKMK_BackupCopy"></a>NumberGuessWorkflowActivities proje bir kopyasını oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="46460-121"><a name="BKMK_BackupCopy"></a> To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="46460-122">Açık **WF45GettingStartedTutorial** çözümde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] açık değilse.</span><span class="sxs-lookup"><span data-stu-id="46460-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="46460-123">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="46460-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="46460-124">Kapat **WF45GettingStartedTutorial** çözümü.</span><span class="sxs-lookup"><span data-stu-id="46460-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="46460-125">Windows Gezgini'ni açın ve Öğreticisi çözümünü dosya ve proje klasörleri bulunduğu klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="46460-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="46460-126">Adlı yeni bir klasör oluşturun **PreviousVersions** aynı klasörde **NumberGuessWorkflowHost** ve **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="46460-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="46460-127">Bu klasör, sonraki öğretici adımlarda kullanılan iş akışları farklı sürümlerini içeren derlemeler kapsamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="46460-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="46460-128">Gidin **NumberGuessWorkflowActivities\bin\debug** klasörü (veya **bin\release** proje ayarlarınızı bağlı olarak).</span><span class="sxs-lookup"><span data-stu-id="46460-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="46460-129">Kopya **NumberGuessWorkflowActivities.dll** ve yapıştırın **PreviousVersions** klasör.</span><span class="sxs-lookup"><span data-stu-id="46460-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="46460-130">Yeniden Adlandır **NumberGuessWorkflowActivities.dll** içinde **PreviousVersions** klasörüne **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="46460-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46460-131">Bu konudaki adımlarda, iş akışları birden fazla sürümünü kapsamak için kullanılmış derlemeleri yönetmenin bir yolu gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="46460-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="46460-132">Güçlü adlandırma derlemeler ve genel derleme önbelleğinde kaydetme gibi başka yöntemler de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="46460-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="46460-133">Adlı yeni bir klasör oluşturun **NumberGuessWorkflowActivities_du** aynı klasörde **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**ve yeni eklenen **PreviousVersions** klasörünü ve tüm dosyaları ve alt kopyalayın **NumberGuessWorkflowActivities** yeni klasöre  **NumberGuessWorkflowActivities_du** klasör.</span><span class="sxs-lookup"><span data-stu-id="46460-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="46460-134">Proje etkinlikleri ilk sürümü için bu yedek kopyasını kullanılan [nasıl yapılır: iş akışı örneği çalışma tanım güncelleştirme](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="46460-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="46460-135">Yeniden açın **WF45GettingStartedTutorial** çözümde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46460-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <span data-ttu-id="46460-136"><a name="BKMK_UpdateWorkflows"></a>İş akışları güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-136"><a name="BKMK_UpdateWorkflows"></a> To update the workflows</span></span>  
 <span data-ttu-id="46460-137">Bu bölümde, iş akışı tanımları güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="46460-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="46460-138">İki `WriteLine` kullanıcının tahmin üzerinde görüş etkinlikleri güncelleştirilmiş ve yeni bir `WriteLine` etkinlik sayısını tahmin sonra oyun hakkında ek bilgi sağlayan eklenir.</span><span class="sxs-lookup"><span data-stu-id="46460-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <span data-ttu-id="46460-139"><a name="BKMK_UpdateStateMachine"></a>Durum makinesi iş akışını güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-139"><a name="BKMK_UpdateStateMachine"></a> To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="46460-140">İçinde **Çözüm Gezgini**altında **NumberGuessWorkflowActivities** projesi, çift **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="46460-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46460-141">Çift **tahmin yanlış** durum makinesinin geçişi.</span><span class="sxs-lookup"><span data-stu-id="46460-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="46460-142">Güncelleştirme `Text` sol en `WriteLine` içinde `If` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="46460-143">Güncelleştirme `Text` sağ en `WriteLine` içinde `If` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="46460-144">Dönmek için genel durum makine görünümünde iş akışı Tasarımcısı'nı tıklatarak **Durum makinesi** haritasındaki iş akışı Tasarımcısı'nı üstünde görüntüle.</span><span class="sxs-lookup"><span data-stu-id="46460-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="46460-145">Çift **tahmin doğru** durum makinesinin geçişi.</span><span class="sxs-lookup"><span data-stu-id="46460-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="46460-146">Sürükleme bir **WriteLine** etkinliğinden **Temelleri** bölümünü **araç** ve bırakın **burada bırakma eylem etkinliği** etiketi Geçişi.</span><span class="sxs-lookup"><span data-stu-id="46460-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="46460-147">İçine aşağıdaki ifadeyi yazın `Text` özellik kutusu.</span><span class="sxs-lookup"><span data-stu-id="46460-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="46460-148"><a name="BKMK_UpdateFlowchart"></a>Akış iş akışı güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-148"><a name="BKMK_UpdateFlowchart"></a> To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="46460-149">İçinde **Çözüm Gezgini**altında **NumberGuessWorkflowActivities** projesi, çift **FlowchartNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="46460-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46460-150">Güncelleştirme `Text` sol en `WriteLine` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="46460-151">Güncelleştirme `Text` sağ en `WriteLine` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="46460-152">Sürükleme bir **WriteLine** etkinliğinden **Temelleri** bölümünü **araç** ve açılan noktasında bırakma `True` eylemi en üstteki `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="46460-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="46460-153">`WriteLine` Etkinlik akış eklenir ve bağlantılı `True` eylemi `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="46460-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="46460-154">İçine aşağıdaki ifadeyi yazın `Text` özellik kutusu.</span><span class="sxs-lookup"><span data-stu-id="46460-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="46460-155"><a name="BKMK_UpdateSequential"></a>Sıralı iş akışı güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-155"><a name="BKMK_UpdateSequential"></a> To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="46460-156">İçinde **Çözüm Gezgini**altında **NumberGuessWorkflowActivities** projesi, çift **SequentialNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="46460-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46460-157">Güncelleştirme `Text` sol en `WriteLine` içinde `If` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="46460-158">Güncelleştirme `Text` sağ en `WriteLine` etkinliğinde `If` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="46460-159">Sürükleme bir **WriteLine** etkinliğinden **Temelleri** bölümünü **araç** ve bundan sonra bırakma **DoWhile** etkinlik böylece  **WriteLine** kök son etkinlik olduğu `Sequence` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="46460-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="46460-160">İçine aşağıdaki ifadeyi yazın `Text` özellik kutusu.</span><span class="sxs-lookup"><span data-stu-id="46460-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <span data-ttu-id="46460-161"><a name="BKMK_UpdateWorkflowVersionMap"></a>İş akışı önceki içerecek şekilde WorkflowVersionMap güncelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="46460-161"><a name="BKMK_UpdateWorkflowVersionMap"></a> To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="46460-162">Çift **WorkflowVersionMap.cs** (veya **WorkflowVersionMap.vb**) altında **NumberGuessWorkflowHost** projeyi açın.</span><span class="sxs-lookup"><span data-stu-id="46460-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="46460-163">Aşağıdakileri ekleyin `using` (veya `Imports`) diğer dosyanın en üstüne deyimlerini `using` (veya `Imports`) deyimleri.</span><span class="sxs-lookup"><span data-stu-id="46460-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="46460-164">Üç yeni iş akışı kimlikleri üç mevcut iş akışı kimliği bildirimleri hemen altına ekleyin.</span><span class="sxs-lookup"><span data-stu-id="46460-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="46460-165">Bu yeni `v1` iş akışı kimlikleri kullanılacak doğru iş akışı tanımı güncelleştirmeleri yapılmadan önce başlatılan iş akışları sağlar.</span><span class="sxs-lookup"><span data-stu-id="46460-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="46460-166">İçinde `WorkflowVersionMap` oluşturucusu, güncelleştirme `Version` üç geçerli iş akışı kimlikleri özelliğinin `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="46460-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="46460-167">İş akışları sözlüğüne geçerli sürümleri kullanan iş akışı tanımları başlatır kod güncelleştirilmesi gerek yoktur, böylece projesinde başvurulan geçerli sürümleri, kodda ekler.</span><span class="sxs-lookup"><span data-stu-id="46460-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="46460-168">Geçerli sürümler sözlüğe ekler koddan sonra oluşturucuda aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="46460-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="46460-169">Bu iş akışı kimlikleri karşılık gelen iş akışı tanımları ilk sürümleri ile ilişkilendirilir.</span><span class="sxs-lookup"><span data-stu-id="46460-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="46460-170">Ardından, iş akışı tanımları ilk sürümünü içeren derleme yükleme ve oluşturun ve karşılık gelen iş akışı tanımları sözlüğe ekleyin.</span><span class="sxs-lookup"><span data-stu-id="46460-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="46460-171">Aşağıdaki örnek tam listesi için güncelleştirilmiş olan `WorkflowVersionMap` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="46460-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <span data-ttu-id="46460-172"><a name="BKMK_BuildAndRun"></a>Derleme ve uygulamayı çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="46460-172"><a name="BKMK_BuildAndRun"></a> To build and run the application</span></span>  
  
1.  <span data-ttu-id="46460-173">Uygulamanızı oluşturmak için CTRL + SHIFT + B ve başlatmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="46460-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="46460-174">Tıklayarak yeni bir iş akışı Başlat **yeni bir oyun**.</span><span class="sxs-lookup"><span data-stu-id="46460-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="46460-175">İş akışı sürümü altında durum penceresi görüntülenir ve güncelleştirilmiş sürümü ilişkili yansıtır `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="46460-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="46460-176">Not `InstanceId` tamamlandığında iş akışı için izleme dosyasını görüntülemek ve oyun tamamlanana kadar tahmin girin.</span><span class="sxs-lookup"><span data-stu-id="46460-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="46460-177">Kullanıcının tahmin güncelleştirmeler göre durum penceresinde görüntülenen bilgileri nasıl görüntüleneceğini unutmayın `WriteLine` etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="46460-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="46460-178">**Lütfen 1 ile 10 arasında bir sayı girin**</span><span class="sxs-lookup"><span data-stu-id="46460-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="46460-179">**5 çok yüksektir.** </span><span class="sxs-lookup"><span data-stu-id="46460-179">**5 is too high.** </span></span>  
<span data-ttu-id="46460-180">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-181">**3 çok yüksektir.** </span><span class="sxs-lookup"><span data-stu-id="46460-181">**3 is too high.** </span></span>  
<span data-ttu-id="46460-182">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-183">**1 çok düşük olur.** </span><span class="sxs-lookup"><span data-stu-id="46460-183">**1 is too low.** </span></span>  
<span data-ttu-id="46460-184">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-185">**Tebrikler, sayı 4 kapatır tahmin.**</span><span class="sxs-lookup"><span data-stu-id="46460-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="46460-186">Güncelleştirilmiş metinden `WriteLine` etkinlikler görüntülenir, son çıktısını `WriteLine` bu konudaki eklendi etkinliği değil.</span><span class="sxs-lookup"><span data-stu-id="46460-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="46460-187">Durum penceresi tarafından güncelleştirilir çünkü `PersistableIdle` işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="46460-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="46460-188">İş akışı tamamlandıktan ve son etkinlik sonra boşta geçmez çünkü `PersistableIdle` işleyici çağrılmaz.</span><span class="sxs-lookup"><span data-stu-id="46460-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="46460-189">Ancak, durum penceresinde tarafından benzer bir ileti görüntülenir `Completed` işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="46460-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="46460-190">İsterseniz, kod eklenemedi `Completed` Metinden ayıklamak için işleyici `StringWriter` ve durum penceresi görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="46460-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="46460-191">Windows Gezgini'ni açın ve gidin **NumberGuessWorkflowHost\bin\debug** klasörü (veya **bin\release** proje ayarlarınızı bağlı olarak) ve karşılık gelen Not Defteri'ni kullanarak izleme dosyasını açın Tamamlanan iş akışına.</span><span class="sxs-lookup"><span data-stu-id="46460-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="46460-192">Not yapmadınız varsa `InstanceId`, doğru izleme dosyası kullanarak tanımlayabilirsiniz **değiştirilme tarihi** Windows Gezgini'nde bilgi.</span><span class="sxs-lookup"><span data-stu-id="46460-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="46460-193">**Lütfen 1 ile 10 arasında bir sayı girin**</span><span class="sxs-lookup"><span data-stu-id="46460-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="46460-194">**5 çok yüksektir.** </span><span class="sxs-lookup"><span data-stu-id="46460-194">**5 is too high.** </span></span>  
<span data-ttu-id="46460-195">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-196">**3 çok yüksektir.** </span><span class="sxs-lookup"><span data-stu-id="46460-196">**3 is too high.** </span></span>  
<span data-ttu-id="46460-197">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-198">**1 çok düşük olur.** </span><span class="sxs-lookup"><span data-stu-id="46460-198">**1 is too low.** </span></span>  
<span data-ttu-id="46460-199">**Lütfen 1 ile 10 arasında bir sayı girin** </span><span class="sxs-lookup"><span data-stu-id="46460-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46460-200">**2 doğrudur. Bu 4 kapatır tahmin.**</span><span class="sxs-lookup"><span data-stu-id="46460-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="46460-201">Güncelleştirilmiş `WriteLine` çıkış çıktısını dahil olmak üzere izleme dosyasında bulunan `WriteLine` bu konudaki eklendi.</span><span class="sxs-lookup"><span data-stu-id="46460-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="46460-202">Geri sayı tahmin eden uygulamaya geçin ve güncelleştirme yapılmadan önce başlatıldı iş akışları birini seçin.</span><span class="sxs-lookup"><span data-stu-id="46460-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="46460-203">Şu anda seçili iş akışı sürümü durum penceresi görüntülenen sürüm bilgilerini bakarak belirleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="46460-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="46460-204">Tahminler girin ve durum eşleşme güncelleştirildiğine dikkat `WriteLine` etkinlik çıkış önceki bir sürümden ve kullanıcının tahmin içermez.</span><span class="sxs-lookup"><span data-stu-id="46460-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="46460-205">Bu iş akışları sahip olmayan önceki iş akışı tanımı kullandığından olan `WriteLine` güncelleştirmeler.</span><span class="sxs-lookup"><span data-stu-id="46460-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="46460-206">Sonraki adımda [nasıl yapılır: iş akışı örneği çalışma tanım güncelleştirme](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), çalışan `v1` iş akışı örnekleri olarak yeni işlevsellik içerdikleri şekilde güncelleştirilir `v2` örnekleri.</span><span class="sxs-lookup"><span data-stu-id="46460-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>