---
title: ICorDebugRuntimeUnwindableFrame Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 003bbab399a9ad0ffe2f1d761aea18ff71ba1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="71a93-102">ICorDebugRuntimeUnwindableFrame Arabirimi</span><span class="sxs-lookup"><span data-stu-id="71a93-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="71a93-103">Çerçeveyi geriye doğru izlemek için ortak dil çalışma zamanı (CLR) gerektiren yönetilmeyen yöntemler için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="71a93-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71a93-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="71a93-104">Remarks</span></span>  
 <span data-ttu-id="71a93-105">`ICorDebugRuntimeUnwindableFrame`Icordebugframe arabirimi, özelleştirilmiş bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="71a93-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="71a93-106">Geçerli yığın çerçevesinde bırakma için çalışma zamanı gerektiren yönetilmeyen yöntemleri tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="71a93-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="71a93-107">JIT derlenmiş kod kullanmadığından varolan unwinding kuralları çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="71a93-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="71a93-108">Hata ayıklayıcı unwindable çerçeve gördüğünde kullanması gereken [Icordebugstackwalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) , ancak bunu bırakma yöntemi denetleme kendisini gerçekleştirmek.</span><span class="sxs-lookup"><span data-stu-id="71a93-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="71a93-109">Hata ayıklayıcıyı zaman alan bir `ICorDebugRuntimeUnwindableFrame`, işleyememesi [Icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) çerçeve bağlamı alma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="71a93-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a93-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="71a93-110">Requirements</span></span>  
 <span data-ttu-id="71a93-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a93-112">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a93-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71a93-114">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a93-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="71a93-115">See Also</span></span>  
 [<span data-ttu-id="71a93-116">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="71a93-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="71a93-117">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="71a93-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)