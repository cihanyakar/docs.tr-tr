---
title: Implements deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253149"
---
# <a name="implements-statement"></a>Implements Deyimi
Bir veya daha fazla arabirimleri veya sınıfta uygulanması gereken arabirim üyeleri veya yapı tanımı göründüğü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Bölümler  
 `interfacename`  
 Gerekli. Karşılık gelen sınıf veya yapının üyeleri tarafından uygulanacak olan özellikleri, yordamları ve olayları olduğundan bir arabirim.  
  
 `interfacemember`  
 Gerekli. Uygulanan bir arabirim üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir koleksiyon bir arabirimdir arabirim üyeleri (özellikleri, yordamları ve olayları) temsil eden prototiplerini kapsüller. Arabirimler yalnızca üyelerinin bildirimlerine içerir; Bu üyeleri, sınıfları ve yapıları uygulayın. Daha fazla bilgi için [arabirimleri](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Implements` Deyimi hemen izlemelidir `Class` veya `Structure` deyimi.  
  
 Bir arabirim, arabirimde bildirilen tüm üyeleri uygulamalıdır. Herhangi bir üyenin atlama söz dizimi hatası olarak kabul edilir. Tek bir üye uygulamak için belirttiğiniz [uygular](../../../visual-basic/language-reference/statements/implements-clause.md) anahtar sözcüğü (ayrı olduğu `Implements` deyimi) sınıf veya yapı üyesi bildirdiğinizde. Daha fazla bilgi için [arabirimleri](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Sınıfları kullanabilirsiniz [özel](../../../visual-basic/language-reference/modifiers/private.md) özellikler ve yordamlar, ancak bu üyeleri uygulamalarıdır uygulayan sınıfa örneği bir değişkene içinde bildirilen arabirim türünde olmasını atama tarafından erişilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `Implements` deyimi bir arabirimin üyeleri uygulamak için. Adlı bir arabirim tanımlar `ICustomerInfo` bir olay, bir özellik ve bir yordam. Sınıf `customerInfo` arabirim içinde tanımlanmış tüm üyelerini uygular.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Unutmayın sınıfı `customerInfo` kullanan `Implements` sınıf tüm üyelerini uyguladığını göstermek için ayrı bir kaynak kod satırında deyimi `ICustomerInfo` arabirimi. Her sınıf üyesi'ı kullanan `Implements` anahtar sözcüğü, arabirim üyesini uyguladığını belirtmek için üye bildiriminin bir parçası olarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki iki yordamdan önceki örnekte uygulanan arabirimi nasıl kullanabileceğinizi gösterir. Uygulamasını test etmek için bu yordamları, proje ve çağrı ekleme `testImplements` yordamı.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulayan](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface Deyimi](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Arabirimler](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
