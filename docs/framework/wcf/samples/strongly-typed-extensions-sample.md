---
title: "Güçlü Yazılmış Uzantılar Örneği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6f6a1d205a0e8443d7dc81da53855a1b7920def
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="strongly-typed-extensions-sample"></a><span data-ttu-id="03dbe-102">Güçlü Yazılmış Uzantılar Örneği</span><span class="sxs-lookup"><span data-stu-id="03dbe-102">Strongly-Typed Extensions Sample</span></span>
<span data-ttu-id="03dbe-103">Örnek kullanır <xref:System.ServiceModel.Syndication.SyndicationFeed> amacıyla sınıfının örneği.</span><span class="sxs-lookup"><span data-stu-id="03dbe-103">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="03dbe-104">Ancak, bu örnekte gösterilen desenleri tüm uzantısını verileri destekleyen dağıtım sınıflar ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="03dbe-104">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data.</span></span>  
  
 <span data-ttu-id="03dbe-105">Dağıtım nesnesi modeli (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, ve ilgili sınıflar) kullanarak uzantısı verilere erişim geniş yazılmış destekler <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> ve <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="03dbe-105">The Syndication object model (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, and related classes) supports loosely-typed access to extension data by using the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> properties.</span></span> <span data-ttu-id="03dbe-106">Bu örnek özel türetilmiş sınıfları uygulayarak uzantısını verileri kesin türü belirtilmiş erişim sağlamak nasıl göstermektedir <xref:System.ServiceModel.Syndication.SyndicationFeed> ve <xref:System.ServiceModel.Syndication.SyndicationItem> , kullanılabilir duruma kesin türü belirtilmiş özellikleri olarak belirli bir uygulamaya özgü uzantılar.</span><span class="sxs-lookup"><span data-stu-id="03dbe-106">This sample shows how to provide strongly-typed access to extension data by implementing custom derived classes of <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that make available certain application-specific extensions as strongly-typed properties.</span></span>  
  
 <span data-ttu-id="03dbe-107">Örnek olarak, bu örnek nasıl önerilen Atom iş parçacığı oluşturma uzantıları RFC tanımlı bir uzantı öğesi uygulanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="03dbe-107">As an example, this sample shows how to implement an extension element defined in the proposed Atom Threading Extensions RFC.</span></span> <span data-ttu-id="03dbe-108">Bu yalnızca tanıtım amacıyla ve bu örnek Önerilen belirtim tam uygulamasını amaçlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="03dbe-108">This is for demonstration purposes only and this sample is not intended to be a full implementation of the proposed specification.</span></span>  
  
## <a name="sample-xml"></a><span data-ttu-id="03dbe-109">Örnek XML</span><span class="sxs-lookup"><span data-stu-id="03dbe-109">Sample XML</span></span>  
 <span data-ttu-id="03dbe-110">Aşağıdaki XML örneği olan ek bir Atom 1.0 giriş gösterir `<in-reply-to>` uzantı öğesi.</span><span class="sxs-lookup"><span data-stu-id="03dbe-110">The following XML example shows an Atom 1.0 entry with an additional `<in-reply-to>` extension element.</span></span>  
  
```xml  
<entry>  
    <id>tag:example.org,2005:1,2</id>  
    <title type="text">Another response to the original</title>  
    <summary type="text">  
         This is a response to the original entry</summary>  
    <updated>2006-03-01T12:12:13Z</updated>  
    <link href="http://www.example.org/entries/1/2" />  
    <in-reply-to p3:ref="tag:example.org,2005:1"   
                 p3:href="http://www.example.org/entries/1"   
                 p3:type="application/xhtml+xml"   
                 xmlns:p3="http://contoso.org/syndication/thread/1.0"   
                 xmlns="http://contoso.org/syndication/thread/1.0">  
      <anotherElement xmlns="http://www.w3.org/2005/Atom">  
                     Some more data</anotherElement>  
      <aDifferentElement xmlns="http://www.w3.org/2005/Atom">  
                     Even more data</aDifferentElement>  
    </in-reply-to>  
</entry>  
```  
  
 <span data-ttu-id="03dbe-111">`<in-reply-to>` Öğesi üç gerekli öznitelikler belirtir (`ref`, `type` ve `href`) ek uzantı öznitelikleri ve genişletme öğeleri varlığını ayrıca verirken.</span><span class="sxs-lookup"><span data-stu-id="03dbe-111">The `<in-reply-to>` element specifies three required attributes (`ref`, `type` and `href`) while also allowing for the presence of additional extension attributes and extension elements.</span></span>  
  
