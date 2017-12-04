---
title: "EndMethodEnumeration işlevi (yönetilmeyen API Başvurusu)"
description: "EndMethodEnumeration işlevi bir yöntem numaralandırma sırası sonlandırır."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndMethodEnumeration
helpviewer_keywords: EndMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1b768292811a752e7a319f853ca8eff85f1bb08
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="1b027-103">EndMethodEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="1b027-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="1b027-104">Çağrı kullanmaya bir numaralandırma sırasını sonlandırır [BeginMethodEnumeration işlevi](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1b027-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1b027-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1b027-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="1b027-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1b027-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1b027-107">[in] Bu parametre kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="1b027-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1b027-108">[in] Bir işaretçi bir [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) örneği.</span><span class="sxs-lookup"><span data-stu-id="1b027-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="1b027-109">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="1b027-109">Return value</span></span>

<span data-ttu-id="1b027-110">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üstbilgi dosyası, veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="1b027-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1b027-111">Sabit</span><span class="sxs-lookup"><span data-stu-id="1b027-111">Constant</span></span>  |<span data-ttu-id="1b027-112">Değer</span><span class="sxs-lookup"><span data-stu-id="1b027-112">Value</span></span>  |<span data-ttu-id="1b027-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1b027-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="1b027-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1b027-114">0x8004101d</span></span> | <span data-ttu-id="1b027-115">Bir iç hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="1b027-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1b027-116">0</span><span class="sxs-lookup"><span data-stu-id="1b027-116">0</span></span> | <span data-ttu-id="1b027-117">İşlev çağrısı başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="1b027-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1b027-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1b027-118">Remarks</span></span>

<span data-ttu-id="1b027-119">Bu işlev çağrısı sarmalar [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1b027-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1b027-120">Numaralandırma dizisi kullanarak arayan başlar [BeginMethodEnumeration işlevi](beginmethodenumeration.md)ve ardından çağırır [NextMethod işlevi](nextmethod.md )yöntemi dönene kadar `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="1b027-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="1b027-121">İsteğe bağlı olarak çağıran çağırarak sırası tamamlandıktan `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="1b027-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="1b027-122">Arayan numaralandırması erken çağırarak sonlandırabilir `EndMethodEnumeration` dilediğiniz zaman.</span><span class="sxs-lookup"><span data-stu-id="1b027-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b027-123">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1b027-123">Requirements</span></span>  
 <span data-ttu-id="1b027-124">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b027-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b027-125">**Başlık:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1b027-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1b027-126">**.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1b027-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b027-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1b027-127">See also</span></span>  
[<span data-ttu-id="1b027-128">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="1b027-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)