---
title: 'Nasıl yapılır: sorgu (LINQ) (Visual Basic) bir dizedeki karakter için'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 0953ff9152a4af1aa40379e15b2279d23ad0aac1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642122"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>Nasıl yapılır: sorgu (LINQ) (Visual Basic) bir dizedeki karakter için
Çünkü <xref:System.String> sınıfı uygulayan genel <xref:System.Collections.Generic.IEnumerable%601> arabirimi, herhangi bir dize bir karakter dizisi sorgulanabilir. Ancak, bu yaygın bir kullanımdır LINQ değildir. İşlem eşleştirme karmaşık desen için kullanmak <xref:System.Text.RegularExpressions.Regex> sınıfı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, içerdiği sayısal basamak sayısını belirlemek için bir dize sorgular. "İlk kez yürütüldükten sonra sorguyu yeniden kullanılacağını" unutmayın. Bu, sorgu herhangi bir gerçek sonuç depolamaz çünkü mümkündür.  
  
```vb  
Class QueryAString  
  
    Shared Sub Main()  
  
        ' A string is an IEnumerable data source.  
        Dim aString As String = "ABCDE99F-J74-12-89A"  
  
        ' Select only those characters that are numbers  
        Dim stringQuery = From ch In aString   
                          Where Char.IsDigit(ch)   
                          Select ch  
        ' Execute the query  
        For Each c As Char In stringQuery  
            Console.Write(c & " ")  
        Next  
  
        ' Call the Count method on the existing query.  
        Dim count As Integer = stringQuery.Count()  
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)  
  
        ' Select all characters before the first '-'  
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")  
  
        ' Execute the second query  
        For Each ch In stringQuery2  
            Console.Write(ch)  
        Next  
  
        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 9 9 7 4 1 2 8 9   
' Count = 8  
' ABCDE99F  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 .NET Framework sürüm 3.5 veya daha yüksek System.Core.dll başvuru hedefleyen bir proje oluşturun ve bir `Imports` System.Linq ad alanı bildirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ ve dizeler (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Nasıl yapılır: (Visual Basic) Normal ifadelerle LINQ sorgularını birleştirme](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
