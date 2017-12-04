---
title: Non-CLS ile uyumlu &lt;membername&gt; CLS uyumlu arabiriminde izin verilmiyor
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="5e9f2-102">Non-CLS ile uyumlu &lt;membername&gt; CLS uyumlu arabiriminde izin verilmiyor</span><span class="sxs-lookup"><span data-stu-id="5e9f2-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="5e9f2-103">Bir özellik, yordam veya olay arabirimdeki olarak işaretlenmiş `<CLSCompliant(True)>` zaman arabirimi olarak işaretli `<CLSCompliant(False)>` veya değil olarak işaretlenmiş.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="5e9f2-104">Uyumlu olması bir arabirim için [dil bağımsızlığı ve dilden bağımsız bileşenler](https://msdn.microsoft.com/library/12a7a7h3) (CLS), tüm üyeleri olmalıdır uyumlu.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="5e9f2-105">Uyguladığınızda <xref:System.CLSCompliantAttribute> bir programlama öğesi için ayarladığınız özniteliğin `isCompliant` ya da parametre `True` veya `False` uyumluluğu veya uyumsuzluğu belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5e9f2-106">Bu parametre için varsayılan yok ve bir değer sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="5e9f2-107">Geçerli <xref:System.CLSCompliantAttribute> bir öğe olarak uyumsuz olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="5e9f2-108">Varsayılan olarak, bu iletiyi bir uyarıdır.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-108">By default, this message is a warning.</span></span> <span data-ttu-id="5e9f2-109">Uyarıları gizleme veya uyarıları hata olarak davranma hakkında daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5e9f2-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5e9f2-110">**Hata Kimliği:** BC40033</span><span class="sxs-lookup"><span data-stu-id="5e9f2-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e9f2-111">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="5e9f2-111">To correct this error</span></span>  
  
-   <span data-ttu-id="5e9f2-112">CLS uyumluluğu gerektiriyorsa ve arabirim kaynak kodu üzerinde denetim sahibi yoksa arabirimi olarak işaretlemek `<CLSCompliant(True)>` tüm üyeleri uyumlu olması durumunda.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="5e9f2-113">CLS uyumluluğu gerektirir ve arabirim kaynak kodu üzerinde denetim sahibi değildir veya da uyumlu olması uygun değilse, bu üye içinde farklı bir arabirim tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="5e9f2-114">Bu üye, geçerli arabirimi içinde kalmasını gerekiyorsa kaldırma <xref:System.CLSCompliantAttribute> kendi tanımındaki veya olarak işaretlemek `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9f2-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5e9f2-115">See Also</span></span>  
 [<span data-ttu-id="5e9f2-116">Interface deyimi</span><span class="sxs-lookup"><span data-stu-id="5e9f2-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="5e9f2-117">\<PAVE üzerinden > CLS uyumlu kod yazma</span><span class="sxs-lookup"><span data-stu-id="5e9f2-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)