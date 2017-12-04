---
title: IHostSyncManager Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="97529-102">IHostSyncManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="97529-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="97529-103">Ortak dil çalışma zamanı (CLR) Win32 eşitleme işlevlerini kullanmak yerine ana bilgisayar çağırarak eşitleme temelleri oluşturmak için izin yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="97529-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97529-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="97529-104">Methods</span></span>  
  
|<span data-ttu-id="97529-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="97529-105">Method</span></span>|<span data-ttu-id="97529-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="97529-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97529-107">CreateAutoEvent yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="97529-108">Otomatik sıfırlama olay nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="97529-109">CreateCrst yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="97529-110">Eşitleme için bir kritik bölüm nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="97529-111">CreateCrstWithSpinCount yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="97529-112">Eşitleme için döndürme sayısı ile bir kritik bölüm nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="97529-113">CreateManualEvent yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="97529-114">El ile sıfırlama olay nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="97529-115">CreateMonitorEvent yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="97529-116">İzlenen otomatik sıfırlama olay nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="97529-117">CreateRWLockReaderEvent yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="97529-118">Bir okuyucu kilidini uygulanması için el ile sıfırlama olay nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="97529-119">CreateRWLockWriterEvent yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="97529-120">Bir yazıcı kilidi uygulama için bir otomatik sıfırlama olay nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="97529-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="97529-121">CreateSemaphore yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="97529-122">Oluşturur bir [Ihostsemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) bekleme olayları için semafor kullanılacak CLR nesnesi.</span><span class="sxs-lookup"><span data-stu-id="97529-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="97529-123">SetCLRSyncManager yöntemi</span><span class="sxs-lookup"><span data-stu-id="97529-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="97529-124">Ayarlar [Iclrsyncmanager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) geçerli ilişkilendirmek için örnek `IHostSyncManager` örneği.</span><span class="sxs-lookup"><span data-stu-id="97529-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97529-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="97529-125">Remarks</span></span>  
 <span data-ttu-id="97529-126">Ana bilgisayarın uyarlamasını CLR bulur `IHostSyncManager` çağırarak [Ihostcontrol::gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) yöntemi ile bir `IID` IID_IHostSyncManager biri.</span><span class="sxs-lookup"><span data-stu-id="97529-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97529-127">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="97529-127">Requirements</span></span>  
 <span data-ttu-id="97529-128">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97529-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97529-129">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97529-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97529-130">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="97529-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97529-131">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97529-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97529-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="97529-132">See Also</span></span>  
 [<span data-ttu-id="97529-133">Iclrsyncmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="97529-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="97529-134">Barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="97529-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)