---
title: ICLRAssemblyIdentityManager Arabirimi
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a58a9ec4ed9514e748ed6c8c21a404feed9560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435673"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager Arabirimi
Derlemeler hakkında ortak dil çalışma zamanı (CLR) ile konak arasındaki iletişimi destekleyen yöntemler sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBindingIdentityFromFile Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Belirtilen dosya yolu konumunda derlemesi için veri bağlama derleme kimliğini alır.|  
|[GetBindingIdentityFromStream Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Belirtilen akış derlemede kurallı derleme kimlik verilerini alır.|  
|[GetCLRAssemblyReferenceList Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Alır bir [Iclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) kısmi derleme kimlikleri sağlanan listeden örneği.|  
|[GetProbingAssembliesFromReference Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Alır bir [Iclrprobingassemblyenum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) belirtilen kimliğe sahip derlemesi tarafından başvurulan derleme kimlikleri için Numaralandırıcı.|  
|[GetReferencedAssembliesFromFile Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Alır bir [Iclrreferenceassemblyenum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) belirtilen dosya yolu konumunda derlemesi tarafından başvurulan bir derleme listesi içeren örneği.|  
|[GetReferencedAssembliesFromStream Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Bir işaretçi alır bir `ICLRReferenceAssemblyEnum` belirtilen stream derlemede tarafından başvurulan derlemeler için derleme kimlik verilerini içeren nesne.|  
|[IsStronglyNamed Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|Belirtilen derleme güçlü olarak adlandırılmamış olup olmadığını belirten bir değer alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `ICLRAssemblyIdentityManager` örneklerini almak için `ICLRAssemblyReferenceList` ve derleme kimlikleri numaralandırılamıyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRAssemblyReferenceList Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRProbingAssemblyEnum Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
