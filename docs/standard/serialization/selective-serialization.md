---
title: "Seçmeli seri hale getirme"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccf1c585a171f2842084c1fdce639e479ce5ca8d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="selective-serialization"></a><span data-ttu-id="78385-102">Seçmeli seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="78385-102">Selective serialization</span></span>
<span data-ttu-id="78385-103">Bir sınıf genellikle seri hale döndürmemelidir alanları içerir.</span><span class="sxs-lookup"><span data-stu-id="78385-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="78385-104">Örneğin, bir sınıf bir iş parçacığı kimliği bir üye değişkeni depolar varsayar.</span><span class="sxs-lookup"><span data-stu-id="78385-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="78385-105">Sınıf serisi, iş parçacığı kimliği depolanan sınıfı zaman sıralandığı managementpack artık çalışmıyor; Bu nedenle bu değer seri hale getirme doesn't make Sense.</span><span class="sxs-lookup"><span data-stu-id="78385-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="78385-106">Üye değişkenleri ile işaretlemeden tarafından seri hale gelen engelleyebilirsiniz [getirilmemiş](xref:System.NonSerializedAttribute) gibi özniteliği.</span><span class="sxs-lookup"><span data-stu-id="78385-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="78385-107">Mümkünse, güvenlik bakımından hassas verileri nonserializable içerebilecek bir nesne olun.</span><span class="sxs-lookup"><span data-stu-id="78385-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="78385-108">Nesne seri hale, Uygula `NonSerialized` özniteliği hassas verileri depolamak için belirli alanları.</span><span class="sxs-lookup"><span data-stu-id="78385-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="78385-109">Seri hale getirme bu alanların yok bıraksanız, depoladıkları veri seri hale getirmek için izne sahip herhangi bir kod sunulan unutmayın.</span><span class="sxs-lookup"><span data-stu-id="78385-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="78385-110">Güvenli serileştirme kodu yazma hakkında daha fazla bilgi için bkz: [güvenlik ve Serileştirme](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="78385-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="78385-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="78385-111">See also</span></span>  
 [<span data-ttu-id="78385-112">İkili seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="78385-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="78385-113">XML ve SOAP seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="78385-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="78385-114">Güvenlik ve Serileştirme</span><span class="sxs-lookup"><span data-stu-id="78385-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)