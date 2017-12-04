---
title: "Hello World özel etkinlik"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b717a5448a32eea3957e1e7e45c4dfc2f8801775
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="20d2b-102">Hello World özel etkinlik</span><span class="sxs-lookup"><span data-stu-id="20d2b-102">Hello World Custom Activity</span></span>
<span data-ttu-id="20d2b-103">Bu örnek birkaç anahtar özelliklerini gösterir [!INCLUDE[wf](../../../../includes/wf-md.md)], basit bir özel etkinlik oluşturmak nasıl dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="20d2b-103">This sample demonstrates several key features of [!INCLUDE[wf](../../../../includes/wf-md.md)], including how to create a simple custom activity.</span></span> <span data-ttu-id="20d2b-104">Bu örnekte gösterilen özelliklerden bazıları C# ve kullanarak özel bir aktivite oluşturmakta olduğunuz `in` ve `out` bağımsız değişkenler (<xref:System.Activities.InArgument> ve <xref:System.Activities.OutArgument>).</span><span class="sxs-lookup"><span data-stu-id="20d2b-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20d2b-105">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="20d2b-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="20d2b-106">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="20d2b-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20d2b-107">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="20d2b-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20d2b-108">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="20d2b-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="20d2b-109">Kodda bir iş akışı oluşturma</span><span class="sxs-lookup"><span data-stu-id="20d2b-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="20d2b-110">Bu örnekte, iki özel etkinlikler, C# kod kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="20d2b-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="20d2b-111">Her iki özel etkinlikler doğrudan veya dolaylı olarak devralınmalıdır <xref:System.Activities.Activity%601> tek bir değer döndürmek için.</span><span class="sxs-lookup"><span data-stu-id="20d2b-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="20d2b-112">Genel olmayan devralan yerine genel dönüş değeri kullanmanın avantajı <xref:System.Activities.Activity> sınıfı, bazı etkinlikler olan (gibi <xref:System.Activities.Statements.Assign>) oluşan bir etkinlik bir parçası olarak kullanıldığında dönüş değeri erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="20d2b-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="20d2b-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="20d2b-113">AppendString</span></span>  
 <span data-ttu-id="20d2b-114">Bu etkinlik devraldığı <xref:System.Activities.Activity%601>ve kullandığı bir <xref:System.Activities.Statements.Assign> birlikte iki dizeyi art arda ekler etkinlik.</span><span class="sxs-lookup"><span data-stu-id="20d2b-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="20d2b-115">Dize önüne ekleyin</span><span class="sxs-lookup"><span data-stu-id="20d2b-115">Prepend String</span></span>  
 <span data-ttu-id="20d2b-116">Bu etkinlik doğrudan devraldığı <xref:System.Activities.CodeActivity%601>ve benzer işlevsellik oluşturur `AppendString` kodu yerine önceden var olan bir etkinliğin oluşturuluyor uygulanan mantığını kullanır etkinlik.</span><span class="sxs-lookup"><span data-stu-id="20d2b-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="20d2b-117">Aşağıdaki dosyaları, bu projede dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="20d2b-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="20d2b-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="20d2b-118">AppendString.cs</span></span>  
 <span data-ttu-id="20d2b-119">Dizeleri birlikte ekler Özel Etkinlik.</span><span class="sxs-lookup"><span data-stu-id="20d2b-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="20d2b-120">Bir dize alır ve "Merhaba Dünya form çıktı olarak tam bir ileti söyler" bir metin dizesiyle birleştirir.</span><span class="sxs-lookup"><span data-stu-id="20d2b-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="20d2b-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="20d2b-121">PrependString.cs</span></span>  
 <span data-ttu-id="20d2b-122">Bu etkinliğin bir giriş dizesi için önceden tanımlanmış bir dize ekler.</span><span class="sxs-lookup"><span data-stu-id="20d2b-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="20d2b-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="20d2b-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="20d2b-124">Kullanan bir iş akışı `AppendString` ve `PrependString` özel etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="20d2b-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="20d2b-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="20d2b-125">Program.cs</span></span>  
 <span data-ttu-id="20d2b-126">İş akışı tarafından çalıştırılan bir program.</span><span class="sxs-lookup"><span data-stu-id="20d2b-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="20d2b-127">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="20d2b-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="20d2b-128">Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], HelloWorld.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="20d2b-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="20d2b-129">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="20d2b-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="20d2b-130">Çözümü çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="20d2b-130">To run the solution, press F5.</span></span>