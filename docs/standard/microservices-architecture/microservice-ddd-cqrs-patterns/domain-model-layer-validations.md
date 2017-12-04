---
title: "Etki alanı modeli katmanda doğrulamaları tasarlama"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Etki alanı modeli katmanda doğrulamaları tasarlama"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="b72fe-104">Etki alanı modeli katmanda doğrulamaları tasarlama</span><span class="sxs-lookup"><span data-stu-id="b72fe-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="b72fe-105">GGG doğrulama kuralları invariants düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="b72fe-106">Ana bir toplama, toplama içinde tüm varlıklar için durum değişiklikleri arasında invariants zorlamak için sorumluluğundadır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="b72fe-107">Etki alanı varlıkları her zaman geçerli varlıkları olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="b72fe-108">Belirli bir sayıda invariants her zaman doğru olması gereken bir nesne için vardır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="b72fe-109">Örneğin, bir siparişi öğesi nesne her zaman, pozitif bir tamsayı ve bir makale adı olması ve fiyat gereken bir miktar sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="b72fe-110">Bu nedenle, invariants zorlama (özellikle kökünün toplama) etki alanı varlıkları sorumluluğundadır ve bir varlık nesnesinin geçerli olmadan mevcut olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="b72fe-111">Değişmez kuralları yalnızca sözleşmeleri ifade edilir ve bunlar ihlal edildiğinde özel durumları veya bildirimleri oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b72fe-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="b72fe-112">Bu arkasındaki mantığı, nesneler, hiçbir zaman içinde olması gereken bir durumda olduğundan birçok hatalar ortaya ' dir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="b72fe-113">Greg Young iyi bir açıklama verilmiştir bir [Çevrimiçi tartışma](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="b72fe-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="b72fe-114">Şimdi bir USERPROFILE... nasıl biz adı null değil o hizmetinde basitleşir götürür SendUserCreationEmailService şimdi sahibiz önermek?</span><span class="sxs-lookup"><span data-stu-id="b72fe-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="b72fe-115">Biz yeniden iade?</span><span class="sxs-lookup"><span data-stu-id="b72fe-115">Do we check it again?</span></span> <span data-ttu-id="b72fe-116">Veya daha büyük bir olasılıkla... denetleyip "için en iyi umuyoruz" yalnızca rahatsız yok — birisi, göndermeden önce doğrulamak için rahatsız umuyoruz.</span><span class="sxs-lookup"><span data-stu-id="b72fe-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="b72fe-117">Elbette, biz hata tetiklemelidir null bir ada sahip bir müşteri gönderebilirim durumunda yazma ilk testin TDD kullanma.</span><span class="sxs-lookup"><span data-stu-id="b72fe-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="b72fe-118">Ancak bu tür testlerin tekrar tekrar yazma başladıktan sonra biz farkında olun... "biz olmasını adı hiçbir zaman izin veriyorsa bekleyin null tüm bu testleri sahibiz olmayacaktır"</span><span class="sxs-lookup"><span data-stu-id="b72fe-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="b72fe-119">Etki alanı modeli katmanda doğrulamaları uygulama</span><span class="sxs-lookup"><span data-stu-id="b72fe-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="b72fe-120">Doğrulama, etki alanı varlık oluşturucuları veya varlık güncelleştirebilirsiniz yöntemleri genellikle uygulanır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="b72fe-121">Doğrulanıyor verileri ve doğrulama başarısız olursa yükseltmeyi özel durumlar gibi doğrulamaları uygulamak için birden çok yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="b72fe-122">Ayrıca vardır doğrulamaların belirtimi desenini kullanarak gibi daha gelişmiş desenleri ve daha sonra giderebilmek yerine her doğrulama için bir özel durum döndürme hataları koleksiyonu döndürmek için bildirim düzeni.</span><span class="sxs-lookup"><span data-stu-id="b72fe-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="b72fe-123">Koşullar doğrulama ve özel durumları atma</span><span class="sxs-lookup"><span data-stu-id="b72fe-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="b72fe-124">Aşağıdaki kod örneği, en kolay yaklaşım doğrulama için bir özel durum yükselterek bir etki alanı varlığı gösterir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="b72fe-125">Bu bölümün sonunda başvuruları tablosundaki biz daha önce ele alınan düzenlerini esas alarak daha gelişmiş uygulamaları bağlantılar görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b72fe-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="b72fe-126">Daha iyi bir örnek iç durum değiştirme veya bir yöntem için tüm mutations ortaya çıktığını sağlamak için gereken göstermek.</span><span class="sxs-lookup"><span data-stu-id="b72fe-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="b72fe-127">Örneğin, aşağıdaki uygulama nesnesi geçersiz bir durumda bırakır:</span><span class="sxs-lookup"><span data-stu-id="b72fe-127">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="b72fe-128">Durum değeri geçersiz, ilk adres satırındaki ve şehir zaten değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="b72fe-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="b72fe-129">Bu adres geçersiz yapabilir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-129">That might make the address invalid.</span></span>

