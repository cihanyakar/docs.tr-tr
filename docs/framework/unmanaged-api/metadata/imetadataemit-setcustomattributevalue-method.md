---
title: "IMetaDataEmit::SetCustomAttributeValue Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetCustomAttributeValue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 30538b0f6f6aa196edf8373f5f4e6f09ba903223
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="0f296-102">IMetaDataEmit::SetCustomAttributeValue Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0f296-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="0f296-103">Ayarlar veya önceki bir çağrı tarafından tanımlanan özel bir öznitelik değeri güncelleştirmeler [Imetadataemit::definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f296-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f296-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0f296-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f296-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0f296-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="0f296-106">[in] Hedef özel öznitelik belirteci.</span><span class="sxs-lookup"><span data-stu-id="0f296-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="0f296-107">[in] Özel öznitelik içeren bir dizi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="0f296-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="0f296-108">[in] Özel özniteliğinin bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="0f296-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f296-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0f296-109">Requirements</span></span>  
 <span data-ttu-id="0f296-110">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f296-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f296-111">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f296-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f296-112">**Kitaplığı:** MSCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="0f296-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f296-113">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f296-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f296-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0f296-114">See Also</span></span>  
 [<span data-ttu-id="0f296-115">Imetadataemit arabirimi</span><span class="sxs-lookup"><span data-stu-id="0f296-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0f296-116">Imetadataemit2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="0f296-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)