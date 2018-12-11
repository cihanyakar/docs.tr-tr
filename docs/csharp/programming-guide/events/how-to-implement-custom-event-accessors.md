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
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Nasıl Yapılır: Özel olay erişimcilerini uygulama (C# Programlama Kılavuzu)
Özel bir tür içinde bildirildiği için yalnızca gelen sınıfın içinden çağrılabilen çok noktaya yayın temsilci bir olaydır. İstemci kodu, olay başlatıldığında, çağrılması gereken bir yönteme başvuru sağlayarak olaya abone olur. Bu yöntemler, olay erişimcileri adlı dışında özellik erişimcileri, benzer olay erişimcileri aracılığıyla temsilcinin çağırma listesine eklenir `add` ve `remove`. Çoğu durumda, özel olay erişimcilerini sağlamanız gerekmez. Derleyici, kodunuzda hiçbir özel olay erişimcilerini sağlandığında, bunları otomatik olarak eklenir. Ancak, bazı durumlarda özel davranış sağlamanız gerekebilir. Böyle bir durumda konu başlığında gösterilen [nasıl yapılır:  Arabirim olaylarını uygulama](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, özel uygulamak gösterilmektedir ekleme ve kaldırma olay erişimcileri. Erişimciler içinde herhangi bir kod birbirinin yerine kullanabilir, ancak olayı ekleyin veya yeni bir olay işleyicisi yöntemi'ı kaldırmadan önce kilit öneririz.  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [Olaylar](../../../csharp/programming-guide/events/index.md)  
- [event](../../../csharp/language-reference/keywords/event.md)