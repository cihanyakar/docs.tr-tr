---
title: "Nasıl yapılır: Web Denetimlerindeki Sayısal Kullanıcı Girişlerini Sayıya Dönüştürme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a><span data-ttu-id="bae56-102">Nasıl yapılır: Web Denetimlerindeki Sayısal Kullanıcı Girişlerini Sayıya Dönüştürme</span><span class="sxs-lookup"><span data-stu-id="bae56-102">How to: Convert Numeric User Input in Web Controls to Numbers</span></span>
<span data-ttu-id="bae56-103">Bir Web sayfası dünyanın her yerden görüntülenebilir olduğundan, kullanıcılar sayısal verisine girebilirsiniz bir <xref:System.Web.UI.WebControls.TextBox> biçimlerinin neredeyse sınırsız sayıda denetiminde.</span><span class="sxs-lookup"><span data-stu-id="bae56-103">Because a Web page can be displayed anywhere in the world, users can input numeric data into a <xref:System.Web.UI.WebControls.TextBox> control in an almost unlimited number of formats.</span></span> <span data-ttu-id="bae56-104">Sonuç olarak, yerel ayar ve Web sayfasının kullanıcı kültürü belirlemek çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="bae56-104">As a result, it is very important to determine the locale and culture of the Web page's user.</span></span> <span data-ttu-id="bae56-105">Kullanıcı girişini ayrıştırmasına, daha sonra kullanıcının yerel ayarı ve kültür tarafından tanımlanan biçimlendirme kuralları uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bae56-105">When you parse user input, you can then apply the formatting conventions defined by the user's locale and culture.</span></span>  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a><span data-ttu-id="bae56-106">Sayısal girişi bir Web TextBox denetimi bir sayıya dönüştürme</span><span class="sxs-lookup"><span data-stu-id="bae56-106">To convert numeric input from a Web TextBox control to a number</span></span>  
  
1.  <span data-ttu-id="bae56-107">Dize dizisi tarafından döndürülen olup olmadığını belirlemek <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> özelliği doldurulur.</span><span class="sxs-lookup"><span data-stu-id="bae56-107">Determine whether the string array returned by the <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> property is populated.</span></span> <span data-ttu-id="bae56-108">Değilse, 6. adıma geçin.</span><span class="sxs-lookup"><span data-stu-id="bae56-108">If it is not, continue to step 6.</span></span>  
  
2.  <span data-ttu-id="bae56-109">Dize dizisi olarak döndürülürse <xref:System.Web.HttpRequest.UserLanguages%2A> özelliği doldurulur, ilk alt öğesi alın.</span><span class="sxs-lookup"><span data-stu-id="bae56-109">If the string array returned by the <xref:System.Web.HttpRequest.UserLanguages%2A> property is populated, retrieve its first element.</span></span> <span data-ttu-id="bae56-110">İlk öğesi, kullanıcının varsayılan veya tercih edilen dil ve bölge gösterir.</span><span class="sxs-lookup"><span data-stu-id="bae56-110">The first element indicates the user's default or preferred language and region.</span></span>  
  
3.  <span data-ttu-id="bae56-111">Örneği bir <xref:System.Globalization.CultureInfo> kullanıcıyı temsil eden nesne tercih edilen kültür çağırarak <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="bae56-111">Instantiate a <xref:System.Globalization.CultureInfo> object that represents the user's preferred culture by calling the <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> constructor.</span></span>  
  
