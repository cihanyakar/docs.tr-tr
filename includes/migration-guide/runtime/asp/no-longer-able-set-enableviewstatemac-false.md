### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="b76ec-101">Artık mümkün EnableViewStateMac false olarak ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="b76ec-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b76ec-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="b76ec-102">Details</span></span>|<span data-ttu-id="b76ec-103">ASP.NET artık geliştiricilerinin belirtmelerini sağlayan <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> veya <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="b76ec-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="b76ec-104">Görünüm durumu ileti kimlik doğrulama kodu (MAC), artık ekli görünüm durumu olan tüm istekler için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="b76ec-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="b76ec-105">Yalnızca açıkça EnableViewStateMac özellik kümesine uygulamaları <code>false</code> etkilenir.</span><span class="sxs-lookup"><span data-stu-id="b76ec-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="b76ec-106">Öneri</span><span class="sxs-lookup"><span data-stu-id="b76ec-106">Suggestion</span></span>|<span data-ttu-id="b76ec-107">EnableViewStateMac kabul, true olarak ve sonuçta elde edilen MAC hataları giderilmesi gerekir (açıklandığı gibi [bu kılavuz](https://support.microsoft.com/kb/2915218), MAC hatalara neden olan özelliklerini bağlı olarak birden çok çözünürlüğü içerir).</span><span class="sxs-lookup"><span data-stu-id="b76ec-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="b76ec-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="b76ec-108">Scope</span></span>|<span data-ttu-id="b76ec-109">Ana</span><span class="sxs-lookup"><span data-stu-id="b76ec-109">Major</span></span>|
|<span data-ttu-id="b76ec-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="b76ec-110">Version</span></span>|<span data-ttu-id="b76ec-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b76ec-111">4.5.2</span></span>|
|<span data-ttu-id="b76ec-112">Tür</span><span class="sxs-lookup"><span data-stu-id="b76ec-112">Type</span></span>|<span data-ttu-id="b76ec-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="b76ec-113">Runtime</span></span>|
