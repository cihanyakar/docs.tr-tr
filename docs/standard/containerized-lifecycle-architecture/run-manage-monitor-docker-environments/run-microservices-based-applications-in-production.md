---
title: Üretim ortamlarında oluşturulan ve mikro hizmet tabanlı uygulamaları çalıştırma
description: Microsoft Platformu ve araçları ile kapsayıcı Docker uygulaması yaşam
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 003bf794f5427e7b2f10d1e04fd27605b980cdfe
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126308"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Üretim ortamlarında oluşturulan ve mikro hizmet tabanlı uygulamaları çalıştırma

Uygulamalar tarafından birden çok mikro hizmetlerden dağıtım karmaşıklığını basitleştirir ve uygun bir BT açısından kolaylaştırmak için orchestrator kümeler halinde dağıtılması gerekiyor. Bir orchestrator kümesi ölçeği genişletilmiş bir karmaşık mikro Hizmetler uygulaması dağıtma ve oldukça zor olurdu.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Düzenleyicileri, zamanlayıcılar ve kapsayıcı kümeleri giriş

Daha önce bu e-kitap, sunduk *kümeleri* ve *zamanlayıcılar* yazılım mimarisi ve geliştirme tartışmaya bir parçası olarak. Docker Swarm ve Mesosphere Datacenter işletim sistemini (DC/OS) Docker kümeleri örnekleridir. Bunların her ikisi de, Microsoft Azure Container Service tarafından sunulan altyapıyı bir parçası olarak çalıştırabilirsiniz.

Uygulamalar arasında birden fazla konak sistemi genişletilmiş olduğunda, her bir konak sistemi yönetmek ve temel alınan platformu karmaşıklığını hemen soyut olanağı cazip hale gelir. Tam olarak neler düzenleyiciler ve zamanlayıcılar sağlar olmasıdır. Burada bunları kısa bir göz atalım:

- **Zamanlayıcılar**. "Zamanlama" özelliği bir yöneticinin hizmet dosya belirli bir kapsayıcı çalıştırma kurar ve bir konak sistemi yüklemesini ifade eder. Kapsayıcıları bir Docker kümesi başlatma zamanlama olarak bilinen eğilimindedir. Hizmet tanımında daha genel bir fikir yükleme belirli Yasası zamanlama başvuruyor ancak zamanlayıcılar gereken herhangi bir kapasite hizmetleri yönetmek için bir ana bilgisayarın init sisteme takma için sorumlu olursunuz.

   Bir küme Zamanlayıcı birden çok hedefi vardır: küme kaynaklarını verimli bir şekilde kullanarak, kullanıcı tarafından sağlanan yerleştirme kısıtlamaları, "eşitliği, hataları güçlü olan" derecesini sahip hızlı bir şekilde onlara bir bekleyen durumda bırakmamaya uygulamalar planlama ile çalışma ve her zaman kullanılabilir olacak.

- **Orchestration**. Platformları, bir konak kümesi üzerinde dağıtılmış karmaşık, çok kapsayıcılı iş yüklerini yaşam döngüsü yönetim özelliklerini genişletin. Aldığı konak altyapısının özetleyen tarafından düzenleme araçları kullanıcıların tüm küme tek dağıtım hedefi olarak değerlendirilecek bir yol sağlar.

   Düzenleme işlemi, Araçlar ve uygulama yönetimi ilk yerleştirme veya kapsayıcı başına dağıtım tüm yönlerini otomatikleştiren bir platform gerektirir; kapsayıcıları kendi ana bilgisayarın sistem durumu veya performans bağlı olarak farklı Konaklara taşıma; sürüm oluşturma ve sıralı güncelleştirmeler ve sistem durumu izleme, ölçeklendirme ve yük devretme destekleyen işlevleri; ve daha fazlası.

   Orchestration kapsayıcı zamanlama, küme yönetimi ve büyük olasılıkla ek ana sağlama için başvuruda bulunan bir geniş bir terimdir.

Düzenleyiciler ve zamanlayıcılar tarafından sağlanan özellikler geliştirmek ve sıfırdan oluşturmak için son derece karmaşık ve bu nedenle, genellikle yapmak istersiniz kullanım düzenleme çözümlerinin satıcıları tarafından sunulan.

>[!div class="step-by-step"]
>[Önceki](index.md)
>[İleri](manage-production-docker-environments.md)