4.  <span data-ttu-id="bae56-112">Ya da çağrısı `TryParse` veya `Parse` kullanıcı dönüştürmek istediğiniz sayısal türü yöntemi için girdisini.</span><span class="sxs-lookup"><span data-stu-id="bae56-112">Call either the `TryParse` or the `Parse` method of the numeric type that you want to convert the user's input to.</span></span> <span data-ttu-id="bae56-113">Bir aşırı yüklemesini kullanın `TryParse` veya `Parse` yöntemi ile bir `provider` parametresi ve aşağıdakilerden birini geçirin:</span><span class="sxs-lookup"><span data-stu-id="bae56-113">Use an overload of the `TryParse` or the `Parse` method with a `provider` parameter, and pass it either of the following:</span></span>  
  
    -   <span data-ttu-id="bae56-114"><xref:System.Globalization.CultureInfo> 3. adımda oluşturulan nesne.</span><span class="sxs-lookup"><span data-stu-id="bae56-114">The <xref:System.Globalization.CultureInfo> object created in step 3.</span></span>  
  
    -   <span data-ttu-id="bae56-115"><xref:System.Globalization.NumberFormatInfo> Tarafından döndürülen nesne <xref:System.Globalization.CultureInfo.NumberFormat%2A> özelliği <xref:System.Globalization.CultureInfo> 3. adımda oluşturulan nesne.</span><span class="sxs-lookup"><span data-stu-id="bae56-115">The <xref:System.Globalization.NumberFormatInfo> object that is returned by the <xref:System.Globalization.CultureInfo.NumberFormat%2A> property of the <xref:System.Globalization.CultureInfo> object created in step 3.</span></span>  
  
5.  <span data-ttu-id="bae56-116">Dönüştürme başarısız olursa, tarafından döndürülen 2 ile 4 dize dizisi kalan her öğe için adımları yineleyin <xref:System.Web.HttpRequest.UserLanguages%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="bae56-116">If the conversion fails, repeat steps 2 through 4 for each remaining element in the string array returned by the <xref:System.Web.HttpRequest.UserLanguages%2A> property.</span></span>  
  