## <a name="modeling-the-in-reply-to-element"></a><span data-ttu-id="03dbe-112">In-Yanıtla öğesi modelleme</span><span class="sxs-lookup"><span data-stu-id="03dbe-112">Modeling the In-Reply-To element</span></span>  
 <span data-ttu-id="03dbe-113">Bu örnekte `<in-reply-to>` öğesi uygulayan CLR Modellenen <xref:System.Xml.Serialization.IXmlSerializable>, ile kullanımı sağlayan <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="03dbe-113">In this sample, the `<in-reply-to>` element is modeled as CLR that implements <xref:System.Xml.Serialization.IXmlSerializable>, which enables its use with the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="03dbe-114">Bu da bazı yöntemleri ve özellikleri öğenin verilere erişmek için aşağıdaki örnek kodda gösterildiği gibi uygular.</span><span class="sxs-lookup"><span data-stu-id="03dbe-114">It also implements some methods and properties for accessing the element’s data, as shown in the following sample code.</span></span>  
  
```  
[XmlRoot(ElementName = "in-reply-to", Namespace = "http://contoso.org/syndication/thread/1.0")]  
public class InReplyToElement : IXmlSerializable  
{  
    internal const string ElementName = "in-reply-to";  
    internal const string NsUri =   
                  "http://contoso.org/syndication/thread/1.0";  
    private Dictionary<XmlQualifiedName, string> extensionAttributes;  
    private Collection<XElement> extensionElements;  
  
    public InReplyToElement()  
    {  
        this.extensionElements = new Collection<XElement>();  
        this.extensionAttributes = new Dictionary<XmlQualifiedName,   
                                                          string>();  
    }  
  
    public Dictionary<XmlQualifiedName, string> AttributeExtensions  
    {  
        get { return this.extensionAttributes; }  
    }  
  
    public Collection<XElement> ElementExtensions  
    {  
        get { return this.extensionElements; }  
    }  
  
    public Uri Href  
    { get; set; }  
  
    public string MediaType  
    { get; set; }  
  
    public string Ref  
    { get; set; }  
  
    public Uri Source  
    { get; set; }  
}  
```  
  
 <span data-ttu-id="03dbe-115">`InReplyToElement` Sınıf gereken özniteliği özelliklerini uygular (`HRef`, `MediaType`, ve `Source`) tutmak için koleksiyonları yanı sıra <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> ve <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="03dbe-115">The `InReplyToElement` class implements properties for the required attribute (`HRef`, `MediaType`, and `Source`) as well as collections to hold <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span></span>  
  
 <span data-ttu-id="03dbe-116">`InReplyToElement` Uygulayan sınıf <xref:System.Xml.Serialization.IXmlSerializable> nesnesi örneklerinin nasıl okuma ve XML olarak yazılmış üzerinde doğrudan denetim sağlayan arabirim.</span><span class="sxs-lookup"><span data-stu-id="03dbe-116">The `InReplyToElement` class implements the <xref:System.Xml.Serialization.IXmlSerializable> interface, which allows direct control over how object instances are read from and written to XML.</span></span> <span data-ttu-id="03dbe-117">`ReadXml` Yöntemi ilk değerlerini okur `Ref`, `HRef`, `Source`, ve `MediaType` özelliklerinden <xref:System.Xml.XmlReader> kendisine geçirilen.</span><span class="sxs-lookup"><span data-stu-id="03dbe-117">The `ReadXml` method first reads the values for the `Ref`, `HRef`, `Source`, and `MediaType` properties from the <xref:System.Xml.XmlReader> passed to it.</span></span> <span data-ttu-id="03dbe-118">Bilinmeyen öznitelik depolanmış <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="03dbe-118">Any unknown attributes are stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection.</span></span> <span data-ttu-id="03dbe-119">Tüm öznitelikleri okuduktan sonra <xref:System.Xml.XmlReader.ReadStartElement> sonraki öğeye okuyucu ilerletmek için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="03dbe-119">When all the attributes have been read, <xref:System.Xml.XmlReader.ReadStartElement> is called to advance the reader to the next element.</span></span> <span data-ttu-id="03dbe-120">Bu sınıf tarafından modellenir öğesi gerekli alt öğesi olduğundan, alt öğelerini içine arabelleğe `XElement` örnekleri ve depolanan <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> aşağıdaki kodda gösterildiği gibi koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="03dbe-120">Because the element modeled by this class has no required children, the child elements get buffered into `XElement` instances and stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection, as shown in the following code.</span></span>  
  
