---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 8a8068c467f9066af3153434187749fa80d254ca
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50048404"
---
# <a name="-refout-visual-basic"></a>-refonly (Visual Basic)

**- Refonly** seçeneği, başvuru bütünleştirilmiş kodu çıkış olmalıdır nerede bir dosya yolu belirtir.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sözdizimi

```console
-refout:filepath
```

## <a name="arguments"></a>Arguments

 `filepath` Başvuru bütünleştirilmiş kodunun dosya adı ve yolu. Genellikle bir alt birincil derlemesi klasörde olması gerekir. Başvuru derlemesinde yerleştirmek için (MSBuild tarafından kullanılır) önerilen kuralı olan bir "ref /" Birincil derleme göreli alt klasör. Tüm klasörleri `filepath` bulunmalıdır; derleyici bunları oluşturmaz. 

## <a name="remarks"></a>Açıklamalar

Visual Basic destekler `-refout` 15.3 sürümünden başlayarak geçin.

Başvuru bütünleştirilmiş kodları meta verileri ancak hiçbir uygulama kodu içeren yalnızca meta veri derlemelerdir. Bunlar, anonim türler dışında her şeyi için tür ve üye bilgilerini içerir. Kendi metot gövdeleri tek bir değiştirilir `throw null` deyimi. Kullanılmasının nedeni `throw null` (gövde yok)'yerine metot gövdeleri olduğu PEVerify çalışmasını ve (Bu nedenle meta veri bütünlüğünü doğrulama) geçirin.

Başvuru derlemelerini içeren bir derleme düzeyi [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) özniteliği. Bu özniteliği, kaynakta belirtilebilir (sonra derleyici bu sentezlemek gerekmez). Bu öznitelik nedeniyle yürütme için başvuru derlemeleri yüklemeye çalışma zamanları Reddet (ancak bunlar yine de salt yansıma bir bağlamda yüklenmiş olabilir). Bunlar salt yansıma olarak başvuru derlemelerini yüklemek emin olmak derlemelerini yansıtan araçları gerekir; Aksi takdirde, çalışma zamanı oluşturur bir <xref:System.BadImageFormatException>.

`-refout` Ve [ `-refonly` ](refonly-compiler-option.md) seçenekleri karşılıklı olarak birbirini dışlar.

## <a name="see-also"></a>Ayrıca Bkz.
[-refonly](refonly-compiler-option.md)   
[Visual Basic komut satırı derleyicisi](index.md)  
[Örnek Derleme Komut Satırları](sample-compilation-command-lines.md)  

