---
title: 'Nasıl yapılır: müdahale veri hizmeti iletileri (WCF Veri Hizmetleri)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 9d79a9ca27470512105b3a04d681906aa365d7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355766"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Nasıl yapılır: müdahale veri hizmeti iletileri (WCF Veri Hizmetleri)
İle [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], böylece bir işlem Özel mantık ekleyebilirsiniz istek iletilerini ele geçirebilir. Bir ileti müdahale için veri hizmeti özel öznitelikli yöntemleri kullanın. Daha fazla bilgi için bkz: [dinleyiciler](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
 Bu konudaki örnek Northwind örnek veri hizmeti kullanır. Bu hizmeti tamamladığınızda oluşturulan [WCF Veri Hizmetleri quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Siparişleri varlık kümesi için sorgu dinleyiciyi tanımlamak için  
  
1.  Northwind veri hizmeti projesi Northwind.svc dosyasını açın.  
  
2.  İçin kod sayfasından `Northwind` sınıfında, aşağıdaki ekleyin `using` deyimi (`Imports` Visual Basic'te).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  İçinde `Northwind` sınıfı, adlı bir hizmet işlemi yöntemi tanımlayın `OnQueryOrders` gibi:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Ürünler varlık kümesi için bir değişiklik dinleyiciyi tanımlamak için  
  
1.  Northwind veri hizmeti projesi Northwind.svc dosyasını açın.  
  
2.  İçinde `Northwind` sınıfı, adlı bir hizmet işlemi yöntemi tanımlayın `OnChangeProducts` gibi:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Örnek  
 Bu örnek için bir sorgu dinleyiciyi yöntemi tanımlar `Orders` lambda ifadesi döndürür varlık kümesi. Bu ifade istenen filtreler bir temsilci içerir `Orders` üzerinde ilgili temel `Customers` belirli bir kişi adına sahip. Ad sırayla istekte bulunan kullanıcı göre belirlenir. Bu örnek veri hizmeti WCF kullanan bir ASP.NET Web uygulaması içinde barındırılır ve bu kimlik doğrulamasının etkin olduğunu varsayar. <xref:System.Web.HttpContext> Sınıfı, geçerli istek ilkesini almak için kullanılır.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Örnek  
 Bu örnek için bir değişiklik dinleyiciyi yöntemi tanımlar `Products` varlık kümesi. Bu yöntem için hizmetine giriş doğrular bir <xref:System.Data.Services.UpdateOperations.Add> veya <xref:System.Data.Services.UpdateOperations.Change> işlemi ve devam etmeyen ürüne yapılan bir değişiklik olursa bir özel durum oluşturur. Ayrıca, desteklenmeyen bir işlem olarak ürünleri silinmesini engeller.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Hizmet İşlemi Tanımlama](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [WCF Veri Hizmetlerini Tanımlama](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
