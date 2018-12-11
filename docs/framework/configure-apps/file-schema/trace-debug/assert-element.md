---
title: '&lt;Assert&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b15e569ff6e42298c0a1de02f77ab7c302c70d86
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154248"
---
# <a name="ltassertgt-element"></a><span data-ttu-id="a9c92-102">&lt;Assert&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="a9c92-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="a9c92-103">Bir ileti kutusu çağırdığınızda görüntülenip görüntülenmeyeceğini belirtir <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> yöntemi de ileti yazmak için dosya adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="a9c92-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="a9c92-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="a9c92-104">\<configuration></span></span>  
<span data-ttu-id="a9c92-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a9c92-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a9c92-106">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="a9c92-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c92-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a9c92-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9c92-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="a9c92-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9c92-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a9c92-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9c92-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="a9c92-110">Attributes</span></span>  
  
|<span data-ttu-id="a9c92-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="a9c92-111">Attribute</span></span>|<span data-ttu-id="a9c92-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a9c92-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="a9c92-113">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="a9c92-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a9c92-114">Görüntülenecek bir ileti kutusunu olup olmadığını belirtir **Debug.Assert** yöntemi değerlendirilen **false**.</span><span class="sxs-lookup"><span data-stu-id="a9c92-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="a9c92-115">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="a9c92-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a9c92-116">Eğer ileti yazmak için dosya adını belirtir **Debug.Assert** değerlendiren **false**.</span><span class="sxs-lookup"><span data-stu-id="a9c92-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="a9c92-117">assertuienabled özniteliği</span><span class="sxs-lookup"><span data-stu-id="a9c92-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="a9c92-118">Değer</span><span class="sxs-lookup"><span data-stu-id="a9c92-118">Value</span></span>|<span data-ttu-id="a9c92-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a9c92-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="a9c92-120">İleti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a9c92-120">Displays the message box.</span></span> <span data-ttu-id="a9c92-121">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="a9c92-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="a9c92-122">İleti kutusu görüntülemez.</span><span class="sxs-lookup"><span data-stu-id="a9c92-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9c92-123">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="a9c92-123">Child Elements</span></span>  
 <span data-ttu-id="a9c92-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="a9c92-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9c92-125">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="a9c92-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a9c92-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="a9c92-126">Element</span></span>|<span data-ttu-id="a9c92-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a9c92-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a9c92-128">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="a9c92-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a9c92-129">Toplamak, depolamak ve iletileri ve bir izleme anahtarı ayarlandığı düzeyi izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="a9c92-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c92-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a9c92-130">Remarks</span></span>  
 <span data-ttu-id="a9c92-131">Her iki öznitelikleri  **\<assert >** öğe isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="a9c92-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="a9c92-132">İleti yazmak için bir dosya belirtmeden ileti kutularını devre dışı bırakabilir veya ileti kutuları etkin bırakılması while iletiler yazmak için bir dosya belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a9c92-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c92-133">Örnek</span><span class="sxs-lookup"><span data-stu-id="a9c92-133">Example</span></span>  
 <span data-ttu-id="a9c92-134">Aşağıdaki örnek, ileti kutularını görüntüleme çağırdığınızda devre dışı bırakmak gösterilmektedir **Debug.Assert** ve iletileri yazma `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="a9c92-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9c92-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a9c92-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="a9c92-136">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="a9c92-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
