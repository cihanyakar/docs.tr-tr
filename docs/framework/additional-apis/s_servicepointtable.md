---
title: ServicePointManager.s_ServicePointTable alan
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ebcf5c3f13b3bd30a8e091be09ae546eee1eaffe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147453"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="fa2fe-102">ServicePointManager.s\_ServicePointTable alan</span><span class="sxs-lookup"><span data-stu-id="fa2fe-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="fa2fe-103">`ServicePointManager.s_ServicePointTable` olan bir <xref:System.Collections.Hashtable> etkin HTTP bağlantıları listesini içeren (<xref:System.Net.ServicePoint>s) içindeki <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fa2fe-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa2fe-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fa2fe-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="fa2fe-105">`ServicePointManager.s_ServicePointTable` Alan özeldir ve kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="fa2fe-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="fa2fe-106">Microsoft hiçbir koşulda, bir üretim uygulamasında bu alanı kullanımını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="fa2fe-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa2fe-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fa2fe-107">Requirements</span></span>

<span data-ttu-id="fa2fe-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fa2fe-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fa2fe-109">**Derleme:** Sistemde (System.dll)</span><span class="sxs-lookup"><span data-stu-id="fa2fe-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="fa2fe-110">**.NET framework sürümleri:** 2.0 sürümünden itibaren kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fa2fe-110">**.NET Framework versions:** Available since 2.0.</span></span>
