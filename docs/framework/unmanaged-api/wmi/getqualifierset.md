---
title: GetQualifierSet işlevi (yönetilmeyen API Başvurusu)
description: Bir sınıf veya örnek için ayarlanmış niteleyicisi GetQualifierSet işlevi alır.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 635dc7605af00f2662a9f9553adefafcd25f9452
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198767"
---
# <a name="getqualifierset-function"></a>GetQualifierSet işlevi
Bir sınıf örneği veya bir sınıf tanımı için ayarlanmış niteleyicisi alır.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`  
[in] Bu parametre kullanılmaz.

`ptr`  
[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.

`ppQualSet`  
[out] Niteleyiciler sınıf nesnesi erişimi sağlayan bir arabirim işaretçisi alır. `ppQualSet` olamaz `null`. Bir hata gerçekleşirse, yeni bir nesne döndürülmez ve işaretçi solda değiştirilmemiş. 

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Belirtilen yöntem yok. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | İşlemi tamamlamak yeterli bellek yok. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Bir parametre `null`. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) yöntemi. 

[IWbemQualifierSet işaretçi](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) eklemek, düzenlemek veya bu niteleyiciler silme çağıran olanak tanır. Tüm örnek veya sınıf tanımına eklenen, düzenlenen veya silinen tür niteleyicileri uygulayın.

## <a name="requirements"></a>Gereksinimler  
**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
