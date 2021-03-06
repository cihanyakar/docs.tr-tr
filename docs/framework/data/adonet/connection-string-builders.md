---
title: Bağlantı dizesi oluşturucular
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: 1c65b0c2c9ae19aa008ecd8fb453d8e41b7c4167
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43737509"
---
# <a name="connection-string-builders"></a>Bağlantı dizesi oluşturucular
Önceki sürümlerinde [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], derleme zamanı yanlış bir anahtar sözcüğü çalışma zamanında oluşturulan birleştirilmiş dizeyi değerleri oluşmadı ile bağlantı dizeleri denetimi bir <xref:System.ArgumentException>. Her biri [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcıları geçerli bağlantı dizelerini zor yapıldığında el ile oluşturmak yapılan bağlantı dizesi anahtar için farklı bir sözdizimi desteklenir. Bu sorunu gidermek için [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 sunulan her yeni bağlantı dizesi oluşturucular [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcısı. Her veri sağlayıcısının devralan bir türü kesin belirlenmiş bağlantı dizesi Oluşturucusu sınıfı içeren <xref:System.Data.Common.DbConnectionStringBuilder>. Aşağıdaki tabloda [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcıları ve bunların ilişkili bağlantı dizesi Oluşturucusu sınıfları.  
  
|Sağlayıcı|ConnectionStringBuilder sınıfı|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Bağlantı dizesi ekleme saldırıları  
 Dinamik dize birleştirme kullanıcı girişini temel alarak bağlantı dizeleri oluşturmak için kullanılan bir bağlantı dizesi ekleme saldırısına oluşabilir. Dize doğrulanmış ve kötü amaçlı bir metin veya kaçış karakteri değil ise, bir saldırganın hassas verileri veya sunucudaki diğer kaynakları içeriklerine erişebilir. Örneğin, bir saldırganın bir noktalı virgül sağlayarak ve ek bir değer ekleme saldırısı. Bağlantı dizesi "son bir WINS" algoritması kullanılarak ayrıştırılır ve tehlikeli giriş için meşru bir değer ile değiştirilir.  
  
 Bağlantı dizesi Oluşturucusu sınıfları kararın ortadan kaldırabilir ve söz dizimi hataları ve güvenlik açıklarına karşı korumak için tasarlanmıştır. Bunlar, yöntemleri ve her bir veri sağlayıcısı tarafından izin verilen bilinen anahtar/değer çiftleri için karşılık gelen özellikleri sağlar. Her sınıf, eş anlamlılar sabit bir koleksiyonunu tutar ve iyi bilinen bir karşılık gelen anahtar adı bir eş anlamlı çevirebilir. Geçerli anahtar/değer çiftleri için önleme denetimleri yapıldıktan ve geçersiz bir çifti bir özel durum oluşturur. Ayrıca, eklenen değerleri güvenli bir şekilde ele alınır.  
  
 Aşağıdaki örnek, gösterir nasıl <xref:System.Data.SqlClient.SqlConnectionStringBuilder> eklenmiş bir ek değer işleme `Initial Catalog` ayarı.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 Çıkış gösteren <xref:System.Data.SqlClient.SqlConnectionStringBuilder> Bu bağlantı dizesine yeni bir anahtar/değer çifti olarak ekleme yerine çift tırnak işareti bulunan ek değer kaçış tarafından doğru şekilde yapılır.  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Yapılandırma dosyalarını oluşturma bağlantı dizeleri  
 Belirli bir bağlantı dizesi öğelerinin önceden biliniyorsa, bunlar bir yapılandırma dosyasında depolanabilir ve tam bağlantı dizesi oluşturmak için çalışma zamanında alınan. Örneğin, önceden bilinen, ancak sunucunun adını değil veritabanının adı olabilir. Veya, diğer değerler bağlantı dizesini ekleme mümkün olmaksızın çalışma zamanında bir adı ve parola sağlamak için bir kullanıcı isteyebilirsiniz.  
  
 Bir bağlantı dizesi oluşturucusu için aşırı yüklü oluşturucular alır bir <xref:System.String> bağımsız değişken olarak, hangi kullanıcı girdisinden tamamlanabilir bir kısmi bağlantı dizesi sağlamanız olanak sağlar. Kısmi bağlantı dizesi, bir yapılandırma dosyasında depolanan ve çalışma zamanında alınır.  
  
> [!NOTE]
>  <xref:System.Configuration> Ad alanı kullanan yapılandırma dosyalarını programlı erişim sağlayan <xref:System.Web.Configuration.WebConfigurationManager> Web uygulamaları ve <xref:System.Configuration.ConfigurationManager> Windows uygulamaları için. Bağlantı dizeleri ve yapılandırma dosyaları ile çalışma hakkında daha fazla bilgi için bkz. [bağlantı dizeleri ve yapılandırma dosyalarını](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Örnek  
 Bu örnek bir yapılandırma dosyasından bir kısmi bağlantı dizesi alma ve ayarlayarak Tamamlanıyor gösterir <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, ve <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> özelliklerini <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Yapılandırma dosyasında şu şekilde tanımlanır.  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  Bir başvuru ayarlamanız gerekir `System.Configuration.dll` çalıştırmak kodu projenizdeki.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı Dizeleri](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Gizlilik ve Veri Güvenliği](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
