### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a>Sonsuz özyineleme IWorkflowInstanceManagement.TransactedCancel ve IWorkflowInstanceManagement.TransactedTerminate önleme

|   |   |
|---|---|
|Ayrıntılar|Kullanırken, bazı koşullarda <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> veya <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> iptal etmek veya bir iş akışının sonlandırmak için API'ler hizmet örneği, iş akışı örneği bir yığın taşması nedeniyle sonsuz özyineleme karşılaşabilirsiniz zaman <code>Workflow</code> çalışma zamanı çalışır kalıcı hale getirmek istek işlenirken bir parçası olarak hizmet örneği. İş akışı örneği burada tamamlamak bazı diğer bekleyen WCF isteği için başka bir hizmet için bekleyen bir durumda ise sorun oluşur. <code>TransactedCancel</code> Ve <code>TransactedTerminate</code> işlemleri için iş akışı hizmet örneği sıraya alınan iş öğeleri oluşturun. Bu iş öğeleri işlenmesini bir parçası olarak yürütülmedi <code>TransactedCancel/TransactedTerminate</code> isteği. İş akışı hizmeti örneği tamamlamak diğer bekleyen WCF isteği beklerken meşgul olduğundan öğesi oluşturulan iş sıraya alınmış olarak kalır. <code>TransactedCancel/TransactedTerminate</code> İşlemi tamamlandıktan ve denetim istemciye döndürülür. İşlem zaman ilişkili <code>TransactedCancel/TransactedTerminate</code> yürütme girişimlerini işlemi, iş akışı hizmeti örnek durum kalıcı olması gerekir. Ancak olmadığı için bir bekleyen <code>WCF</code> istek örneği için iş akışı çalışma zamanı iş akışı hizmeti örneği kalıcı yapılamıyor ve sonsuz özyineleme döngü yığın taşması yol açar. Çünkü <code>TransactedCancel</code> ve <code>TransactedTerminate</code> yalnızca bellekte bir iş öğesi oluşturma, bir işlem var olduğunu olgu herhangi bir etkisi yoktur. Geri alma işlemi, iş öğesi atmak değil. .NET Framework 4.7.2, başlatma, bu sorunu gidermek için gösterdiğimizi bir <code>AppSetting</code> için eklenebilir <code>web.config/app.config</code> işlemleri için yoksaymak için söyler iş akışı hizmeti <code>TransactedCancel</code> ve <code>TransactedTerminate</code>. Bu kalıcı hale getirmek iş akışı örneği için beklemeden yürütmesi işlem sağlar. Bu özellik için AppSetting adlı <code>microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate</code>. Değerini <code>true</code> işlem, bu nedenle yığın taşması önleme dikkate alınması gerektiğini gösterir. Bu ayarı varsayılan değeri <code>false</code>, var olan iş akışı hizmeti örnekleri etkilenmez.|
|Öneri|AppFabric ya da başka bir kullanıyorsanız <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> istemci ve bu iş akışı hizmeti örneği bir yığın taşması ile iptal etme veya bir iş akışı örneği sonlandırılacak çalışırken karşılaşmadan, aşağıdaki ekleyebilirsiniz <code>&lt;appSettings&gt;</code> web.config/ Bölümü İş akışı hizmeti için app.config dosyası:<pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre>Sorun karşılaşılıyorsa değil, bunu yapmak gerekmez.|
|Kapsam|Kenar|
|Sürüm|4.7.2|
|Tür|Yeniden hedefleme|
