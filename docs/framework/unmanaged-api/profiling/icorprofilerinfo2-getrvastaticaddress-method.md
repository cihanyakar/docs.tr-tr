---
title: ICorProfilerInfo2::GetRVAStaticAddress Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64553e8f611a8111aaaf9ababd1a7556f1192740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="4cc18-102">ICorProfilerInfo2::GetRVAStaticAddress Metodu</span><span class="sxs-lookup"><span data-stu-id="4cc18-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="4cc18-103">Belirtilen göreli sanal adres (RAV) statik alan adresini alır.</span><span class="sxs-lookup"><span data-stu-id="4cc18-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc18-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4cc18-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cc18-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4cc18-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="4cc18-106">[in] İstenen RVA statik alan içeren sınıf kimliği.</span><span class="sxs-lookup"><span data-stu-id="4cc18-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="4cc18-107">[in] İstenen RVA statik alan için meta veri belirteci.</span><span class="sxs-lookup"><span data-stu-id="4cc18-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="4cc18-108">[out] RVA statik alan adresini gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="4cc18-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cc18-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4cc18-109">Remarks</span></span>  
 <span data-ttu-id="4cc18-110">`GetRVAStaticAddress` Yöntemi döndürebilir şunlardan biri:</span><span class="sxs-lookup"><span data-stu-id="4cc18-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="4cc18-111">Bir CORPROF_E_DATAINCOMPLETE belirtilen statik alanda belirtilen bağlam bir adres değil atanmışsa HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4cc18-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="4cc18-112">Çöp toplama yığınında olabilir nesneleri adresleri.</span><span class="sxs-lookup"><span data-stu-id="4cc18-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="4cc18-113">Çöp toplama sonra profil oluşturucular geçerli varsayımında bulunmamalıdır şekilde bu adresleri çöp toplama sonra geçersiz hale gelebilir.</span><span class="sxs-lookup"><span data-stu-id="4cc18-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="4cc18-114">Sınıf sınıfı oluşturucusu tamamlanmadan önce `GetRVAStaticAddress` statik alanları bazıları zaten başlatılmış ve atık toplama nesneleri kök dizini değiştirme ancak CORPROF_E_DATAINCOMPLETE tüm kendi statik alanları için döndürür.</span><span class="sxs-lookup"><span data-stu-id="4cc18-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc18-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4cc18-115">Requirements</span></span>  
 <span data-ttu-id="4cc18-116">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cc18-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc18-117">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cc18-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cc18-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc18-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc18-119">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc18-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc18-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4cc18-120">See Also</span></span>  
 [<span data-ttu-id="4cc18-121">Icorprofilerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="4cc18-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="4cc18-122">Icorprofilerınfo2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="4cc18-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)