---
title: NotifyIcon Bileşenine Genel Bakış (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 5d77099eeb1ef33f3b9e65bd99d4e22e38c3ec38
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087212"
---
# <a name="notifyicon-component-overview-windows-forms"></a>NotifyIcon Bileşenine Genel Bakış (Windows Forms)

Windows Forms <xref:System.Windows.Forms.NotifyIcon> bileşeni genellikle çoğu zaman arka planda çalışan ve bir kullanıcı gösterme işlemleri arabiriminin simgeleri göstermek için kullanılır. Görev çubuğu durum bildirim alanındaki simgeye tıklayarak erişilebilir bir virüs koruma programı örnek verilebilir.

## <a name="key-properties-of-notifyicons"></a>NotifyIcons anahtar özellikleri

Her <xref:System.Windows.Forms.NotifyIcon> bileşeni durum alanında tek bir simge görüntüler. Üç arka plan işlemleri ve her biri için bir simge görüntülemek istediğiniz varsa, üç eklemelisiniz <xref:System.Windows.Forms.NotifyIcon> forma bileşenleri. Anahtar özelliklerini <xref:System.Windows.Forms.NotifyIcon> bileşenidir <xref:System.Windows.Forms.NotifyIcon.Icon%2A> ve <xref:System.Windows.Forms.NotifyIcon.Visible%2A>. <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Özelliğini ayarlar durum alanında görüntülenen simge. Simgesinin görünmesi sırayla <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özelliği ayarlanmalıdır `true`.

## <a name="notifyicons-options"></a>NotifyIcons seçenekleri

Balon ipuçları, kısayol menüleri ve araç ipuçları ile ilişkilendirebilirsiniz bir <xref:System.Windows.Forms.NotifyIcon> kullanıcı yardımcı olmak için.

Balon ipuçları görüntüleyebileceğiniz bir <xref:System.Windows.Forms.NotifyIcon> çağırarak <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> zaman span belirtme yöntemi görüntülenecek balon ipucu istiyor. Metin, simge ve balon ucuyla başlığının belirtebilirsiniz <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> ve <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>sırasıyla. <xref:System.Windows.Forms.NotifyIcon> bileşenleri araç ipuçları ve kısayol menüleri ilişkili. Daha fazla bilgi için [ToolTip bileşenine genel bakış](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) ve [ContextMenu bileşenine genel bakış](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).

## <a name="see-also"></a>Ayrıca Bkz.

- <xref:System.Windows.Forms.NotifyIcon>
- [NotifyIcon Bileşeni](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)