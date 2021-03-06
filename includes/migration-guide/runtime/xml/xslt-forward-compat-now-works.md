### <a name="xslt-forward-compat-now-works"></a>Nasıl çalıştığını XSLT İleri Uyumluluk

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4'te XSLT 1.0 ileriye dönük aşağıdaki sorunları vardı:<ul><li>Sürümü 2.0 değerine ayarlanmış bir stil sayfasının yüklenmesi başarısız oldu ve ayrıştırıcı tanınmayan bir XSLT 1.0 yapısıyla karşılaştı.</li><li><code>xsl:sort</code> Yapısı başarısız stil sayfası sürümü 1.1 olarak ayarlanmışsa verileri sıralayamadı.</li></ul>.NET Framework 4.5, bu sorunlar düzeltildi ve XSLT 1.0 ileriye dönük uyumluluk modu düzgün çalışır.|
|Öneri|Sort uyulduğundan artık, verileri farklı bazı durumlarda sıralanır ancak çoğu uygulama etkilenmeyen, olmalıdır. Varsa <code>xsl:sort</code> olan 1.1 stil sayfasında kullanıldığında, uygulamaları sıralanmamış siparişin veri bağlı değil, onaylayın. Uygulamaları sıralama davranışını 4.0 güveniyorsanız, kaldırma <code>xsl:sort</code> stil sayfasından.|
|Kapsam|Kenar|
|Sürüm|4,5|
|Tür|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|

