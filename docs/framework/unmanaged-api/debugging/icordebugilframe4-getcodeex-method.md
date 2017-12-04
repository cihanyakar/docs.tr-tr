---
title: ICorDebugILFrame4::GetCodeEx Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc80882353bd7a9861f4db79b83493d1cef7bfee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="42590-102">ICorDebugILFrame4::GetCodeEx Metodu</span><span class="sxs-lookup"><span data-stu-id="42590-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="42590-103">[.NET Framework 4.5.2 ve sonraki sürümlerinde desteklenen]</span><span class="sxs-lookup"><span data-stu-id="42590-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="42590-104">Bir işaretçi Bu yığın çerçevesi yürütülen kodu alır.</span><span class="sxs-lookup"><span data-stu-id="42590-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42590-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="42590-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42590-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="42590-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="42590-107">[in] Bir [Ilcodekind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) Profil Oluşturucu'nın ReJIT isteği tarafından tanımlanan Ara dile (IL) çerçevede dahil edilip edilmediğini belirten numaralandırma üyesi.</span><span class="sxs-lookup"><span data-stu-id="42590-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="42590-108">[out] Bir işaretçi adresine "ICorDebugCode" nesnenin Bu yığın çerçevesi yürütüyor kodunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="42590-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42590-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="42590-109">Remarks</span></span>  
 <span data-ttu-id="42590-110">Bu yöntem benzer [Icordebugframe::getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) olan isteğe bağlı olarak kod Profil Oluşturucu'nın ReJIT isteği tarafından tanımlanan erişen dışında yöntemi.</span><span class="sxs-lookup"><span data-stu-id="42590-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="42590-111">Bu yöntem çağırma bir `flags` değerini `ILCODE_ORIGINAL_IL` arama için eşdeğer bir gruba [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); yöntemi sürümlerde desteklenir, kendi IL erişilemeyecek.</span><span class="sxs-lookup"><span data-stu-id="42590-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="42590-112">`ILCODE_REJIT_IL`Profil Oluşturucu'nın ReJIT isteği tarafından tanımlanan IL erişmek hata ayıklayıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="42590-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="42590-113">IL izlenmemektedir, `ppCode` olan **null**, ve yöntemi `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="42590-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42590-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="42590-114">Requirements</span></span>  
 <span data-ttu-id="42590-115">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42590-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42590-116">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42590-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42590-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42590-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42590-118">**.NET framework sürümleri:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42590-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42590-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="42590-119">See Also</span></span>  
 [<span data-ttu-id="42590-120">Icordebugılframe4 arabirimi</span><span class="sxs-lookup"><span data-stu-id="42590-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="42590-121">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="42590-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="42590-122">ReJIT: Nasıl yapılır Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="42590-122">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)