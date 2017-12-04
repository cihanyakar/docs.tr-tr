---
title: "ICLRTask2::EndPreventAsyncAbort Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.EndPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c76a75004b4593e8e93aa4dd999c85c0fb7cf38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="e8e48-102">ICLRTask2::EndPreventAsyncAbort Yöntemi</span><span class="sxs-lookup"><span data-stu-id="e8e48-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="e8e48-103">Yeni izin verir veya bekleyen iş parçacığı elde etmek iş parçacığı durdurma isteği geçerli iş parçacığı üzerinde durdurur.</span><span class="sxs-lookup"><span data-stu-id="e8e48-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e48-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e8e48-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e8e48-105">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="e8e48-105">Return Value</span></span>  
 <span data-ttu-id="e8e48-106">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="e8e48-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e8e48-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8e48-107">HRESULT</span></span>|<span data-ttu-id="e8e48-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e8e48-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8e48-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8e48-109">S_OK</span></span>|<span data-ttu-id="e8e48-110">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="e8e48-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="e8e48-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="e8e48-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="e8e48-112">Yöntemi, geçerli iş parçacığının olmayan bir iş parçacığında çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="e8e48-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8e48-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e8e48-113">Remarks</span></span>  
 <span data-ttu-id="e8e48-114">Bu yöntem azaltır gecikme iş parçacığı durdurma sayaç için geçerli iş parçacığı tarafından çağrılıyor.</span><span class="sxs-lookup"><span data-stu-id="e8e48-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="e8e48-115">Çağrılar [Iclrtask2::beginpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) ve `EndPreventAsyncAbort` iç içe olamaz.</span><span class="sxs-lookup"><span data-stu-id="e8e48-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="e8e48-116">Sayaç sıfırdan büyük olduğu sürece, geçerli iş parçacığı için iş parçacığı iptalleri gecikir.</span><span class="sxs-lookup"><span data-stu-id="e8e48-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="e8e48-117">Bu özellik tarafından sunulan işlevselliği sanal makine (VM) tarafından dahili olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e8e48-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="e8e48-118">Bu yöntemlerin kötüye VM'yi belirtilmeyen davranışlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="e8e48-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="e8e48-119">Örneğin, arama `EndPreventAsyncAbort` ilk çağırmadan `BeginPreventAsyncAbort` VM daha önce onu artar olduğunda Sayaç sıfıra ayarlanamıyor.</span><span class="sxs-lookup"><span data-stu-id="e8e48-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="e8e48-120">Benzer şekilde, iç sayaç için taşma işaretlenmemiştir.</span><span class="sxs-lookup"><span data-stu-id="e8e48-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="e8e48-121">Konak ve VM tarafından artırılır çünkü tam sayı sınırını aşarsa, bunun sonucunda oluşan davranışı belirtilmemiş.</span><span class="sxs-lookup"><span data-stu-id="e8e48-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8e48-122">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e8e48-122">Requirements</span></span>  
 <span data-ttu-id="e8e48-123">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8e48-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8e48-124">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8e48-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8e48-125">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="e8e48-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8e48-126">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8e48-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e48-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e8e48-127">See Also</span></span>  
 [<span data-ttu-id="e8e48-128">BeginPreventAsyncAbort yöntemi</span><span class="sxs-lookup"><span data-stu-id="e8e48-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="e8e48-129">Iclrtask2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="e8e48-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="e8e48-130">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="e8e48-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e8e48-131">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="e8e48-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e8e48-132">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="e8e48-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="e8e48-133">Barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="e8e48-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)