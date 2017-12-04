---
title: "ICLRStrongName::StrongNameSignatureGenerationEx Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b0527be680ed755366f77593e4dc7e1dea830c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="4b021-102">ICLRStrongName::StrongNameSignatureGenerationEx Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4b021-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="4b021-103">Belirtilen bayrakları göre belirtilen derleme için bir tanımlayıcı ad imzası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4b021-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b021-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4b021-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b021-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4b021-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4b021-106">[in] Tanımlayıcı ad imzası oluşturulmayacak derleme bildirimi içeren dosyanın yolu.</span><span class="sxs-lookup"><span data-stu-id="4b021-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="4b021-107">[in] Ortak/özel anahtar çiftini içeren anahtar kapsayıcı adı.</span><span class="sxs-lookup"><span data-stu-id="4b021-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="4b021-108">Varsa `pbKeyBlob` null, `wszKeyContainer` şifreleme hizmeti sağlayıcısı (CSP) geçerli bir kapsayıcıda belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4b021-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="4b021-109">Bu durumda, kapsayıcısında depolanan anahtar çifti dosyasını imzalamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4b021-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="4b021-110">Varsa `pbKeyBlob` anahtar çifti varsayılır anahtar ikili büyük nesne (BLOB) dahil edilmek üzere null değil.</span><span class="sxs-lookup"><span data-stu-id="4b021-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4b021-111">[in] Ortak/özel anahtar çifti için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="4b021-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4b021-112">Bu çiftidir Win32 tarafından oluşturulan biçiminde `CryptExportKey` işlevi.</span><span class="sxs-lookup"><span data-stu-id="4b021-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4b021-113">Varsa `pbKeyBlob` null, belirtilen anahtar kapsayıcısı olan `wszKeyContainer` anahtar çiftini içeren varsayılır.</span><span class="sxs-lookup"><span data-stu-id="4b021-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4b021-114">[in] Bayt olarak boyutu, `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4b021-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="4b021-115">[out] Ortak dil çalışma zamanı imza döndüğü konuma bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="4b021-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="4b021-116">Varsa `ppbSignatureBlob` olduğu çalışma zamanı tarafından belirtilen dosyada imza null depolar `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="4b021-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="4b021-117">Varsa `ppbSignatureBlob` olan null, ortak dil çalışma zamanı imza döndürmek üzere alan ayırır.</span><span class="sxs-lookup"><span data-stu-id="4b021-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="4b021-118">Arayan kullanarak bu alanı boş gerekir [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4b021-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="4b021-119">[out] Döndürülen imza bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="4b021-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4b021-120">[in] Bir veya daha fazla aşağıdaki değerlerden biri:</span><span class="sxs-lookup"><span data-stu-id="4b021-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="4b021-121">`SN_SIGN_ALL_FILES`(0x00000001) - bağlantılı modülleri için tüm karmaları yeniden hesaplamak.</span><span class="sxs-lookup"><span data-stu-id="4b021-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="4b021-122">`SN_TEST_SIGN`(0x00000002) - test-oturum derleme.</span><span class="sxs-lookup"><span data-stu-id="4b021-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b021-123">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="4b021-123">Return Value</span></span>  
 <span data-ttu-id="4b021-124">`S_OK`Yöntem başarıyla tamamlandı Aksi takdirde hata belirten bir HRESULT değeri (bkz [ortak HRESULT değerleri](http://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="4b021-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b021-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4b021-125">Remarks</span></span>  
 <span data-ttu-id="4b021-126">İçin null belirtin `wszFilePath` imza oluşturmadan imza boyutu hesaplanamadı.</span><span class="sxs-lookup"><span data-stu-id="4b021-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="4b021-127">İmza ya da doğrudan dosyasında depolanan veya yapana.</span><span class="sxs-lookup"><span data-stu-id="4b021-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="4b021-128">Varsa `SN_SIGN_ALL_FILES` belirtildi ancak bir ortak anahtar dahil değildir (her ikisi de `pbKeyBlob` ve `wszFilePath` null) bağlantılı modülleri için karmaları yeniden ancak derleme yeniden imzalı değil.</span><span class="sxs-lookup"><span data-stu-id="4b021-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="4b021-129">Varsa `SN_TEST_SIGN` belirtilirse, ortak dil çalışma zamanı üstbilgisi derleme tanımlayıcı bir ad ile imzalı olduğunu belirtmek için değişiklik yok.</span><span class="sxs-lookup"><span data-stu-id="4b021-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b021-130">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4b021-130">Requirements</span></span>  
 <span data-ttu-id="4b021-131">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b021-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b021-132">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4b021-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4b021-133">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="4b021-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b021-134">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b021-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b021-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4b021-135">See Also</span></span>  
 [<span data-ttu-id="4b021-136">StrongNameSignatureGeneration yöntemi</span><span class="sxs-lookup"><span data-stu-id="4b021-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="4b021-137">Iclrstrongname arabirimi</span><span class="sxs-lookup"><span data-stu-id="4b021-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)