---
title: Bütünleştirilmiş kod ve DLL adları
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: KrzysztofCwalina
ms.openlocfilehash: 8e20d77c20be8dc74723117f3b0910ecc2090ef7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130981"
---
# <a name="names-of-assemblies-and-dlls"></a>Bütünleştirilmiş kod ve DLL adları
Bir derleme dağıtım ve yönetilen kod programları için kimlik birimidir. Genellikle bir veya daha çok dosya derlemeleri yayılabilir olsa da, bir derleme bir DLL ile bire bir eşlenir. Bu nedenle, bu bölümde olan derleme adlandırma kurallarına eşlenebilir yalnızca DLL adlandırma kurallarını açıklar.  
  
 **✓ DO** derlemenizi System.Data gibi işlevleri büyük boyutta önermek DLL'ler için adları'ı seçin.  
  
 Bütünleştirilmiş kod ve DLL adları ad alanı adları için karşılık gelen gerekmez ancak ad alanı adı derlemelerini adlandırma izlenmesi gereken şüphelenilebilir. Bir iyi derlemesinde bulunan ad alanlarının yaygın önekini temel DLL adı için udur. Örneğin, iki ad alanı, bir derlemeye `MyCompany.MyTechnology.FirstFeature` ve `MyCompany.MyTechnology.SecondFeature`, çağrılabilir `MyCompany.MyTechnology.dll`.  
  
 **✓ CONSIDER** göre aşağıdaki düzeni DLL'leri adlandırma:  
  
 `<Company>.<Component>.dll`  
  
 Burada `<Component>` bir veya daha fazla noktayla ayrılmış yan tümce içeriyor. Örneğin:  
  
 `Litware.Controls.dll`.  
  
 *Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)  
- [Adlandırma Kuralları](../../../docs/standard/design-guidelines/naming-guidelines.md)