```  
public void ReadXml(System.Xml.XmlReader reader)  
{  
    bool isEmpty = reader.IsEmptyElement;  
  
    if (reader.HasAttributes)  
    {  
        for (int i = 0; i < reader.AttributeCount; i++)  
        {  
            reader.MoveToNextAttribute();  
  
            if (reader.NamespaceURI == "")  
            {  
                if (reader.LocalName == "ref")  
                {  
                    this.Ref = reader.Value;  
                }  
                else if (reader.LocalName == "href")  
                {  
                    this.Href = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "source")  
                {  
                    this.Source = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "type")  
                {  
                    this.MediaType = reader.Value;  
                }  
                else  
                {  
                    this.AttributeExtensions.Add(new   
                                 XmlQualifiedName(reader.LocalName,   
                                 reader.NamespaceURI),   
                                 reader.Value);  
                }  
            }  
        }  
    }  
  
    reader.ReadStartElement();  
  
    if (!isEmpty)  
    {  
        while (reader.IsStartElement())  
        {  
            ElementExtensions.Add(  
                  (XElement) XElement.ReadFrom(reader));  
        }  
        reader.ReadEndElement();  
    }  
}  
```  
  
 <span data-ttu-id="03dbe-121">İçinde `WriteXml`, `InReplyToElement` yöntemi ilk değerlerini Yazar `Ref`, `HRef`, `Source`, ve `MediaType` özellikleri XML öznitelikleri olarak (`WriteXml` gerçek dış öğe yazmak için sorumlu değildir çağıran tarafından yapılan olarak kendisini `WriteXml`).</span><span class="sxs-lookup"><span data-stu-id="03dbe-121">In `WriteXml`, the `InReplyToElement` method first writes out the values of the `Ref`, `HRef`, `Source`, and `MediaType` properties as XML attributes (`WriteXml` is not responsible for writing the actual outer element itself, as that done by the caller of `WriteXml`).</span></span> <span data-ttu-id="03dbe-122">Ayrıca içeriğini Yazar <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> ve <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> aşağıdaki kodda gösterildiği gibi yazıcı.</span><span class="sxs-lookup"><span data-stu-id="03dbe-122">It also writes the contents of the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> to the writer, as shown in the following code.</span></span>  
  
```  
public void WriteXml(System.Xml.XmlWriter writer)  
{  
    if (this.Ref != null)  
    {  
        writer.WriteAttributeString("ref", InReplyToElement.NsUri,   
                                            this.Ref);  
    }  
    if (this.Href != null)  
    {  
        writer.WriteAttributeString("href", InReplyToElement.NsUri,   
                                                this.Href.ToString());  
    }  
    if (this.Source != null)  
    {  
        writer.WriteAttributeString("source", InReplyToElement.NsUri,   
                                              this.Source.ToString());  
    }  
    if (this.MediaType != null)  
    {  
        writer.WriteAttributeString("type", InReplyToElement.NsUri,   
                                                    this.MediaType);  
    }  
  
    foreach (KeyValuePair<XmlQualifiedName, string> kvp in   
                                             this.AttributeExtensions)  
    {  
        writer.WriteAttributeString(kvp.Key.Name, kvp.Key.Namespace,   
                                                   kvp.Value);  
    }  
  
    foreach (XElement element in this.ElementExtensions)  
    {  
        element.WriteTo(writer);  
    }  
}  
```  
  
