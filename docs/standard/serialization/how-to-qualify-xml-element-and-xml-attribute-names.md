---
title: 'Nasıl yapılır: XML öğesi ve XML öznitelik adlarını Sınıflandır'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 3c477923387e5a28dcc14b44b0f77bb6acb686e5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176740"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a>Nasıl yapılır: XML öğesi ve XML öznitelik adlarını Sınıflandır

XML ad alanları örneklerini tarafından bulunan <xref:System.Xml.Serialization.XmlSerializerNamespaces> sınıf adlı World Wide Web Consortium (W3C) belirtimi için uygun olmalıdır [ad alanları XML](https://www.w3.org/TR/REC-xml-names/).

XML ad alanları, XML öğelerine ve XML belgeleri XML öznitelikleri adlarını niteleme için bir yöntem sağlar. Tam adı bir önek ve virgül ile ayrılmış bir yerel ad oluşur. Önek yalnızca bir yer tutucu olarak işlev görür; bir ad alanı belirten bir URI ile eşleşir. Evrensel yönetilen URI ad alanı ve yerel adı birleşimi evrensel benzersiz olması garanti bir ad oluşturur.

Öğesinin bir örneğini oluşturarak `XmlSerializerNamespaces` ve ad alanı çiftleri nesnesine ekleniyor, XML belgesinde kullanılan öneklerini belirtebilirsiniz.

## <a name="to-create-qualified-names-in-an-xml-document"></a>Bir XML belgesinde tam adları oluşturmak için

1. Öğesinin bir örneğini oluşturur `XmlSerializerNamespaces` sınıfı.

2. Tüm öneklerine ve ad alanı çiftleri için Ekle `XmlSerializerNamespaces`.

3. Uygun uygulamak `System.Xml.Serialization` , sınıf veya öznitelik her üyesine <xref:System.Xml.Serialization.XmlSerializer> XML belgesine serileştirmek için.

  Kullanılabilir öznitelikler: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, ve <xref:System.Xml.Serialization.XmlTypeAttribute>.

4. Ayarlama `Namespace` özelliğine her özniteliğinin ad alanı değerlerinden birine `XmlSerializerNamespaces`.

5. Geçiş `XmlSerializerNamespaces` için `Serialize` yöntemi `XmlSerializer`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, oluşturur bir `XmlSerializerNamespaces`, ve iki önek ve ad alanı çiftleri nesneye ekler. Kod oluşturur bir `XmlSerializer` örneğini serileştirmek için kullanılan `Books` sınıfı. Kod çağrıları `Serialize` yöntemiyle `XmlSerializerNamespaces`, önekli ad alanları içeren XML izin verme.

```vb
Option Explicit
public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}

Option Strict

Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Class Run

    Public Shared Sub Main()
        Dim test As New Run()
        test.SerializeObject("XmlNamespaces.xml")
    End Sub 'Main

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Class

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class 'Books

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book

    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _
        price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Run
{
    public static void Main()
    {
        Run test = new Run();
        test.SerializeObject("XmlNamespaces.xml");
    }
    public void SerializeObject(string filename)
    {
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        XmlSerializerNamespaces myNamespaces =
        new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        Book myBook = new Book();
        myBook.TITLE = "A Book Title";
        Price myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        Books myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Serialization.XmlSerializer>
- [XML Şema Tanımı Aracı ve XML Serileştirme](the-xml-schema-definition-tool-and-xml-serialization.md)
- [XML Serileştirmeye Giriş](introducing-xml-serialization.md)
- [XmlSerializer sınıfını](xref:System.Xml.Serialization.XmlSerializer)
- [XML Serileştirmeyi Denetleyen Öznitelikler](attributes-that-control-xml-serialization.md)
- [Nasıl yapılır: XML Akışı için Alternatif Öğe Adı Belirtme](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Nasıl yapılır: Nesne Serileştirme](how-to-serialize-an-object.md)
- [Nasıl yapılır: Nesneyi Seri Durumdan Çıkarma](how-to-deserialize-an-object.md)
