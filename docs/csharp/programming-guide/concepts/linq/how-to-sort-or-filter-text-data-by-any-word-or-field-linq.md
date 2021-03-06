---
title: 'Nasıl yapılır: herhangi bir sözcük veya alana (LINQ) (C#) göre filtre metin verilerini sıralama veya'
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: 46a6c81a2f6e937bbd567dd4ce1b1e448ca073db
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502624"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a>Nasıl yapılır: herhangi bir sözcük veya alana (LINQ) (C#) göre filtre metin verilerini sıralama veya
Aşağıdaki örnek nasıl satırında herhangi bir alan olarak virgülle ayrılmış değerler gibi yapılandırılmış metin satırlarını sıralanacağını gösterir. Alanın, çalışma zamanında dinamik olarak belirtilebilir. Scores.csv alanlarında dört test puanlarını bir dizi tarafından izlenen bir öğrenci kimlik numarasını temsil ettiğini varsayar.  
  
### <a name="to-create-a-file-that-contains-data"></a>Veri içeren bir dosya oluşturmak için  
  
1.  Konu başlığından scores.csv veri kopyalama [nasıl yapılır: içerik katılın gelen benzer olmayan dosyaları (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) ve Çözüm klasörünüz olarak kaydedin.  
  
## <a name="example"></a>Örnek  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 Bu örnek ayrıca sorgu değişkeni bir yöntemin dönüş gösterir.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  

 .NET Framework sürüm 3.5 veya üzeri bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [LINQ ve dizeler (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
