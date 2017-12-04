---
title: "Ek açıklamalara Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc4ef4473a200a424134a16d64655a5acf1488b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="annotations-overview"></a><span data-ttu-id="fb86c-102">Ek açıklamalara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="fb86c-102">Annotations Overview</span></span>
<span data-ttu-id="fb86c-103">Not yazma veya kağıt belge açıklamalarını biz neredeyse sorgulamadan kabul ederiz, bir tür bir sıradan etkinlik değil.</span><span class="sxs-lookup"><span data-stu-id="fb86c-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="fb86c-104">Bu notlar veya yorumlar "açıklamalardır" bilgilere bayrak ya da daha sonra başvurmak için ilgi vurgulamak için bir belgeye ekleriz.</span><span class="sxs-lookup"><span data-stu-id="fb86c-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="fb86c-105">Kolay ve sıradan Yazdırılan belgeleri Not yazma olmasına karşın, elektronik belgelere kişisel açıklamalar ekleme yeteneği genellikle hiç varsa çok sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="fb86c-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="fb86c-106">Bu konu ortak çeşitli ek açıklamalarını, özellikle Yapışkan Notlar ve vurgular, gözden geçirir ve gösterilmektedir nasıl [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] bu tür uygulamalar aracılığıyla ek açıklamalar kolaylaştıran [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] belge görüntüleme denetimleri.</span><span class="sxs-lookup"><span data-stu-id="fb86c-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] facilitates these types of annotations in applications through the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] document viewing controls.</span></span>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="fb86c-107">ek açıklamaları destekleyen belge görüntüleme denetimleri dahil <xref:System.Windows.Controls.FlowDocumentReader> ve <xref:System.Windows.Controls.FlowDocumentScrollViewer>, yanı sıra denetimleri türetilmiş <xref:System.Windows.Controls.Primitives.DocumentViewerBase> gibi <xref:System.Windows.Controls.DocumentViewer> ve <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span><span class="sxs-lookup"><span data-stu-id="fb86c-107"> document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  
  
  
<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a><span data-ttu-id="fb86c-108">Yapışkan Notlar</span><span class="sxs-lookup"><span data-stu-id="fb86c-108">Sticky Notes</span></span>  
 <span data-ttu-id="fb86c-109">Tipik bir Yapışkan Not küçük bir sonra "belgeye takıldı" renkli kağıt üzerine yazılan bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="fb86c-110">Dijital Yapışkan Not sağlamak benzer işlevselliği elektronik belgeleri, ancak birçok içerik türleri gibi eklemek için eklenen esnekliği yazılı metni, el yazısı notlar (örneğin, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "mürekkep" vuruşları), Web bağlantıları veya.</span><span class="sxs-lookup"><span data-stu-id="fb86c-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="fb86c-111">Aşağıda bazı örnekler vurgulama, metin yapışkan not ve mürekkep yapışkan not ek açıklamaları gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="fb86c-112">![Vurgu, metin ve mürekkep yapışkan ek açıklamaları unutmayın. ] (../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="fb86c-112">![Highlight, text and ink sticky note annotations.](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="fb86c-113">Aşağıdaki örnek, uygulamanızdaki ek açıklama desteğini etkinleştirmek için kullanabileceğiniz yöntemi gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a><span data-ttu-id="fb86c-114">Öne çıkan özellikleri</span><span class="sxs-lookup"><span data-stu-id="fb86c-114">Highlights</span></span>  
 <span data-ttu-id="fb86c-115">Kişiler, alt çizgi, vurgulama, tümcedeki sözcüklerin daire içine veya boşlukta çizim işaretleri veya gösterimler gibi bir kağıt belgeyi işaretlediğinizde ilgi öğelere dikkat çekmek için yaratıcı yöntemlerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="fb86c-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="fb86c-116">Ek açıklamalar vurgulayın [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] benzer bir özellik olarak görüntülenen bilgiler işaretleme sağlar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] belge görüntüleme denetimleri.</span><span class="sxs-lookup"><span data-stu-id="fb86c-116">Highlight annotations in [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] provide a similar feature for marking up information displayed in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] document viewing controls.</span></span>  
  
 <span data-ttu-id="fb86c-117">Aşağıdaki çizimde vurgulama ek açıklama örneği gösterir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="fb86c-118">![Ek açıklama vurgulayın](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="fb86c-118">![Highlight Annotation](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="fb86c-119">Kullanıcılar ilk bazı metin veya ilgi öğeyi seçerek ve görüntülemek için sağ tıklatıp ek açıklamaları genellikle oluşturma bir <xref:System.Windows.Controls.ContextMenu> ek açıklama seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="fb86c-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="fb86c-120">Aşağıdaki örnekte gösterildiği [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] bildirmek için kullanabileceğiniz bir <xref:System.Windows.Controls.ContextMenu> yönlendirilmiş komutlarla oluşturmak ve ek açıklamaları yönetmek için kullanıcılar erişebilir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a><span data-ttu-id="fb86c-121">Veri bağlama</span><span class="sxs-lookup"><span data-stu-id="fb86c-121">Data Anchoring</span></span>  
 <span data-ttu-id="fb86c-122">[!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] Ek açıklamaları, kullanıcının seçtiği verileri, yalnızca görüntü görünümü konumuna bağlar.</span><span class="sxs-lookup"><span data-stu-id="fb86c-122">The [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="fb86c-123">Bu nedenle, zaman kullanıcı kaydırdığında veya görüntü boyutlandırır gibi belge görünümü değişirse ek açıklama, bağlı olduğu veri seçimi ile kalır.</span><span class="sxs-lookup"><span data-stu-id="fb86c-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="fb86c-124">Örneğin, aşağıdaki grafikte kullanıcının metin seçiminde yaptığı bir ek açıklamanın gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="fb86c-125">Belgeyi görünümü değiştiğinde (kayarken, yeniden boyutlandırır, ölçekler veya başka bir hareket), özgün veri seçimiyle Vurgu ek açıklama taşır.</span><span class="sxs-lookup"><span data-stu-id="fb86c-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="fb86c-126">![Ek açıklama veri bağlama](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="fb86c-126">![Annotation Data Anchoring](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="fb86c-127">Açıklanmış nesnelerle eşleşen ek açıklamaları</span><span class="sxs-lookup"><span data-stu-id="fb86c-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="fb86c-128">Ek açıklamaları karşılık gelen açıklanmış nesnelerle eşleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fb86c-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="fb86c-129">Örneğin, açıklamalar bölmesi olan basit bir belge okuyucu uygulamasını göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="fb86c-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="fb86c-130">Açıklamalar bölmesi belgeye bağlantılı ek açıklamaları listesinden metni görüntüleyen bir liste kutusu olabilir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="fb86c-131">Kullanıcı liste kutusunda bir öğe seçerse, uygulama karşılık gelen ek açıklama nesnesinin sabitlenmiş olduğu belgedeki paragrafı görünüme getirir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="fb86c-132">Aşağıdaki örnek, açıklamalar bölmesi olarak hizmet böyle bir liste kutusu olay işleyicisinin uygulanacak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="fb86c-133">Başka bir örnek senaryo ek açıklamalar ve e-posta yoluyla belge okuyucular arasındaki Yapışkan Notlar alışverişini etkinleştirmek uygulamaları içerir.</span><span class="sxs-lookup"><span data-stu-id="fb86c-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through e-mail.</span></span> <span data-ttu-id="fb86c-134">Bu özellik, okuyucu değiştirilen ek açıklamayı içeren sayfaya gitmek bu uygulamaları sağlar.</span><span class="sxs-lookup"><span data-stu-id="fb86c-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb86c-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fb86c-135">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>  
 <xref:System.Windows.Controls.DocumentViewer>  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>  
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
 <xref:System.Windows.Controls.FlowDocumentReader>  
 <xref:System.Windows.Annotations.IAnchorInfo>  
 [<span data-ttu-id="fb86c-136">Ek Açıklamalar Şeması</span><span class="sxs-lookup"><span data-stu-id="fb86c-136">Annotations Schema</span></span>](../../../../docs/framework/wpf/advanced/annotations-schema.md)  
 [<span data-ttu-id="fb86c-137">ContextMenu genel bakış</span><span class="sxs-lookup"><span data-stu-id="fb86c-137">ContextMenu Overview</span></span>](../../../../docs/framework/wpf/controls/contextmenu-overview.md)  
 [<span data-ttu-id="fb86c-138">Komut verme genel bakış</span><span class="sxs-lookup"><span data-stu-id="fb86c-138">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="fb86c-139">Akış belgesi genel bakış</span><span class="sxs-lookup"><span data-stu-id="fb86c-139">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="fb86c-140">Nasıl yapılır: bir MenuItem komut ekleme</span><span class="sxs-lookup"><span data-stu-id="fb86c-140">How to: Add a Command to a MenuItem</span></span>](http://msdn.microsoft.com/en-us/013d68a0-5373-4a68-bd91-5de574307370)