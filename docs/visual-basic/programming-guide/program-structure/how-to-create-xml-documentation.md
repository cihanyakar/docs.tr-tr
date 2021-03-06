---
title: "Nasıl yapılır: Visual Basic'de XML Belgesi Oluşturma"
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 3dfec94a3dd1b8da5d371529b91b47f018bb3843
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527602"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Nasıl yapılır: Visual Basic'de XML Belgesi Oluşturma
Bu örnek XML belge açıklamaları ekleme kodunuzu gösterir.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Bir tür veya üye için XML belgeleri oluşturmak için  
  
1.  İçinde **Kod Düzenleyicisi**, yukarıdaki belgeleri oluşturmak istediğiniz türe veya üyeye satırında imlecinizi.  
  
2.  Tür `'''` (üç tek tırnak işareti).  
  
     Türe veya üyeye bir XML çatısı eklenir **Kod Düzenleyicisi**.  
  
3.  Uygun etiketleri arasına tanımlayıcı bilgiler ekleyin.  
  
    > [!NOTE]
    >  XML belgeleri bloğu içinde ek satırlar eklerseniz, her bir çizgi ile başlamalıdır `'''`.  
  
4.  Türe veya üyeye yeni XML belge açıklamaları kullanan ek kod ekleyin.  
  
     IntelliSense görüntüler metinden \<Özet > türe veya üyeye etiketi.  
  
5.  Belge açıklamaları içeren bir XML dosyası oluşturmak için kodu derleyin. Daha fazla bilgi için [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML ile Kodunuzu Belgeleme](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [XML Açıklama Etiketleri](../../../visual-basic/language-reference/xmldoc/index.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
