---
title: 'Nasıl Yapılır: -Özel olay erişimcilerini uygulama C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: aaf58307cb4e33a1caa7b1ef8584fbb33decea3f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240079"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="9799a-102">Nasıl Yapılır: Özel olay erişimcilerini uygulama (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="9799a-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="9799a-103">Özel bir tür içinde bildirildiği için yalnızca gelen sınıfın içinden çağrılabilen çok noktaya yayın temsilci bir olaydır.</span><span class="sxs-lookup"><span data-stu-id="9799a-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="9799a-104">İstemci kodu, olay başlatıldığında, çağrılması gereken bir yönteme başvuru sağlayarak olaya abone olur.</span><span class="sxs-lookup"><span data-stu-id="9799a-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="9799a-105">Bu yöntemler, olay erişimcileri adlı dışında özellik erişimcileri, benzer olay erişimcileri aracılığıyla temsilcinin çağırma listesine eklenir `add` ve `remove`.</span><span class="sxs-lookup"><span data-stu-id="9799a-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="9799a-106">Çoğu durumda, özel olay erişimcilerini sağlamanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="9799a-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="9799a-107">Derleyici, kodunuzda hiçbir özel olay erişimcilerini sağlandığında, bunları otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="9799a-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="9799a-108">Ancak, bazı durumlarda özel davranış sağlamanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="9799a-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="9799a-109">Böyle bir durumda konu başlığında gösterilen [nasıl yapılır:  Arabirim olaylarını uygulama](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="9799a-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9799a-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="9799a-110">Example</span></span>  
 <span data-ttu-id="9799a-111">Aşağıdaki örnek, özel uygulamak gösterilmektedir ekleme ve kaldırma olay erişimcileri.</span><span class="sxs-lookup"><span data-stu-id="9799a-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="9799a-112">Erişimciler içinde herhangi bir kod birbirinin yerine kullanabilir, ancak olayı ekleyin veya yeni bir olay işleyicisi yöntemi'ı kaldırmadan önce kilit öneririz.</span><span class="sxs-lookup"><span data-stu-id="9799a-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="9799a-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9799a-113">See Also</span></span>

- [<span data-ttu-id="9799a-114">Olaylar</span><span class="sxs-lookup"><span data-stu-id="9799a-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="9799a-115">event</span><span class="sxs-lookup"><span data-stu-id="9799a-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)