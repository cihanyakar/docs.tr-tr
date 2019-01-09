---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: a59f4f4ca5024b492a1e99b50776870032077818
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149619"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="012ab-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="012ab-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="012ab-103">SOAP ileti aktarım en iyi duruma getirme mekanizması (temel MTOM) iletiler için kullanılan kodlama ve ileti sürüm oluşturmayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="012ab-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="012ab-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="012ab-104">\<system.serviceModel></span></span>  
<span data-ttu-id="012ab-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="012ab-105">\<bindings></span></span>  
<span data-ttu-id="012ab-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="012ab-106">\<customBinding></span></span>  
<span data-ttu-id="012ab-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="012ab-107">\<binding></span></span>  
<span data-ttu-id="012ab-108">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="012ab-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="012ab-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="012ab-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="012ab-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="012ab-110">Attributes and Elements</span></span>  
 <span data-ttu-id="012ab-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="012ab-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="012ab-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="012ab-112">Attributes</span></span>  
  
|<span data-ttu-id="012ab-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="012ab-113">Attribute</span></span>|<span data-ttu-id="012ab-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="012ab-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="012ab-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="012ab-115">maxBufferSize</span></span>|<span data-ttu-id="012ab-116">Kullanılabilir arabelleğinin en büyük boyutunu belirten bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="012ab-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="012ab-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="012ab-117">maxReadPoolSize</span></span>|<span data-ttu-id="012ab-118">İleti sayısını belirten bir tamsayı yeni okuyucu ayırmadan aynı anda okuyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="012ab-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="012ab-119">Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="012ab-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="012ab-120">64 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="012ab-120">The default is 64.</span></span>|  
|<span data-ttu-id="012ab-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="012ab-121">maxWritePoolSize</span></span>|<span data-ttu-id="012ab-122">İleti sayısını belirten bir tamsayı, yeni yazıcı ayırmadan aynı anda gönderilebilecek.</span><span class="sxs-lookup"><span data-stu-id="012ab-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="012ab-123">Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="012ab-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="012ab-124">Varsayılan değer 16'dır.</span><span class="sxs-lookup"><span data-stu-id="012ab-124">The default is 16.</span></span>|  
|<span data-ttu-id="012ab-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="012ab-125">messageVersion</span></span>|<span data-ttu-id="012ab-126">Bağlama kullanılarak gönderilen iletilerin SOAP sürümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="012ab-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="012ab-127">Geçerli değerler:</span><span class="sxs-lookup"><span data-stu-id="012ab-127">Valid values are</span></span><br /><br /> <span data-ttu-id="012ab-128">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="012ab-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="012ab-129">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="012ab-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="012ab-130">Soap12Addressing10 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="012ab-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="012ab-131">Bu öznitelik türünde <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="012ab-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="012ab-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="012ab-132">writeEncoding</span></span>|<span data-ttu-id="012ab-133">Bağlamadaki yayma iletileri için kullanılacak kodlama karakter kümesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="012ab-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="012ab-134">Geçerli değerler:</span><span class="sxs-lookup"><span data-stu-id="012ab-134">Valid values are</span></span><br /><br /> <span data-ttu-id="012ab-135">-UnicodeFffeTextEncoding: Unicode kodlama BigEndian</span><span class="sxs-lookup"><span data-stu-id="012ab-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="012ab-136">-Utf16TextEncoding: Unicode kodlama</span><span class="sxs-lookup"><span data-stu-id="012ab-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="012ab-137">-Utf8TextEncoding: 8-bit kodlama</span><span class="sxs-lookup"><span data-stu-id="012ab-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="012ab-138">Utf8TextEncoding varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="012ab-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="012ab-139">Bu öznitelik türünde <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="012ab-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="012ab-140">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="012ab-140">Child Elements</span></span>  
  
|<span data-ttu-id="012ab-141">Öğe</span><span class="sxs-lookup"><span data-stu-id="012ab-141">Element</span></span>|<span data-ttu-id="012ab-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="012ab-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="012ab-143">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="012ab-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="012ab-144">Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="012ab-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="012ab-145">Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="012ab-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="012ab-146">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="012ab-146">Parent Elements</span></span>  
  
|<span data-ttu-id="012ab-147">Öğe</span><span class="sxs-lookup"><span data-stu-id="012ab-147">Element</span></span>|<span data-ttu-id="012ab-148">Açıklama</span><span class="sxs-lookup"><span data-stu-id="012ab-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="012ab-149">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="012ab-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="012ab-150">Özel bağlama tüm bağlama yeteneklerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="012ab-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="012ab-151">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="012ab-151">Remarks</span></span>  
 <span data-ttu-id="012ab-152">Kodlama bir ileti bir dizi bayta dönüştürme işlemidir.</span><span class="sxs-lookup"><span data-stu-id="012ab-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="012ab-153">Kod çözme ters işlemidir.</span><span class="sxs-lookup"><span data-stu-id="012ab-153">Decoding is the reverse process.</span></span> <span data-ttu-id="012ab-154">Windows Communication Foundation (WCF) için SOAP iletilerini kodlama üç türlerini içerir: Metin, ikili ve ileti aktarım en iyi duruma getirme mekanizması (MTOM).</span><span class="sxs-lookup"><span data-stu-id="012ab-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="012ab-155">`MtomMessageEncoding` Öğesi, karakter kodlamasını ve ileti sürüm oluşturmayı ve bir ileti aktarım en iyi duruma getirme mekanizması (MTOM) kodlaması kullanarak iletiler için kullanılan diğer ayarları belirtir.</span><span class="sxs-lookup"><span data-stu-id="012ab-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="012ab-156">MTOM WCF iletilerinde ikili veri aktarımı için verimli bir teknolojidir.</span><span class="sxs-lookup"><span data-stu-id="012ab-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="012ab-157">MTOM Kodlayıcısı verimliliği ve birlikte çalışabilirlik arasında bir denge oluşturmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="012ab-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="012ab-158">MTOM kodlama çoğu XML metin biçiminde aktarır, ancak büyük ikili veri blokları olarak ileterek iyileştirir-base64 kodlu biçimlerini dönüştürme olmadan olduğu.</span><span class="sxs-lookup"><span data-stu-id="012ab-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="012ab-159">Örnek</span><span class="sxs-lookup"><span data-stu-id="012ab-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="012ab-160">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="012ab-160">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
 [<span data-ttu-id="012ab-161">İleti Kodlama</span><span class="sxs-lookup"><span data-stu-id="012ab-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="012ab-162">İleti Kodlayıcı Seçme</span><span class="sxs-lookup"><span data-stu-id="012ab-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="012ab-163">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="012ab-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="012ab-164">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="012ab-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="012ab-165">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="012ab-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="012ab-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="012ab-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
