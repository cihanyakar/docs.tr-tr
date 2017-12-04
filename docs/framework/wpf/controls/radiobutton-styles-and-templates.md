---
title: "RadioButton Stilleri ve Şablonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 384a587fe01fb69ff5d377f2aa34d03ff110880d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="0f642-102">RadioButton Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="0f642-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="0f642-103">Stilleri ve şablonları için bu konuda açıklanmaktadır <xref:System.Windows.Controls.RadioButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="0f642-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="0f642-104">Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetimi benzersiz bir görünüm vermek için.</span><span class="sxs-lookup"><span data-stu-id="0f642-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0f642-105">Daha fazla bilgi için bkz: [ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0f642-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="0f642-106">RadioButton bölümleri</span><span class="sxs-lookup"><span data-stu-id="0f642-106">RadioButton Parts</span></span>  
 <span data-ttu-id="0f642-107"><xref:System.Windows.Controls.RadioButton> Denetim adlandırılmış tüm bölümler sahip değil.</span><span class="sxs-lookup"><span data-stu-id="0f642-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="0f642-108">RadioButton durumları</span><span class="sxs-lookup"><span data-stu-id="0f642-108">RadioButton States</span></span>  
 <span data-ttu-id="0f642-109">Aşağıdaki tablo için görsel durumlarını listeler <xref:System.Windows.Controls.RadioButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="0f642-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="0f642-110">VisualState adı</span><span class="sxs-lookup"><span data-stu-id="0f642-110">VisualState Name</span></span>|<span data-ttu-id="0f642-111">VisualStateGroup adı</span><span class="sxs-lookup"><span data-stu-id="0f642-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0f642-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0f642-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0f642-113">Normal</span><span class="sxs-lookup"><span data-stu-id="0f642-113">Normal</span></span>|<span data-ttu-id="0f642-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f642-114">CommonStates</span></span>|<span data-ttu-id="0f642-115">Varsayılan durumu.</span><span class="sxs-lookup"><span data-stu-id="0f642-115">The default state.</span></span>|  
|<span data-ttu-id="0f642-116">Fare üzerinde</span><span class="sxs-lookup"><span data-stu-id="0f642-116">MouseOver</span></span>|<span data-ttu-id="0f642-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f642-117">CommonStates</span></span>|<span data-ttu-id="0f642-118">Fare işaretçisini üzerinde denetim konumlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="0f642-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0f642-119">Basılı</span><span class="sxs-lookup"><span data-stu-id="0f642-119">Pressed</span></span>|<span data-ttu-id="0f642-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f642-120">CommonStates</span></span>|<span data-ttu-id="0f642-121">Denetim basıldığında.</span><span class="sxs-lookup"><span data-stu-id="0f642-121">The control is pressed.</span></span>|  
|<span data-ttu-id="0f642-122">Devre dışı</span><span class="sxs-lookup"><span data-stu-id="0f642-122">Disabled</span></span>|<span data-ttu-id="0f642-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f642-123">CommonStates</span></span>|<span data-ttu-id="0f642-124">Denetim devre dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="0f642-124">The control is disabled.</span></span>|  
|<span data-ttu-id="0f642-125">Odaklanmış</span><span class="sxs-lookup"><span data-stu-id="0f642-125">Focused</span></span>|<span data-ttu-id="0f642-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0f642-126">FocusStates</span></span>|<span data-ttu-id="0f642-127">Denetimi odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="0f642-127">The control has focus.</span></span>|  
|<span data-ttu-id="0f642-128">Odaksız</span><span class="sxs-lookup"><span data-stu-id="0f642-128">Unfocused</span></span>|<span data-ttu-id="0f642-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0f642-129">FocusStates</span></span>|<span data-ttu-id="0f642-130">Denetim odağı yok.</span><span class="sxs-lookup"><span data-stu-id="0f642-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="0f642-131">İşaretli</span><span class="sxs-lookup"><span data-stu-id="0f642-131">Checked</span></span>|<span data-ttu-id="0f642-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0f642-132">CheckStates</span></span>|<span data-ttu-id="0f642-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>olan `true`.</span><span class="sxs-lookup"><span data-stu-id="0f642-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="0f642-134">İşaretli</span><span class="sxs-lookup"><span data-stu-id="0f642-134">Unchecked</span></span>|<span data-ttu-id="0f642-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0f642-135">CheckStates</span></span>|<span data-ttu-id="0f642-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>olan `false`.</span><span class="sxs-lookup"><span data-stu-id="0f642-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="0f642-137">Belirsiz</span><span class="sxs-lookup"><span data-stu-id="0f642-137">Indeterminate</span></span>|<span data-ttu-id="0f642-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0f642-138">CheckStates</span></span>|<span data-ttu-id="0f642-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>olan `true`, ve <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> olan `null`.</span><span class="sxs-lookup"><span data-stu-id="0f642-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="0f642-140">Geçerli</span><span class="sxs-lookup"><span data-stu-id="0f642-140">Valid</span></span>|<span data-ttu-id="0f642-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f642-141">ValidationStates</span></span>|<span data-ttu-id="0f642-142">Denetim kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> iliştirilmiş özelliği `false`.</span><span class="sxs-lookup"><span data-stu-id="0f642-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0f642-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0f642-143">InvalidFocused</span></span>|<span data-ttu-id="0f642-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f642-144">ValidationStates</span></span>|<span data-ttu-id="0f642-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="0f642-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0f642-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0f642-146">InvalidUnfocused</span></span>|<span data-ttu-id="0f642-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f642-147">ValidationStates</span></span>|<span data-ttu-id="0f642-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip değil.</span><span class="sxs-lookup"><span data-stu-id="0f642-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="0f642-149">RadioButton ControlTemplate Örneği</span><span class="sxs-lookup"><span data-stu-id="0f642-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="0f642-150">Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.RadioButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="0f642-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="0f642-151">Önceki örnekte, bir veya daha fazla aşağıdaki kaynakları kullanır.</span><span class="sxs-lookup"><span data-stu-id="0f642-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0f642-152">Tam bir örnek için bkz: [ControlTemplates örneği ile stil oluşturma](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="0f642-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f642-153">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0f642-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="0f642-154">Denetim stilleri ve şablonları</span><span class="sxs-lookup"><span data-stu-id="0f642-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="0f642-155">Denetim özelleştirme</span><span class="sxs-lookup"><span data-stu-id="0f642-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="0f642-156">Stil ve şablon oluşturma</span><span class="sxs-lookup"><span data-stu-id="0f642-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="0f642-157">ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme</span><span class="sxs-lookup"><span data-stu-id="0f642-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)