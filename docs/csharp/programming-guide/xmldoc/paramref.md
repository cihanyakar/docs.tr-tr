---
title: '&lt;paramref&gt; - C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 90c22b81f17adb1fcfdb94f32047e85c0bd8f4e5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243638"
---
# <a name="ltparamrefgt-c-programming-guide"></a>&lt;paramref&gt; (C# programlama Kılavuzu)
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Başvurmak için parametrenin adı. Adı çift tırnak içine alın ("").  
  
## <a name="remarks"></a>Açıklamalar  
 \<Paramref > etiketi kodda bir sözcük, örnekte yorum olduğunu göstermek için bir yol sağlar bir \<Özet > veya \<remarks > blok bir parametresine başvuruyor. XML dosyası, bu sözcüğü biçimlendirmek kalın veya Yatık yazı tipiyle farklı şekilde, gibi için işlenebilir.  
  
 Derleme [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) işlem belgeleri açıklamaları için bir dosya için.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Belge Açıklamaları için Önerilen Etiketler](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
