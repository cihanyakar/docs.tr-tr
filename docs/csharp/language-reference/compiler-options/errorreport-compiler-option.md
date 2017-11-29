---
title: "-errorreport (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: "35"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3063a29452d90a09d5904d2a598b62530104d739
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="1dff3-102">/errorreport (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="1dff3-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="1dff3-103">Bu seçenek, bir C# derleyici iç hatası Microsoft'a bildirmek için kolay bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="1dff3-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dff3-104">Windows Vista ve Windows Server 2008 üzerinde Visual Studio için yaptığınız hata bildirimi ayarlarını Windows hata bildirimi (WER) üzerinden yapılan ayarları geçersiz kılmaz.</span><span class="sxs-lookup"><span data-stu-id="1dff3-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="1dff3-105">WER ayarları her zaman Visual Studio hata bildirimi ayarları önceliklidir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dff3-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1dff3-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="1dff3-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="1dff3-107">Arguments</span></span>  
 <span data-ttu-id="1dff3-108">**yok**</span><span class="sxs-lookup"><span data-stu-id="1dff3-108">**none**</span></span>  
 <span data-ttu-id="1dff3-109">İç derleyici hataları hakkında raporlar değil toplanmayacak veya Microsoft'a gönderilir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="1dff3-110">**istemi**</span><span class="sxs-lookup"><span data-stu-id="1dff3-110">**prompt**</span></span>  
 <span data-ttu-id="1dff3-111">Derleyici iç hatası aldığınızda, bir raporu göndermek isteyip istemediğinizi sorar.</span><span class="sxs-lookup"><span data-stu-id="1dff3-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="1dff3-112">**İstemi** geliştirme ortamında bir uygulamayı derlediğinizde varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1dff3-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="1dff3-113">**sırası**</span><span class="sxs-lookup"><span data-stu-id="1dff3-113">**queue**</span></span>  
 <span data-ttu-id="1dff3-114">Hata raporu sıralar.</span><span class="sxs-lookup"><span data-stu-id="1dff3-114">Queues the error report.</span></span> <span data-ttu-id="1dff3-115">Yönetici kimlik bilgileriyle oturum açtığınızda, günlüğe kaydedilmiş en son ne zaman bu yana hataları bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dff3-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="1dff3-116">Üç günde birden çok kez hata raporu göndermek için istenmez.</span><span class="sxs-lookup"><span data-stu-id="1dff3-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="1dff3-117">**sıra** komut satırında bir uygulamayı derlediğinizde varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1dff3-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="1dff3-118">**Gönder**</span><span class="sxs-lookup"><span data-stu-id="1dff3-118">**send**</span></span>  
 <span data-ttu-id="1dff3-119">Derleyici iç hata raporlarını otomatik olarak Microsoft'a gönderir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="1dff3-120">Bu seçeneği etkinleştirmek için önce Microsoft veri toplama ilkesini kabul etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="1dff3-121">Belirttiğiniz ilk kez **/errorreport:send** bir bilgisayarda, bir derleyici iletisi Microsoft Veri Toplama İlkesi içeren bir Web sitesine başvurur.</span><span class="sxs-lookup"><span data-stu-id="1dff3-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
    
## <a name="remarks"></a><span data-ttu-id="1dff3-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1dff3-122">Remarks</span></span>  
 <span data-ttu-id="1dff3-123">Kaynak kodu dosyasının derleyici işleyemediğinde iç derleyici hatası (çok) sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="1dff3-123">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="1dff3-124">Bir çok oluştuğunda derleyici çıktı dosyası ya da kodunuzu düzeltmek için kullanabileceğiniz herhangi bir kullanışlı tanılama üretmez.</span><span class="sxs-lookup"><span data-stu-id="1dff3-124">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="1dff3-125">Bir çok alındığında önceki sürümlerde, sorunu bildirmek için Microsoft Ürün Destek Hizmetleri'ne başvurmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-125">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="1dff3-126">Kullanarak **/errorreport**, Visual C# ekibine çok bilgi sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-126">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="1dff3-127">Hata raporlarını gelecek derleyici sürümler artırmaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="1dff3-127">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="1dff3-128">Bir kullanıcının, raporları göndermek becerisini bilgisayar ve kullanıcı ilkesi izinlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="1dff3-128">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="1dff3-129">Hata ayıklayıcısı hakkında daha fazla bilgi için bkz: [Dr açıklaması. Windows (Drwtsn32.exe) aracı için Watson](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="1dff3-129">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1dff3-130">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="1dff3-130">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1dff3-131">Projenin açmak **özellikleri** sayfası.</span><span class="sxs-lookup"><span data-stu-id="1dff3-131">Open the project's **Properties** page.</span></span> <span data-ttu-id="1dff3-132">Daha fazla bilgi için bkz: [derleme sayfası, Proje Tasarımcısı (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="1dff3-132">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="1dff3-133">Tıklatın **yapı** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="1dff3-133">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1dff3-134">Tıklatın **Gelişmiş** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="1dff3-134">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="1dff3-135">Değiştirme **iç derleyici hatası raporlama** özelliği.</span><span class="sxs-lookup"><span data-stu-id="1dff3-135">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="1dff3-136">Bu derleyici seçeneği programlı olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dff3-136">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dff3-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1dff3-137">See Also</span></span>  
 [<span data-ttu-id="1dff3-138">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="1dff3-138">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)