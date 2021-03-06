---
title: 'Nasıl yapılır: Nesnelerin geç başlatılmasını gerçekleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3bcdbfacf02d84848934e21d58ed6fff7d37d52
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362892"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a>Nasıl yapılır: Nesnelerin geç başlatılmasını gerçekleştirme
<xref:System.Lazy%601?displayProperty=nameWithType> Sınıfı yavaş başlatma ve nesne örneğinin gerçekleştirmenin iş basitleştirir. Nesneleri yavaş bir şekilde başlatarak bunları hiçbir zaman gerekli ya da ilk erişilen kadar başlatma erteleyebilirsiniz hiç oluşturmak zorunda önleyebilirsiniz. Daha fazla bilgi için [yavaş başlatma](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir değer ile başlatmak gösterilmektedir <xref:System.Lazy%601>. Yavaş değişkeni, ayarlar bazı diğer kod bağlı olarak gerekli olabileceği değil varsayar `someCondition` değişken true veya false.  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> sınıfı yalnızca geçerli iş parçacığının geçerli nesne örneğinde görünür olan bir türü başlatılamadı.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>  
 [Geç Başlatma](../../../docs/framework/performance/lazy-initialization.md)
