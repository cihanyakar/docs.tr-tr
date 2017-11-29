---
title: "İç içe geçme DataRelations"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db7df753bf6066d3a89c46a82b66e47281076f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="nesting-datarelations"></a><span data-ttu-id="1895e-102">İç içe geçme DataRelations</span><span class="sxs-lookup"><span data-stu-id="1895e-102">Nesting DataRelations</span></span>
<span data-ttu-id="1895e-103">İlişkisel bir veri içinde gösterimini tek tek tablolar birbirine bir sütun veya sütun kümesini kullanarak ilişkili satırları içerir.</span><span class="sxs-lookup"><span data-stu-id="1895e-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="1895e-104">ADO.NET <xref:System.Data.DataSet>, tablolar arasında ilişki kullanılarak uygulanan bir <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="1895e-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="1895e-105">Oluştururken bir **DataRelation**, sütun üst alt ilişkilerinde yalnızca ilişkisi yönetilir.</span><span class="sxs-lookup"><span data-stu-id="1895e-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="1895e-106">Tablolar ve sütunlar ayrı varlıklardır.</span><span class="sxs-lookup"><span data-stu-id="1895e-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="1895e-107">XML sağlayan veri hiyerarşik gösterimini üst alt ilişkilerinde iç içe geçmiş alt öğeleri içeren üst öğeler tarafından temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="1895e-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="1895e-108">İç içe alt nesnelerin kolaylaştırmak için bir **DataSet** ile eşitlenen bir <xref:System.Xml.XmlDataDocument> veya XML verileri kullanarak olarak yazılmış **WriteXml**, **DataRelation** kullanıma sunan bir **iç içe** özelliği.</span><span class="sxs-lookup"><span data-stu-id="1895e-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="1895e-109">Ayarı **iç içe** özelliği bir **DataRelation** için **true** alt satır XML verileri olarak yazılırken üst sütun içinde iç içe ilişkisinin neden olan veya eşitlenmiş bir **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="1895e-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="1895e-110">**İç içe** özelliği **DataRelation** olan **yanlış**, varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="1895e-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="1895e-111">Örneğin, aşağıdakileri göz önünde bulundurun **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="1895e-111">For example, consider the following **DataSet**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 <span data-ttu-id="1895e-112">Çünkü **iç içe** özelliği **DataRelation** nesne ayarlı değil **true** bu **DataSet**, bağımlı nesneler iç içe değil üst öğeler içinde olduğunda bu **DataSet** XML verileri olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="1895e-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="1895e-113">XML gösterimini dönüştürme bir **DataSet** içeren ilgili **DataSet**olmayan iç içe geçmiş veri ilişkileri s yavaş performans neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="1895e-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="1895e-114">Veri ilişkileri içe öneririz.</span><span class="sxs-lookup"><span data-stu-id="1895e-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="1895e-115">Bunu yapmak için ayarlayın **iç içe** özelliğine **doğru**.</span><span class="sxs-lookup"><span data-stu-id="1895e-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="1895e-116">Ardından kod bulun ve verileri dönüştürmek için yukarıdan aşağıya doğru hiyerarşik XPath sorgu ifadeleri kullanan XSLT stil sayfası yazın.</span><span class="sxs-lookup"><span data-stu-id="1895e-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="1895e-117">Aşağıdaki kod örneğinde arama sonuç gösterir **WriteXml** üzerinde **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="1895e-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 <span data-ttu-id="1895e-118">Unutmayın **müşteriler** öğesi ve **siparişleri** öğeleri Eşdüzey öğeleri olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="1895e-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="1895e-119">İsterseniz **siparişleri** kendi ilgili üst öğeler alt öğesi olarak görüntülenmesini öğeleri **iç içe** özelliği **DataRelation** içinayarlanmışolmasıgerekir**doğru** ve aşağıdaki eklemeniz:</span><span class="sxs-lookup"><span data-stu-id="1895e-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="1895e-120">Aşağıdaki kod sonuçta çıktı gibi görünür gösterir ile **siparişleri** öğeleri, ilgili üst öğelerini içinde iç içe geçmiş.</span><span class="sxs-lookup"><span data-stu-id="1895e-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1895e-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1895e-121">See Also</span></span>  
 [<span data-ttu-id="1895e-122">Bir veri kümesini XML kullanma</span><span class="sxs-lookup"><span data-stu-id="1895e-122">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="1895e-123">DataRelation ekleme</span><span class="sxs-lookup"><span data-stu-id="1895e-123">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [<span data-ttu-id="1895e-124">Veri kümeleri, DataTable ve DataView</span><span class="sxs-lookup"><span data-stu-id="1895e-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="1895e-125">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="1895e-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)