## <a name="threadedfeed-and-threadeditem"></a><span data-ttu-id="03dbe-123">ThreadedFeed ve ThreadedItem</span><span class="sxs-lookup"><span data-stu-id="03dbe-123">ThreadedFeed and ThreadedItem</span></span>  
 <span data-ttu-id="03dbe-124">Örnekte, `SyndicationItems` ile `InReplyTo` uzantıları tarafından modellenir `ThreadedItem` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="03dbe-124">In the sample, `SyndicationItems` with `InReplyTo` extensions are modeled by the `ThreadedItem` class.</span></span> <span data-ttu-id="03dbe-125">Benzer şekilde, `ThreadedFeed` sınıfı bir `SyndicationFeed` öğelerinin olan tüm örneklerini `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="03dbe-125">Similarly, the `ThreadedFeed` class is a `SyndicationFeed` whose items are all instances of `ThreadedItem`.</span></span>  
  
 <span data-ttu-id="03dbe-126">`ThreadedFeed` Sınıfının devraldığı `SyndicationFeed` ve geçersiz kılmalar `OnCreateItem` döndürmek için bir `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="03dbe-126">The `ThreadedFeed` class inherits from `SyndicationFeed` and overrides `OnCreateItem` to return a `ThreadedItem`.</span></span> <span data-ttu-id="03dbe-127">Erişim için bir yöntem de uygulayan `Items` koleksiyonu olarak `ThreadedItems`aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="03dbe-127">It also implements a method for accessing the `Items` collection as `ThreadedItems`, as shown in the following code.</span></span>  
  
```  
public class ThreadedFeed : SyndicationFeed  
{  
    public ThreadedFeed()  
    {  
    }  
  
    public IEnumerable<ThreadedItem> ThreadedItems  
    {  
        get  
        {  
            return this.Items.Cast<ThreadedItem>();  
        }  
    }  
  
    protected override SyndicationItem CreateItem()  
    {  
        return new ThreadedItem();  
    }  
}  
```  
  
 <span data-ttu-id="03dbe-128">Sınıf `ThreadedItem` devraldığı `SyndicationItem` ve yapar `InReplyToElement` kesin türü belirtilmiş bir özellik olarak.</span><span class="sxs-lookup"><span data-stu-id="03dbe-128">The class `ThreadedItem` inherits from `SyndicationItem` and makes `InReplyToElement` as a strongly-typed property.</span></span> <span data-ttu-id="03dbe-129">Bu kullanışlı programlı erişim sağlayan `InReplyTo` uzantısını verileri.</span><span class="sxs-lookup"><span data-stu-id="03dbe-129">This provides for convenient programmatic access to the `InReplyTo` extension data.</span></span> <span data-ttu-id="03dbe-130">Ayrıca uygulayan `TryParseElement` ve `WriteElementExtensions` okumak ve aşağıdaki kodda gösterildiği gibi uzantısı verilerini yazmak için.</span><span class="sxs-lookup"><span data-stu-id="03dbe-130">It also implements `TryParseElement` and `WriteElementExtensions` for reading and writing its extension data, as shown in the following code.</span></span>  
  
```  
public class ThreadedItem : SyndicationItem  
{  
    private InReplyToElement inReplyTo;  
    // Constructors  
        public ThreadedItem()  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
        public ThreadedItem(string title, string content, Uri itemAlternateLink, string id, DateTimeOffset lastUpdatedTime) : base(title, content, itemAlternateLink, id, lastUpdatedTime)  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
    public InReplyToElement InReplyTo  
    {  
        get { return this.inReplyTo; }  
    }  
  
    protected override bool TryParseElement(  
                        System.Xml.XmlReader reader,   
                        string version)  
    {  
        if (version == SyndicationVersions.Atom10 &&  
            reader.NamespaceURI == InReplyToElement.NsUri &&  
            reader.LocalName == InReplyToElement.ElementName)  
        {  
            this.inReplyTo = new InReplyToElement();  
  
            this.InReplyTo.ReadXml(reader);  
  
            return true;  
        }  
        else  
        {  
            return base.TryParseElement(reader, version);  
        }  
    }  
  
    protected override void WriteElementExtensions(XmlWriter writer,   
                                                 string version)  
    {  
        if (this.InReplyTo != null &&   
                     version == SyndicationVersions.Atom10)  
        {  
            writer.WriteStartElement(InReplyToElement.ElementName,   
                                           InReplyToElement.NsUri);  
            this.InReplyTo.WriteXml(writer);  
            writer.WriteEndElement();  
        }  
  
        base.WriteElementExtensions(writer, version);  
    }  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="03dbe-131">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="03dbe-131">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="03dbe-132">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03dbe-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="03dbe-133">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03dbe-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="03dbe-134">Tek veya çapraz makine yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03dbe-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03dbe-135">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="03dbe-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="03dbe-136">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="03dbe-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="03dbe-137">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="03dbe-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03dbe-138">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="03dbe-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="03dbe-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="03dbe-139">See Also</span></span>