---
title: XPathDocument ve XmlDocument kullanarak XML verilerini okuma
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 607d9d3616db0d0bd431fa2ca0b6aee03a85f896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a><span data-ttu-id="cd551-102">XPathDocument ve XmlDocument kullanarak XML verilerini okuma</span><span class="sxs-lookup"><span data-stu-id="cd551-102">Reading XML Data using XPathDocument and XmlDocument</span></span>
<span data-ttu-id="cd551-103">XML belgesi olarak okumak için iki yolla <xref:System.Xml.XPath?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="cd551-103">There are two ways to read an XML document in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="cd551-104">Salt okunur kullanarak bir XML belgesi okumak için biridir <xref:System.Xml.XPath.XPathDocument> sınıfı ve diğer olan düzenlenebilir kullanarak bir XML belgesi okumak için <xref:System.Xml.XmlDocument> sınıfını <xref:System.Xml?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="cd551-104">One is to read an XML document using the read-only <xref:System.Xml.XPath.XPathDocument> class and the other is to read an XML document using the editable <xref:System.Xml.XmlDocument> class in the <xref:System.Xml?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a><span data-ttu-id="cd551-105">Okuma XML belgelerini XPathDocument sınıfını kullanma</span><span class="sxs-lookup"><span data-stu-id="cd551-105">Reading XML Documents using the XPathDocument Class</span></span>  
 <span data-ttu-id="cd551-106"><xref:System.Xml.XPath.XPathDocument> Sınıfı XPath veri modelini kullanarak bir XML belgesi hızlı, salt okunur, bellek içi bir gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="cd551-106">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="cd551-107">Örneklerini <xref:System.Xml.XPath.XPathDocument> sınıfı altı oluşturucular biri kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="cd551-107">Instances of the <xref:System.Xml.XPath.XPathDocument> class are created using one of its six constructors.</span></span> <span data-ttu-id="cd551-108">Bu oluşturucu kullanılarak bir XML belgesi okuma izin bir <xref:System.IO.Stream>, <xref:System.IO.TextReader>, veya <xref:System.Xml.XmlReader> nesnesi yanı sıra `string` bir XML dosyasının yolu.</span><span class="sxs-lookup"><span data-stu-id="cd551-108">These constructors allow you to read an XML document using a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="cd551-109">Aşağıdaki örnek kullanarak gösterilmektedir <xref:System.Xml.XPath.XPathDocument> sınıfının `string` bir XML belgesi okumak için Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="cd551-109">The following example illustrates using the <xref:System.Xml.XPath.XPathDocument> class's `string` constructor to read an XML document.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a><span data-ttu-id="cd551-110">XmlDocument sınıfını kullanarak XML belgeleri okuma</span><span class="sxs-lookup"><span data-stu-id="cd551-110">Reading XML Documents using the XmlDocument Class</span></span>  
 <span data-ttu-id="cd551-111"><xref:System.Xml.XmlDocument> W3C belge nesne modeli (DOM) Düzey 1 çekirdek ve çekirdek DOM Düzey 2 uygulayan bir XML belgesi düzenlenebilir bir bellek içi temsili bir sınıftır.</span><span class="sxs-lookup"><span data-stu-id="cd551-111">The <xref:System.Xml.XmlDocument> class is an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="cd551-112">Örneklerini <xref:System.Xml.XmlDocument> sınıfı, üç oluşturucular biri kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="cd551-112">Instances of the <xref:System.Xml.XmlDocument> class are created using one of its three constructors.</span></span> <span data-ttu-id="cd551-113">Yeni, boş oluşturabilirsiniz <xref:System.Xml.XmlDocument> çağırarak nesne <xref:System.Xml.XmlDocument> hiçbir parametre sınıfı oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="cd551-113">You can create a new, empty <xref:System.Xml.XmlDocument> object by calling the <xref:System.Xml.XmlDocument> class constructor with no parameters.</span></span> <span data-ttu-id="cd551-114">Oluşturucusu çağrıldıktan sonra kullanın <xref:System.Xml.XmlDocument.Load%2A> metodu XML verilerini yeni içine yüklemek için <xref:System.Xml.XmlDocument> nesnesinin bir <xref:System.IO.Stream>, <xref:System.IO.TextReader>, veya <xref:System.Xml.XmlReader> nesnesi yanı sıra `string` bir XML dosyasının yolu.</span><span class="sxs-lookup"><span data-stu-id="cd551-114">After calling the constructor, use the <xref:System.Xml.XmlDocument.Load%2A> method to load XML data into the new <xref:System.Xml.XmlDocument> object from a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="cd551-115">Kullanarak aşağıdaki örnekte gösterilmiştir <xref:System.Xml.XmlDocument> hiçbir parametre sınıfı oluşturucusu ve <xref:System.Xml.XmlDocument.Load%2A> bir XML belgesi okumak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="cd551-115">The following example illustrates using the <xref:System.Xml.XmlDocument> class constructor with no parameters and the <xref:System.Xml.XmlDocument.Load%2A> method to read an XML document.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a><span data-ttu-id="cd551-116">Bir XML belgesi kodlama belirleme</span><span class="sxs-lookup"><span data-stu-id="cd551-116">Determining the Encoding of an XML Document</span></span>  
 <span data-ttu-id="cd551-117">Bir <xref:System.Xml.XmlReader> nesne bir XML belgesi okuyun ve oluşturmak için kullanılabilir <xref:System.Xml.XPath.XPathDocument> ve <xref:System.Xml.XmlDocument> nesneleri önceki bölümlerde gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="cd551-117">An <xref:System.Xml.XmlReader> object can be used to read an XML document and to create <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> objects as shown in the previous sections.</span></span> <span data-ttu-id="cd551-118">Ancak, bir <xref:System.Xml.XmlReader> nesnesi kodlanmamış ve sonuç olarak herhangi bir kodlama bilgi sağlamaz veri okuma.</span><span class="sxs-lookup"><span data-stu-id="cd551-118">However, an <xref:System.Xml.XmlReader> object may read data that is not encoded and as a result does not provide any encoding information.</span></span>  
  
 <span data-ttu-id="cd551-119"><xref:System.Xml.XmlTextReader> Sınıfının devraldığı <xref:System.Xml.XmlReader> sınıfı, kodlama bilgileri kullanarak sağlar, <xref:System.Xml.XmlTextReader.Encoding%2A> özelliği ve oluşturmak için kullanılan bir <xref:System.Xml.XPath.XPathDocument> nesne veya <xref:System.Xml.XmlDocument> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="cd551-119">The <xref:System.Xml.XmlTextReader> class inherits from the <xref:System.Xml.XmlReader> class, provides encoding information using its <xref:System.Xml.XmlTextReader.Encoding%2A> property, and can be used to create an <xref:System.Xml.XPath.XPathDocument> object or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="cd551-120">Tarafından sağlanan kodlama bilgileri hakkında daha fazla bilgi için <xref:System.Xml.XmlTextReader> sınıfı için bkz: <xref:System.Xml.XmlTextReader.Encoding%2A> özelliğinde <xref:System.Xml.XmlTextReader> sınıf başvurusu belgelerinde.</span><span class="sxs-lookup"><span data-stu-id="cd551-120">For more information about the encoding information provided by the <xref:System.Xml.XmlTextReader> class, see the <xref:System.Xml.XmlTextReader.Encoding%2A> property in the <xref:System.Xml.XmlTextReader> class reference documentation.</span></span>  
  
