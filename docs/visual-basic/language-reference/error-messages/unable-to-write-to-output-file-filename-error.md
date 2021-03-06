---
title: 'Çıkış dosyası yazılamıyor &#39; &lt;filename&gt;&#39;: &lt;hata&gt;'
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: e8fbfd54782e601595712035827ea346d1dbf500
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597516"
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>Çıkış dosyası yazılamıyor &#39; &lt;filename&gt;&#39;: &lt;hata&gt;
Dosya oluşturulurken hata oluştu.  
  
 Bir çıkış dosyası yazmak için açılamıyor. Başka bir işlem tarafından özel kullanım için dosya (veya dosyasını içeren klasör) açılabilir veya kendi salt okunur özniteliği kümesine sahip.  
  
 Burada bir dosya özel olarak açılmış ortak durumlar şunlardır:  
  
-   Uygulama zaten çalışan ve kendi dosyalarını kullanma. Bu sorunu çözmek için uygulama çalışmadığından emin olun.  
  
-   Başka bir uygulama, dosya açtı. Bu sorunu çözmek için başka bir uygulama dosyaları erişiyor emin olun. Her zaman hangi uygulamanın, dosyalarınızı erişiyor belirgin değildir; Bu durumda, bilgisayarı yeniden başlatmadan sonlandırmak için en kolay yolu olabilir.  
  
 Proje çıktı dosyalarını biri bile salt okunur olarak işaretlenmişse, bu özel durum.  
  
 **Hata Kimliği:** BC31019  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Hata durumunda yinelenen yeniden görmek için programı derleyin.  
  
2.  Hata devam ederse, çalışmanızı kaydedin ve Visual Studio'yu yeniden başlatın.  
  
3.  Hata devam ederse bilgisayarı yeniden başlatın.  
  
4.  Hata tekrar oluşursa, Visual Basic yeniden yükleyin.  
  
5.  Yeniden yüklenmesinden sonra hata devam ederse, Microsoft Ürün Destek Hizmetleri'ne bildirin.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>Dosya Gezgini'nde dosya öznitelikleri denetlemek için  
  
1.  İlgilendiğiniz klasörünü açın.  
  
2.  Tıklatın **görünümleri** simgesini seçin **ayrıntıları**.  
  
3.  Sütun başlığını sağ tıklatın ve seçin **öznitelikleri** aşağı açılan listeden.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>Bir dosya veya klasör özniteliklerini değiştirmek için  
  
1.  İçinde **dosya Gezgini**, dosyayı veya klasörü sağ tıklatın ve seçin **özellikleri**.  
  
2.  İçinde **öznitelikleri** bölümünü **genel** sekmesi, Temizle **salt okunur** kutusu.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bizimle İletişime Geçin](/visualstudio/ide/talk-to-us)
