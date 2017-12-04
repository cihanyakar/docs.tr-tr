---
title: "DynamicResource Biçimlendirme Uzantısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c80d975e756fab449c254b9e1d8d1bc99a25652e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="bb171-102">DynamicResource Biçimlendirme Uzantısı</span><span class="sxs-lookup"><span data-stu-id="bb171-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="bb171-103">İçin herhangi bir değer sağlar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] özellik özniteliği tarafından tanımlanan bir kaynağa başvuru olması için bu değeri erteleniyor.</span><span class="sxs-lookup"><span data-stu-id="bb171-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="bb171-104">Bu kaynak için arama davranışı çalışma zamanı aramasına benzer.</span><span class="sxs-lookup"><span data-stu-id="bb171-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="bb171-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="bb171-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="bb171-106">XAML Özellik Öğesi Kullanımı</span><span class="sxs-lookup"><span data-stu-id="bb171-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bb171-107">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="bb171-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="bb171-108">İstenen kaynak için anahtar.</span><span class="sxs-lookup"><span data-stu-id="bb171-108">The key for the requested resource.</span></span> <span data-ttu-id="bb171-109">Bu anahtar tarafından başlangıçta atandığı [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md) bir kaynak biçimlendirme içinde oluşturulduğu veya olarak sağlanan `key` çağırırken parametre <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> kaynak kodunda oluşturduysanız.</span><span class="sxs-lookup"><span data-stu-id="bb171-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb171-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bb171-110">Remarks</span></span>  
 <span data-ttu-id="bb171-111">A `DynamicResource` ilk derleme sırasında geçici bir ifade oluşturur ve bu nedenle istenen kaynak değeri bir nesne oluşturmak için gerçekten gerekli olana kadar kaynaklara arama erteleneceği.</span><span class="sxs-lookup"><span data-stu-id="bb171-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="bb171-112">Bu büyük olasılıkla sonra olabilir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfa yüklenir.</span><span class="sxs-lookup"><span data-stu-id="bb171-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="bb171-113">Kaynak değeri geçerli sayfanın kapsamdan başlayarak tüm etkin kaynak sözlüklerindeki karşı anahtar arama göre bulundu ve derleme yer tutucu ifade için değiştirdi.</span><span class="sxs-lookup"><span data-stu-id="bb171-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb171-114">Bağımlılık özelliği önceliği açısından bir `DynamicResource` ifadesi dinamik kaynak başvurusu uygulanan burada konuma eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="bb171-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="bb171-115">Daha önce sahip bir özellik için yerel bir değer ayarlarsanız bir `DynamicResource` ifade yerel değerin olarak `DynamicResource` tamamen kaldırılır.</span><span class="sxs-lookup"><span data-stu-id="bb171-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="bb171-116">Ayrıntılar için bkz [bağımlılık özelliği değeri önceliği](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-116">For details, see [Dependency Property Value Precedence](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="bb171-117">Belirli kaynak erişim senaryoları için özellikle uygun `DynamicResource` tersine bir [StaticResource biçimlendirme uzantısı](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span> <span data-ttu-id="bb171-118">Bkz: [XAML kaynakları](../../../../docs/framework/wpf/advanced/xaml-resources.md) göreli değeri ve performans etkileri hakkında tartışma için `DynamicResource` ve `StaticResource`.</span><span class="sxs-lookup"><span data-stu-id="bb171-118">See [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="bb171-119">Belirtilen <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> tarafından belirlenen varolan bir kaynağa karşılık gelmelidir [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md) sayfanızı, uygulama, kullanılabilir denetim temalar ve dış kaynaklara veya sistem kaynaklarının düzeyde ve Kaynak arama, o sırada gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="bb171-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="bb171-120">Statik ve dinamik kaynaklara kaynak arama hakkında daha fazla bilgi için bkz: [XAML kaynakları](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="bb171-121">Kaynak anahtarı içinde tanımlanan herhangi bir dize olabilir [XamlName Dilbilgisi](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-121">A resource key may be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="bb171-122">Kaynak anahtarı da diğer nesne türleri gibi olabilir bir <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="bb171-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="bb171-123">A <xref:System.Type> anahtarıdır denetimleri temalar tarafından nasıl biçimlendirilebilir için temel.</span><span class="sxs-lookup"><span data-stu-id="bb171-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="bb171-124">Daha fazla bilgi için bkz: [denetimine genel bakış yazma](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-124">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]<span data-ttu-id="bb171-125">Kaynak değerleri araması için gibi <xref:System.Windows.FrameworkElement.FindResource%2A>, tarafından kullanılan aynı kaynak arama mantığını izleyin `DynamicResource`.</span><span class="sxs-lookup"><span data-stu-id="bb171-125"> for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="bb171-126">Alternatif bildirime dayanan bir kaynağa başvuran olduğundan bir [StaticResource biçimlendirme uzantısı](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="bb171-127">Öznitelik sözdizimi, bu işaretleme uzantısı ile kullanılan en yaygın sözdizimidir.</span><span class="sxs-lookup"><span data-stu-id="bb171-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="bb171-128">Sonra sağlanan dize belirteci `DynamicResource` kimlik dizesi olarak atandığı <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> temel değer <xref:System.Windows.DynamicResourceExtension> uzantısı sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bb171-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="bb171-129">`DynamicResource`nesne öğesi sözdiziminde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="bb171-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="bb171-130">Bu durumda, değerini belirten <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> özelliği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="bb171-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="bb171-131">`DynamicResource`belirten bir ayrıntılı öznitelik kullanımı da kullanılabilir <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> özelliği bir özellik olarak değer çifti =:</span><span class="sxs-lookup"><span data-stu-id="bb171-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="bb171-132">Ayrıntılı kullanım, genellikle birden fazla ayarlanabilir özelliğe sahip uzantılar için veya bazı özellikler isteğe bağlıysa yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="bb171-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="bb171-133">Çünkü `DynamicResource` yalnızca gerekli olan bir ayarlanabilir özelliği, bu ayrıntılı kullanım tipik sahiptir.</span><span class="sxs-lookup"><span data-stu-id="bb171-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="bb171-134">İçinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] işlemci uygulamasında, bu biçimlendirme uzantısı işlenmesi tarafından tanımlanan <xref:System.Windows.DynamicResourceExtension> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bb171-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="bb171-135">`DynamicResource`bir biçimlendirme uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="bb171-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="bb171-136">Biçimlendirme uzantıları, genellikle öznitelik değerlerinin değişmez değerler veya işleyici isimleri dışına çıkma gereksinimi olduğunda ve bu gereksinim, belirli türler veya özellikler üzerine tür dönüştürücülerini koymaktan daha genel olduğunda uygulanır.</span><span class="sxs-lookup"><span data-stu-id="bb171-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="bb171-137">İçindeki tüm biçimlendirme uzantıları [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kullanmak {ve} kurala göre kendi öznitelik sözdiziminde karakterler bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] işlemci tanıdığı biçimlendirme uzantısı öznitelik işlemelidir.</span><span class="sxs-lookup"><span data-stu-id="bb171-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="bb171-138">Daha fazla bilgi için bkz: [biçimlendirme uzantıları ve WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-138">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb171-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bb171-139">See Also</span></span>  
 [<span data-ttu-id="bb171-140">XAML kaynakları</span><span class="sxs-lookup"><span data-stu-id="bb171-140">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="bb171-141">Kaynaklar ve kod</span><span class="sxs-lookup"><span data-stu-id="bb171-141">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="bb171-142">x: Key yönergesi</span><span class="sxs-lookup"><span data-stu-id="bb171-142">x:Key Directive</span></span>](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [<span data-ttu-id="bb171-143">XAML genel bakış (WPF)</span><span class="sxs-lookup"><span data-stu-id="bb171-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="bb171-144">Biçimlendirme uzantıları ve WPF XAML</span><span class="sxs-lookup"><span data-stu-id="bb171-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="bb171-145">StaticResource biçimlendirme uzantısı</span><span class="sxs-lookup"><span data-stu-id="bb171-145">StaticResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [<span data-ttu-id="bb171-146">Biçimlendirme uzantıları ve WPF XAML</span><span class="sxs-lookup"><span data-stu-id="bb171-146">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)