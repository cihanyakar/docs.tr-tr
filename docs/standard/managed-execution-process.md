---
title: "Yönetilen Yürütme İşlemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source code language
- code, managed execution process
- runtime, managed execution process
- compiling source code, managed execution process
- managed execution process
- common language runtime, managed execution process
ms.assetid: 476b03dc-2b12-49a7-b067-41caeaa2f533
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a47761acfabd3de77d65483d50fbe7a77f96e076
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="managed-execution-process"></a><span data-ttu-id="b138e-102">Yönetilen Yürütme İşlemi</span><span class="sxs-lookup"><span data-stu-id="b138e-102">Managed Execution Process</span></span>
<span data-ttu-id="b138e-103"><a name="introduction"></a>Yönetilen yürütme işlemi, bu konunun ilerleyen bölümlerinde ayrıntılı olarak ele alınmıştır aşağıdaki adımları içerir:</span><span class="sxs-lookup"><span data-stu-id="b138e-103"><a name="introduction"></a> The managed execution process includes the following steps, which are discussed in detail later in this topic:</span></span>  
  
1.  <span data-ttu-id="b138e-104">[Derleyici seçme](#choosing_a_compiler).</span><span class="sxs-lookup"><span data-stu-id="b138e-104">[Choosing a compiler](#choosing_a_compiler).</span></span>  
  
     <span data-ttu-id="b138e-105">Ortak dil çalışma zamanı tarafından sağlanan avantajları elde etmek için çalışma zamanı hedefleyen bir veya daha fazla dil derleyicileri kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-105">To obtain the benefits provided by the common language runtime, you must use one or more language compilers that target the runtime.</span></span>  
  
2.  <span data-ttu-id="b138e-106">[MSIL kodunuzu derlerken](#compiling_to_msil).</span><span class="sxs-lookup"><span data-stu-id="b138e-106">[Compiling your code to MSIL](#compiling_to_msil).</span></span>  
  
     <span data-ttu-id="b138e-107">Derleme kaynak kodunuzu Microsoft Ara dile (MSIL) çevirir ve gerekli meta veriler oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b138e-107">Compiling translates your source code into Microsoft intermediate language (MSIL) and generates the required metadata.</span></span>  
  
3.  <span data-ttu-id="b138e-108">[MSIL için yerel kodu derleme](#compiling_msil_to_native_code).</span><span class="sxs-lookup"><span data-stu-id="b138e-108">[Compiling MSIL to native code](#compiling_msil_to_native_code).</span></span>  
  
     <span data-ttu-id="b138e-109">Yürütme sırasında bir tam zamanında (JIT) derleyici MSIL yerel kod içine çevirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-109">At execution time, a just-in-time (JIT) compiler translates the MSIL into native code.</span></span> <span data-ttu-id="b138e-110">Bu derleme sırasında kod olup olmadığını kodu türü güvenli belirlenebilir çıkışı bulmak için MSIL ve meta veri inceler bir doğrulama işlemi geçmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-110">During this compilation, code must pass a verification process that examines the MSIL and metadata to find out whether the code can be determined to be type safe.</span></span>  
  
4.  <span data-ttu-id="b138e-111">[Kod çalıştırmasını](#running_code).</span><span class="sxs-lookup"><span data-stu-id="b138e-111">[Running code](#running_code).</span></span>  
  
     <span data-ttu-id="b138e-112">Ortak dil çalışma zamanı yerinde ve yürütme sırasında kullanılan hizmetleri yapılacak yürütme etkinleştirir altyapı sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-112">The common language runtime provides the infrastructure that enables execution to take place and services that can be used during execution.</span></span>  
  
<a name="choosing_a_compiler"></a>   
## <a name="choosing-a-compiler"></a><span data-ttu-id="b138e-113">Bir derleme seçme</span><span class="sxs-lookup"><span data-stu-id="b138e-113">Choosing a Compiler</span></span>  
 <span data-ttu-id="b138e-114">Ortak dil çalışma zamanı tarafından (CLR) sağlanan avantajları elde etmek için bir veya daha fazla dil derleyicileri hedefleyen Visual Basic, C#, Visual C++, F # veya Eiffel, Perl veya COBOL derleyici gibi çok sayıda üçüncü taraf derleyicileri biri gibi çalışma zamanı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-114">To obtain the benefits provided by the common language runtime (CLR), you must use one or more language compilers that target the runtime, such as Visual Basic, C#, Visual C++, F#, or one of many third-party compilers such as an Eiffel, Perl, or COBOL compiler.</span></span>  
  
 <span data-ttu-id="b138e-115">Çok dilli yürütme ortamı olduğu için çalışma zamanı çok çeşitli veri türleri ve dil özellikleri destekler.</span><span class="sxs-lookup"><span data-stu-id="b138e-115">Because it is a multilanguage execution environment, the runtime supports a wide variety of data types and language features.</span></span> <span data-ttu-id="b138e-116">Kullandığınız dil derleyici hangi çalışma zamanı özelliklerin kullanılabilir olduğunu belirler ve bu özellikleri kullanarak kodunuzu tasarlayın.</span><span class="sxs-lookup"><span data-stu-id="b138e-116">The language compiler you use determines which runtime features are available, and you design your code using those features.</span></span> <span data-ttu-id="b138e-117">Derleyici, çalışma zamanı değil, kodunuzu kullanmalısınız sözdizimi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b138e-117">Your compiler, not the runtime, establishes the syntax your code must use.</span></span> <span data-ttu-id="b138e-118">Bileşeniniz diğer dillerde yazılmış bileşenler tarafından tamamen kullanılabilir olması gerekiyorsa, bileşenin verilen türleri dahil edilen dil özellikleri kullanıma [dil bağımsızlığı ve dilden bağımsız bileşenler](../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="b138e-118">If your component must be completely usable by components written in other languages, your component's exported types must expose only language features that are included in the [Language Independence and Language-Independent Components](../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="b138e-119">Kullanabileceğiniz <xref:System.CLSCompliantAttribute> özniteliği kodunuzu CLS ile uyumlu olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="b138e-119">You can use the <xref:System.CLSCompliantAttribute> attribute to ensure that your code is CLS-compliant.</span></span> <span data-ttu-id="b138e-120">Daha fazla bilgi için bkz: [dil bağımsızlığı ve dilden bağımsız bileşenler](../../docs/standard/language-independence-and-language-independent-components.md).</span><span class="sxs-lookup"><span data-stu-id="b138e-120">For more information, see [Language Independence and Language-Independent Components](../../docs/standard/language-independence-and-language-independent-components.md).</span></span>  
  
 [<span data-ttu-id="b138e-121">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b138e-121">Back to top</span></span>](#introduction)  
  
<a name="compiling_to_msil"></a>   
## <a name="compiling-to-msil"></a><span data-ttu-id="b138e-122">MSIL için derleme</span><span class="sxs-lookup"><span data-stu-id="b138e-122">Compiling to MSIL</span></span>  
 <span data-ttu-id="b138e-123">Yönetilen kod için derleme, derleyici, kaynak kodunuzu yerel koda verimli bir şekilde dönüştürülebilir yönergeler CPU bağımsız kümesi olan Microsoft Ara dili (MSIL) çevirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-123">When compiling to managed code, the compiler translates your source code into Microsoft intermediate language (MSIL), which is a CPU-independent set of instructions that can be efficiently converted to native code.</span></span> <span data-ttu-id="b138e-124">MSIL yüklenirken, depolama, başlatma ve nesneler üzerinde çağıran yöntemleri için yönergeler yanı sıra, aritmetik ve mantıksal işlemleri, akış denetimi, doğrudan bellek erişimi, özel durum işleme ve diğer işlemler için yönergeler içerir.</span><span class="sxs-lookup"><span data-stu-id="b138e-124">MSIL includes instructions for loading, storing, initializing, and calling methods on objects, as well as instructions for arithmetic and logical operations, control flow, direct memory access, exception handling, and other operations.</span></span> <span data-ttu-id="b138e-125">Kod çalıştırmadan önce MSIL CPU'ya özel kod, genellikle göre dönüştürülmelidir bir [tam zamanında (JIT) derleyici](#compiling_msil_to_native_code).</span><span class="sxs-lookup"><span data-stu-id="b138e-125">Before code can be run, MSIL must be converted to CPU-specific code, usually by a [just-in-time (JIT) compiler](#compiling_msil_to_native_code).</span></span> <span data-ttu-id="b138e-126">Ortak dil çalışma zamanı desteklediği her bilgisayar mimarisi için bir veya daha fazla JIT derleyicileri sağladığı için MSIL aynı kümesini JIT derlenmiş ve çalışma desteklenen tüm mimarisine olabilir.</span><span class="sxs-lookup"><span data-stu-id="b138e-126">Because the common language runtime supplies one or more JIT compilers for each computer architecture it supports, the same set of MSIL can be JIT-compiled and run on any supported architecture.</span></span>  
  
 <span data-ttu-id="b138e-127">MSIL derleyici ürettiği zaman ayrıca meta veriler üretir.</span><span class="sxs-lookup"><span data-stu-id="b138e-127">When a compiler produces MSIL, it also produces metadata.</span></span> <span data-ttu-id="b138e-128">Meta veri türleri dahil her tür tanımı, her tür üyeleri, kodunuzu başvuran üyeleri ve çalışma zamanı yürütme sırasında kullanan diğer veri imzalarını kodunuzda açıklar.</span><span class="sxs-lookup"><span data-stu-id="b138e-128">Metadata describes the types in your code, including the definition of each type, the signatures of each type's members, the members that your code references, and other data that the runtime uses at execution time.</span></span> <span data-ttu-id="b138e-129">MSIL ve meta veri dosyasında, temel alır ve geçmişte yürütülebilir içerik için kullanılan ortak nesne dosyası biçimi (COFF) ve yayımlanan Microsoft PE genişleten bir taşınabilir yürütülebilir (PE) bulunur.</span><span class="sxs-lookup"><span data-stu-id="b138e-129">The MSIL and metadata are contained in a portable executable (PE) file that is based on and that extends the published Microsoft PE and common object file format (COFF) used historically for executable content.</span></span> <span data-ttu-id="b138e-130">Meta veri yanı sıra MSIL veya yerel kod düzenler, bu dosya biçimi ortak dil çalışma zamanı görüntüleri tanımak işletim sisteminin sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-130">This file format, which accommodates MSIL or native code as well as metadata, enables the operating system to recognize common language runtime images.</span></span> <span data-ttu-id="b138e-131">MSIL birlikte dosyasındaki meta veri varlığını hangi tür kitaplığı veya arabirimi tanım dili (IDL) için gerekli olduğu anlamına gelir kendisini tanımlamak kodunuzu sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-131">The presence of metadata in the file together with MSIL enables your code to describe itself, which means that there is no need for type libraries or Interface Definition Language (IDL).</span></span> <span data-ttu-id="b138e-132">Çalışma zamanı bulur ve yürütme sırasında gerektiği gibi meta veri dosyasından ayıklar.</span><span class="sxs-lookup"><span data-stu-id="b138e-132">The runtime locates and extracts the metadata from the file as needed during execution.</span></span>  
  
 [<span data-ttu-id="b138e-133">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b138e-133">Back to top</span></span>](#introduction)  
  
<a name="compiling_msil_to_native_code"></a>   
## <a name="compiling-msil-to-native-code"></a><span data-ttu-id="b138e-134">MSIL yerel kodu derleme</span><span class="sxs-lookup"><span data-stu-id="b138e-134">Compiling MSIL to Native Code</span></span>  
 <span data-ttu-id="b138e-135">Microsoft Ara dili (MSIL) çalıştırmadan önce karşı ortak dil çalışma zamanı hedef makine mimarisi için yerel koda derlenmiş gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-135">Before you can run Microsoft intermediate language (MSIL), it must be compiled against the common language runtime to native code for the target machine architecture.</span></span> <span data-ttu-id="b138e-136">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Bu dönüştürme gerçekleştirmek için iki yöntem sunar:</span><span class="sxs-lookup"><span data-stu-id="b138e-136">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides two ways to perform this conversion:</span></span>  
  
-   <span data-ttu-id="b138e-137">.NET Framework tam zamanında (JIT) derleyicisi.</span><span class="sxs-lookup"><span data-stu-id="b138e-137">A .NET Framework just-in-time (JIT) compiler.</span></span>  
  
-   <span data-ttu-id="b138e-138">.NET Framework [Ngen.exe (yerel Görüntü Oluşturucu)](../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="b138e-138">The .NET Framework [Ngen.exe (Native Image Generator)](../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
### <a name="compilation-by-the-jit-compiler"></a><span data-ttu-id="b138e-139">JIT Derleyici tarafından derleme</span><span class="sxs-lookup"><span data-stu-id="b138e-139">Compilation by the JIT Compiler</span></span>  
 <span data-ttu-id="b138e-140">JIT derleme MSIL uygulama çalışma zamanı bütünleştirilmiş içeriğini ne zaman yüklendi ve yürütülen isteğe bağlı yerel koda dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="b138e-140">JIT compilation converts MSIL to native code on demand at application run time, when the contents of an assembly are loaded and executed.</span></span> <span data-ttu-id="b138e-141">Ortak dil çalışma zamanı JIT Derleyici desteklenen her CPU mimarisi için sağladığı olduğundan, geliştiriciler JIT derlenmiş ve farklı bilgisayarlarda farklı makine mimarileri ile çalışma MSIL derlemeler kümesini oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="b138e-141">Because the common language runtime supplies a JIT compiler for each supported CPU architecture, developers can build a set of MSIL assemblies that can be JIT-compiled and run on different computers with different machine architectures.</span></span> <span data-ttu-id="b138e-142">Bununla birlikte, yönetilen kod platforma özgü yerel API'leri veya bir platforma özgü sınıf kitaplığı çağırırsa, yalnızca bu işletim sisteminde çalışır.</span><span class="sxs-lookup"><span data-stu-id="b138e-142">However, if your managed code calls platform-specific native APIs or a platform-specific class library, it will run only on that operating system.</span></span>  
  
 <span data-ttu-id="b138e-143">JIT derleme bazı kod hiç yürütme sırasında çağrılabilir olasılığını dikkate alır.</span><span class="sxs-lookup"><span data-stu-id="b138e-143">JIT compilation takes into account the possibility that some code might never be called during execution.</span></span> <span data-ttu-id="b138e-144">Yerine süresi ve bellek PE dosyasındaki tüm MSIL yerel koda dönüştürmek için onu MSIL yürütme sırasında gerektiği şekilde dönüştürür ve böylece bu işlemin bağlamında sonraki çağrılar için erişilebilir elde edilen yerel kod bellekte depolar.</span><span class="sxs-lookup"><span data-stu-id="b138e-144">Instead of using time and memory to convert all the MSIL in a PE file to native code, it converts the MSIL as needed during execution and stores the resulting native code in memory so that it is accessible for subsequent calls in the context of that process.</span></span> <span data-ttu-id="b138e-145">Yükleyici oluşturur ve türü yüklenmiş ve başlatılmış bir saplama bir türdeki her yöntem ekler.</span><span class="sxs-lookup"><span data-stu-id="b138e-145">The loader creates and attaches a stub to each method in a type when the type is loaded and initialized.</span></span> <span data-ttu-id="b138e-146">Bir yöntem ilk kez çağrıldığında, saplama denetim bu yöntem için MSIL yerel koda dönüştürür ve doğrudan oluşturulan yerel kod işaret edecek şekilde saplama değiştirir JIT Derleyici geçirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-146">When a method is called for the first time, the stub passes control to the JIT compiler, which converts the MSIL for that method into native code and modifies the stub to point directly to the generated native code.</span></span> <span data-ttu-id="b138e-147">Bu nedenle, JIT derlenmiş yöntemine yapılan sonraki çağrılar doğrudan yerel koda gitme olanağı.</span><span class="sxs-lookup"><span data-stu-id="b138e-147">Therefore, subsequent calls to the JIT-compiled method go directly to the native code.</span></span>  
  
### <a name="install-time-code-generation-using-ngenexe"></a><span data-ttu-id="b138e-148">NGen.exe kullanarak yükleme zamanı kodu oluşturma</span><span class="sxs-lookup"><span data-stu-id="b138e-148">Install-Time Code Generation Using NGen.exe</span></span>  
 <span data-ttu-id="b138e-149">Çünkü yerel kod tek tek zaman bir derlemenin MSIL JIT Derleyici dönüştürür bu derlemede tanımlanan yöntemler olarak adlandırılır, çalışma zamanında olumsuz performansı etkiler.</span><span class="sxs-lookup"><span data-stu-id="b138e-149">Because the JIT compiler converts an assembly's MSIL to native code when individual methods defined in that assembly are called, it affects performance adversely at run time.</span></span> <span data-ttu-id="b138e-150">Düşüklüğü, artan performans kabul edilebilir çoğu durumda.</span><span class="sxs-lookup"><span data-stu-id="b138e-150">In most cases, that diminished performance is acceptable.</span></span> <span data-ttu-id="b138e-151">Daha da önemlisi, JIT Derleyici tarafından üretilen kod derleme tetiklenen işleme bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="b138e-151">More importantly, the code generated by the JIT compiler is bound to the process that triggered the compilation.</span></span> <span data-ttu-id="b138e-152">Birden çok süreçler arasında paylaşılamaz.</span><span class="sxs-lookup"><span data-stu-id="b138e-152">It cannot be shared across multiple processes.</span></span> <span data-ttu-id="b138e-153">Bir uygulamanın birden çok çağrılarını arasında veya derlemeler kümesini paylaşan birden çok işlemler arasında paylaşılması için oluşturulan kodu izin vermek için ortak dil çalışma zamanı, zaman önceden derleme moduna destekler.</span><span class="sxs-lookup"><span data-stu-id="b138e-153">To allow the generated code to be shared across multiple invocations of an application or across multiple processes that share a set of assemblies, the common language runtime supports an ahead-of-time compilation mode.</span></span> <span data-ttu-id="b138e-154">Bu, zaman önceden derleme moduna kullanan [Ngen.exe (yerel Görüntü Oluşturucu)](../../docs/framework/tools/ngen-exe-native-image-generator.md) JIT Derleyici yaptığı gibi MSIL dönüştürmek için yerel derlemelere çok kod.</span><span class="sxs-lookup"><span data-stu-id="b138e-154">This ahead-of-time compilation mode uses the [Ngen.exe (Native Image Generator)](../../docs/framework/tools/ngen-exe-native-image-generator.md) to convert MSIL assemblies to native code much like the JIT compiler does.</span></span> <span data-ttu-id="b138e-155">Ancak, Ngen.exe işlemi, üç yolla JIT Derleyici farklıdır:</span><span class="sxs-lookup"><span data-stu-id="b138e-155">However, the operation of Ngen.exe differs from that of the JIT compiler in three ways:</span></span>  
  
-   <span data-ttu-id="b138e-156">Uygulama çalışırken yerine uygulamayı çalıştırmadan önce yerel koda dönüştürme MSIL işlemini gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-156">It performs the conversion from MSIL to native code before running the application instead of while the application is running.</span></span>  
  
-   <span data-ttu-id="b138e-157">Tüm bütünleştirilmiş birer birer birer birer bir yöntem yerine derler.</span><span class="sxs-lookup"><span data-stu-id="b138e-157">It compiles an entire assembly at a time, instead of one method at a time.</span></span>  
  
-   <span data-ttu-id="b138e-158">Bu oluşturulan kodda yerel görüntü önbelleği disk üzerindeki bir dosya olarak devam ettirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-158">It persists the generated code in the Native Image Cache as a file on disk.</span></span>  
  
### <a name="code-verification"></a><span data-ttu-id="b138e-159">Kod doğrulama</span><span class="sxs-lookup"><span data-stu-id="b138e-159">Code Verification</span></span>  
 <span data-ttu-id="b138e-160">Bir yönetici doğrulamayı atlama kodu izin veren bir güvenlik ilkesi kurulduğunda sürece yerel koda kendi derleme bir parçası olarak, bir doğrulama işlemi MSIL kod geçmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-160">As part of its compilation to native code, the MSIL code must pass a verification process unless an administrator has established a security policy that allows the code to bypass verification.</span></span> <span data-ttu-id="b138e-161">Doğrulama MSIL ve meta verileri kodu erişimi için yetkilendirilmiş bellek konumlarına erişen anlamı türü güvenli olup olmadığını öğrenmek için inceler.</span><span class="sxs-lookup"><span data-stu-id="b138e-161">Verification examines MSIL and metadata to find out whether the code is type safe, which means that it accesses only the memory locations it is authorized to access.</span></span> <span data-ttu-id="b138e-162">Tür güvenliği nesneleri birbirinden yalıtmak yardımcı olur ve yanlışlıkla veya kötü amaçlı bozulmaya karşı korunmasına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="b138e-162">Type safety helps isolate objects from each other and helps protect them from inadvertent or malicious corruption.</span></span> <span data-ttu-id="b138e-163">Ayrıca, kod üzerinde güvenlik kısıtlamaları güvenilir bir şekilde zorunlu tutulabilir güvence sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-163">It also provides assurance that security restrictions on code can be reliably enforced.</span></span>  
  
 <span data-ttu-id="b138e-164">Çalışma zamanı aşağıdaki deyimleri için doğrulanabilir şekilde güvenli türü olan kodu doğru olgu kullanır:</span><span class="sxs-lookup"><span data-stu-id="b138e-164">The runtime relies on the fact that the following statements are true for code that is verifiably type safe:</span></span>  
  
-   <span data-ttu-id="b138e-165">Türüne bir başvuru kesinlikle başvurulan türü ile uyumludur.</span><span class="sxs-lookup"><span data-stu-id="b138e-165">A reference to a type is strictly compatible with the type being referenced.</span></span>  
  
-   <span data-ttu-id="b138e-166">Yalnızca uygun şekilde tanımlanan işlemlerine bir nesne üzerinde çağrılır.</span><span class="sxs-lookup"><span data-stu-id="b138e-166">Only appropriately defined operations are invoked on an object.</span></span>  
  
-   <span data-ttu-id="b138e-167">Bunlar olması talep hesaplardır.</span><span class="sxs-lookup"><span data-stu-id="b138e-167">Identities are what they claim to be.</span></span>  
  
 <span data-ttu-id="b138e-168">Doğrulama işlemi sırasında kod bellek konumlarına erişmek ve düzgün şekilde tanımlı türler yalnızca yoluyla yöntemlerini çağıran onaylayın girişimi MSIL kod incelenir.</span><span class="sxs-lookup"><span data-stu-id="b138e-168">During the verification process, MSIL code is examined in an attempt to confirm that the code can access memory locations and call methods only through properly defined types.</span></span> <span data-ttu-id="b138e-169">Örneğin, kod taşmasına belleğinden izin veren bir şekilde Erişilecek nesnenin alanları izin veremez.</span><span class="sxs-lookup"><span data-stu-id="b138e-169">For example, code cannot allow an object's fields to be accessed in a manner that allows memory locations to be overrun.</span></span> <span data-ttu-id="b138e-170">Ayrıca, doğrulama kodu yanlış MSIL türü güvenlik kuralları ihlali için yol açabileceğinden MSIL doğru bir şekilde oluşturuldu olup olmadığını, belirlemek için inceler.</span><span class="sxs-lookup"><span data-stu-id="b138e-170">Additionally, verification inspects code to determine whether the MSIL has been correctly generated, because incorrect MSIL can lead to a violation of the type safety rules.</span></span> <span data-ttu-id="b138e-171">Tür kullanımı uyumlu kod iyi tanımlanmış bir dizi doğrulama işlemi başarılı ve güvenli bir türe sahip code geçirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-171">The verification process passes a well-defined set of type-safe code, and it passes only code that is type safe.</span></span> <span data-ttu-id="b138e-172">Ancak, bazı tür kullanımı uyumlu kod doğrulama doğrulama işlemi bazı sınırlamaları nedeniyle geçebilir değildir ve bazı dillerde tasarım gereği, doğrulanabilir şekilde tür kullanımı uyumlu kod üretmez.</span><span class="sxs-lookup"><span data-stu-id="b138e-172">However, some type-safe code might not pass verification because of some limitations of the verification process, and some languages, by design, do not produce verifiably type-safe code.</span></span> <span data-ttu-id="b138e-173">Tür kullanımı uyumlu kod güvenlik ilkesi tarafından gerekli ancak kod doğrulama değerine geçmiyor kodu çalıştırdığınızda özel durum oluşur.</span><span class="sxs-lookup"><span data-stu-id="b138e-173">If type-safe code is required by the security policy but the code does not pass verification, an exception is thrown when the code is run.</span></span>  
  
 [<span data-ttu-id="b138e-174">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b138e-174">Back to top</span></span>](#introduction)  
  
<a name="running_code"></a>   
## <a name="running-code"></a><span data-ttu-id="b138e-175">Çalışan kod</span><span class="sxs-lookup"><span data-stu-id="b138e-175">Running Code</span></span>  
 <span data-ttu-id="b138e-176">Ortak dil çalışma zamanı yürütme sırasında yönetilen yürütme gerçekleşmesi için hizmetleri altyapısı kullanılabilir sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-176">The common language runtime provides the infrastructure that enables managed execution to take place and services that can be used during execution.</span></span> <span data-ttu-id="b138e-177">Bir yöntem çalıştırmadan önce işlemci özgü kod derlenmiş gerekir.</span><span class="sxs-lookup"><span data-stu-id="b138e-177">Before a method can be run, it must be compiled to processor-specific code.</span></span> <span data-ttu-id="b138e-178">Bu olduğunda ilk kez çağrılır ve ardından çalıştırın MSIL oluşturulan her JIT derlenmiş yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="b138e-178">Each method for which MSIL has been generated is JIT-compiled when it is called for the first time, and then run.</span></span> <span data-ttu-id="b138e-179">Yöntemi, İleri çalıştırıldığında mevcut JIT derlenmiş yerel kod çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="b138e-179">The next time the method is run, the existing JIT-compiled native code is run.</span></span> <span data-ttu-id="b138e-180">JIT derleme ve kodu çalıştırma işlemi, yürütme işlemi tamamlanana kadar yinelenir.</span><span class="sxs-lookup"><span data-stu-id="b138e-180">The process of JIT-compiling and then running the code is repeated until execution is complete.</span></span>  
  
 <span data-ttu-id="b138e-181">Yürütme sırasında yönetilen kod atık toplama, güvenlik, yönetilmeyen kod, çapraz dil hata ayıklama desteği ve Gelişmiş dağıtıma ve sürüm oluşturma desteği ile birlikte çalışabilirlik gibi hizmetleri alır.</span><span class="sxs-lookup"><span data-stu-id="b138e-181">During execution, managed code receives services such as garbage collection, security, interoperability with unmanaged code, cross-language debugging support, and enhanced deployment and versioning support.</span></span>  
  
 <span data-ttu-id="b138e-182">Microsoft [!INCLUDE[winxp](../../includes/winxp-md.md)] ve [!INCLUDE[windowsver](../../includes/windowsver-md.md)], işletim sistemi yükleyicisi biraz COFF üstbilgisinde inceleyerek yönetilen modülleri için denetler.</span><span class="sxs-lookup"><span data-stu-id="b138e-182">In Microsoft [!INCLUDE[winxp](../../includes/winxp-md.md)] and [!INCLUDE[windowsver](../../includes/windowsver-md.md)], the operating system loader checks for managed modules by examining a bit in the COFF header.</span></span> <span data-ttu-id="b138e-183">Ayarlanan bit yönetilen bir modül gösterir.</span><span class="sxs-lookup"><span data-stu-id="b138e-183">The bit being set denotes a managed module.</span></span> <span data-ttu-id="b138e-184">Yükleyici yönetilen modüller algılarsa, mscoree.dll, yükler ve `_CorValidateImage` ve `_CorImageUnloading` yönetilen modül görüntüleri yüklendiğinde ve kaldırıldığında olduğunda yükleyicisi bildirin.</span><span class="sxs-lookup"><span data-stu-id="b138e-184">If the loader detects managed modules, it loads mscoree.dll, and `_CorValidateImage` and `_CorImageUnloading` notify the loader when the managed module images are loaded and unloaded.</span></span> <span data-ttu-id="b138e-185">`_CorValidateImage`Aşağıdaki eylemleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="b138e-185">`_CorValidateImage` performs the following actions:</span></span>  
  
1.  <span data-ttu-id="b138e-186">Kod geçerli yönetilen kod olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="b138e-186">Ensures that the code is valid managed code.</span></span>  
  
2.  <span data-ttu-id="b138e-187">Çalışma zamanında bir giriş noktası için giriş noktası görüntüdeki değiştirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-187">Changes the entry point in the image to an entry point in the runtime.</span></span>  
  
 <span data-ttu-id="b138e-188">64-bit Windows `_CorValidateImage` PE32 + biçimine PE32 dönüştürerek bellekte görüntüsü değiştirir.</span><span class="sxs-lookup"><span data-stu-id="b138e-188">On 64-bit Windows, `_CorValidateImage` modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
 [<span data-ttu-id="b138e-189">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b138e-189">Back to top</span></span>](#introduction)  
  
## <a name="see-also"></a><span data-ttu-id="b138e-190">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b138e-190">See Also</span></span>  
 [<span data-ttu-id="b138e-191">Genel bakış</span><span class="sxs-lookup"><span data-stu-id="b138e-191">Overview</span></span>](../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="b138e-192">Dil bağımsızlığı ve dilden bağımsız bileşenler</span><span class="sxs-lookup"><span data-stu-id="b138e-192">Language Independence and Language-Independent Components</span></span>](../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="b138e-193">Meta veriler ve kendiliğinden açıklayıcı bileşenler</span><span class="sxs-lookup"><span data-stu-id="b138e-193">Metadata and Self-Describing Components</span></span>](../../docs/standard/metadata-and-self-describing-components.md)  
 [<span data-ttu-id="b138e-194">Ilasm.exe (IL derleyici)</span><span class="sxs-lookup"><span data-stu-id="b138e-194">Ilasm.exe (IL Assembler)</span></span>](../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 [<span data-ttu-id="b138e-195">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="b138e-195">Security</span></span>](../../docs/standard/security/index.md)  
 [<span data-ttu-id="b138e-196">Yönetilmeyen kod ile birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="b138e-196">Interoperating with Unmanaged Code</span></span>](../../docs/framework/interop/index.md)  
 [<span data-ttu-id="b138e-197">Dağıtım</span><span class="sxs-lookup"><span data-stu-id="b138e-197">Deployment</span></span>](../../docs/framework/deployment/net-framework-applications.md)  
 [<span data-ttu-id="b138e-198">Ortak dil çalışma zamanı derlemeleri</span><span class="sxs-lookup"><span data-stu-id="b138e-198">Assemblies in the Common Language Runtime</span></span>](../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="b138e-199">Uygulama etki alanları</span><span class="sxs-lookup"><span data-stu-id="b138e-199">Application Domains</span></span>](../../docs/framework/app-domains/application-domains.md)