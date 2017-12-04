---
title: "Nasıl yapılır: MEX Olmayan Bağlama Üzerinden Meta Verileri Alma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1f2fe2b7634b57e424773c16023fb657f09f23a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="795fb-102">Nasıl yapılır: MEX Olmayan Bağlama Üzerinden Meta Verileri Alma</span><span class="sxs-lookup"><span data-stu-id="795fb-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="795fb-103">Bu konuda, bir MEX uç noktasından MEX olmayan bağlama üzerinden meta verilerini almak açıklar.</span><span class="sxs-lookup"><span data-stu-id="795fb-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="795fb-104">Bu örnek kodda dayanır [özel güvenli meta veri uç noktasının](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="795fb-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="795fb-105">MEX olmayan bağlama üzerinden meta verilerini almak için</span><span class="sxs-lookup"><span data-stu-id="795fb-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1.  <span data-ttu-id="795fb-106">MEX bitiş noktası tarafından kullanılan bağlama belirler.</span><span class="sxs-lookup"><span data-stu-id="795fb-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="795fb-107">İçin [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Hizmetleri, hizmetin yapılandırma dosyası erişerek MEX bağlama belirleyebilir.</span><span class="sxs-lookup"><span data-stu-id="795fb-107">For [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="795fb-108">Bu durumda, MEX bağlama aşağıdaki hizmet yapılandırmasında tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="795fb-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2.  <span data-ttu-id="795fb-109">İstemci yapılandırma dosyası, aynı özel bağlama yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="795fb-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="795fb-110">Burada istemci de tanımlayan bir `clientCredentials` meta verileri MEX uç noktasından isterken hizmete kimlik doğrulaması için kullanılacak bir sertifika sağlamak için davranış.</span><span class="sxs-lookup"><span data-stu-id="795fb-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="795fb-111">Özel bağlama üzerinden meta veri istemek için svcutil.exe kullanırken Svcutil.exe (Svcutil.exe.config) MEX uç nokta yapılandırması yapılandırma dosyasına eklemelisiniz ve uç nokta yapılandırması adresinin URI şeması adıyla aynı olmalıdır Aşağıdaki kodda gösterildiği gibi MEX endpoint.</span><span class="sxs-lookup"><span data-stu-id="795fb-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="795fb-112">Oluşturma bir `MetadataExchangeClient` ve arama `GetMetadata`.</span><span class="sxs-lookup"><span data-stu-id="795fb-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="795fb-113">Bunu yapmanın iki yolu vardır: Yapılandırması'nda özel bağlama belirtin veya özel bağlama aşağıdaki örnekte gösterildiği gibi kodda belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="795fb-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4.  <span data-ttu-id="795fb-114">Oluşturma bir `WsdlImporter` ve arama `ImportAllEndpoints`aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="795fb-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  <span data-ttu-id="795fb-115">Bu noktada, hizmet uç noktaları koleksiyonu vardır.</span><span class="sxs-lookup"><span data-stu-id="795fb-115">At this point, you have a collection of service endpoints.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="795fb-116">bkz: meta verileri, içeri aktarma [nasıl yapılır: hizmet uç noktaları içine meta verileri içeri aktarma](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="795fb-116"> importing metadata, see [How to: Import Metadata into Service Endpoints](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795fb-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="795fb-117">See Also</span></span>  
 [<span data-ttu-id="795fb-118">Meta veriler</span><span class="sxs-lookup"><span data-stu-id="795fb-118">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)