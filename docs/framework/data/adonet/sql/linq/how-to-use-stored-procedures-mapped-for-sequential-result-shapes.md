---
title: 'Nasıl yapılır: sıralı sonuç şekiller için eşlenen saklı yordamları kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: ade123f10e1c9ffd6d042b45599cc6e352614e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351946"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Nasıl yapılır: sıralı sonuç şekiller için eşlenen saklı yordamları kullanma
Bu tür bir saklı yordam birden fazla sonuç şekil oluşturabilir, ancak hangi sırada sonuçların döndürülmesini bildirin. Bu senaryo burada döndürür dizisini bilmiyorsanız senaryo ile karşılaştırın. Daha fazla bilgi için bkz: [nasıl yapılır: kullanım saklı yordamları eşlenen birden çok sonuç şekilleri](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## <a name="example"></a>Örnek  
 Birden çok sonuç şekil sıralı olarak döndüren bir saklı yordam T-SQL şöyledir:  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Örnek  
 Bu saklı yordamı yürütmek için aşağıdakine benzer bir kod kullanırsınız.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saklı Yordamlar](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
