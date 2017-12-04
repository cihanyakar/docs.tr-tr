---
title: "Varlık etkinlikleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ec801ca995ec30c86fa003d16379bc2c6620aa0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="entity-activities"></a><span data-ttu-id="1ccaf-102">Varlık etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="1ccaf-102">Entity Activities</span></span>
<span data-ttu-id="1ccaf-103">Bu örnek ADO.NET Entity Framework ile kullanmayı gösterir [!INCLUDE[wf2](../../../../includes/wf2-md.md)] veri erişimi basitleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-103">This sample shows how to use the ADO.NET Entity Framework with [!INCLUDE[wf2](../../../../includes/wf2-md.md)] to simplify data access.</span></span>  
  
 <span data-ttu-id="1ccaf-104">ADO.NET Entity Framework, özellikler ve ilişkiler müşteriler, siparişler, sipariş ayrıntılarını ve bu varlıkları arasındaki ilişkileri gibi etki alanına özgü nesneleri biçiminde verilerle çalışmak geliştiricilerin sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="1ccaf-105">ADO.NET Entity Framework bunu doğrudan bir ilişkisel depolama şema karşı programlama yerine kavramsal uygulama modeli karşı programlama etkinleştirir özet düzeyi sağlayarak gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1ccaf-106">ADO.NET Entity Framework Bkz: [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span><span class="sxs-lookup"><span data-stu-id="1ccaf-106"> the ADO.NET Entity Framework see [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="1ccaf-107">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="1ccaf-107">Sample details</span></span>  
 <span data-ttu-id="1ccaf-108">Bu örnekte `Northwind` veritabanı ve oluşturma ve kaldırma için komutlar içerir `Northwind` veritabanı (Setup.cmd ve Cleanup.cmd).</span><span class="sxs-lookup"><span data-stu-id="1ccaf-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="1ccaf-109">Bu örnek projelerinde göre bir varlık veri modeli dahil `Northwind` veritabanı.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="1ccaf-110">Model açarak bulabileceğiniz `Northwind.edmx` projeye dahil dosyası.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="1ccaf-111">ADO.NET Entity Framework kullanılarak erişilebilir nesnelerin şeklini tanımlayan modeli budur.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="1ccaf-112">Bu örnekte aşağıdaki etkinlikleri bulunmaktadır:</span><span class="sxs-lookup"><span data-stu-id="1ccaf-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="1ccaf-113">`EntitySQLQuery``EntitySQLQuery` Etkinliği bir varlık SQL sorgu dizesine dayalı veritabanından nesneleri almanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="1ccaf-114">Varlık SQL, SQL için benzer bir mağaza bağımsız dildir ve kavramsal model ve model veya etki alanının parçası olan varlıkların temel alan sorgular belirtmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1ccaf-115">Varlık SQL dil bkz [varlık SQL dil](http://go.microsoft.com/fwlink/?LinkId=165646).</span><span class="sxs-lookup"><span data-stu-id="1ccaf-115"> Entity SQL Language, see [Entity SQL Language](http://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="1ccaf-116">`EntityLinqQuery`: Bu etkinlik, bir LINQ Sorgu veya koşulu göre veritabanından nesneleri almanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="1ccaf-117">`EntityAdd``EntityAdd` Etkinlik, bir varlık veya bir varlıklar koleksiyonu veritabanına eklemenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="1ccaf-118">`EntityDelete``EntityDelete` Etkinlik, bir varlık veya bir varlıklar koleksiyonu veritabanından silmek sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="1ccaf-119">`ObjectContextScope`: Yukarıda açıklanan etkinlikler içeren bir içinde yalnızca kullanılabilir `ObjectContextScope` etkinliği örneği.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="1ccaf-120">`ObjectContextScope` Etkinlik veritabanına bağlantı kurar.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="1ccaf-121">(Ya da geçirilen veya bir yapılandırma dosyası ayarı kullanılarak alınıp) bir bağlantı dizesi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="1ccaf-122">`ObjectContextScope` Etkinlik grubu varlıkları ilgili işlemlerinin gerçekleştirmek kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="1ccaf-123">Bu kapsam etkin bir bağlantı korur, Hayır kalıcı bir kapsam demektir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="1ccaf-124">Ayrıca, `ObjectContextScope` etkinlik çıkar, varlık etkinlikleri kullanarak bu kapsamı içinde otomatik olarak alınan nesnelere yapılan değişiklikleri veritabanına kalıcı ve nesneleri geri için hiçbir açık veya sonraki bir eylem gerekli Veritabanı.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="1ccaf-125">Varlık etkinlikleri kullanma</span><span class="sxs-lookup"><span data-stu-id="1ccaf-125">Using the entity activities</span></span>  
 <span data-ttu-id="1ccaf-126">Aşağıdaki kod parçacıkları, bu örnekte sunulan varlık etkinlikleri kullanımını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="1ccaf-127">EntitySql</span><span class="sxs-lookup"><span data-stu-id="1ccaf-127">EntitySql</span></span>  
 <span data-ttu-id="1ccaf-128">Aşağıdaki kod parçacığında adına göre sıralanmış Londra'daki tüm müşteriler sorgulama ve müşterilerin listesini yineleme gösterir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="1ccaf-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="1ccaf-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="1ccaf-130">Aşağıdaki kod parçacığında, Londra'daki tüm müşteriler sorgulama ve ortaya çıkan müşteriler listesi yineleme gösterir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="1ccaf-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="1ccaf-131">EntityAdd</span></span>  
 <span data-ttu-id="1ccaf-132">Aşağıdaki kod parçacığında, bir OrderDetail kaydı için var olan bir siparişi ekleme gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="1ccaf-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="1ccaf-133">EntityDelete</span></span>  
 <span data-ttu-id="1ccaf-134">Aşağıdaki kod parçacığında, (varsa) bir sırada varolan OrderDetail kaydını silmek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="1ccaf-135">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="1ccaf-135">To use this sample</span></span>  
 <span data-ttu-id="1ccaf-136">Oluşturmanız gerekir `Northwind` Bu örneği çalıştırmadan önce yerel SQL server Express örneği veritabanında.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="1ccaf-137">Northwind veritabanı ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="1ccaf-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="1ccaf-138">Bir komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="1ccaf-139">Yeni bir komut istemi penceresinde EntityActivities\CS klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="1ccaf-140">Tür `setup.cmd` ve ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="1ccaf-141">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="1ccaf-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="1ccaf-142">Kullanarak [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], EntityActivities.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1ccaf-143">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1ccaf-144">Çözümü çalıştırmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="1ccaf-145">Bu örnek çalıştırdıktan sonra kaldırmak isteyebilirsiniz `Northwind` veritabanı.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="1ccaf-146">Northwind veritabanı kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="1ccaf-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="1ccaf-147">Bir komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="1ccaf-148">Yeni bir komut istemi penceresinde EntityActivities\CS klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="1ccaf-149">Tür `cleanup.cmd` ve ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ccaf-150">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1ccaf-151">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1ccaf-152">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ccaf-153">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="1ccaf-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`