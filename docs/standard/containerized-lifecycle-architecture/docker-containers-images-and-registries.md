---
title: Docker kapsayıcıları, görüntüleri ve kayıt defterleri
description: Microsoft Platformu ve araçları ile kapsayıcı Docker uygulaması yaşam
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: af235280c985d20f9e6a2ee6096edbe6c3aad63a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53142755"
---
# <a name="docker-containers-images-and-registries"></a>Docker kapsayıcıları, görüntüleri ve kayıt defterleri

Docker'ı kullanarak bir uygulama veya hizmeti ve paketi ve bağımlılıkları bir kapsayıcı görüntüsü oluşturduğunuzda. Görüntü uygulamayı veya hizmeti ve kendi yapılandırma ve bağımlılıklarla statik bir gösterimidir.

Uygulamanızı veya hizmetinizi çalıştırmak için uygulamanın resmi Docker ana bilgisayarda çalışan bir kapsayıcı oluşturmak için örneği oluşturulur. Kapsayıcı başlangıçta bir geliştirme ortamı veya bilgisayar test edilmez.

Görüntü kitaplığı hareket eden bir kayıt defteri, görüntüleri depolayın. Bir kayıt defteri için üretim düzenleyicileri dağıtırken gerekir. Genel bir kayıt defterinden docker tutar [Docker Hub](https://hub.docker.com/); diğer satıcıları görüntüleri farklı koleksiyonlar için kayıt defterleri sağlayın. Alternatif olarak, kuruluşlar, özel bir kayıt defteri sahip olabilir, kendi Docker görüntüleri için şirket içi.

Şekil 1-4 nasıl görüntüler ve Docker kayıt defterleri için diğer bileşenleri ilişkilendirilmesi gösterir. Ayrıca birden çok kayıt defteri teklifleri satıcılardan gösterir.

![](./media/image4.png)

Şekil 1-4: Docker terimleri ve kavramları'nin Taksonomisi

Kayıt defterindeki görüntüleri koyarak çerçevesi düzeyinde, bağımlılıklarının tümü de dahil olmak üzere, statik ve sabit uygulama BITS depolayabilirsiniz. Ardından sürüm ve birden çok ortama görüntülerde dağıtabilir ve bu nedenle, tutarlı dağıtım birimi sağlayın.

Özel görüntü kayıt defterleri, şirket içinde barındırılan veya bulutta, aşağıdaki durumlarda önerilir:

-   Nedeniyle gizlilik görüntülerinizin herkese açık şekilde paylaşılmamalı.

-   Görüntüleri ve seçilen dağıtım ortamınız arasında düşük ağ gecikme süresine sahiptir istiyorsunuz. Üretim ortamınızı Azure ise, örneğin, büyük olasılıkla ağ gecikme süresi çok az olması görüntülerinizi Azure Container Registry'de depolamak istediğiniz. Üretim ortamınıza şirket içinde ise benzer şekilde, bu, bir şirket içi Docker Trusted Registry aynı yerel ağda kullanılabilir olmasını isteyebilirsiniz.

>[!div class="step-by-step"]
>[Önceki](docker-terminology.md)
>[İleri](Docker-application-lifecycle/index.md)