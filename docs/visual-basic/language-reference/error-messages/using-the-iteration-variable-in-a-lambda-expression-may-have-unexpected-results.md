---
title: "Lambda ifadesinde yineleme değişkeni kullanılması beklenmeyen sonuçlara neden olabilir"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords: BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb707cd4e09a149d21b70bb0f998a40c7ed58b49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="f945c-102">Lambda ifadesinde yineleme değişkeni kullanılması beklenmeyen sonuçlara neden olabilir</span><span class="sxs-lookup"><span data-stu-id="f945c-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="f945c-103">Lambda ifadesinde yineleme değişkeni kullanılması olabilir beklenmeyen sonuçlar.</span><span class="sxs-lookup"><span data-stu-id="f945c-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="f945c-104">Bunun yerine, döngü içinde yerel bir değişken oluşturun ve yineleme değişkenin değerini atayın.</span><span class="sxs-lookup"><span data-stu-id="f945c-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="f945c-105">Döngünün içinde bildirilen bir lambda ifadesinde bir döngü yineleme değişkeni kullandığınızda, bu uyarı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="f945c-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="f945c-106">Örneğin, aşağıdaki örnekte, görüntülenecek uyarı neden olur.</span><span class="sxs-lookup"><span data-stu-id="f945c-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="f945c-107">Aşağıdaki örnek, ortaya çıkabilecek beklenmeyen sonuçları gösterir.</span><span class="sxs-lookup"><span data-stu-id="f945c-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f945c-108">`For` Döngü oluşturuyor döngü yineleme değişkenin değerini döndürür, her biri bir dizi lambda ifadeleri `i`.</span><span class="sxs-lookup"><span data-stu-id="f945c-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="f945c-109">Ne zaman lambda ifadeleri değerlendirilir içinde `For Each` döngüsü 0, 1, 2, 3 ve 4 görüntülenen, art arda değerlerini görmeyi beklediğiniz `i` içinde `For` döngü.</span><span class="sxs-lookup"><span data-stu-id="f945c-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="f945c-110">Bunun yerine, son değerini görmek `i` beş kez görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="f945c-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="f945c-111">Varsayılan olarak, bu iletiyi bir uyarıdır.</span><span class="sxs-lookup"><span data-stu-id="f945c-111">By default, this message is a warning.</span></span> <span data-ttu-id="f945c-112">Uyarıları gizleme veya uyarıları hata olarak davranma hakkında daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f945c-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f945c-113">**Hata Kimliği:** BC42324</span><span class="sxs-lookup"><span data-stu-id="f945c-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f945c-114">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="f945c-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f945c-115">Yineleme değişkeninin değeri yerel bir değişkene atayın ve yerel değişken lambda ifadesinde kullanın.</span><span class="sxs-lookup"><span data-stu-id="f945c-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="f945c-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f945c-116">See Also</span></span>  
 [<span data-ttu-id="f945c-117">Lambda ifadeleri</span><span class="sxs-lookup"><span data-stu-id="f945c-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)