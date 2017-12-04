---
title: "ICorDebugClass2::SetJMCStatus Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da9f61bd9a652b4c8e340ddecdee4b48bbdb086e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="b39d5-102">ICorDebugClass2::SetJMCStatus Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b39d5-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="b39d5-103">Her sınıf yöntemi için yöntem kullanıcı tanımlı kod olup olmadığını belirten bir değer ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b39d5-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b39d5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b39d5-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b39d5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b39d5-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="b39d5-106">[in] Kümesine `true` yöntemi kullanıcı tanımlı olduğunu belirtmek için; Aksi takdirde kümesine kodu `false`.</span><span class="sxs-lookup"><span data-stu-id="b39d5-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b39d5-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b39d5-107">Remarks</span></span>  
 <span data-ttu-id="b39d5-108">Yalnızca-my-code (JMC) Adımlayıcı kullanıcı tanımlı olmayan kod atlar.</span><span class="sxs-lookup"><span data-stu-id="b39d5-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="b39d5-109">Kullanıcı tanımlı kod bir alt kümesini debuggable kodu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b39d5-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="b39d5-110">`SetJMCStatus`başarıyla diğer tüm yöntemleri için değeri ayarlar olsa bile herhangi bir yöntem değerini ayarlamak başarısız olursa S_FALSE HRESULT değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="b39d5-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b39d5-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b39d5-111">Requirements</span></span>  
 <span data-ttu-id="b39d5-112">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b39d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b39d5-113">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b39d5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b39d5-114">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b39d5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b39d5-115">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b39d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>