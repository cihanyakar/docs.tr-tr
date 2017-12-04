---
title: "-moduleassemblyname (C# derleyici seçeneği)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8ebd6f7498adead4586c9e90ec58ca8efe81aaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname-c-compiler-option"></a><span data-ttu-id="296d4-102">/moduleassemblyname (C# Derleyici Seçeneği)</span><span class="sxs-lookup"><span data-stu-id="296d4-102">/moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="296d4-103">Ortak olmayan türlere bir .netmodule erişebileceği bir derleme belirtir.</span><span class="sxs-lookup"><span data-stu-id="296d4-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="296d4-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="296d4-104">Syntax</span></span>  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="296d4-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="296d4-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="296d4-106">.netmodule, genel türleri derlemenin adını erişebilir.</span><span class="sxs-lookup"><span data-stu-id="296d4-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="296d4-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="296d4-107">Remarks</span></span>  
 <span data-ttu-id="296d4-108">**/ moduleassemblyname** bir .netmodule oluştururken ve aşağıdaki koşullar doğru olduğunda kullanılmalıdır:</span><span class="sxs-lookup"><span data-stu-id="296d4-108">**/moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="296d4-109">.netmodule mevcut bir derlemede ortak olmayan türlere erişimi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="296d4-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="296d4-110">İçine .netmodule oluşturulacak derleme adını öğrenin.</span><span class="sxs-lookup"><span data-stu-id="296d4-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="296d4-111">Varolan derleme içine .netmodule oluşturulacak derlemeye arkadaş derleme erişimi verildi.</span><span class="sxs-lookup"><span data-stu-id="296d4-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="296d4-112">Bir .netmodule oluşturma hakkında daha fazla bilgi için bkz: [/target: Module (C# Derleyici Seçenekleri)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="296d4-112">For more information on building a .netmodule, see [/target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="296d4-113">Arkadaş derlemeler hakkında daha fazla bilgi için bkz: [arkadaş derlemeleri](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="296d4-113">For more information on friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="296d4-114">Bu seçenek geliştirme ortamında kullanılamaz; Yalnızca komut satırından derlerken kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="296d4-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="296d4-115">Bu derleyici seçeneği Visual Studio'da kullanılamıyor ve programlı olarak değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="296d4-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="296d4-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="296d4-116">Example</span></span>  
 <span data-ttu-id="296d4-117">Bu örnek özel türüne sahip bir derleme oluşturur ve csman_an_assembly adlı bir derlemeye arkadaş derleme erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="296d4-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="296d4-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="296d4-118">Example</span></span>  
 <span data-ttu-id="296d4-119">Bu örnek bir genel türünde derleme moduleassemblyname_1.dll erişen bir .netmodule oluşturur.</span><span class="sxs-lookup"><span data-stu-id="296d4-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="296d4-120">Bu .netmodule csman_an_assembly adlı bir derlemeye oluşturulacak öğrenerek biz belirtebilirsiniz **/moduleassemblyname**, ortak olmayan türlere derlemedeki derlemeyi verildi erişmek .netmodule izin verme için csman_an_assembly erişin.</span><span class="sxs-lookup"><span data-stu-id="296d4-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **/moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="296d4-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="296d4-121">Example</span></span>  
 <span data-ttu-id="296d4-122">Bu kod örneği daha önce oluşturulmuş derlemeyi ve .netmodule başvuran derlemenin csman_an_assembly oluşturur.</span><span class="sxs-lookup"><span data-stu-id="296d4-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 <span data-ttu-id="296d4-123">**An_Internal_Class.test**</span><span class="sxs-lookup"><span data-stu-id="296d4-123">**An_Internal_Class.Test called**</span></span>  
## <a name="see-also"></a><span data-ttu-id="296d4-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="296d4-124">See Also</span></span>  
 [<span data-ttu-id="296d4-125">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="296d4-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="296d4-126">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="296d4-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)