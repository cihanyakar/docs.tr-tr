---
title: "-out (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 332e369b6fe2de79c9063daa9e6d5c0e83f0bcc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="out-c-compiler-options"></a><span data-ttu-id="08510-102">/out (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="08510-102">/out (C# Compiler Options)</span></span>
<span data-ttu-id="08510-103">**/Out** seçeneği çıktı dosyası adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="08510-103">The **/out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08510-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="08510-104">Syntax</span></span>  
  
```console  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="08510-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="08510-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="08510-106">Derleyici tarafından oluşturulan çıkış dosyasının adı.</span><span class="sxs-lookup"><span data-stu-id="08510-106">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08510-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="08510-107">Remarks</span></span>  
 <span data-ttu-id="08510-108">Komut satırında, derleme için birden çok çıktı dosyaları belirtmek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="08510-108">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="08510-109">Aşağıdaki bir veya daha fazla kaynak kodu dosyaları bulmak derleyici bekliyor **/out** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="08510-109">The compiler expects to find one or more source code files following the **/out** option.</span></span> <span data-ttu-id="08510-110">Ardından, tüm kaynak kodu dosyaları tarafından belirtilen çıktı dosyasına derlenecek **/out** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="08510-110">Then, all source code files will be compiled into the output file specified by that **/out** option.</span></span>  
  
 <span data-ttu-id="08510-111">Oluşturmak istediğiniz dosya uzantısını ve tam adını belirtin.</span><span class="sxs-lookup"><span data-stu-id="08510-111">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="08510-112">Çıktı dosyası adını belirtmezseniz:</span><span class="sxs-lookup"><span data-stu-id="08510-112">If you do not specify the name of the output file:</span></span>  
  
-   <span data-ttu-id="08510-113">Bir .exe adını içeren kaynak kodu dosyasından alacaktır **ana** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="08510-113">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
-   <span data-ttu-id="08510-114">Bir .dll veya .netmodule adının ilk kaynak kodu dosyasından olur.</span><span class="sxs-lookup"><span data-stu-id="08510-114">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="08510-115">Bir çıkış dosyası derlemek için kullanılan bir kaynak kodu dosyasının aynı derlemede başka bir çıktı dosyası derleme için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="08510-115">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="08510-116">Komut satırı derleme birden çok çıktı dosyasında üretirken, çıktı dosyaları yalnızca tek bir derleme olabilir ve yalnızca ilk çıkış dosyası belirtilen göz önünde bulundurun (örtük veya açık olarak ile **/out**) derleme olabilir .</span><span class="sxs-lookup"><span data-stu-id="08510-116">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **/out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="08510-117">Bir derleme bir parçası olarak oluşturulan herhangi bir modül ayrıca derlemede üretilen derleme ile ilişkili dosyalar haline gelir.</span><span class="sxs-lookup"><span data-stu-id="08510-117">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="08510-118">Kullanım [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) ilişkili dosyaları görmek için derleme bildirimi görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="08510-118">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="08510-119">/ Out derleyici seçeneği sırada bir arkadaş derleme hedefi bir exe için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="08510-119">The /out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="08510-120">Daha fazla bilgi için bkz: [arkadaş derlemeleri](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="08510-120">For more information see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="08510-121">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="08510-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="08510-122">Projenin açmak **özellikleri** sayfası.</span><span class="sxs-lookup"><span data-stu-id="08510-122">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="08510-123">Tıklatın **uygulama** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="08510-123">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="08510-124">Değiştirme **derleme adı** özelliği.</span><span class="sxs-lookup"><span data-stu-id="08510-124">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="08510-125">Bu derleyici seçeneği programlı olarak ayarlamak için: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> proje türü (exe, kitaplık ve benzeri) ve derleme adı birleşimi tarafından belirlenir. bir salt okunur özelliği.</span><span class="sxs-lookup"><span data-stu-id="08510-125">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="08510-126">Birini veya her ikisini bu özellikleri değiştirme çıktı dosyası adını ayarlamak gerekli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="08510-126">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08510-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="08510-127">Example</span></span>  
 <span data-ttu-id="08510-128">Derleme `t.cs` ve çıktı dosyası oluşturma `t.exe`, yapı yanı sıra `t2.cs` ve modül çıkış dosyası oluşturma `mymodule.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="08510-128">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="08510-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="08510-129">See Also</span></span>  
 [<span data-ttu-id="08510-130">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="08510-130">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="08510-131">Arkadaş derlemeleri</span><span class="sxs-lookup"><span data-stu-id="08510-131">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="08510-132">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="08510-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)