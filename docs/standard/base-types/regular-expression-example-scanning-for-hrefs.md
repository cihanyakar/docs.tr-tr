---
title: "Normal İfade Örneği: HREF Tarama"
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="35308-102">Normal İfade Örneği: HREF Tarama</span><span class="sxs-lookup"><span data-stu-id="35308-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="35308-103">Aşağıdaki örnek giriş dizesi arar ve görüntüler tüm href = "..." değerlerini ve konumlarına dize.</span><span class="sxs-lookup"><span data-stu-id="35308-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="35308-104">Regex Nesnesi</span><span class="sxs-lookup"><span data-stu-id="35308-104">The Regex Object</span></span>  
 <span data-ttu-id="35308-105">Çünkü `DumpHRefs` yöntemi çağrılabilir birden çok kez kullanıcı kodundan, kullandığı `static` (`Shared` Visual Basic'te) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="35308-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="35308-106">Bu normal ifade önbelleğe almak normal ifade altyapısı sağlar ve yeni bir örneği, yüke engel <xref:System.Text.RegularExpressions.Regex> nesne her zaman yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="35308-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="35308-107">A <xref:System.Text.RegularExpressions.Match> nesnesi dizesindeki tüm eşleşmeleri yinelemek için sonra kullanılır.</span><span class="sxs-lookup"><span data-stu-id="35308-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="35308-108">Aşağıdaki örnekte, ardından bir çağrı gösterilmektedir `DumpHRefs` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="35308-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="35308-109">Normal ifade deseni `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` aşağıdaki tabloda gösterildiği gibi yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="35308-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="35308-110">Desen</span><span class="sxs-lookup"><span data-stu-id="35308-110">Pattern</span></span>|<span data-ttu-id="35308-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="35308-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="35308-112">"Href" değişmez değer dize eşleşmesi.</span><span class="sxs-lookup"><span data-stu-id="35308-112">Match the literal string "href".</span></span> <span data-ttu-id="35308-113">Eşleşme büyük/küçük harf duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="35308-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="35308-114">Sıfır veya daha fazla boşluk karakteriyle eşleş.</span><span class="sxs-lookup"><span data-stu-id="35308-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="35308-115">Eşittir işareti ile aynı.</span><span class="sxs-lookup"><span data-stu-id="35308-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="35308-116">Sıfır veya daha fazla boşluk karakteriyle eşleş.</span><span class="sxs-lookup"><span data-stu-id="35308-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="35308-117">Aşağıdakilerden birini yakalanan bir gruba sonucu atamadan eşleştir:</span><span class="sxs-lookup"><span data-stu-id="35308-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="35308-118">-Bir tırnak işareti veya tırnak işareti veya kesme işareti, bir tırnak işareti veya kesme işareti gelmelidir dışındaki herhangi bir karakter, sıfır veya daha fazla tekrarı ve ardından kesme işareti.</span><span class="sxs-lookup"><span data-stu-id="35308-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="35308-119">Adlı grup `1` bu modelinde eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="35308-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="35308-120">-Bir veya daha fazla boşluk olmayan karakter.</span><span class="sxs-lookup"><span data-stu-id="35308-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="35308-121">Adlı grup `1` bu modelinde eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="35308-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="35308-122">Tırnak işareti veya kesme işareti dışındaki herhangi bir karakter, sıfır veya daha fazla tekrarı adlı yakalama grubuna atayın `1`.</span><span class="sxs-lookup"><span data-stu-id="35308-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="35308-123">Bir veya daha fazla boşluk olmayan karakter adlı yakalama grubuna atayın `1`.</span><span class="sxs-lookup"><span data-stu-id="35308-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="35308-124">Sonuç Sınıfını Eşleştirme</span><span class="sxs-lookup"><span data-stu-id="35308-124">Match Result Class</span></span>  
 <span data-ttu-id="35308-125">Arama sonuçlarını depolanmış <xref:System.Text.RegularExpressions.Match> aramada ayıklanan tüm alt dizeler erişim sağlayan sınıf.</span><span class="sxs-lookup"><span data-stu-id="35308-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="35308-126">Bunu çağırması, ayrıca Aranmakta dize ve kullanılan, normal ifade hatırlıyor <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> başka bir arama burada sonuncu sona erdi başlangıç yapmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="35308-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="35308-127">Açıkça Adlandırılmış Yakalamalar</span><span class="sxs-lookup"><span data-stu-id="35308-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="35308-128">Geleneksel normal ifadelerde yakalama parantez otomatik olarak ardışık olarak numaralandırılır.</span><span class="sxs-lookup"><span data-stu-id="35308-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="35308-129">Bu iki sorunlara yol açar.</span><span class="sxs-lookup"><span data-stu-id="35308-129">This leads to two problems.</span></span> <span data-ttu-id="35308-130">Normal bir ifade ekleme veya bir dizi parantez kaldırarak değiştirilirse, ilk olarak, numaralandırılmış yakalamaları başvuran tüm kod yeni numaralandırma yansıtacak şekilde yazılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="35308-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="35308-131">İkinci olarak, genellikle farklı ayarlar parantez kabul edilebilir bir eşleşme için iki alternatif ifadeler sağlamak için kullanıldığından, iki ifadeye hangisinin gerçekte bir sonuç döndürdü belirlemek zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="35308-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="35308-132">Bu sorunları gidermek için <xref:System.Text.RegularExpressions.Regex> sınıfı destekler söz dizimi `(?<name>…)` bir eşleşme belirtilen yuvaya yakalamak için (bir string veya tamsayı kullanarak yuvaya adlandırılabilir; tamsayılar geri daha hızlı).</span><span class="sxs-lookup"><span data-stu-id="35308-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="35308-133">Bu nedenle, tüm aynı yerde yönlendirilebilir aynı dize için alternatif eşleşir.</span><span class="sxs-lookup"><span data-stu-id="35308-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="35308-134">Bir çakışma durumunda bir yuvaya bırakılan son başarılı eşleşme eşleşmedir.</span><span class="sxs-lookup"><span data-stu-id="35308-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="35308-135">(Ancak, tek bir yuva için birden çok eşleşen tam bir listesi kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="35308-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="35308-136">Bkz: <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> ayrıntıları toplamalarında.)</span><span class="sxs-lookup"><span data-stu-id="35308-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35308-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35308-137">See Also</span></span>  
 [<span data-ttu-id="35308-138">.NET normal ifadeler</span><span class="sxs-lookup"><span data-stu-id="35308-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)