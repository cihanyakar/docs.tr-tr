---
title: ICLRRuntimeInfo::GetRuntimeDirectory Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetRuntimeDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddaca8232f0b262377c7915852da89cecec09993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="62fc9-102">ICLRRuntimeInfo::GetRuntimeDirectory Metodu</span><span class="sxs-lookup"><span data-stu-id="62fc9-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="62fc9-103">Bu arabirim ile ilişkili ortak dil çalışma zamanı (CLR) yükleme dizinini alır.</span><span class="sxs-lookup"><span data-stu-id="62fc9-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="62fc9-104">Bu yöntem yerini [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) .NET Framework sürüm 2.0, 3.0 ve 3.5 içinde sağlanan işlevi.</span><span class="sxs-lookup"><span data-stu-id="62fc9-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62fc9-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="62fc9-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62fc9-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="62fc9-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="62fc9-107">[out] CLR yükleme dizinini döndürür.</span><span class="sxs-lookup"><span data-stu-id="62fc9-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="62fc9-108">Yükleme yolu tam; Örneğin, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="62fc9-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="62fc9-109">[içinde out] Boyutunu belirtir `pwzBuffer` arabellek taşmaları önlemek için.</span><span class="sxs-lookup"><span data-stu-id="62fc9-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="62fc9-110">Varsa `pwzBuffer` null, `pchBuffer` gerekli boyutu döndüren `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="62fc9-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62fc9-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="62fc9-111">Return Value</span></span>  
 <span data-ttu-id="62fc9-112">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="62fc9-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="62fc9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62fc9-113">HRESULT</span></span>|<span data-ttu-id="62fc9-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="62fc9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62fc9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="62fc9-115">S_OK</span></span>|<span data-ttu-id="62fc9-116">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="62fc9-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="62fc9-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="62fc9-117">E_POINTER</span></span>|<span data-ttu-id="62fc9-118">`pwzBuffer`veya `pchBuffer` null.</span><span class="sxs-lookup"><span data-stu-id="62fc9-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62fc9-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="62fc9-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62fc9-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="62fc9-120">Requirements</span></span>  
 <span data-ttu-id="62fc9-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62fc9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62fc9-122">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="62fc9-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="62fc9-123">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="62fc9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62fc9-124">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62fc9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fc9-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="62fc9-125">See Also</span></span>  
 [<span data-ttu-id="62fc9-126">Iclrruntimeınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="62fc9-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="62fc9-127">Barındırma</span><span class="sxs-lookup"><span data-stu-id="62fc9-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)