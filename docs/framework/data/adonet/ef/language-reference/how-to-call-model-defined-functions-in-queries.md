---
title: 'Nasıl yapılır: sorgularda Model tanımlı işlevler çağırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 2a20a2bb524c1ef9135b8b7187b2519088ddb762
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778740"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Nasıl yapılır: sorgularda Model tanımlı işlevler çağırma
Bu konu, içinden kavramsal modelde tanımlı işlevleri çağırmak açıklar [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgular.  
  
 Aşağıdaki yordam bir model tanımlı işlev içinden çağırmak için İleri düzey bir özeti sağlar. bir [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgu. Aşağıdaki örnek, bu yordamdaki adımları hakkında daha fazla ayrıntı sağlar. Yordam, kavramsal modelde tanımlı bir işlev varsayar. Daha fazla bilgi için [nasıl yapılır: özel işlevleri tanımlamak kavramsal Model](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Kavramsal modelde tanımlı bir işlevi çağırmak için  
  
1.  Bir ortak dil çalışma zamanı (CLR) yöntem kavramsal modelde tanımlı işlev eşlendiği uygulamanıza ekleyin. Map yöntemi için uygulamanız gereken bir <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> yöntemi. Unutmayın <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> ve <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> öznitelik parametreleri: kavramsal modelin ad alanı adı ve işlev adı kavramsal modeldeki sırasıyla. LINQ için ad çözümlemesi işlevi büyük/küçük harfe duyarlıdır.  
  
2.  İşlev Çağır bir [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek içinden kavramsal modelde tanımlı bir işlev çağrısı yapmayı gösteren bir [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgu. Örneğin, okul modeli kullanır. Okul modeli hakkında daha fazla bilgi için bkz: [School örnek veritabanını oluşturma](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) ve [Okul .edmx dosyası oluşturma](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 Bir eğitmen işe alındım olduğundan aşağıdaki kavramsal model işlevi yıl sayısını döndürür. Kavramsal bir modele işlevi ekleme hakkında daha fazla bilgi için bkz. [nasıl yapılır: özel işlevleri tanımlamak kavramsal Model](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Örnek  
 Ardından, uygulamanızı ve kullanmak için aşağıdaki yöntemi ekleyin bir <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> kavramsal model işleve eşlemek için:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Örnek  
 İçinden kavramsal model işlevi çağırabilir artık bir [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgu. Aşağıdaki kod, on yıldan önce işe alınan tüm Eğitmenler görüntülenecek yöntemini çağırır:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.edmx dosyasını genel bakış](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [LINQ to Entities Sorguları](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [LINQ to Entities Sorgularında Çağırma İşlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Nasıl Yapılır: Model Tanımlı İşlevleri Nesne Yöntemleri Olarak Çağırma](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
