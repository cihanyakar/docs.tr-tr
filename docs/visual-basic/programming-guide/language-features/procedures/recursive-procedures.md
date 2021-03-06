---
title: Özyinelemeli Yordamlar (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 0bb89ac855d65d7677a062346db8665698dbb805
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514348"
---
# <a name="recursive-procedures-visual-basic"></a>Özyinelemeli Yordamlar (Visual Basic)
A *özyinelemeli* yordam, kendi kendini çağıran bir kullanılır. Genel olarak, Visual Basic kod yazmak için en etkili yolu değil.  
  
 Aşağıdaki yordam, özgün bağımsız değişkeninin faktöriyelini hesaplamak için özyineleme kullanır.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Özyinelemeli yordamlar hakkında konuları  
 **Koşullar sınırlama**. Özyineleme sonlandırabilirsiniz en az bir koşul için test etmek için bir özyinelemeli yordamı tasarlamanız gerekir ve ayrıca burada herhangi bir koşul makul bir özyinelemeli çağrıların sayısı içinde sağlanırsa durum işlemesi gerekir. Başarısız karşılanabiliyorsa en az bir koşul olmadan yordamınız sonsuz bir döngüde yürütmenin bir yüksek riskli çalıştırır.  
  
 **Bellek kullanımı**. Uygulamanızı yerel değişkenler için alan sınırlı bir süre vardır. Bir yordam kendisini çağıran her zaman daha bu alan yerel değişkenlerini ek kopyalarını kullanır. Bu işlem süresiz olarak devam ederse, sonunda neden olan bir <xref:System.StackOverflowException> hata.  
  
 **Verimliliği**. Neredeyse her zaman bir döngü için özyineleme birbirinin yerine kullanabilir. Bir döngü, ek depolama alanı'nı başlatma ve değerler döndüren argümanları başlatır, yükü yok. Performansınızı özyinelemeli çağrılar çok daha iyi olabilir.  
  
 **Karşılıklı özyineleme**. Her iki yordam çağırırsanız çok kötü performans veya hatta bir sonsuz döngüye mümkün görebilirsiniz. Bu tür bir tasarım tek özyinelemeli yordamla aynı oluşturur, ancak algılama ve hata ayıklamayı daha zor olabilir.  
  
 **Parantezler ile çağırma**. Olduğunda bir `Function` yordam çağrıları kendisini yinelemeli olarak, hiçbir bağımsız değişken listesi olsa bile, parantezli yordam adı izlemelidir. Aksi halde, işlev adı alınmış işlevinin dönüş değerini temsil eden olarak.  
  
 **Test**. Bir özyinelemeli yordam yazarsanız, bu çok dikkatli bir şekilde her zaman bir sınırlama bazı koşullar karşıladığından emin olmak için test etmelisiniz. Ayrıca, özyinelemeli çağrı sayısı çok fazla olması nedeniyle bellek yetersiz çalıştıramazsınız emin olmalısınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.StackOverflowException>  
 [Yordamlar](./index.md)  
 [Alt Yordamlar](./sub-procedures.md)  
 [İşlev Yordamları](./function-procedures.md)  
 [Özellik Yordamları](./property-procedures.md)  
 [İşleç Yordamları](./operator-procedures.md)  
 [Yordam Parametreleri ve Bağımsız Değişkenleri](./procedure-parameters-and-arguments.md)  
 [Yordam Aşırı Yüklemesi](./procedure-overloading.md)  
 [Yordam Sorunlarını Giderme](./troubleshooting-procedures.md)  
 [Döngü Yapıları](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Özel durum sorunlarını giderme: System.StackOverflowException](https://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
