---
title: "Nasıl yapılır: Bir Sertifikanın Parmak İzini Alma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f66a7003fe712ab482d5237762e2bafffc5a6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a><span data-ttu-id="b1069-102">Nasıl yapılır: Bir Sertifikanın Parmak İzini Alma</span><span class="sxs-lookup"><span data-stu-id="b1069-102">How to: Retrieve the Thumbprint of a Certificate</span></span>
<span data-ttu-id="b1069-103">Yazılırken bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kimlik doğrulaması için bir X.509 sertifikası kullanan bir uygulama olmasından genellikle sertifika içinde bulunan talepleri belirtmek gerekli.</span><span class="sxs-lookup"><span data-stu-id="b1069-103">When writing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses an X.509 certificate for authentication, it is often necessary to specify claims found in the certificate.</span></span> <span data-ttu-id="b1069-104">Örneğin, kullanırken bir parmak izi talep sağlamalısınız <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> numaralandırmada <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="b1069-104">For example, you must supply a thumbprint claim when using the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> enumeration in the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="b1069-105">Talep değeri bulma iki adımı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b1069-105">Finding the claim value requires two steps.</span></span> <span data-ttu-id="b1069-106">İlk olarak, sertifikalar için Microsoft Yönetim Konsolu (MMC) ek bileşenini açın.</span><span class="sxs-lookup"><span data-stu-id="b1069-106">First, open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="b1069-107">(Bkz [nasıl yapılır: MMC ek bileşeni ile sertifikaları görüntüle](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) İkinci olarak, burada açıklandığı gibi uygun bir sertifika Bul ve kendi parmak izi (veya diğer talep değerleri) kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="b1069-107">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) Second, as described here, find an appropriate certificate and copy its thumbprint (or other claim values).</span></span>  
  
 <span data-ttu-id="b1069-108">Hizmet kimlik doğrulaması için bir sertifika kullanıyorsanız, değeri not daha önemlidir **çıkarılan** sütun (ilk sütun konsolunda).</span><span class="sxs-lookup"><span data-stu-id="b1069-108">If you are using a certificate for service authentication, it is important to note the value of the **Issued To** column (the first column in the console).</span></span> <span data-ttu-id="b1069-109">Tekdüzen Kaynak Tanımlayıcısı (URI) bir hizmetin temel karşılaştırmak için bir taşıma güvenliği, yapılan ilk denetimleri birini olduğu gibi Güvenli Yuva Katmanı (SSL) kullanarak adres **çıkarılan** değeri.</span><span class="sxs-lookup"><span data-stu-id="b1069-109">When using Secure Sockets Layer (SSL) as a transport security, one of the first checks done is to compare the base address Uniform Resource Identifier (URI) of a service to the **Issued To** value.</span></span> <span data-ttu-id="b1069-110">Değerler eşleşmelidir veya kimlik doğrulama işlemi durdu.</span><span class="sxs-lookup"><span data-stu-id="b1069-110">The values must match or the authentication process is halted.</span></span>  
  
 <span data-ttu-id="b1069-111">Makecert.exe aracından de kullanabilirsiniz [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK'sını yalnızca geliştirme sırasında kullanmak için geçici sertifikalar oluşturma.</span><span class="sxs-lookup"><span data-stu-id="b1069-111">You can also use the Makecert.exe tool from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK to create temporary certificates for use only during development.</span></span> <span data-ttu-id="b1069-112">Varsayılan olarak, ancak bu tür bir sertifika bir sertifika yetkilisi tarafından verilmemiş ve üretim için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b1069-112">By default, however, such a certificate is not issued by a certification authority, and is unusable for production purposes.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="b1069-113">[Nasıl yapılır: geliştirme sırasında kullanmak için geçici sertifikalar oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span><span class="sxs-lookup"><span data-stu-id="b1069-113"> [How to: Create Temporary Certificates for Use During Development](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span></span>  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a><span data-ttu-id="b1069-114">Bir sertifikanın parmak izi almak için</span><span class="sxs-lookup"><span data-stu-id="b1069-114">To retrieve a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="b1069-115">Sertifikalar için Microsoft Yönetim Konsolu (MMC) ek bileşenini açın.</span><span class="sxs-lookup"><span data-stu-id="b1069-115">Open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="b1069-116">(Bkz [nasıl yapılır: MMC ek bileşeni ile sertifikaları görüntüle](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span><span class="sxs-lookup"><span data-stu-id="b1069-116">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span></span>  
  
2.  <span data-ttu-id="b1069-117">İçinde **konsol kökü** penceresinin sol bölmesinde, tıklatın **sertifikalar (yerel bilgisayar)**.</span><span class="sxs-lookup"><span data-stu-id="b1069-117">In the **Console Root** window's left pane, click **Certificates (Local Computer)**.</span></span>  
  
3.  <span data-ttu-id="b1069-118">Tıklatın **kişisel** klasörünü genişletin.</span><span class="sxs-lookup"><span data-stu-id="b1069-118">Click the **Personal** folder to expand it.</span></span>  
  
4.  <span data-ttu-id="b1069-119">Tıklatın **sertifikaları** klasörünü genişletin.</span><span class="sxs-lookup"><span data-stu-id="b1069-119">Click the **Certificates** folder to expand it.</span></span>  
  
5.  <span data-ttu-id="b1069-120">Sertifikaları listesinde Not **Hedeflenen amaçlar** başlığı.</span><span class="sxs-lookup"><span data-stu-id="b1069-120">In the list of certificates, note the **Intended Purposes** heading.</span></span> <span data-ttu-id="b1069-121">Listeleyen bir sertifika bulunamadı **istemci kimlik doğrulaması** hedeflenen amacı olarak.</span><span class="sxs-lookup"><span data-stu-id="b1069-121">Find a certificate that lists **Client Authentication** as an intended purpose.</span></span>  
  
6.  <span data-ttu-id="b1069-122">Sertifikayı çift tıklatın.</span><span class="sxs-lookup"><span data-stu-id="b1069-122">Double-click the certificate.</span></span>  
  
7.  <span data-ttu-id="b1069-123">İçinde **sertifika** iletişim kutusu, tıklatın **ayrıntıları** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="b1069-123">In the **Certificate** dialog box, click the **Details** tab.</span></span>  
  
8.  <span data-ttu-id="b1069-124">Alanları listede ilerleyin ve tıklayın **parmak izi**.</span><span class="sxs-lookup"><span data-stu-id="b1069-124">Scroll through the list of fields and click **Thumbprint**.</span></span>  
  
9. <span data-ttu-id="b1069-125">Onaltılık karakterler kutusundan kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="b1069-125">Copy the hexadecimal characters from the box.</span></span> <span data-ttu-id="b1069-126">Bu parmak izi kodu kullanılıyorsa `X509FindType`, onaltılık sayılar arasında boşluk kaldırın.</span><span class="sxs-lookup"><span data-stu-id="b1069-126">If this thumbprint is used in code for the `X509FindType`, remove the spaces between the hexadecimal numbers.</span></span> <span data-ttu-id="b1069-127">Örneğin, parmak izi "a9 09 50 2B d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" Code "a909502dd82ae41433e6f83886b00d4277a32a7b" olarak belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="b1069-127">For example, the thumbprint "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" should be specified as "a909502dd82ae41433e6f83886b00d4277a32a7b" in code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1069-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b1069-128">See Also</span></span>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>  
 [<span data-ttu-id="b1069-129">Nasıl yapılır: bir SSL sertifikası ile bir bağlantı noktası yapılandırın</span><span class="sxs-lookup"><span data-stu-id="b1069-129">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="b1069-130">Nasıl yapılır: MMC ek bileşeni ile sertifikaları görüntüle</span><span class="sxs-lookup"><span data-stu-id="b1069-130">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="b1069-131">Nasıl yapılır: geliştirme sırasında kullanmak için geçici sertifikalar oluşturma</span><span class="sxs-lookup"><span data-stu-id="b1069-131">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)