## <a name="creating-xpathnavigator-objects"></a><span data-ttu-id="cd551-121">XPathNavigator nesneleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="cd551-121">Creating XPathNavigator Objects</span></span>  
 <span data-ttu-id="cd551-122">Ya da bir XML belgesi okuduktan sonra bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne oluşturabileceğiniz bir <xref:System.Xml.XPath.XPathNavigator> nesneyi seçin, değerlendirmek, sayfasına gidin ve bazı durumlarda, temel alınan XML verilerini düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="cd551-122">After you have read an XML document into either an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, you can create an <xref:System.Xml.XPath.XPathNavigator> object to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="cd551-123">Hem <xref:System.Xml.XPath.XPathDocument> ve <xref:System.Xml.XmlDocument> , ayrıca için sınıfları <xref:System.Xml.XmlNode> sınıfı, uygulama <xref:System.Xml.XPath.IXPathNavigable> arabiriminin <xref:System.Xml.XPath?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="cd551-123">Both the <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> classes, in addition to the <xref:System.Xml.XmlNode> class, implement the <xref:System.Xml.XPath.IXPathNavigable> interface of the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="cd551-124">Sonuç olarak, tüm üç sınıf sağlayan bir <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> döndüren yöntemi bir <xref:System.Xml.XPath.XPathNavigator> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="cd551-124">As a result, all three classes provide a <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> method that returns an <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a><span data-ttu-id="cd551-125">XML belgeleri XPathNavigator sınıfı kullanarak düzenleme</span><span class="sxs-lookup"><span data-stu-id="cd551-125">Editing XML Documents using the XPathNavigator Class</span></span>  
 <span data-ttu-id="cd551-126">Seçerek, değerlendirme ve XML veri gezinme yanı sıra <xref:System.Xml.XPath.XPathNavigator> sınıfı, bazı durumlarda, oluşturulduğu nesnesini temel alan bir XML belgesi düzenlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="cd551-126">In addition to selecting, evaluating, and navigating XML data, the <xref:System.Xml.XPath.XPathNavigator> class can be used to edit an XML document in some cases, based on the object that created it.</span></span>  
  
 <span data-ttu-id="cd551-127"><xref:System.Xml.XPath.XPathDocument> Sınıftır salt okunur sırasında <xref:System.Xml.XmlDocument> sınıftır düzenlenebilir ve sonuç olarak, <xref:System.Xml.XPath.XPathNavigator> oluşturulan nesneleri bir <xref:System.Xml.XPath.XPathDocument> nesnesi, bir XML belgesi olanlar oluşturulduğu sırasında düzenlemek için kullanılamaz bir <xref:System.Xml.XmlDocument> nesne olabilir.</span><span class="sxs-lookup"><span data-stu-id="cd551-127">The <xref:System.Xml.XPath.XPathDocument> class is read-only while the <xref:System.Xml.XmlDocument> class is editable and as a result, <xref:System.Xml.XPath.XPathNavigator> objects created from an <xref:System.Xml.XPath.XPathDocument> object cannot be used to edit an XML document while those created from an <xref:System.Xml.XmlDocument> object can.</span></span> <span data-ttu-id="cd551-128"><xref:System.Xml.XPath.XPathDocument> Sınıfı, bir XML belgesi yalnızca okumak için kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cd551-128">The <xref:System.Xml.XPath.XPathDocument> class should be used to read an XML document only.</span></span> <span data-ttu-id="cd551-129">Gereken bir XML belgesi düzenlemek ya da tarafından sağlanan ek işlevsellik erişim gerektiren durumlarda <xref:System.Xml.XmlDocument> olay işleme gibi sınıfı <xref:System.Xml.XmlDocument> sınıfı kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cd551-129">In cases where you need to edit an XML document, or require access to the additional functionality provided by the <xref:System.Xml.XmlDocument> class, like event handling, the <xref:System.Xml.XmlDocument> class should be used.</span></span>  
  
 <span data-ttu-id="cd551-130"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Özelliği <xref:System.Xml.XPath.XPathNavigator> sınıfı belirtirse bir <xref:System.Xml.XPath.XPathNavigator> nesneyi XML verileri düzenleme.</span><span class="sxs-lookup"><span data-stu-id="cd551-130">The <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class specifies if an <xref:System.Xml.XPath.XPathNavigator> object may edit XML data.</span></span>  
  
 <span data-ttu-id="cd551-131">Aşağıdaki tabloda değerini açıklanmaktadır <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> her sınıf özelliği.</span><span class="sxs-lookup"><span data-stu-id="cd551-131">The following table describes the value of the <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property for each class.</span></span>  
  
|<span data-ttu-id="cd551-132"><xref:System.Xml.XPath.IXPathNavigable>Uygulama</span><span class="sxs-lookup"><span data-stu-id="cd551-132"><xref:System.Xml.XPath.IXPathNavigable> Implementation</span></span>|<span data-ttu-id="cd551-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>Değer</span><span class="sxs-lookup"><span data-stu-id="cd551-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Value</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a><span data-ttu-id="cd551-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cd551-134">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="cd551-135">XPath veri modelini kullanarak işlem XML verileri</span><span class="sxs-lookup"><span data-stu-id="cd551-135">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="cd551-136">XML XPathNavigator kullanarak verilerine erişme</span><span class="sxs-lookup"><span data-stu-id="cd551-136">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="cd551-137">XML XPathNavigator kullanarak verileri düzenleme</span><span class="sxs-lookup"><span data-stu-id="cd551-137">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="cd551-138">XPathNavigator kullanarak şema doğrulaması</span><span class="sxs-lookup"><span data-stu-id="cd551-138">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)