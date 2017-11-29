---
title: "Hizmet Çerçevesi Meta Verileri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76afc73a-0770-4084-93f3-6701a757911e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3ab689a6a0d9bf91582ced3435439061c655d10e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="service-framework-metadata"></a><span data-ttu-id="e1d7c-102">Hizmet Çerçevesi Meta Verileri</span><span class="sxs-lookup"><span data-stu-id="e1d7c-102">Service Framework Metadata</span></span>
<span data-ttu-id="e1d7c-103">Bu konu hizmet çerçevesi meta verileri tarafından oluşturulan tüm özel durumları listeler.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-103">This topic lists all exceptions generated by Service Framework Metadata.</span></span>  
  
## <a name="exception-list"></a><span data-ttu-id="e1d7c-104">Özel durum listesi</span><span class="sxs-lookup"><span data-stu-id="e1d7c-104">Exception List</span></span>  
  
|<span data-ttu-id="e1d7c-105">Kaynak kodu</span><span class="sxs-lookup"><span data-stu-id="e1d7c-105">Resource Code</span></span>|<span data-ttu-id="e1d7c-106">Kaynak dizesi</span><span class="sxs-lookup"><span data-stu-id="e1d7c-106">Resource String</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="e1d7c-107">AsyncEndCalledOnWrongChannel</span><span class="sxs-lookup"><span data-stu-id="e1d7c-107">AsyncEndCalledOnWrongChannel</span></span>|<span data-ttu-id="e1d7c-108">Zaman uyumsuz bir son yanlış kanalda çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-108">An asynchronous End was called on the wrong channel.</span></span>|  
|<span data-ttu-id="e1d7c-109">AsyncEndCalledWithAnIAsyncResult</span><span class="sxs-lookup"><span data-stu-id="e1d7c-109">AsyncEndCalledWithAnIAsyncResult</span></span>|<span data-ttu-id="e1d7c-110">Zaman uyumsuz sonuç bir IAsyncResult ile farklı bir Begin yönteminden çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-110">An asynchronous End was called with an IAsyncResult from a different Begin method.</span></span>|  
|<span data-ttu-id="e1d7c-111">AttemptedToGetContractTypeForButThatTypeIs1</span><span class="sxs-lookup"><span data-stu-id="e1d7c-111">AttemptedToGetContractTypeForButThatTypeIs1</span></span>|<span data-ttu-id="e1d7c-112">Sözleşme türü için belirtilen alınmaya çalışıldı. Tür bir ServiceContract değil ve bir ServiceContract devralmıyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-112">Attempted to get contract type for the specified.The type is not a ServiceContract and it does not inherit a ServiceContract.</span></span>|  
|<span data-ttu-id="e1d7c-113">CannotHaveTwoOperationsWithTheSameName3</span><span class="sxs-lookup"><span data-stu-id="e1d7c-113">CannotHaveTwoOperationsWithTheSameName3</span></span>|<span data-ttu-id="e1d7c-114">İki işlem, aynı sözleşme aynı ada sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-114">Cannot have two operations in the same contract with the same name.</span></span> <span data-ttu-id="e1d7c-115">Belirtilen tür belirtilen yöntemlere bu kural ihlal ediyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-115">The specified methods in the specified type violate this rule.</span></span> <span data-ttu-id="e1d7c-116">Yöntem adını değiştirme veya OperationContractAttribute adını kullanarak işlemlerden biri adını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-116">Change the name of one of the operations by changing the method name or by using the Name property of OperationContractAttribute.</span></span>|  
|<span data-ttu-id="e1d7c-117">CannotInheritTwoOperationsWithTheSameName3</span><span class="sxs-lookup"><span data-stu-id="e1d7c-117">CannotInheritTwoOperationsWithTheSameName3</span></span>|<span data-ttu-id="e1d7c-118">Aynı ada sahip iki farklı işlemler devralır olamaz.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-118">Cannot inherit two different operations with the same name.</span></span> <span data-ttu-id="e1d7c-119">Belirtilen sözleşmeleri belirtilen işlemi bu kuralı ihlal ediyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-119">The specified operation from the specified contracts violate this rule.</span></span> <span data-ttu-id="e1d7c-120">Yöntem adını değiştirme veya OperationContractAttribute adını kullanarak işlemlerden biri adını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-120">Change the name of one of the operations by changing the method name or by using the Name property of OperationContractAttribute.</span></span>|  
|<span data-ttu-id="e1d7c-121">CantCreateChannelWithManualAddressing</span><span class="sxs-lookup"><span data-stu-id="e1d7c-121">CantCreateChannelWithManualAddressing</span></span>|<span data-ttu-id="e1d7c-122">Bir istek/yanıt ve el ile adresleme gerektiriyor, ancak yalnızca çift yönlü iletişimi destekleyen bir bağlama gerektiren bir sözleşme için bir kanal oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-122">Cannot create a channel for a contract that requires a request/reply and a binding that requires manual addressing but only supports duplex communication.</span></span>|  
|<span data-ttu-id="e1d7c-123">DuplicateBehavior1</span><span class="sxs-lookup"><span data-stu-id="e1d7c-123">DuplicateBehavior1</span></span>|<span data-ttu-id="e1d7c-124">Değer koleksiyonuna eklenemez.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-124">The value cannot be added to the collection.</span></span> <span data-ttu-id="e1d7c-125">Koleksiyon zaten aynı belirtilen türde bir öğe içeriyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-125">The collection already contains an item of the same specified type.</span></span> <span data-ttu-id="e1d7c-126">Bu koleksiyon yalnızca her türünün bir örneği destekler.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-126">This collection only supports one instance of each type.</span></span>|  
|<span data-ttu-id="e1d7c-127">InAContractInheritanceHierarchyIfParentHasCallbackChildMustToo</span><span class="sxs-lookup"><span data-stu-id="e1d7c-127">InAContractInheritanceHierarchyIfParentHasCallbackChildMustToo</span></span>|<span data-ttu-id="e1d7c-128">Belirtilen temel hizmet sözleşmesi belirtilen geri arama sözleşmesi olduğundan, belirtilen türetilen hizmet sözleşmesi ayrıca belirtilen türe veya türetilmiş bir tür geri çağırma sözleşmesi belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-128">Because the specified base service contract has a specified callback contract, the specified derived service contract must also specify either the specified type, or a derived type as its callback contract.</span></span>|  
|<span data-ttu-id="e1d7c-129">InvalidAsyncBeginMethodSignatureForMethod2</span><span class="sxs-lookup"><span data-stu-id="e1d7c-129">InvalidAsyncBeginMethodSignatureForMethod2</span></span>|<span data-ttu-id="e1d7c-130">Zaman uyumsuz başlangıç yöntemi için geçersiz imzası belirtilen belirtilen ServiceContract yazın.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-130">Invalid asynchronous Begin method signature for the specified method in the specified ServiceContract type.</span></span> <span data-ttu-id="e1d7c-131">Başlamak yöntemi son iki bağımsız değişken olarak bir AsyncCallback ve bir nesne getirin ve bir IAsyncResult döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-131">Your begin method must take an AsyncCallback and an object as the last two arguments and return an IAsyncResult.</span></span>|  
|<span data-ttu-id="e1d7c-132">InvalidAsyncEndMethodSignatureForMethod2</span><span class="sxs-lookup"><span data-stu-id="e1d7c-132">InvalidAsyncEndMethodSignatureForMethod2</span></span>|<span data-ttu-id="e1d7c-133">Zaman uyumsuz son yöntemi için geçersiz imzası belirtilen belirtilen ServiceContract yazın.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-133">Invalid asynchronous End method signature for the specified method in the specified ServiceContract type.</span></span> <span data-ttu-id="e1d7c-134">End yöntemi son bağımsız değişkeni olarak bir IAsyncResult almanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-134">Your end method must take an IAsyncResult as the last argument.</span></span>|  
|<span data-ttu-id="e1d7c-135">MessagePropertiesArraySize0</span><span class="sxs-lookup"><span data-stu-id="e1d7c-135">MessagePropertiesArraySize0</span></span>|<span data-ttu-id="e1d7c-136">Geçirilen dizi bu koleksiyonda bulunan tüm özellikleri tutmak için yeterli alan yok.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-136">The array that was passed does not have enough space to hold all the properties contained by this collection.</span></span>|  
|<span data-ttu-id="e1d7c-137">OneWayAndFaultsIncompatible2</span><span class="sxs-lookup"><span data-stu-id="e1d7c-137">OneWayAndFaultsIncompatible2</span></span>|<span data-ttu-id="e1d7c-138">Belirtilen türdeki belirtilen yöntem IsOneWay işaretlenmiş = true ve bir veya daha fazla FaultContractAttributes bildiriyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-138">The specified method in the specified type is marked as IsOneWay=true and declares one or more FaultContractAttributes.</span></span> <span data-ttu-id="e1d7c-139">Tek yönlü yöntemleri FaultContractAttributes bildiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-139">One-way methods cannot declare FaultContractAttributes.</span></span> <span data-ttu-id="e1d7c-140">IsOneWay yanlış olarak değiştirin ya da FaultContractAttributes öğesini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-140">Change IsOneWay to false or remove the FaultContractAttributes.</span></span>|  
|<span data-ttu-id="e1d7c-141">UnsupportedWSDLOnlyOneMessage</span><span class="sxs-lookup"><span data-stu-id="e1d7c-141">UnsupportedWSDLOnlyOneMessage</span></span>|<span data-ttu-id="e1d7c-142">Desteklenmeyen Web Hizmetleri Açıklama Dili.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-142">Unsupported Web Services Description Language.</span></span> <span data-ttu-id="e1d7c-143">Tek bir ileti bölümü hata iletileri için desteklenir.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-143">Only one message part is supported for fault messages.</span></span> <span data-ttu-id="e1d7c-144">Bu hata iletisi için birden fazla ileti bölümü başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-144">This fault message refers to more than one message part.</span></span> <span data-ttu-id="e1d7c-145">Web Hizmetleri Açıklama Dili dosyasına düzenleme erişiminiz varsa, ileti başvuruları yalnızca bir bölümü arıza gibi ek ileti bölümlerini kaldırarak sorunu düzeltebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-145">If you have edit access to the Web Services Description Language file, you can fix the problem by removing the extra message parts such that fault message references just one part.</span></span>|  
|<span data-ttu-id="e1d7c-146">UnsupportedWSDLTheFault</span><span class="sxs-lookup"><span data-stu-id="e1d7c-146">UnsupportedWSDLTheFault</span></span>|<span data-ttu-id="e1d7c-147">Desteklenmeyen Web Hizmetleri Açıklama Dili.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-147">Unsupported Web Services Description Language.</span></span> <span data-ttu-id="e1d7c-148">Hata iletisi bölümü bir öğeye başvuru gerekir.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-148">The fault message part must reference an element.</span></span> <span data-ttu-id="e1d7c-149">Bu hata iletisi, bir öğeye başvurmuyor.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-149">This fault message does not refer to an element.</span></span> <span data-ttu-id="e1d7c-150">Web Hizmetleri tanımlama dili belge düzenleme erişiminiz varsa 'element' özniteliğini kullanarak şema öğesi başvurarak sorunu düzeltebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-150">If you have edit access to the Web Services Definition Language document, you can fix the problem by referencing a schema element using the 'element' attribute.</span></span>|  
|<span data-ttu-id="e1d7c-151">WsdlImportErrorDependencyDetail</span><span class="sxs-lookup"><span data-stu-id="e1d7c-151">WsdlImportErrorDependencyDetail</span></span>|<span data-ttu-id="e1d7c-152">Belirtilen alınırken bir hata oluştu diğer belirtilen değere bağlı olduğundan.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-152">An error occurred while importing the specified that the other specified value is dependent on.</span></span> <span data-ttu-id="e1d7c-153">Xpath da belirtilmiş.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-153">The Xpath is also specified.</span></span>|  
|<span data-ttu-id="e1d7c-154">XsdMissingRequiredAttribute1</span><span class="sxs-lookup"><span data-stu-id="e1d7c-154">XsdMissingRequiredAttribute1</span></span>|<span data-ttu-id="e1d7c-155">Belirtilen eksik özniteliği gerekli.</span><span class="sxs-lookup"><span data-stu-id="e1d7c-155">Missing the specified required attribute.</span></span>|