6.  <span data-ttu-id="bae56-117">Dönüştürme yine başarısız olursa veya dize dizisi olarak döndürülürse <xref:System.Web.HttpRequest.UserLanguages%2A> özelliği boşsa, dize sabit kültür tarafından döndürülen kullanarak XML'in <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="bae56-117">If the conversion still fails or if the string array returned by the <xref:System.Web.HttpRequest.UserLanguages%2A> property is empty, parse the string by using the invariant culture, which is returned by the <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae56-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="bae56-118">Example</span></span>  
 <span data-ttu-id="bae56-119">Aşağıdaki örnek bir sayısal değer girmesini ister Web formu tam arka plan kodu sayfasıdır bir <xref:System.Web.UI.WebControls.TextBox> denetlemek ve bir sayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="bae56-119">The following example is the complete code-behind page for a Web form that asks the user to enter a numeric value in a <xref:System.Web.UI.WebControls.TextBox> control and converts it to a number.</span></span> <span data-ttu-id="bae56-120">Bu sayıyı sonra iki katına ve özgün giriş olarak aynı biçimlendirme kuralları kullanılarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="bae56-120">That number is then doubled and displayed by using the same formatting rules as the original input.</span></span>  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 <span data-ttu-id="bae56-121"><xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Özelliği bulunan kültür adlarından doldurulur `Accept-Language` bir HTTP isteğine dahil üstbilgileri.</span><span class="sxs-lookup"><span data-stu-id="bae56-121">The <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> property is populated from the culture names that are contained in `Accept-Language` headers included in an HTTP request.</span></span> <span data-ttu-id="bae56-122">Ancak, tüm tarayıcılar dahil `Accept-Language` üstbilgileri kendi isteklerini ve kullanıcılar da bastırmak üstbilgileri tamamen.</span><span class="sxs-lookup"><span data-stu-id="bae56-122">However, not all browsers include `Accept-Language` headers in their requests, and users can also suppress the headers completely.</span></span> <span data-ttu-id="bae56-123">Bu, kullanıcı girişi ayrıştırırken bir geri dönüş kültür sağlamak önemli kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="bae56-123">This makes it important to have a fallback culture when parsing user input.</span></span> <span data-ttu-id="bae56-124">Genellikle, geri dönüş tarafından döndürülen sabit kültür kültürdür <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bae56-124">Typically, the fallback culture is the invariant culture returned by <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bae56-125">Kullanıcılar ayrıca Internet Explorer kültür adlarıyla kültür adları geçerli olmayabilir olasılığı oluşturan bir metin kutusunda giriş sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bae56-125">Users can also provide Internet Explorer with culture names that they input in a text box, which creates the possibility that the culture names may not be valid.</span></span> <span data-ttu-id="bae56-126">Bu örneği oluşturulurken özel durum işleme kullanmak önemli kılar bir <xref:System.Globalization.CultureInfo> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="bae56-126">This makes it important to use exception handling when instantiating a <xref:System.Globalization.CultureInfo> object.</span></span>  
  
 <span data-ttu-id="bae56-127">Internet Explorer tarafından gönderilen HTTP isteğinden alınırken <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> dizi kullanıcı tercih sırasına göre doldurulur.</span><span class="sxs-lookup"><span data-stu-id="bae56-127">When retrieved from an HTTP request submitted by Internet Explorer, the <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> array is populated in order of user preference.</span></span> <span data-ttu-id="bae56-128">Dizinin ilk öğesi, kullanıcının birincil kültür/bölge adını içerir.</span><span class="sxs-lookup"><span data-stu-id="bae56-128">The first element in the array contains the name of the user's primary culture/region.</span></span> <span data-ttu-id="bae56-129">Dizi ek öğeler içeriyorsa, Internet Explorer bunları rasgele kültür adı noktalı virgülle ayrılmış bir kalite belirticisi atar.</span><span class="sxs-lookup"><span data-stu-id="bae56-129">If the array contains any additional items, Internet Explorer arbitrarily assigns them a quality specifier, which is delimited from the culture name by a semicolon.</span></span> <span data-ttu-id="bae56-130">Örneğin, fr-FR kültür için bir giriş form alabilir `fr-FR;q=0.7`.</span><span class="sxs-lookup"><span data-stu-id="bae56-130">For example, an entry for the fr-FR culture might take the form `fr-FR;q=0.7`.</span></span>  
  
 <span data-ttu-id="bae56-131">Örnek aramalar <xref:System.Globalization.CultureInfo.%23ctor%2A> Oluşturucu kendi `useUserOverride` parametre kümesine `false` yeni <xref:System.Globalization.CultureInfo> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="bae56-131">The example calls the <xref:System.Globalization.CultureInfo.%23ctor%2A> constructor with its `useUserOverride` parameter set to `false` to create a new <xref:System.Globalization.CultureInfo> object.</span></span> <span data-ttu-id="bae56-132">Kültür adı sunucusundaki varsayılan kültür adı ise bu, sağlar yeni <xref:System.Globalization.CultureInfo> sınıfı oluşturucusu tarafından oluşturulan nesne bir kültürün varsayılan ayarları içerir ve sunucunun kullanarak geçersiz kılınmış herhangi bir ayarı yansıtmaz  **Bölge ve Dil Seçenekleri** uygulama.</span><span class="sxs-lookup"><span data-stu-id="bae56-132">This ensures that, if the culture name is the default culture name on the server, the new <xref:System.Globalization.CultureInfo> object created by the class constructor contains a culture's default settings and does not reflect any settings overridden by using the server's **Regional and Language Options** application.</span></span> <span data-ttu-id="bae56-133">Sunucudaki tüm geçersiz kılınmış ayarları değerleri, kullanıcının sistemde yok veya kullanıcının giriş yansıtılması düşüktür.</span><span class="sxs-lookup"><span data-stu-id="bae56-133">The values from any overridden settings on the server are unlikely to exist on the user's system or to be reflected in the user's input.</span></span>  
  
 <span data-ttu-id="bae56-134">Kodunuzu ya da çağırabilirsiniz `Parse` veya `TryParse` kullanıcı girişi sayısal türü yöntemi dönüştürülür.</span><span class="sxs-lookup"><span data-stu-id="bae56-134">Your code can call either the `Parse` or the `TryParse` method of the numeric type that the user's input will be converted to.</span></span> <span data-ttu-id="bae56-135">Parse yöntemi yinelenen çağrıları için tek bir ayrıştırma işlemi gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="bae56-135">Repeated calls to a parse method may be required for a single parsing operation.</span></span> <span data-ttu-id="bae56-136">Sonuç olarak, `TryParse` yöntemi olduğundan daha iyi döndürdüğü `false` ayrıştırma işlemi başarısız olursa.</span><span class="sxs-lookup"><span data-stu-id="bae56-136">As a result, the `TryParse` method is better, because it returns `false` if a parse operation fails.</span></span> <span data-ttu-id="bae56-137">Buna karşılık, tarafından oluşturulan yinelenen özel durumları işleme `Parse` yöntemi, bir Web uygulaması çok pahalı bir teklifinde olabilir.</span><span class="sxs-lookup"><span data-stu-id="bae56-137">In contrast, handling the repeated exceptions that may be thrown by the `Parse` method can be a very expensive proposition in a Web application.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bae56-138">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="bae56-138">Compiling the Code</span></span>  
 <span data-ttu-id="bae56-139">Kodu derlemek için bu dosyaya kopyalayın bir [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] olan tüm var olan kodu değiştirir için arka plan kod sayfası.</span><span class="sxs-lookup"><span data-stu-id="bae56-139">To compile the code, copy it into an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] code-behind page so that it replaces all the existing code.</span></span> <span data-ttu-id="bae56-140">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web sayfası aşağıdaki denetimleri içermelidir:</span><span class="sxs-lookup"><span data-stu-id="bae56-140">The [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web page should contain the following controls:</span></span>  
  
-   <span data-ttu-id="bae56-141">A <xref:System.Web.UI.WebControls.Label> kodunda başvurulmuyor denetim.</span><span class="sxs-lookup"><span data-stu-id="bae56-141">A <xref:System.Web.UI.WebControls.Label> control, which is not referenced in code.</span></span> <span data-ttu-id="bae56-142">Ayarlama, <xref:System.Web.UI.WebControls.TextBox.Text%2A> özelliğine "bir sayı girin:".</span><span class="sxs-lookup"><span data-stu-id="bae56-142">Set its <xref:System.Web.UI.WebControls.TextBox.Text%2A> property to "Enter a Number:".</span></span>  
  
-   <span data-ttu-id="bae56-143">A <xref:System.Web.UI.WebControls.TextBox> adlı Denetim `NumericString`.</span><span class="sxs-lookup"><span data-stu-id="bae56-143">A <xref:System.Web.UI.WebControls.TextBox> control named `NumericString`.</span></span>  
  
-   <span data-ttu-id="bae56-144">A <xref:System.Web.UI.WebControls.Button> adlı Denetim `OKButton`.</span><span class="sxs-lookup"><span data-stu-id="bae56-144">A <xref:System.Web.UI.WebControls.Button> control named `OKButton`.</span></span> <span data-ttu-id="bae56-145">Ayarlama, <xref:System.Web.UI.WebControls.Button.Text%2A> "Tamam" özelliğine.</span><span class="sxs-lookup"><span data-stu-id="bae56-145">Set its <xref:System.Web.UI.WebControls.Button.Text%2A> property to "OK".</span></span>  
  
 <span data-ttu-id="bae56-146">Sınıfından adını değiştirmek `NumericUserInput` tarafından tanımlanan sınıf adını `Inherits` özniteliği [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] sayfanın `Page` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="bae56-146">Change the name of the class from `NumericUserInput` to the name of the class that is defined by the `Inherits` attribute of the [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page's `Page` directive.</span></span> <span data-ttu-id="bae56-147">Adını değiştirmek `NumericInput` nesnesi tarafından tanımlanan adına başvuru `id` özniteliği [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] sayfanın `form` etiketi.</span><span class="sxs-lookup"><span data-stu-id="bae56-147">Change the name of the `NumericInput` object reference to the name defined by the `id` attribute of the [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page's `form` tag.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bae56-148">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="bae56-148">.NET Framework Security</span></span>  
 <span data-ttu-id="bae56-149">Bir kullanıcının HTML akışa betik injecting önlemek için kullanıcı girişi hiçbir zaman doğrudan sunucu yanıtta yansıtılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="bae56-149">To prevent a user from injecting script into the HTML stream, user input should never be directly echoed back in the server response.</span></span> <span data-ttu-id="bae56-150">Bunun yerine, bunu kullanarak kodlanması gereken <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="bae56-150">Instead, it should be encoded by using the <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae56-151">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bae56-151">See Also</span></span>  
 [<span data-ttu-id="bae56-152">Biçimlendirme işlemlerini gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="bae56-152">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="bae56-153">Sayısal dizeleri ayrıştırma</span><span class="sxs-lookup"><span data-stu-id="bae56-153">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)