---
title: 'Nasıl yapılır: Bir nesneyi kullanarak nesneleri başlatma Başlatıcı - C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 29987b9ba1f1f18f4e768766bd2391ebb5862f97
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084881"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Nasıl yapılır: Bir nesne Başlatıcı kullanarak nesneleri başlatma (C# Programlama Kılavuzu)

Nesne başlatıcıları türü nesne türü için bir oluşturucu açıkça çağırmadan bildirim temelli bir şekilde başlatmak için kullanabilirsiniz.  
  
Aşağıdaki örnekler, adlandırılmış nesneleriyle nesne başlatıcıları kullanın gösterilmektedir. Derleyici işlemleri başlatıcılar nesne ilk varsayılan örnek oluşturucusu erişme ve sonra üye başlatmalar işleme. Bu nedenle, varsayılan oluşturucu olarak bildirilirse `private` sınıfında genel erişim gerektiren bir nesne başlatıcıları başarısız olur.
  
Anonim bir tür tanımlıyorsanız, bir nesne Başlatıcı kullanmanız gerekir. Daha fazla bilgi için [nasıl yapılır: Bir sorguda öğe özelliklerinin alt kümelerini dönüş](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Örnek  

Aşağıdaki örnek, yeni bir başlatma işlemi gösterilmektedir `StudentName` nesne başlatıcıları kullanarak türü. Bu örnekte'nın özelliklerini ayarlar `StudentName` türü:
  
[!code-csharp-interactive[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Nesne başlatıcıları, bir nesne içinde dizin oluşturucular ayarlamak için kullanılabilir. Aşağıdaki örnekte tanımlayan bir `BaseballTeam` almak ve farklı konumlar oyuncuların ayarlamak için bir dizin oluşturucu kullanan sınıf. Başlatıcı konumu kısaltması göre oyuncuları ya da her konum Beyzbol karneleri için kullanılan sayıyı atayabilirsiniz:

[!code-csharp-interactive[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../index.md)  
- [Nesne ve Koleksiyon Başlatıcıları](object-and-collection-initializers.md)
