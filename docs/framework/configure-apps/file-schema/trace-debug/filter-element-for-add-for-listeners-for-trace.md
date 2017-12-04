---
title: "&lt;Filtre&gt; öğesi için &lt;ekleme&gt; için &lt;dinleyicileri&gt; için &lt;izleme&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3d1cf912e5a07e7514a6b032ff511923ae93c5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="e783c-102">&lt;Filtre&gt; öğesi için &lt;ekleme&gt; için &lt;dinleyicileri&gt; için &lt;izleme&gt;</span><span class="sxs-lookup"><span data-stu-id="e783c-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="e783c-103">Bir dinleyici için bir filtre ekler `Listeners` koleksiyonu için bir izleme.</span><span class="sxs-lookup"><span data-stu-id="e783c-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="e783c-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="e783c-104">\<configuration></span></span>  
<span data-ttu-id="e783c-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e783c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e783c-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="e783c-106">\<trace></span></span>  
<span data-ttu-id="e783c-107">\<dinleyicileri ></span><span class="sxs-lookup"><span data-stu-id="e783c-107">\<listeners></span></span>  
<span data-ttu-id="e783c-108">\<ekleme ></span><span class="sxs-lookup"><span data-stu-id="e783c-108">\<add></span></span>  
<span data-ttu-id="e783c-109">\<Filtre ></span><span class="sxs-lookup"><span data-stu-id="e783c-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e783c-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e783c-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e783c-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e783c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e783c-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e783c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e783c-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e783c-113">Attributes</span></span>  
  
|<span data-ttu-id="e783c-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e783c-114">Attribute</span></span>|<span data-ttu-id="e783c-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e783c-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e783c-116">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="e783c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e783c-117">Devralınan filtre türünü belirtir <xref:System.Diagnostics.TraceFilter> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e783c-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="e783c-118">Tür için karşılık gelen türü ad alanı tam adını kullanabilirsiniz <xref:System.Type.FullName%2A> özelliği veya karşılık gelen derleme bilgileri dahil tam olarak nitelenmiş tür adını kullanabilir <xref:System.Type.AssemblyQualifiedName%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="e783c-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="e783c-119">Tam olarak nitelenmiş tür adları hakkında daha fazla bilgi için bkz: [belirtme tam olarak nitelenmiş tür adları](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e783c-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e783c-120">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="e783c-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e783c-121">Dize belirtilen filtre sınıfı oluşturucuya geçirilen.</span><span class="sxs-lookup"><span data-stu-id="e783c-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e783c-122">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e783c-122">Child Elements</span></span>  
 <span data-ttu-id="e783c-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="e783c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e783c-124">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e783c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e783c-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="e783c-125">Element</span></span>|<span data-ttu-id="e783c-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e783c-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e783c-127">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="e783c-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e783c-128">Toplamak, depolamak ve iletileri ve izleme anahtarı ayarlandığı düzeyi rota izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="e783c-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="e783c-129">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="e783c-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e783c-130">Toplamak, depolamak ve iletileri yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="e783c-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="e783c-131">Dinleyicileri uygun hedef İzleme çıkışı yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="e783c-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="e783c-132">Bir dinleyici ekler `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="e783c-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e783c-133">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e783c-133">Remarks</span></span>  
 <span data-ttu-id="e783c-134">`<filter>` Öğesi içeriyordu, içinde bir `<add>` yalnızca bir dinleyici adını öğesi dinleyicisi türünü belirtir. bir izleme dinleyicisi için tanımlanmış bir [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="e783c-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="e783c-135">Dinleyici tanımlanmış olması durumunda bir [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), filtre bu dinleyici için bu öğe tanımlanmış olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e783c-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="e783c-136">Bu öğe makine yapılandırma dosyası (Machine.config) ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e783c-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e783c-137">Örnek</span><span class="sxs-lookup"><span data-stu-id="e783c-137">Example</span></span>  
 <span data-ttu-id="e783c-138">Aşağıdaki örnekte nasıl kullanılacağını gösterir `<filter>` dinleyiciye filtre eklemek için öğesi `console` içinde `Listeners` koleksiyonu olarak filtre olay düzeyi belirtme izleme için `Error`.</span><span class="sxs-lookup"><span data-stu-id="e783c-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e783c-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e783c-139">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="e783c-140">İzleme ve hata ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="e783c-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)