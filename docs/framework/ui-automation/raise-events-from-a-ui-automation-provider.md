---
title: "UI Otomasyon Sağlayıcıda Olay Tetikleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 323c748a8d40158e51a776e4493975c55b117885
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="d7d80-102">UI Otomasyon Sağlayıcıda Olay Tetikleme</span><span class="sxs-lookup"><span data-stu-id="d7d80-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="d7d80-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="d7d80-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d7d80-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d7d80-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d7d80-105">Bu konu, bir olayı UI Otomasyonu sağlayıcısından gösteren kod örneği içerir.</span><span class="sxs-lookup"><span data-stu-id="d7d80-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d80-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="d7d80-106">Example</span></span>  
 <span data-ttu-id="d7d80-107">Aşağıdaki örnekte, bir [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] olayı özel düğme denetimi uygulamasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="d7d80-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="d7d80-108">Uygulama düğmesini tıklatın benzetimini yapmak için UI otomasyon istemci uygulaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="d7d80-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="d7d80-109">Örnek denetler gereksiz işleme engel olmak için <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> olayları oluşturup oluşturmadığını görmek için.</span><span class="sxs-lookup"><span data-stu-id="d7d80-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="d7d80-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d7d80-110">See Also</span></span>  
 [<span data-ttu-id="d7d80-111">UI Otomasyon sağlayıcılara genel bakış</span><span class="sxs-lookup"><span data-stu-id="d7d80-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)