---
title: (C# üzerinde LINQ) bileşik anahtarlar kullanarak birleştirme
description: LINQ to bileşik anahtarlar kullanarak birleştirme hakkında bilgi edinin.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: ae37d03f996f0b0cc184a86663f16d62e6c29c69
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080110"
---
# <a name="join-by-using-composite-keys"></a>Bileşik anahtarlar kullanarak birleştirme

Bu örnek, birden fazla anahtar bir eşleşme tanımlamak için kullanmak istediğiniz birleştirme işlemleri gerçekleştirme gösterilmektedir. Bu, bir bileşik anahtarı kullanılarak gerçekleştirilir. Bir bileşik anahtarı anonim bir tür olarak veya adlandırılmış karşılaştırmak istediğiniz değerlerle yazılı oluşturursunuz. Sorgu değişkeni yöntemi sınırlarında geçirilir, geçersiz kılmalar adlandırılmış bir tür kullanın. <xref:System.Object.Equals%2A> ve <xref:System.Object.GetHashCode%2A> anahtarı. Özellikler ve, bunlar, sırayla adları içindeki her anahtarın aynı olmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, üç tablolardaki verileri birleştirmek için bir bileşik anahtarı kullanacak şekilde gösterilmiştir:

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

Anahtarlar ve, bunlar sırayla özelliklerinde adlarını bileşik anahtarlar tür çıkarımı bağlıdır. Kaynak dizileri özelliklerinde aynı ada sahip değilseniz, yeni anahtarları adlarında atamanız gerekir. Örneğin, varsa `Orders` tablo ve `OrderDetails` her tabloda kullanılan kendilerine ait sütunların için farklı adlar, anonim türde aynı ada atayarak bileşik anahtarlar oluşturabilirsiniz:

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

Bileşik anahtarlar da kullanılabilir bir `group` yan tümcesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Dil ile Tümleşik Sorgu (LINQ)](index.md)  
- [join yan tümcesi](../language-reference/keywords/join-clause.md)  
- [group yan tümcesi](../language-reference/keywords/group-clause.md)  