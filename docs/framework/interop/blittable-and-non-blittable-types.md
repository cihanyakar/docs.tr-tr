---
title: Blok Halinde Kopyalanabilir ve Kopyalanamaz Türler
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b4c1d213c2ed87126fc5eb9995050e14f9214bd
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155346"
---
# <a name="blittable-and-non-blittable-types"></a>Blok Halinde Kopyalanabilir ve Kopyalanamaz Türler
Çoğu veri türleri, hem yönetilen hem de yönetilmeyen bellekte bir ortak gösterilmesi ve birlikte çalışma sıralayıcısı ile özel işlem gerektirmez. Bu tür adında *türlerse* arasında geçirildiğinde, dönüştürme gerektirmediği için yönetilen ve yönetilmeyen kod.  
  
 Platformdan iade yapıları çağırma çağrıları blok halinde kopyalanabilir türler olmalıdır. Platform çağırma dönüş türleri olarak kopyalanamaz yapıları desteklemez.  
  
 Aşağıdaki türlerini <xref:System> ad alanı blittable türleri şunlardır:  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 Aşağıdaki karmaşık türler, ayrıca blittable türleri şunlardır:  
  
-   Tamsayı dizisi gibi belirli bir türlerse tek boyutlu dizi. Ancak blittable türleri değişken bir dizi içeren bir tür kendisini değil blok halinde kopyalanabilir.  
  
-   Biçimlendirilmiş değer türleri yalnızca bir blok halinde kopyalanabilir türler (ve biçimlendirilmiş türleri olarak sıralanmış, sınıflar) bulunur. Biçimlendirilmiş değer türleri hakkında daha fazla bilgi için bkz: [değer türleri için varsayılan hazırlama](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100)).  
  
 Nesne başvuruları blittable değil. Bu blittable başlarına olan nesnelere yapılan başvuruların dizisi içerir. Örneğin, blittable bir yapısı tanımlayabilirsiniz, ancak bu yapıların yapılan başvuruların dizisi içeren bir blok halinde kopyalanabilir türü tanımlayamazsınız.  
  
 Bir iyileştirme blok halinde kopyalanabilir türler yalnızca blittable üyeleri içeren sınıflar ve dizilerdir [sabitlenmiş](../../../docs/framework/interop/copying-and-pinning.md) yerine sıralama sırasında kopyalanır. Bu türler, çağıran ve çağrılan aynı grupta olduğunda In/Out parametreleri sıralanması görünebilir. Ancak, bu tür parametreleri olduğu gibi gerçekten sıralanmış ve uygulamalısınız <xref:System.Runtime.InteropServices.InAttribute> ve <xref:System.Runtime.InteropServices.OutAttribute> bağımsız değişkeni olarak bir ın/Out parametresi hazırlamak istiyorsanız öznitelikleri.  
  
 Bazı yönetilen veri türleri, yönetilmeyen bir ortamda farklı bir gösterimi gerektirir. Bu blittable olmayan veri türlerini sıralanabilir bir biçime dönüştürülmelidir. Örneğin, çünkü bunlar sıralanabilir önce dize nesnelerini dönüştürülmelidir yönetilen dizeler kopyalanamaz türler ' dir.  
  
 Kopyalanamaz türleri aşağıdaki tabloda <xref:System> ad alanı. [Temsilciler](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100)), statik bir yöntem veya bir sınıf örneğine başvuruda bulunan veri yapılarını hangilerinin ayrıca kopyalanamaz.  
  
|Örnekteki türü|Açıklama|  
|-------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Bir C tarzı diziye dönüştürür veya `SAFEARRAY`.|  
|[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))|1, 2 veya 4 baytlık değeriyle dönüştürür `true` 1 veya -1 olarak.|  
|[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))|Bir Unicode veya ANSI karakterine dönüştürür.|  
|[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))|Sınıf arabirimine dönüştürür.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Bir değişken veya bir arabirim dönüştürür.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Bir C tarzı diziye dönüştürür veya `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|BSTR veya null başvuru sonlandıran bir dizeye dönüştürür.|  
|[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))|Sabit bellek düzeni ile bir yapıya dönüştürür.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Bir C tarzı diziye dönüştürür veya `SAFEARRAY`.|  
  
 Sınıf ve nesne türleri yalnızca COM birlikte çalışma tarafından desteklenir. Karşılık gelen türler için [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#ve C++ bkz [sınıf kitaplığına genel bakış](../../../docs/standard/class-library-overview.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Varsayılan Hazırlama Davranışı](../../../docs/framework/interop/default-marshaling-behavior.md)
