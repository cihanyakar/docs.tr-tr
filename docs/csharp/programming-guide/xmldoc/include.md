---
title: '&lt;dahil&gt; - C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 05c671f029e9597db05fe2104424545d0ee2b98f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239431"
---
# <a name="ltincludegt-c-programming-guide"></a>&lt;dahil&gt; (C# programlama Kılavuzu)
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Belgeleri içeren XML dosyasının adı. Dosya adı, kaynak kodu dosyasının göreli bir yol ile nitelenmiş olmalıdır. İçine `filename` tek tırnak işareti (' ').  
  
 `tagpath`  
 Etiketleri yolunu `filename` etikete müşteri adayları `name`. Yolu, tek tırnak işaretleri içine alın (' ').  
  
 `name`  
 Yorumları önündeki etiketinde ad tanımlayıcısı; `name` sahip bir `id`.  
  
 `id`  
 Yorumları önünde etiket kimliği. Kimliği çift tırnak içine alın ("").  
  
## <a name="remarks"></a>Açıklamalar  
 \<Dahil > etiket türleri açıklayan yorumlar başka bir dosyaya ve üyeleri, kaynak kodunuzdaki bakın olanak tanır. Bu belge açıklamaları doğrudan, kaynak kodu dosyasında yerleştirme için bir alternatifidir. Ayrı bir dosyada belgeleri koyarak, kaynak denetimi belgeleri için ayrı ayrı kaynak koddan uygulayabilirsiniz. Bir kişi kaynak kod dosyasını kullanıma alınmış olabilir ve başka birisi kullanıma belge dosyası olabilir.  
  
 \<Dahil > etiketini XML XPath sözdizimi kullanır. Özelleştirme yolları için XPath belgelerine bakın, \<dahil > kullanın.  
  
## <a name="example"></a>Örnek  
 Bu çok dosyalı bir örnektir. Kullanan ilk dosya \<dahil >, aşağıda verilmiştir:  
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 İkinci bir dosya, xml_include_tag.doc, aşağıdaki belgeleri açıklamaları içerir:  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Program çıktısı  
 Test ve Test2 sınıfları aşağıdaki komut satırı ile derleme yaparken aşağıdaki çıkış üretilir: `/doc:DocFileName.xml.` Visual Studio'da derleme bölmesindeki seçeneği XML belge açıklamaları Proje Tasarımcısı belirtin. Zaman C# derleyici görür \<dahil > etiketi, arama yapacağı xml_include_tag.doc geçerli kaynak dosyanın yerine, belge açıklamaları için. Derleyici, ardından DocFileName.xml oluşturur ve bu belgeleri araçları tarafından gibi kullanılan dosya [Sandcastle](https://github.com/EWSoftware/SHFB) son belgeleri oluşturmak için.  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Belge Açıklamaları için Önerilen Etiketler](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
