---
title: "Kesinlik temelli kod tabanlı doğrulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92cb1d88ff74dd685f10330b914b857258c05860
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="3f0cb-102">Kesinlik temelli kod tabanlı doğrulama</span><span class="sxs-lookup"><span data-stu-id="3f0cb-102">Imperative Code-Based Validation</span></span>
<span data-ttu-id="3f0cb-103">Kesinlik temelli kod tabanlı doğrulama kendisi hakkında doğrulama sağlamak bir etkinlik için basit bir yol sağlar ve türetilen etkinlikler için kullanılabilir <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, ve <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="3f0cb-104">Herhangi bir doğrulama hata veya uyarı belirler doğrulama kodunu aktivite eklenir.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="3f0cb-105">Kod tabanlı doğrulama kullanma</span><span class="sxs-lookup"><span data-stu-id="3f0cb-105">Using Code-Based Validation</span></span>  
 <span data-ttu-id="3f0cb-106">Kod tabanlı doğrulama öğesinden türetilen etkinlikleri tarafından desteklenen <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, ve <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="3f0cb-107">Doğrulama kodu yerleştirilebilen <xref:System.Activities.CodeActivity.CacheMetadata%2A> geçersiz kıl ve doğrulama hatalar veya uyarılar meta verileri bağımsız değişkeni olarak eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="3f0cb-108">Aşağıdaki örnekte, geçen [temel doğrulama](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) , örnek `Cost` değerinden daha büyük `Price`, meta veriler için bir doğrulama hatası eklenir.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-108">In the following example, taken from the [Basic Validation](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) sample, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f0cb-109">Unutmayın `Cost` ve `Price` etkinlik bağımsız değişkenleri değildir, ancak tasarım zamanında ayarlama özelliklerdir.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="3f0cb-110">Diğer bir deyişle neden değerlerine içinde doğrulanabilir <xref:System.Activities.CodeActivity.CacheMetadata%2A> geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="3f0cb-111">Veri çalışma zamanına kadar akış değil, ancak etkinlik bağımsız değişkenler doğrulanmış bunlar kullanarak bağlı emin olmak için tasarım zamanında bir bağımsız değişken akan verilere değeri doğrulanamıyor `RequiredArgument` özniteliği ve grupları aşırı yükleme.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="3f0cb-112">Bu kod örneği görür `RequiredArgument` için öznitelik `Description` bağımsız değişkeni ve bağlı değilse sonra bir doğrulama hatası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="3f0cb-113">Gerekli bağımsız ele alınmıştır [gerekli bağımsız değişkenleri ve aşırı grupları](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3f0cb-113">Required arguments are covered in [Required Arguments and Overload Groups](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="3f0cb-114">Varsayılan olarak, meta veriler için bir doğrulama hatası eklenir, <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="3f0cb-115">Doğrulama uyarısı eklemek için kullanın <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> alan aşırı bir <xref:System.Activities.Validation.ValidationError>, belirleyen <xref:System.Activities.Validation.ValidationError> ayarlayarak bir uyarı temsil eden <xref:System.Activities.Validation.ValidationError.IsWarning%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="3f0cb-116">Bir iş akışı iş akışı Tasarımcısı'nda değiştirilir ve herhangi bir doğrulama hata veya uyarı iş akışı Tasarımcısı'nda görüntülenen doğrulama oluşur.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="3f0cb-117">Doğrulama da ortaya çıkar çalışma zamanında bir iş akışı çalıştırıldığında ve herhangi bir doğrulama hatası oluşursa, bir <xref:System.Activities.InvalidWorkflowException> varsayılan Doğrulama mantığı tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="3f0cb-118">doğrulama çağırma ve herhangi bir doğrulama uyarılar veya hatalar, erişme bkz [çağırma etkinlik doğrulama](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="3f0cb-118"> invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="3f0cb-119">Öğesinden oluşturulan özel durumlar <xref:System.Activities.CodeActivity.CacheMetadata%2A> doğrulama hata olarak kabul edilmediği.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="3f0cb-120">Bu özel durumlar için çağrısından kaçış <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> ve çağıran tarafından yapılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="3f0cb-121">Kod tabanlı doğrulama kodunu içeren aktiviteyi doğrulamak için yararlıdır, ancak diğer etkinlikler görünürlük iş akışı içinde yok.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="3f0cb-122">Bildirim temelli kısıtlamaları doğrulama aktivite ve iş akışındaki diğer etkinlikleri arasındaki ilişkileri doğrulama olanağı sağlar ve içinde ele [bildirim temelli kısıtlamaları](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) konu.</span><span class="sxs-lookup"><span data-stu-id="3f0cb-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) topic.</span></span>