---
title: Kodlanmış SOAP serileştirmesini denetleyen öznitelikler
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 7b5a48003ff9bfb398c05c8d70a9076d49ad83d6
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003249"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Kodlanmış SOAP serileştirmesini denetleyen öznitelikler

Adlı World Wide Web Consortium (W3C) belgenin [Basit Nesne Erişim Protokolü (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) nasıl SOAP parametreleri kodlanmış açıklayan isteğe bağlı bir bölüm (Bölüm 5) içerir. Belirtiminin 5 bölümüne uymak için özel öznitelikler bulundu kümesi kullanmak <xref:System.Xml.Serialization> ad alanı. Özniteliklerle sınıfları ve sınıf üyeleri için uygun olarak uygulayın ve ardından <xref:System.Xml.Serialization.XmlSerializer> sınıf veya sınıfların örneklerini serileştirmek için.

Aşağıdaki tablo nerede bunlar uygulanabilir, öznitelikleri ve neler yaptığını gösterir. Denetim XML serileştirme için bu öznitelikleri kullanmayla ilgili daha fazla bilgi için bkz. [nasıl yapılır: bir SOAP olarak bir nesneyi serileştirip-kodlanmış XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) ve [nasıl yapılır: Kodlanmış SOAP XML serileştirme geçersiz kılma](how-to-override-encoded-soap-xml-serialization.md).

Öznitelikler hakkında daha fazla bilgi için bkz. [öznitelikleri](../../../docs/standard/attributes/index.md).

|Öznitelik|Uygulandığı öğe:|Belirler|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|Ortak alan, özelliği, parameTRe veya dönüş değeri.|Sınıf üyesi bir XML özniteliği olarak seri hale.|
|<xref:System.Xml.Serialization.SoapElementAttribute>|Ortak alan, özelliği, parameTRe veya dönüş değeri.|Sınıf bir XML öğesi olarak seri hale.|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|Bir numaralandırma tanımlayıcı ortak alan.|Numaralandırma üyesi öğe adı.|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|Ortak özellikler ve alanları.|Kapsayan sınıfı serileştirilmiş olduğunda özellik veya alan yoksayılacak.|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|Genel türetilmiş sınıf bildirimleri ve Web Hizmetleri Açıklama Dili (WSDL) belgeleri için ortak yöntemleri.|Türü (serileştirilmiş olduğunda tanınması için) şemalar oluşturulurken dahil edilecek.|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|Ortak sınıf bildirimleri.|Sınıf bir XML türü olarak seri hale.|

## <a name="see-also"></a>Ayrıca bkz.

- [XML ve SOAP Serileştirme](xml-and-soap-serialization.md)  
- [Nasıl yapılır: SOAP Kodlu XML Akışı Olarak Nesneyi Serileştirme](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
- [Nasıl yapılır: Kodlanmış SOAP XML Serileştirmesini Geçersiz Kılma](how-to-override-encoded-soap-xml-serialization.md)  
- [Öznitelikler](../../../docs/standard/attributes/index.md)  
- <xref:System.Xml.Serialization.XmlSerializer>  
- [Nasıl yapılır: Nesne Serileştirme](how-to-serialize-an-object.md)  
- [Nasıl yapılır: Nesneyi Seri Durumdan Çıkarma](how-to-deserialize-an-object.md)
