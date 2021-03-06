---
title: Docker kapsayıcıları için .NET Core ve .NET Framework arasında seçim
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Docker kapsayıcıları için .NET Core ve .NET Framework arasında seçim
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: e71739b06275d4ee786d246004930d7b66fbc72b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151427"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a>Docker kapsayıcıları için .NET Core ve .NET Framework arasında seçim

Docker uygulamaları .NET ile kapsayıcılı hale sunucu tarafı oluşturmak için iki desteklenen çerçeveler şunlardır: [.NET Framework ve .NET Core](https://www.microsoft.com/net/download). Birçok .NET platformu bileşenleri paylaşır ve ikisi arasında kod paylaşabilirsiniz. Ancak, bunları ve kullandığınız hangi framework gerçekleştirmek istediğinize göre değişir arasındaki temel farklar vardır. Bu bölümde, ne zaman her bir çerçeve seçin hakkında yönergeler sağlanmaktadır.

>[!div class="step-by-step"]
>[Önceki](../container-docker-introduction/docker-containers-images-registries.md)
>[İleri](general-guidance.md)