---
title: 'Nasıl Yapılır: Store olay örnekleri için-Sözlük kullanma C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245148"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="bb6e8-102">Nasıl Yapılır: Store olay örnekleri için Sözlük kullanma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="bb6e8-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="bb6e8-103">Bir kullanımı `accessor-declarations` her olay için bir alan ayırma, ancak bunun yerine olay örneklerini depolamak için bir sözlük kullanarak çok sayıda olay kullanıma sunulmasıdır.</span><span class="sxs-lookup"><span data-stu-id="bb6e8-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="bb6e8-104">Bu yalnızca çok sayıda olay olması, ancak çoğu olayların uygulanmadı beklediğiniz yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="bb6e8-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb6e8-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="bb6e8-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bb6e8-106">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bb6e8-106">See Also</span></span>

- [<span data-ttu-id="bb6e8-107">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="bb6e8-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bb6e8-108">Olaylar</span><span class="sxs-lookup"><span data-stu-id="bb6e8-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="bb6e8-109">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="bb6e8-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
