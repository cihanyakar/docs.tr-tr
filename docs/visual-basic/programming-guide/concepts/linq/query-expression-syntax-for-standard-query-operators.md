---
title: Standart sorgu işleçleri (Visual Basic) için sorgu ifade sözdizimi
ms.date: 07/20/2015
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
ms.openlocfilehash: 2f0a32ca2e76122aa13e4ad44c4b69838af26cdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648612"
---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>Standart sorgu işleçleri (Visual Basic) için sorgu ifade sözdizimi
Bazı daha sık kullanılan standart sorgu işleçleri, bunları bir parçası olarak çağrılacak sağlayan Visual Basic dil anahtar sözcüğü söz dizimine adanmış bir *sorgu ifadesi*. Bir sorgu ifadesi daha sorgu ifade, farklı, daha okunabilir bir form olan kendi *yöntemi tabanlı* eşdeğer. Sorgu ifadesi yan tümceleri derleme zamanında sorgu yöntemleri çağrıları içine çevrilir.  
  
## <a name="query-expression-syntax-table"></a>Sorgu ifade sözdizimi tablosu  
 Aşağıdaki tabloda eşdeğer sorgu ifadesi yan tümceleri sahip standart sorgu işleçleri listeler.  
  
|Yöntem|Visual Basic sorgu ifade sözdizimi|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> (Daha fazla bilgi için bkz: [From yan tümcesi](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> (Daha fazla bilgi için bkz: [Distinct tümcesi](../../../../visual-basic/language-reference/queries/distinct-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> (Daha fazla bilgi için bkz: [Grup By yan tümcesi](../../../../visual-basic/language-reference/queries/group-by-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> (Daha fazla bilgi için bkz: [Grup JOIN yan tümcesi](../../../../visual-basic/language-reference/queries/group-join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> -veya-<br /><br /> `Join … [As …]In … On …`<br /><br /> (Daha fazla bilgi için bkz: [JOIN yan tümcesi](../../../../visual-basic/language-reference/queries/join-clause.md).)|  
|<xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> (Daha fazla bilgi için bkz: [Order By yan tümcesi](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> (Daha fazla bilgi için bkz: [Order By yan tümcesi](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (Daha fazla bilgi için bkz: [Select tümcesi](../../../../visual-basic/language-reference/queries/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Birden çok `From` yan tümceleri<br /><br /> (Daha fazla bilgi için bkz: [From yan tümcesi](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> (Daha fazla bilgi için bkz: [SKIP yan tümcesi](../../../../visual-basic/language-reference/queries/skip-clause.md).)|  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> (Daha fazla bilgi için bkz: [Skip While tümcesi](../../../../visual-basic/language-reference/queries/skip-while-clause.md).)|  
|<xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> (Daha fazla bilgi için bkz: [Aggregate tümcesi](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> (Daha fazla bilgi için bkz: [ele yan tümcesi](../../../../visual-basic/language-reference/queries/take-clause.md).)|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> (Daha fazla bilgi için bkz: [ele While tümcesi](../../../../visual-basic/language-reference/queries/take-while-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> (Daha fazla bilgi için bkz: [Order By yan tümcesi](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> (Daha fazla bilgi için bkz: [Order By yan tümcesi](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> (Daha fazla bilgi için bkz: [Where yan tümcesi](../../../../visual-basic/language-reference/queries/where-clause.md).)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Linq.Enumerable>  
 <xref:System.Linq.Queryable>  
 [Standart sorgu işleçlerine genel bakış (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Standart sorgu işleçleri (Visual Basic) yürütme yöntemine göre sınıflandırılması](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
