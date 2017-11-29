---
title: "Geri Çağırma İşlevleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84c3f13317f771ba81af0fc7368124c59f8a1a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="callback-functions"></a><span data-ttu-id="507f2-102">Geri Çağırma İşlevleri</span><span class="sxs-lookup"><span data-stu-id="507f2-102">Callback Functions</span></span>
<span data-ttu-id="507f2-103">Bir geri çağırma işlevini bir görevi tamamlamak yönetilmeyen DLL işlev yardımcı olan yönetilen bir uygulama içinde kodudur.</span><span class="sxs-lookup"><span data-stu-id="507f2-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="507f2-104">Bir geri çağırma işlevi çağrıları dolaylı bir DLL işlevi aracılığıyla yönetilen bir uygulama geçirmek ve yönetilen uygulama geri.</span><span class="sxs-lookup"><span data-stu-id="507f2-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="507f2-105">Bazı platformuyla adlı birçok DLL işlevleri çağırma düzgün çalışması için yönetilen kodda bir geri çağırma işlevini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="507f2-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="507f2-106">Yönetilen koddan çoğu DLL işlevleri çağırmak için işlevinin yönetilen tanımı oluşturun ve onu çağırın.</span><span class="sxs-lookup"><span data-stu-id="507f2-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="507f2-107">Basit bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="507f2-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="507f2-108">Bir geri çağırma işlevini gerektiren DLL işlevini kullanarak, bazı ek adımlar vardır.</span><span class="sxs-lookup"><span data-stu-id="507f2-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="507f2-109">İlk olarak, işlev belgelerine bakarak işlevi bir geri çağırma gerekip gerekmediğini belirlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="507f2-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="507f2-110">Ardından, geri çağırma işlevi, yönetilen bir uygulamada oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="507f2-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="507f2-111">Son olarak, bir işaretçi geri çağırma işlevi bağımsız değişken olarak geçirme DLL işlevini çağırın.</span><span class="sxs-lookup"><span data-stu-id="507f2-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span> <span data-ttu-id="507f2-112">Aşağıdaki çizim, bu adımları özetlemektedir.</span><span class="sxs-lookup"><span data-stu-id="507f2-112">The following illustration summarizes these steps.</span></span>  
  
 <span data-ttu-id="507f2-113">![Platform çağırma geri çağırma](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span><span class="sxs-lookup"><span data-stu-id="507f2-113">![Platform invoke callback](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span></span>  
<span data-ttu-id="507f2-114">Geri çağırma işlevini ve uygulama</span><span class="sxs-lookup"><span data-stu-id="507f2-114">Callback function and implementation</span></span>  
  
 <span data-ttu-id="507f2-115">Geri arama işlevleri, bir görev art arda gerçekleştirilen durumlarda kullanmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="507f2-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="507f2-116">Başka bir yaygın kullanım numaralandırma işlevleri ile olduğu gibi **EnumFontFamilies**, **EnumPrinters**, ve **EnumWindows** Win32 API içinde.</span><span class="sxs-lookup"><span data-stu-id="507f2-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Win32 API.</span></span> <span data-ttu-id="507f2-117">**EnumWindows** işlevi numaralandırır her penceresinde bir görevi gerçekleştirmek için geri çağırma işlevini çağırarak bilgisayarınızdaki tüm var olan windows aracılığıyla.</span><span class="sxs-lookup"><span data-stu-id="507f2-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="507f2-118">Yönergeler ve bir örnek için bkz: [nasıl yapılır: uygulama geri arama işlevleri](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="507f2-118">For instructions and an example, see [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507f2-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="507f2-119">See Also</span></span>  
 [<span data-ttu-id="507f2-120">Nasıl yapılır: geri çağırma işlevlerini uygulama</span><span class="sxs-lookup"><span data-stu-id="507f2-120">How to: Implement Callback Functions</span></span>](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [<span data-ttu-id="507f2-121">DLL işlevini çağırma</span><span class="sxs-lookup"><span data-stu-id="507f2-121">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)