---
title: MsmqBindingElementBase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b70b4b4a1529085cba8625598f56a9eece07e866
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="635cd-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="635cd-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="635cd-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="635cd-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635cd-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="635cd-104">Syntax</span></span>  
  
```  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="635cd-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="635cd-105">Methods</span></span>  
 <span data-ttu-id="635cd-106">MsmqBindingElementBase sınıfı herhangi bir yöntem tanımlamıyor.</span><span class="sxs-lookup"><span data-stu-id="635cd-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="635cd-107">Özellikler</span><span class="sxs-lookup"><span data-stu-id="635cd-107">Properties</span></span>  
 <span data-ttu-id="635cd-108">MsmqBindingElementBase sınıfı aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="635cd-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="635cd-109">customDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="635cd-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="635cd-110">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="635cd-110">Data type: string</span></span>  
  
 <span data-ttu-id="635cd-111">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-112">Süresi dolan veya aktarımı veya teslim başarısız olmuş iletileri yerleştirildiği her uygulama için sahipsiz sıra konumunu içeren bir URI.</span><span class="sxs-lookup"><span data-stu-id="635cd-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="635cd-113">deadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="635cd-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="635cd-114">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="635cd-114">Data type: string</span></span>  
  
 <span data-ttu-id="635cd-115">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-116">Kullanılacak sahipsiz sıra türünü gösteren bir numaralandırma değeri.</span><span class="sxs-lookup"><span data-stu-id="635cd-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="635cd-117">dayanıklı</span><span class="sxs-lookup"><span data-stu-id="635cd-117">Durable</span></span>  
 <span data-ttu-id="635cd-118">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="635cd-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="635cd-119">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-120">Bu bağlama tarafından işlenen iletilerin kalıcı veya geçici olup olmadığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="635cd-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="635cd-121">exactlyOnce</span><span class="sxs-lookup"><span data-stu-id="635cd-121">ExactlyOnce</span></span>  
 <span data-ttu-id="635cd-122">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="635cd-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="635cd-123">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-124">Bu bağlama tarafından işlenen iletilerin tam olarak bir kez alınan olup olmadığını gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="635cd-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="635cd-125">maxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="635cd-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="635cd-126">Veri türü: SINT32</span><span class="sxs-lookup"><span data-stu-id="635cd-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="635cd-127">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-128">İletileri teslim alma işlemini yapan uygulamanın için denemek için yeniden deneme döngüsü sayısı.</span><span class="sxs-lookup"><span data-stu-id="635cd-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="635cd-129">receiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="635cd-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="635cd-130">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="635cd-130">Data type: string</span></span>  
  
 <span data-ttu-id="635cd-131">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-132">Zehirli ileti işleme yönelik ayarlar.</span><span class="sxs-lookup"><span data-stu-id="635cd-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="635cd-133">receiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="635cd-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="635cd-134">Veri türü: SINT32</span><span class="sxs-lookup"><span data-stu-id="635cd-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="635cd-135">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-136">Hemen yeniden deneme sayısı uygulama sırasından okunan bir ileti üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="635cd-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="635cd-137">retryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="635cd-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="635cd-138">Veri türü: datetime</span><span class="sxs-lookup"><span data-stu-id="635cd-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="635cd-139">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-140">Yeniden deneme arasındaki gecikme süresini belirten bir değer hemen teslim edilemeyen bir ileti teslim çalışılırken geçiş yapar.</span><span class="sxs-lookup"><span data-stu-id="635cd-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="635cd-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="635cd-141">TimeToLive</span></span>  
 <span data-ttu-id="635cd-142">Veri türü: datetime</span><span class="sxs-lookup"><span data-stu-id="635cd-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="635cd-143">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-144">Süresi dolmadan önce bu bağlama tarafından işlenen ne kadar süreyle iletileri gösterir zaman aralığını sırada olabilir.</span><span class="sxs-lookup"><span data-stu-id="635cd-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="635cd-145">useMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="635cd-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="635cd-146">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="635cd-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="635cd-147">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-148">Bu bağlama tarafından işlenen iletileri olup olmadığını gösteren bir Boole değeri izlenen.</span><span class="sxs-lookup"><span data-stu-id="635cd-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="635cd-149">useSourceJournal</span><span class="sxs-lookup"><span data-stu-id="635cd-149">UseSourceJournal</span></span>  
 <span data-ttu-id="635cd-150">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="635cd-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="635cd-151">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="635cd-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="635cd-152">Bu bağlama tarafından işlenen iletilerin kopyalarını kaynak günlük sırasındaki depolanması gerekip gerekmediğini gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="635cd-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635cd-153">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="635cd-153">Requirements</span></span>  
  
|<span data-ttu-id="635cd-154">MOF</span><span class="sxs-lookup"><span data-stu-id="635cd-154">MOF</span></span>|<span data-ttu-id="635cd-155">Bildirilen Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="635cd-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="635cd-156">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="635cd-156">Namespace</span></span>|<span data-ttu-id="635cd-157">İçinde tanımlanan root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="635cd-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="635cd-158">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="635cd-158">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>