---
title: 'Nasıl Yapılır: Bir dosyanın derleme olup olmadığını belirleme (C#)'
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: 0cf9258aa4a5a1a633ee0bb04808d384de8f48d0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125541"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Nasıl Yapılır: Bir dosyanın derleme olup olmadığını belirleme (C#)
Yönetilen ve bir derleme girişi meta verilerini içeren ve yalnızca, bir dosyanın derleme olup. Derlemeler ve meta veriler hakkında daha fazla bilgi için Ek Yardım konusuna [derleme bildirimi](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>El ile bir dosyanın derleme olup olmadığını belirleme  
  
1.  Başlangıç [Ildasm.exe (IL ayrıştırıcı)](../../../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2.  Test etmek istediğiniz dosya yükleyin.  
  
3.  Varsa **ILDASM** raporlar dosya taşınabilir çalıştırılabilir (PE) dosyası değil ve ardından bir derleme değil. Daha fazla bilgi için Ek Yardım konusuna [nasıl yapılır: Bütünleştirilmiş kod içeriklerini görüntüleme](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Program aracılığıyla bir dosyanın derleme olup olmadığını belirleme  
  
1.  Çağrı <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> test dosyasının adını ve tam dosya yolunu geçirerek yöntemi.  
  
2.  Varsa bir <xref:System.BadImageFormatException> özel durum oluştu, dosyanın bir derleme değil.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir DLL derleme olup olmadığını görmek için sınar.  
  
```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> Yöntemi test dosyasını yükler ve bilgileri okunduktan sonra bırakır.  
  
## <a name="see-also"></a>Ayrıca Bkz.

- <xref:System.Reflection.AssemblyName>  
- [C# Programlama Kılavuzu](../../../../csharp/programming-guide/index.md)  
- [Derlemeler ve Genel Derleme Önbelleği (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
