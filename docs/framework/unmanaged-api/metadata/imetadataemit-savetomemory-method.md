---
title: "IMetaDataEmit::SaveToMemory Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SaveToMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 685ed69964970f505ad6f938af361c48664d2279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="78a98-102">IMetaDataEmit::SaveToMemory Yöntemi</span><span class="sxs-lookup"><span data-stu-id="78a98-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="78a98-103">Bellek belirtilen alan için geçerli kapsamdaki tüm meta verilerini kaydeder.</span><span class="sxs-lookup"><span data-stu-id="78a98-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a98-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="78a98-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78a98-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="78a98-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="78a98-106">[out] Meta veri yazma başlanan adresi.</span><span class="sxs-lookup"><span data-stu-id="78a98-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="78a98-107">[in] Ayrılan belleğin bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="78a98-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a98-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="78a98-108">Requirements</span></span>  
 <span data-ttu-id="78a98-109">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a98-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a98-110">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78a98-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78a98-111">**Kitaplığı:** MSCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="78a98-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a98-112">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a98-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a98-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="78a98-113">See Also</span></span>  
 [<span data-ttu-id="78a98-114">Imetadataemit arabirimi</span><span class="sxs-lookup"><span data-stu-id="78a98-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="78a98-115">Imetadataemit2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="78a98-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)