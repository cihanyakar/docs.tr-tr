### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="07a03-101">Zaman aşımı bağımsız değişkenlerle Task.WaitAll yöntemleri için davranış değiştirme</span><span class="sxs-lookup"><span data-stu-id="07a03-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

|   |   |
|---|---|
|<span data-ttu-id="07a03-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="07a03-102">Details</span></span>|<span data-ttu-id="07a03-103">Task.WaitAll davranışı .NET 4.5.In .NET Framework 4, tutarsız bir şekilde davranan bu yöntemleri daha tutarlı hale getirildi.</span><span class="sxs-lookup"><span data-stu-id="07a03-103">Task.WaitAll behavior was made more consistent in .NET 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="07a03-104">Zaman aşımı süresi bir veya daha fazla görev tamamlandı veya yöntem çağrısı önce iptal ise, yöntem belirtti bir <xref:System.AggregateException?displayProperty=name> özel durum.</span><span class="sxs-lookup"><span data-stu-id="07a03-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=name> exception.</span></span> <span data-ttu-id="07a03-105">Hiçbir görev tamamlandı veya yöntem çağrısı önce iptal edildi, ancak bir veya daha fazla görev yöntemi çağrısından sonra bu durumları girilen zaman aşımı süresi, yöntem false döndürdü.</span><span class="sxs-lookup"><span data-stu-id="07a03-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="07a03-106">.NET Framework 4.5, bu yöntem aşırı artık herhangi bir görevi hala zaman aşımı aralığı süresi ve bunlar throw çalıştırıyorsanız return false bir <xref:System.AggregateException?displayProperty=name> yalnızca bir giriş görevi (onu önce veya sonra yöntem olmasına bakılmaksızın iptal edildiyse özel durumu Çağrı) ve diğer bir görevler çalışmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="07a03-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=name> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>|
|<span data-ttu-id="07a03-107">Öneri</span><span class="sxs-lookup"><span data-stu-id="07a03-107">Suggestion</span></span>|<span data-ttu-id="07a03-108">Varsa bir <xref:System.AggregateException?displayProperty=name> kod IsCanceled özelliği aracılığıyla aynı algılama yerine yapmalısınız çağrılan, WaitAll çağrıdan önce iptal edildi bir görev algılama yolu olarak yakalanan (örneğin:. Any(t =&gt; t.IsCanceled)) zaman aşımı önce tüm awaited görevler tamamladıysanız .NET 4.6 yalnızca bu durumda başlatıldıysa bu yana.</span><span class="sxs-lookup"><span data-stu-id="07a03-108">If an <xref:System.AggregateException?displayProperty=name> was being caught as a means of detecting a task that was cancelled prior to the WaitAll call being invoked, that code should instead do the same detection via the IsCanceled property (for example: .Any(t =&gt; t.IsCanceled)) since .NET 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>|
|<span data-ttu-id="07a03-109">Kapsam</span><span class="sxs-lookup"><span data-stu-id="07a03-109">Scope</span></span>|<span data-ttu-id="07a03-110">Küçük</span><span class="sxs-lookup"><span data-stu-id="07a03-110">Minor</span></span>|
|<span data-ttu-id="07a03-111">Sürüm</span><span class="sxs-lookup"><span data-stu-id="07a03-111">Version</span></span>|<span data-ttu-id="07a03-112">4,5</span><span class="sxs-lookup"><span data-stu-id="07a03-112">4.5</span></span>|
|<span data-ttu-id="07a03-113">Tür</span><span class="sxs-lookup"><span data-stu-id="07a03-113">Type</span></span>|<span data-ttu-id="07a03-114">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="07a03-114">Runtime</span></span>|
|<span data-ttu-id="07a03-115">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="07a03-115">Affected APIs</span></span>|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
