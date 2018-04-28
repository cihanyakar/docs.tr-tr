### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="0cca4-101">WPF yazım denetimi beklenmeyen şekilde başarısız</span><span class="sxs-lookup"><span data-stu-id="0cca4-101">WPF Spell Checking fails in unexpected ways</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0cca4-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="0cca4-102">Details</span></span>|<span data-ttu-id="0cca4-103">Bu, birkaç WPF yazım denetleyicisi sorunları içerir:</span><span class="sxs-lookup"><span data-stu-id="0cca4-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="0cca4-104">WPF yazım denetleyicisi bazen oluşturur <xref:System.Runtime.InteropServices.COMException?displayProperty=name></span><span class="sxs-lookup"><span data-stu-id="0cca4-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=name></span></span></li><li><span data-ttu-id="0cca4-105">WPF yazım denetimi başarısız olan <xref:System.UnauthorizedAccessException> 'farklı bir kullanıcı olarak çalıştır' kullanarak uygulamaları başlatılan zaman</span><span class="sxs-lookup"><span data-stu-id="0cca4-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="0cca4-106">WPF yazım denetleyicisi yanlış Almanca 'Hausnummer' gibi bileşik sözcüklerin yazım hatalarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0cca4-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>|
|<span data-ttu-id="0cca4-107">Öneri</span><span class="sxs-lookup"><span data-stu-id="0cca4-107">Suggestion</span></span>|<span data-ttu-id="0cca4-108">Sorun #1 - Bu .NET Framework 4.6.2 düzeltildiğini sorunu #2 - WPF yazım denetleyicisi 'farklı bir kullanıcı olarak çalıştır' kullanarak uygulamalar başlatıldığında, artık desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="0cca4-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="0cca4-109">.NET Framework 4.6.2 başlayarak, bu şekilde başlatılan uygulamalara artık beklenmedik bir şekilde kilitleniyor - bunun yerine yazım denetleyicisi sessiz bir şekilde devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="0cca4-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="0cca4-110">Sorun #3 - Bu .NET Framework 4.6.2 düzeltilmiştir.</span><span class="sxs-lookup"><span data-stu-id="0cca4-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>|
|<span data-ttu-id="0cca4-111">Kapsam</span><span class="sxs-lookup"><span data-stu-id="0cca4-111">Scope</span></span>|<span data-ttu-id="0cca4-112">Kenar</span><span class="sxs-lookup"><span data-stu-id="0cca4-112">Edge</span></span>|
|<span data-ttu-id="0cca4-113">Sürüm</span><span class="sxs-lookup"><span data-stu-id="0cca4-113">Version</span></span>|<span data-ttu-id="0cca4-114">4.6.1</span><span class="sxs-lookup"><span data-stu-id="0cca4-114">4.6.1</span></span>|
|<span data-ttu-id="0cca4-115">Tür</span><span class="sxs-lookup"><span data-stu-id="0cca4-115">Type</span></span>|<span data-ttu-id="0cca4-116">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="0cca4-116">Runtime</span></span>|
