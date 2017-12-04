---
title: "Çekme etkinliğini kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18c8af9717cb03bd262ceb0a62c91dbc778071c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="44441-102">Çekme etkinliğini kullanma</span><span class="sxs-lookup"><span data-stu-id="44441-102">Using the Pick Activity</span></span>
<span data-ttu-id="44441-103">Bu örnek nasıl kullanılacağı ortaya <xref:System.Activities.Statements.Pick> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="44441-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="44441-104"><xref:System.Activities.Statements.Pick> Etkinlik olay tabanlı denetim modelleme sağlar.</span><span class="sxs-lookup"><span data-stu-id="44441-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="44441-105">C# benzer şekilde davranır `switch` dallarda yalnızca biri yürütür deyimi `switch` deyimi.</span><span class="sxs-lookup"><span data-stu-id="44441-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="44441-106">Farklı `switch` bir dal yürütüldüğünde deyimi dayalı olarak bir değer üzerinde <xref:System.Activities.Statements.Pick> etkinlik nasıl bir etkinlik tamamlandıktan sonra dayalı bir dal yürütür.</span><span class="sxs-lookup"><span data-stu-id="44441-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="44441-107">Bu örnek adlarının konsolunda belirli bir süre içinde yazmak için bir kullanıcıya sorar.</span><span class="sxs-lookup"><span data-stu-id="44441-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="44441-108"><xref:System.Activities.Statements.Pick> Örnek etkinlik sahip olup olmadığını kullanıcı adında 5 saniye içinde veya türleri üzerinde temel yürütülen iki dalı.</span><span class="sxs-lookup"><span data-stu-id="44441-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="44441-109">Kullanıcı adında 5 saniye içinde yazdığında ilk dal, özel bir içeren yürütülür `ReadLine` etkinlik; Aksi takdirde diğer dal, içeren yürütülür bir <xref:System.Activities.Statements.Delay> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="44441-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="44441-110">Bir kullanıcının adını konsolda yazılmış sonra kullanıcı adını konsola yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="44441-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="44441-111">Giriş 5 saniye içinde girilmezse, işlemi zaman aşımına.</span><span class="sxs-lookup"><span data-stu-id="44441-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="44441-112">Gösteriler</span><span class="sxs-lookup"><span data-stu-id="44441-112">Demonstrates</span></span>  
 <span data-ttu-id="44441-113"><xref:System.Activities.Statements.Pick>Etkinlik.</span><span class="sxs-lookup"><span data-stu-id="44441-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="44441-114">Tartışma</span><span class="sxs-lookup"><span data-stu-id="44441-114">Discussion</span></span>  
 <span data-ttu-id="44441-115">Örnek İş Akışı Tasarımcısı ve kodlanmış iş akışı içerir.</span><span class="sxs-lookup"><span data-stu-id="44441-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="44441-116">İş Akışı Tasarımcısı</span><span class="sxs-lookup"><span data-stu-id="44441-116">Designer Workflow</span></span>  
 <span data-ttu-id="44441-117">Örnek Tasarımcısı sürümü, bir iş akışı Tasarımcısı'nda oluşturma gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="44441-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="44441-118">Aşağıdaki dosyalar eklenmiştir:</span><span class="sxs-lookup"><span data-stu-id="44441-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="44441-119">Program.cs: İçerir `Main` örnek iş akışı yürüten işlev.</span><span class="sxs-lookup"><span data-stu-id="44441-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="44441-120">ReadString.cs: bazı giriş konsoldan okuyan bir özel etkinlik.</span><span class="sxs-lookup"><span data-stu-id="44441-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="44441-121">Sequence1.XAML: kullanır çekme Tasarımcı kullanarak bir iş akışı oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="44441-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="44441-122">Kodlanmış iş akışı</span><span class="sxs-lookup"><span data-stu-id="44441-122">Coded Workflow</span></span>  
 <span data-ttu-id="44441-123">Örnek kodlanmış sürümü, bir iş akışı Tasarımcısı'nda oluşturma gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="44441-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="44441-124">Aşağıdaki dosyalar eklenmiştir:</span><span class="sxs-lookup"><span data-stu-id="44441-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="44441-125">Program.cs: İçerir `Main` örnek iş akışı yürüten işlev.</span><span class="sxs-lookup"><span data-stu-id="44441-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="44441-126">ReadString.cs: bazı giriş konsoldan okuyan bir özel etkinlik.</span><span class="sxs-lookup"><span data-stu-id="44441-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="44441-127">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="44441-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="44441-128">Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], Pick.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="44441-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="44441-129">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="44441-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="44441-130">Çözümü çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="44441-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44441-131">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="44441-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44441-132">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="44441-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44441-133">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="44441-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44441-134">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="44441-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`