---
title: ISymUnmanagedMethod::GetParameters Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetParameters
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 057cafc5270eeb82b4c9b9becac59ea45ea21371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="18b1a-102">ISymUnmanagedMethod::GetParameters Metodu</span><span class="sxs-lookup"><span data-stu-id="18b1a-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="18b1a-103">Bu yöntem için parametre alır.</span><span class="sxs-lookup"><span data-stu-id="18b1a-103">Gets the parameters for this method.</span></span> <span data-ttu-id="18b1a-104">Parametreleri yöntemin imzası içinde tanımlanan sırada döndürülür.</span><span class="sxs-lookup"><span data-stu-id="18b1a-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b1a-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="18b1a-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18b1a-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="18b1a-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="18b1a-107">[in] Boyutunu `params` dizi.</span><span class="sxs-lookup"><span data-stu-id="18b1a-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="18b1a-108">[in] Bir işaretçi bir `ULONG32` parametreleri içermesi için gerekli arabellek boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="18b1a-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="18b1a-109">[out] Parametreleri alır arabellek için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="18b1a-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18b1a-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="18b1a-110">Return Value</span></span>  
 <span data-ttu-id="18b1a-111">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="18b1a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18b1a-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="18b1a-112">Requirements</span></span>  
 <span data-ttu-id="18b1a-113">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18b1a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b1a-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="18b1a-114">See Also</span></span>  
 [<span data-ttu-id="18b1a-115">Isymunmanagedmethod arabirimi</span><span class="sxs-lookup"><span data-stu-id="18b1a-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)