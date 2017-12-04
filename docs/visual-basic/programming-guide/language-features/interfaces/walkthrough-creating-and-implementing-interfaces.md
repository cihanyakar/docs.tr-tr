---
title: "Oluşturma ve uygulama arabirimler (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="dc702-102">İzlenecek yol: Arabirimleri Oluşturma ve Uygulama (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc702-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="dc702-103">Arabirimleri özellikleri, yöntemleri ve olay özelliklerini açıklayan, ancak uygulama ayrıntılarını yapıları veya sınıfları kadar bırakın.</span><span class="sxs-lookup"><span data-stu-id="dc702-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="dc702-104">Bu kılavuz, bildirme ve bir arabirim gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="dc702-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc702-105">Bu kılavuz, bir kullanıcı arabirimi oluşturma hakkında bilgi sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="dc702-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="dc702-106">Bir arabirimi tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="dc702-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="dc702-107">Yeni bir [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows uygulama projesi.</span><span class="sxs-lookup"><span data-stu-id="dc702-107">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="dc702-108">Yeni bir modül projeye tıklayarak ekleyin **Modül Ekle** üzerinde **proje** menüsü.</span><span class="sxs-lookup"><span data-stu-id="dc702-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="dc702-109">Yeni modül adı `Module1.vb` tıklatıp **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="dc702-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="dc702-110">Yeni modül kodu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dc702-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="dc702-111">Adlı bir arabirim tanımlayın `TestInterface` içinde `Module1` yazarak `Interface TestInterface` arasında `Module` ve `End Module` deyimleri ve sonra ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="dc702-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="dc702-112">**Kod düzenleyicisinde** girintileri `Interface` anahtar sözcüğü ve ekleyen bir `End Interface` kod bloğu oluşturmak için ifade.</span><span class="sxs-lookup"><span data-stu-id="dc702-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="dc702-113">Aşağıdaki kod arasında koyarak özelliği, yöntemi ve olay arabirimi tanımlamak `Interface` ve `End Interface` deyimleri:</span><span class="sxs-lookup"><span data-stu-id="dc702-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a><span data-ttu-id="dc702-114">Uygulama</span><span class="sxs-lookup"><span data-stu-id="dc702-114">Implementation</span></span>  
 <span data-ttu-id="dc702-115">Arabirim üyeleri bildirmek için kullanılan sözdizimi sınıf üyesi bildirmek için kullanılan sözdiziminden, farklı olduğunu fark edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dc702-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="dc702-116">Bu farkı arabirimler uygulama kodu içeremez olgu yansıtır.</span><span class="sxs-lookup"><span data-stu-id="dc702-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="dc702-117">Arabirim uygulamak için</span><span class="sxs-lookup"><span data-stu-id="dc702-117">To implement the interface</span></span>  
  
1.  <span data-ttu-id="dc702-118">Adlı bir sınıf ekleyin `ImplementationClass` şu deyimi ekleyerek `Module1`, sonra `End Interface` deyimi önce `End Module` deyimi ve sonra ENTER tuşuna basın:</span><span class="sxs-lookup"><span data-stu-id="dc702-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     <span data-ttu-id="dc702-119">Tümleşik geliştirme ortamında çalışıyorsanız **Kod Düzenleyicisi** eşleşen bir sağlayan `End Class` deyimi ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="dc702-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="dc702-120">Aşağıdakileri ekleyin `Implements` ifadesine `ImplementationClass`, hangi arabirimi sınıfı adları uygular:</span><span class="sxs-lookup"><span data-stu-id="dc702-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     <span data-ttu-id="dc702-121">Bir sınıf veya yapı, üstündeki diğer öğelerden ayrı olarak listelenen `Implements` deyimi gösteren sınıf veya yapı bir arabirimi uygular.</span><span class="sxs-lookup"><span data-stu-id="dc702-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="dc702-122">Tümleşik geliştirme ortamında çalışıyorsanız **Kod düzenleyicisinde** gerektirdiği sınıf üyeleri uygulayan `TestInterface` zaman ENTER tuşuna basın ve sonraki adıma atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dc702-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="dc702-123">Tümleşik geliştirme ortamında çalışmıyorsanız arabirimi tüm üyeleri uygulamalıdır `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="dc702-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="dc702-124">Aşağıdaki kodu ekleyin `ImplementationClass` uygulamak için `Event1`, `Method1`, ve `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="dc702-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     <span data-ttu-id="dc702-125">`Implements` Deyimi adları uygulanan arabirim üyesini ve arabirim.</span><span class="sxs-lookup"><span data-stu-id="dc702-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="dc702-126">Tanımını tamamlamak `Prop1` özellik değeri depolanan sınıfı için özel bir alan ekleyerek:</span><span class="sxs-lookup"><span data-stu-id="dc702-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     <span data-ttu-id="dc702-127">Değeri döndürmesi `pval` özelliğinden get erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="dc702-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     <span data-ttu-id="dc702-128">Değerini `pval` özelliğinde ayarlama erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="dc702-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  <span data-ttu-id="dc702-129">Tanımını tamamlamak `Method1` aşağıdaki kodu ekleyerek düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="dc702-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="dc702-130">Arabirim uygulanmasını test etmek için</span><span class="sxs-lookup"><span data-stu-id="dc702-130">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="dc702-131">Projenizde başlangıç formu sağ **Çözüm Gezgini**, tıklatıp **görünümü kodu**.</span><span class="sxs-lookup"><span data-stu-id="dc702-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="dc702-132">Düzenleyici başlangıç formunuz için sınıf görüntüler.</span><span class="sxs-lookup"><span data-stu-id="dc702-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="dc702-133">Varsayılan olarak, başlangıç formu adlı `Form1`.</span><span class="sxs-lookup"><span data-stu-id="dc702-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="dc702-134">Aşağıdakileri ekleyin `testInstance` alanı `Form1` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="dc702-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     <span data-ttu-id="dc702-135">Bildirme tarafından `testInstance` olarak `WithEvents`, `Form1` sınıfı olaylarına işleyebilir.</span><span class="sxs-lookup"><span data-stu-id="dc702-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="dc702-136">Aşağıdaki olay işleyicisi ekleme `Form1` tarafından başlatılan olayları işlemek için sınıf `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="dc702-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  <span data-ttu-id="dc702-137">Adlı bir alt yordama ekleme `Test` için `Form1` sınıfı uygulama sınıfı test etmek için:</span><span class="sxs-lookup"><span data-stu-id="dc702-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     <span data-ttu-id="dc702-138">`Test` Yordam uygulayan sınıf örneği oluşturur `MyInterface`, bu örneğe atar `testInstance` alan, bir özelliği ayarlar ve bir yöntem arabirimi aracılığıyla çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="dc702-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="dc702-139">Çağırmak için kodu ekleyin `Test` yordamdan `Form1 Load` başlangıç formu yordam:</span><span class="sxs-lookup"><span data-stu-id="dc702-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  <span data-ttu-id="dc702-140">Çalıştırma `Test` F5'e basarak yordamı.</span><span class="sxs-lookup"><span data-stu-id="dc702-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="dc702-141">İleti "Prop1 9 ayarlandı" görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dc702-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="dc702-142">"X parametresi Method1 için 5." iletisi Tamam ' ı sonra görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dc702-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="dc702-143">Tamam'ı tıklatın ve "olay olay işleyicisi yakalanan" iletisi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dc702-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc702-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dc702-144">See Also</span></span>  
 [<span data-ttu-id="dc702-145">Implements deyimi</span><span class="sxs-lookup"><span data-stu-id="dc702-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="dc702-146">Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="dc702-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="dc702-147">Interface deyimi</span><span class="sxs-lookup"><span data-stu-id="dc702-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="dc702-148">Event deyimi</span><span class="sxs-lookup"><span data-stu-id="dc702-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)