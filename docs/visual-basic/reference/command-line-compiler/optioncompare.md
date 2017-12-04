---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6f602e0b0b23345bf1f5aae843bd44bd2642bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="optioncompare"></a><span data-ttu-id="b5af6-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="b5af6-102">/optioncompare</span></span>
<span data-ttu-id="b5af6-103">Dize karşılaştırmaları nasıl yapılacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="b5af6-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5af6-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b5af6-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5af6-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b5af6-105">Remarks</span></span>  
 <span data-ttu-id="b5af6-106">Belirleyebileceğiniz `/optioncompare` iki forms birinde: `/optioncompare:binary` ikili dize karşılaştırmaları kullanmak için ve `/optioncompare:text` metin dize karşılaştırmaları kullanmak için.</span><span class="sxs-lookup"><span data-stu-id="b5af6-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="b5af6-107">Varsayılan olarak, derleyici kullanır `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="b5af6-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="b5af6-108">Microsoft Windows'daki kullanılan kod sayfası ikili sıralama düzenini belirler.</span><span class="sxs-lookup"><span data-stu-id="b5af6-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="b5af6-109">Tipik bir ikili sıralama aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b5af6-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="b5af6-110">Metin tabanlı dize karşılaştırmaları sisteminizin bölgeye göre belirlenir büyük küçük harf duyarsız metin sıralama düzenini temel alır.</span><span class="sxs-lookup"><span data-stu-id="b5af6-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="b5af6-111">Bir normal metin sıralama aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b5af6-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="b5af6-112">/ Optioncompare Visual Studio IDE'de ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="b5af6-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="b5af6-113">Seçili bir projeyi **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="b5af6-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b5af6-114">Üzerinde **proje** menüsünde tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="b5af6-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b5af6-115">Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="b5af6-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="b5af6-116">Tıklatın **derleme** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="b5af6-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="b5af6-117">Değer değiştirme **seçeneği karşılaştırmak** kutusu.</span><span class="sxs-lookup"><span data-stu-id="b5af6-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="b5af6-118">/ Optioncompare programlı olarak ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="b5af6-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="b5af6-119">Bkz: [Option Compare deyimi](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5af6-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5af6-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="b5af6-120">Example</span></span>  
 <span data-ttu-id="b5af6-121">Aşağıdaki kod derlerken `ProjFile.vb` ve ikili dize karşılaştırmalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="b5af6-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5af6-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b5af6-122">See Also</span></span>  
 [<span data-ttu-id="b5af6-123">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="b5af6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b5af6-124">/ optionexplicit</span><span class="sxs-lookup"><span data-stu-id="b5af6-124">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="b5af6-125">/ optionstrict</span><span class="sxs-lookup"><span data-stu-id="b5af6-125">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="b5af6-126">/ optioninfer</span><span class="sxs-lookup"><span data-stu-id="b5af6-126">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="b5af6-127">Örnek derleme komut satırları</span><span class="sxs-lookup"><span data-stu-id="b5af6-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b5af6-128">Option Compare deyimi</span><span class="sxs-lookup"><span data-stu-id="b5af6-128">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="b5af6-129">Visual Basic Varsayılanları, projeler, Seçenekler iletişim kutusu</span><span class="sxs-lookup"><span data-stu-id="b5af6-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)