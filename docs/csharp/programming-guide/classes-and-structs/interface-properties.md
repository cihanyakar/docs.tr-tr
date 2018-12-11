---
title: Arabirim Özellikleri - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: c51064f9bb5e834648e0086fd8d28f9c0bd84b61
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241593"
---
# <a name="interface-properties-c-programming-guide"></a>Arabirim Özellikleri (C# Programlama Kılavuzu)
Özellikleri bildirilebilir bir [arabirimi](../../../csharp/language-reference/keywords/interface.md). Bir arabirim özellik erişimcisi örneği verilmiştir:  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 Gövde arabirim özelliği erişimcisine sahip değil. Bu nedenle, amacı, erişimci özelliği salt okunur, salt okunur veya sadece yazılabilir olup olmadığını belirtmektir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, arabirim `IEmployee` bir okuma-yazma özelliğine sahip `Name`ve salt okunur bir özellik `Counter`. Sınıf `Employee` uygulayan `IEmployee` arabirim ve bu iki özellik kullanır. Programın adını yeni bir çalışan ve çalışanların geçerli sayısını okur ve çalışan adını ve hesaplanan çalışan sayısını görüntüler.  
  
 Üyesi bildirildiği arabirimde başvuran özelliği tam adını kullanabilirsiniz. Örneğin:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Bu adlandırılır [açık arabirim uygulaması](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md). Örneğin, sınıf `Employee` iki arabirim uygulama `ICitizen` ve `IEmployee` ve her iki arabirimde `Name` özelliği açık arabirim üyesi uygulaması gerekli olacak. Diğer bir deyişle, aşağıdaki özellik bildirimi:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 uygulayan `Name` özelliği `IEmployee` arabirimi, aşağıdaki bildirim yandan:  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 uygulayan `Name` özelliği `ICitizen` arabirimi.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Örnek Çıktı  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [Özellikler](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Özellikleri Kullanma](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
- [Özellikler ve Dizin Oluşturucular Arasında Karşılaştırma](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
- [Dizin Oluşturucular](../../../csharp/programming-guide/indexers/index.md)  
- [Arabirimler](../../../csharp/programming-guide/interfaces/index.md)