<span data-ttu-id="b72fe-130">Benzer bir yaklaşım oluşturulduktan sonra varlık geçerli olduğundan emin olmak için bir özel durum yükseltme varlığın oluşturucuda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="b72fe-131">Üzerinde veri ek açıklamaları temel modelinde doğrulama öznitelikleri kullanma</span><span class="sxs-lookup"><span data-stu-id="b72fe-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="b72fe-132">Başka bir yaklaşım üzerinde veri ek açıklamaları temel doğrulama öznitelikleri kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="b72fe-133">Doğrulama öznitelikleri kavramsal olarak, veritabanı tablolarındaki alanlar doğrulama benzer model doğrulama yapılandırmak için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="b72fe-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="b72fe-134">Bu, veri türleri veya gerekli alanları atama gibi kısıtlamaları içerir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="b72fe-135">Doğrulama diğer türleri gibi bir kredi kartı numarası, telefon numarası, iş kurallarını zorunlu tutmak için veri desenleri uygulamak dahil etmek veya e-posta adresi.</span><span class="sxs-lookup"><span data-stu-id="b72fe-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="b72fe-136">Doğrulama öznitelikleri gereksinimleri zorlamak kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="b72fe-137">MVC denetleyicilerinden çağırmalısınız Microsoft.AspNetCore.Mvc.ModelState arasında ModelState.IsValid üzerinde bir bağımlılık geçen olduğundan ancak, aşağıdaki kodda gösterildiği gibi bu yaklaşım DDD modelinde, çok zorlayıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="b72fe-138">Model doğrulama çağrılan her denetleyici eylemi önce gerçekleşir ve onu çağıran ModelState.IsValid sonucunu inceleyin ve uygun şekilde tepki denetleyici yöntemin sorumluluğundadır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="b72fe-139">Kullanmaya karar bağlıdır sıkı şekilde bağlı model, altyapı ile olmasını istiyor.</span><span class="sxs-lookup"><span data-stu-id="b72fe-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

