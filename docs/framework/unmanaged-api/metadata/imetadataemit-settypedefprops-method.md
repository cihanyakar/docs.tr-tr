---
title: IMetaDataEmit::SetTypeDefProps Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b72088e4aa9994ca6ae411ec36d4c578e3017e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447889"
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps Yöntemi
Önceki bir çağrı tarafından tanımlanan bir türü özelliklerini ayarlar [Imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `td`  
 [in] Bir `mdTypeDef` belirteç elde özgün çağrıya [Imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` öznitelikleri. Bu, bir bit maskesi olan `CorTypeAttr` değerleri.  
  
 `tkExtends`  
 [in] `mdToken` Temel sınıf. Önceki çağrısından alınan [Imetadataemit::defineımporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), veya `null`.  
  
 `rtkImplements[]`  
 [in] Bu tür uygulayan arabirimler için belirteçleri dizisi. Bunlar `mdTypeRef` belirteçleri elde edilir kullanarak [Imetadataemit::defineımporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md). Dizinin son öğesi olmalı `mdTokenNil`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** Cor.h  
  
 **Kitaplığı:** MSCorEE.dll kaynak olarak kullanılır  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IMetaDataEmit Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
