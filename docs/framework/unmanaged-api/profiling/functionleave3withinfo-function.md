---
title: "FunctionLeave3WithInfo İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave3WithInfo
helpviewer_keywords: FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e42614531afb11a811e8862abad0caddf8873483
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="b928f-102">FunctionLeave3WithInfo İşlevi</span><span class="sxs-lookup"><span data-stu-id="b928f-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="b928f-103">Profil Oluşturucu denetim bir işlevinden döndürülen olduğunu bildirir ve için geçirilen tanıtıcı sağlar [Icorprofilerınfo3::getfunctionleave3ınfo yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) yığın çerçevesi ve dönüş değeri alınamadı.</span><span class="sxs-lookup"><span data-stu-id="b928f-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b928f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b928f-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b928f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b928f-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="b928f-106">[in] Denetim döndürülen işlevi tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="b928f-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="b928f-107">[in] Verilen yığın çerçevesi ilgili bilgileri temsil eder donuk işleci.</span><span class="sxs-lookup"><span data-stu-id="b928f-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="b928f-108">Bu tanıtıcı geçirilen yalnızca geri çağırma sırasında geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="b928f-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b928f-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b928f-109">Remarks</span></span>  
 <span data-ttu-id="b928f-110">`FunctionLeave3WithInfo` Geri çağırma yöntemi olarak işlevler olarak adlandırılır ve kullanmak profil oluşturucu sağlar profil oluşturucu bildirir [Icorprofilerınfo3::getfunctionleave3ınfo yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) dönüş değerini denetlemek için.</span><span class="sxs-lookup"><span data-stu-id="b928f-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="b928f-111">Dönüş değeri bilgilere erişmek için `COR_PRF_ENABLE_FUNCTION_RETVAL` bayrağı ayarlanmış olması gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="b928f-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="b928f-112">Profil Oluşturucu kullanabilirsiniz [Icorprofilerınfo::seteventmask yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) olay bayraklarını ayarlayın ve sonra kullanmak için [Icorprofilerınfo3::setenterleavefunctionhooks3withınfo yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) kaydetmek için Bu işlev uygulaması.</span><span class="sxs-lookup"><span data-stu-id="b928f-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b928f-113">`FunctionLeave3WithInfo` İşlevi bir geri çağırma; uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b928f-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="b928f-114">Uygulama kullanmalısınız `__declspec(naked)` depolama sınıfı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="b928f-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b928f-115">Yürütme altyapısı, bu işlevi çağrılmadan önce tüm kayıtları kaydetmez.</span><span class="sxs-lookup"><span data-stu-id="b928f-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="b928f-116">Girişte kayan nokta birim (FPU) de dahil olmak üzere, kullandığınız tüm kayıtları kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b928f-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="b928f-117">Çıkış yapıldığında, çağıran tarafından gönderilen tüm parametreleri kapalı pencerelerinin tarafından yığın geri yüklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b928f-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b928f-118">Uygulaması `FunctionLeave3WithInfo` çöp toplama geciktirir çünkü bloğunu değil.</span><span class="sxs-lookup"><span data-stu-id="b928f-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="b928f-119">Yığın bir atık toplama kolay durumda olmayabileceğinden uygulaması bir atık toplama çalışmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="b928f-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b928f-120">Çöp toplama bulamazsa, çalışma zamanı kadar engeller `FunctionLeave3WithInfo` döndürür.</span><span class="sxs-lookup"><span data-stu-id="b928f-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="b928f-121">`FunctionLeave3WithInfo` İşlevi gerekir değil yönetilen koda çağrı veya herhangi bir şekilde bir yönetilen bellek ayırma neden.</span><span class="sxs-lookup"><span data-stu-id="b928f-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b928f-122">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b928f-122">Requirements</span></span>  
 <span data-ttu-id="b928f-123">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b928f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b928f-124">**Başlık:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b928f-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b928f-125">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b928f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b928f-126">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b928f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b928f-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b928f-127">See Also</span></span>  
 [<span data-ttu-id="b928f-128">Getfunctionleave3ınfo</span><span class="sxs-lookup"><span data-stu-id="b928f-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)  
 [<span data-ttu-id="b928f-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b928f-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="b928f-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b928f-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="b928f-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b928f-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="b928f-132">Functionenter3withınfo</span><span class="sxs-lookup"><span data-stu-id="b928f-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="b928f-133">Functiontailcall3withınfo</span><span class="sxs-lookup"><span data-stu-id="b928f-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="b928f-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b928f-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="b928f-135">Setenterleavefunctionhooks3withınfo</span><span class="sxs-lookup"><span data-stu-id="b928f-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="b928f-136">Setfunctionıdmapper</span><span class="sxs-lookup"><span data-stu-id="b928f-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="b928f-137">Setfunctionıdmapper2</span><span class="sxs-lookup"><span data-stu-id="b928f-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="b928f-138">Profil oluşturma genel statik işlevleri</span><span class="sxs-lookup"><span data-stu-id="b928f-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)