<span data-ttu-id="b72fe-140">Ancak, bir DDD açısından bakıldığında, etki alanı modeli en iyi, varlığın davranışını yöntemleri veya doğrulama kurallarını zorunlu tutmak için belirtimi ve bildirim desenleri uygulama özel durumları kullanımı ile yalın tutulur.</span><span class="sxs-lookup"><span data-stu-id="b72fe-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="b72fe-141">ASP.NET Core veri ek açıklamalar gibi doğrulama çerçeveleri veya herhangi bir doğrulama çerçeve FluentValidation gibi uygulama çerçevesi çağırmak için bir gereksinim taşır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="b72fe-142">Örneğin, ModelState.IsValid yöntemi içinde veri ek açıklamaları çağrılırken, ASP.NET denetleyicileri çağırma gerekir.</span><span class="sxs-lookup"><span data-stu-id="b72fe-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="b72fe-143">Veri ek açıklamaları model doğrulama UI katman içinde izin vermek için giriş kabul ViewModel sınıflarında (yerine etki alanı varlıklar) uygulama katmanında kullanmak için anlamlı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b72fe-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="b72fe-144">Ancak, bu etki alanı modeli içindeki doğrulama dışlama adresindeki yapılmalıdır değil.</span><span class="sxs-lookup"><span data-stu-id="b72fe-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="b72fe-145">Varlıkları belirtimi düzeni ve bildirim düzeni uygulayarak doğrulanıyor</span><span class="sxs-lookup"><span data-stu-id="b72fe-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="b72fe-146">Son olarak, etki alanı modelinde doğrulamaları uygulamak için bir daha karmaşık bildirim düzeni ile birlikte belirtimi düzeni uygulayarak daha sonra listelenen ek kaynaklar bazıları açıklandığı gibi bir yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="b72fe-147">Bu, aynı zamanda bu düzenlere yalnızca biri kullanabileceğiniz tümleştirilmediği de unutulmamalıdır — Örneğin, el ile denetim ifadeleri doğrulama, ancak uyarı desenini kullanarak yığın ve doğrulama hatalarının listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="b72fe-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="b72fe-148">Ertelenmiş doğrulama etki alanında kullanma</span><span class="sxs-lookup"><span data-stu-id="b72fe-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="b72fe-149">Etki alanındaki ertelenmiş doğrulamaları uğraşmanız çeşitli yaklaşım vardır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="b72fe-150">Kendi kitaptaki [Implementing Domain-Driven tasarım](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon bu bölümdeki doğrulamasını açıklanır.</span><span class="sxs-lookup"><span data-stu-id="b72fe-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="b72fe-151">İki aşamalı doğrulama</span><span class="sxs-lookup"><span data-stu-id="b72fe-151">Two-step validation</span></span>

<span data-ttu-id="b72fe-152">Ayrıca, iki aşamalı doğrulama göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="b72fe-152">Also consider two-step validation.</span></span> <span data-ttu-id="b72fe-153">Alan düzeyindeki doğrulama komutu veri aktarım nesneleri (DTOs) ve etki alanı düzeyi doğrulama varlıklarınızı içinde kullanın.</span><span class="sxs-lookup"><span data-stu-id="b72fe-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="b72fe-154">Sonuç nesnesi bunun yerine özel durumları doğrulama hatalarla ilgilenir kolaylaştırmak için döndürerek bunu yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b72fe-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="b72fe-155">Alan doğrulama ile veri ek açıklamaları kullanılarak, örneğin, doğrulama yinelenen tanımı değil.</span><span class="sxs-lookup"><span data-stu-id="b72fe-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="b72fe-156">Yürütme rağmen sunucu tarafı ve istemci tarafı DTOs durumunda olabilir (komutlar ve ViewModels, örneğin).</span><span class="sxs-lookup"><span data-stu-id="b72fe-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b72fe-157">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b72fe-157">Additional resources</span></span>

-   <span data-ttu-id="b72fe-158">**Rachel Appel. ASP.NET Core MVC model doğrulama giriş**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="b72fe-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="b72fe-159">**Rick Anderson. Doğrulama ekleme**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="b72fe-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="b72fe-160">**Martin Fowler. Doğrulama içinde bildirim özel durumları atma değiştirme**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="b72fe-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="b72fe-161">**Belirtimi ve bildirim desenleri**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="b72fe-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="b72fe-162">**Levası Gorodinski. Etki alanı Odaklı Tasarım (DDD) doğrulama**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="b72fe-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="b72fe-163">**Colin prizine. Etki alanı Model doğrulama**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="b72fe-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="b72fe-164">**Jimmy Bogard. Doğrulama DDD dünyada**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="b72fe-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b72fe-165">[Önceki] (numaralandırması-sınıfları-üzerinden-enum-types.md) [sonraki] (istemci-tarafı-validation.md)</span><span class="sxs-lookup"><span data-stu-id="b72fe-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>