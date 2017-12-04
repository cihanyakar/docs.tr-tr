---
title: "GetSchema ve şeması koleksiyonları"
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
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4790195d5f02ac1f68f8ab4c5ef39499052cd725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="debe9-102">GetSchema ve şeması koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="debe9-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="debe9-103">**Bağlantı** her .NET Framework yönetilen sağlayıcıları uygulayan sınıflar bir **GetSchema** şu anda bağlı olduğu, veritabanında ilgili şema bilgileri almak için kullanılan yöntem ve döndürülen şema bilgileri **GetSchema** yöntemi gelen biçiminde bir <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="debe9-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="debe9-104">**GetSchema** dönmek için şema koleksiyonu belirtme ve döndürülen bilgi tutarını sınırlamak için isteğe bağlı parametreler sağlayan bir aşırı yüklenmiş yöntemin bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="debe9-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="debe9-105">Şema koleksiyonları belirtme</span><span class="sxs-lookup"><span data-stu-id="debe9-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="debe9-106">İlk isteğe bağlı parametresi **GetSchema** bir dize olarak belirtilen bir koleksiyon adını bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="debe9-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="debe9-107">Şema koleksiyonların iki tür vardır: tüm sağlayıcılar için ortak olan ortak şeması koleksiyonları ve her sağlayıcıya özgü belirli şeması koleksiyonları.</span><span class="sxs-lookup"><span data-stu-id="debe9-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="debe9-108">Çağıran desteklenen şema koleksiyonları listesini belirlemek için bir .NET Framework yönetilen sağlayıcısı sorgulayabilirsiniz **GetSchema** yöntemi bağımsız değişken içermeyen veya şema koleksiyonu adı "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="debe9-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="debe9-109">Bu döndürülecek bir <xref:System.Data.DataTable> desteklenen şeması koleksiyonları, her destekledikleri kısıtlama sayısı ve kullandıkları tanımlayıcı bölümlerinin sayısını listesini içeren.</span><span class="sxs-lookup"><span data-stu-id="debe9-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="debe9-110">Şema koleksiyonları örnek alma</span><span class="sxs-lookup"><span data-stu-id="debe9-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="debe9-111">Aşağıdaki örnekler nasıl kullanılacağını gösteren <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> SQL Server için .NET Framework veri sağlayıcısı yöntemi <xref:System.Data.SqlClient.SqlConnection> şema tüm içinde yer alan tabloları hakkında bilgi almak için sınıf **AdventureWorks**örnek veritabanı:</span><span class="sxs-lookup"><span data-stu-id="debe9-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="debe9-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="debe9-112">See Also</span></span>  
 [<span data-ttu-id="debe9-113">Veritabanı şema bilgileri alınıyor</span><span class="sxs-lookup"><span data-stu-id="debe9-113">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="debe9-114">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="debe9-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)