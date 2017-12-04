---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="42147-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="42147-102">/rootnamespace</span></span>
<span data-ttu-id="42147-103">Tüm tür bildirimleri için bir ad alanını belirtir.</span><span class="sxs-lookup"><span data-stu-id="42147-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42147-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="42147-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="42147-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="42147-105">Arguments</span></span>  
  
|<span data-ttu-id="42147-106">Terim</span><span class="sxs-lookup"><span data-stu-id="42147-106">Term</span></span>|<span data-ttu-id="42147-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="42147-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="42147-108">Geçerli projenin tüm tür bildirimleri kapsamak ad alanı adı.</span><span class="sxs-lookup"><span data-stu-id="42147-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42147-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="42147-109">Remarks</span></span>  
 <span data-ttu-id="42147-110">Visual Studio yürütülebilir dosya (Devenv.exe) oluşturulmuş bir projeyi derlemek için Visual Studio tümleşik geliştirme ortamında kullanım kullanırsanız `/rootnamespace` değerini belirtmek için <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="42147-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="42147-111">Bkz: [Devenv komut satırı anahtarları](/visualstudio/ide/reference/devenv-command-line-switches) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="42147-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="42147-112">Ortak dil çalışma zamanı MSIL ayrıştırıcı kullanın (`Ildasm.exe`) çıkış dosyanızın ad alanı adlarını görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="42147-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="42147-113">Tümleşik geliştirme ortamı/RootNamespace Visual Studio'da ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="42147-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="42147-114">1.  Seçili bir projeyi **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="42147-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="42147-115">Üzerinde **proje** menüsünde tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="42147-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="42147-116">Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="42147-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="42147-117">2.  Tıklatın **uygulama** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="42147-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="42147-118">3.  Değer değiştirme **kök Namespace** kutusu.</span><span class="sxs-lookup"><span data-stu-id="42147-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42147-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="42147-119">Example</span></span>  
 <span data-ttu-id="42147-120">Aşağıdaki kod derlerken `In.vb` ve ad alanındaki tüm tür bildirimleri barındırır `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="42147-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="42147-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="42147-121">See Also</span></span>  
 [<span data-ttu-id="42147-122">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="42147-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="42147-123">Ildasm.exe (IL ayrıştırıcı)</span><span class="sxs-lookup"><span data-stu-id="42147-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="42147-124">Örnek derleme komut satırları</span><span class="sxs-lookup"><span data-stu-id="42147-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)