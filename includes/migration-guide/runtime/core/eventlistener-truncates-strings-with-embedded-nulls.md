### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="7d99c-101">Katıştırılmış null değerlere dizelerle EventListener keser</span><span class="sxs-lookup"><span data-stu-id="7d99c-101">EventListener truncates strings with embedded nulls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7d99c-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="7d99c-102">Details</span></span>|<span data-ttu-id="7d99c-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> Katıştırılmış null değerlere dizelerle tamsayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="7d99c-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> truncates strings with embedded nulls.</span></span> <span data-ttu-id="7d99c-104">Boş karakterler tarafından desteklenmeyen <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7d99c-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> class.</span></span> <span data-ttu-id="7d99c-105">Değişiklik yalnızca kullanan uygulamaları etkiler <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> okumak için <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> işleminde veri ve, sınırlayıcı olarak boş karakterler kullanın.</span><span class="sxs-lookup"><span data-stu-id="7d99c-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process and that use null characters as delimiters.</span></span>|
|<span data-ttu-id="7d99c-106">Öneri</span><span class="sxs-lookup"><span data-stu-id="7d99c-106">Suggestion</span></span>|<span data-ttu-id="7d99c-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> Veri Mümkünse, katıştırılmış boş karakterler kullanmayacak şekilde güncelleştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="7d99c-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data should be updated, if possible, to not use embedded null characters.</span></span>|
|<span data-ttu-id="7d99c-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="7d99c-108">Scope</span></span>|<span data-ttu-id="7d99c-109">Kenar</span><span class="sxs-lookup"><span data-stu-id="7d99c-109">Edge</span></span>|
|<span data-ttu-id="7d99c-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="7d99c-110">Version</span></span>|<span data-ttu-id="7d99c-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7d99c-111">4.5.1</span></span>|
|<span data-ttu-id="7d99c-112">Tür</span><span class="sxs-lookup"><span data-stu-id="7d99c-112">Type</span></span>|<span data-ttu-id="7d99c-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="7d99c-113">Runtime</span></span>|
|<span data-ttu-id="7d99c-114">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="7d99c-114">Affected APIs</span></span>|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
