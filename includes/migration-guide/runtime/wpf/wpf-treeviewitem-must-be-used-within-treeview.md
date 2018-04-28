### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a><span data-ttu-id="1e7a5-101">WPF TreeViewItem TreeView içinde kullanılması gerekir</span><span class="sxs-lookup"><span data-stu-id="1e7a5-101">WPF TreeViewItem must be used within a TreeView</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1e7a5-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="1e7a5-102">Details</span></span>|<span data-ttu-id="1e7a5-103">Bir değişiklik kullanımını kısıtlar 4.5 içinde sunulan <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> öğeleri dışında bir <xref:System.Windows.Controls.TreeView?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-103">A change was introduced in 4.5 that restricts usage of <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> elements outside of a <xref:System.Windows.Controls.TreeView?displayProperty=name>.</span></span> <span data-ttu-id="1e7a5-104">Bu, aşağıdaki koşullar altında bildirimleri:</span><span class="sxs-lookup"><span data-stu-id="1e7a5-104">This manifests under the following conditions:</span></span><ul><li><span data-ttu-id="1e7a5-105"><xref:System.Windows.Controls.TreeViewItem?displayProperty=name>ın visual üst bir panel değil.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-105"><xref:System.Windows.Controls.TreeViewItem?displayProperty=name>'s visual parent is not a panel.</span></span> <span data-ttu-id="1e7a5-106">(A <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> için oluşturulan bir <xref:System.Windows.Controls.TreeView?displayProperty=name> Masası kendi üst gerekir)</span><span class="sxs-lookup"><span data-stu-id="1e7a5-106">(A <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> generated for a <xref:System.Windows.Controls.TreeView?displayProperty=name> will have a panel as its parent)</span></span></li><li><span data-ttu-id="1e7a5-107"><xref:System.Windows.Controls.TreeViewItem?displayProperty=name> Alt öğesi olan bir <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> gören &quot;öğeleri konak&quot; liste denetimi (ListBox, DataGrid, ListView, vb.) için.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-107">The <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> is a descendant of a <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> acting as the &quot;items host&quot; for a list control (ListBox, DataGrid, ListView, etc.).</span></span> <span data-ttu-id="1e7a5-108">Sanallaştırma etkinleştirilmesi gerekmez.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-108">Virtualization doesn't need to be enabled.</span></span></li><li><span data-ttu-id="1e7a5-109"><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> Öğesi kaydırma olduğu (<code>ScrollUnit=&quot;Item&quot;</code>).</span><span class="sxs-lookup"><span data-stu-id="1e7a5-109">The <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> is item-scrolling (<code>ScrollUnit=&quot;Item&quot;</code>).</span></span></li><li><span data-ttu-id="1e7a5-110">Birisi çağırır <code>VirtualizingStackPanel.MakeVisible(v)</code> öğenin kaydırma <code>v</code> gelsin.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-110">Someone calls <code>VirtualizingStackPanel.MakeVisible(v)</code> to scroll an element <code>v</code> into view.</span></span> <span data-ttu-id="1e7a5-111">Bu açık veya örtülü olarak çeşitli şekillerde yapılabilir; belki de en yaygın şekilde yalnızca tıklayarak <code>v</code> klavye odağını vermek için.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-111">This can be done explicitly, or implicitly in a number of ways; perhaps the most common way is simply clicking on <code>v</code> to give it the keyboard focus.</span></span></li><li><span data-ttu-id="1e7a5-112">Visual üst zincirinden <code>v</code> için <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> geçtiği <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-112">The visual-parent chain from <code>v</code> to the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> passes through the <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>.</span></span></li></ul><span data-ttu-id="1e7a5-113">Diğer bir deyişle, bu görülür, bir <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> dışında kullanılan bir <xref:System.Windows.Controls.TreeView?displayProperty=name>, ve kullanıcı bir alt öğesi üzerinde <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> görünüme getirmek için.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-113">In other words, this is seen when a <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> is used outside of a <xref:System.Windows.Controls.TreeView?displayProperty=name>, and the user clicks on a descendant of the <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> to bring it into view.</span></span> <span data-ttu-id="1e7a5-114">Varsa <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> odaklanabilir hiçbir alt öğelere sahip, bu sorunu hiçbir zaman görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-114">If the <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> has no focusable descendants, you'll never see this issue.</span></span> <span data-ttu-id="1e7a5-115">Bir örneği burada bu isabet bir durum olduğunda bir <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> DataTemplate köküdür.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-115">An example of a situation where this is hit is when a <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> is the root of a DataTemplate.</span></span> <span data-ttu-id="1e7a5-116">Bu sorunu gelindiğinde WPF Framework'te oluşan bir InvalidCastException yoktur.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-116">When this issue is hit, there is an InvalidCastException that occurs within the WPF framework.</span></span>|
|<span data-ttu-id="1e7a5-117">Öneri</span><span class="sxs-lookup"><span data-stu-id="1e7a5-117">Suggestion</span></span>|<span data-ttu-id="1e7a5-118">Bir düzeltme bu kullanıma sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-118">A hotfix will be made available for this.</span></span>|
|<span data-ttu-id="1e7a5-119">Kapsam</span><span class="sxs-lookup"><span data-stu-id="1e7a5-119">Scope</span></span>|<span data-ttu-id="1e7a5-120">Küçük</span><span class="sxs-lookup"><span data-stu-id="1e7a5-120">Minor</span></span>|
|<span data-ttu-id="1e7a5-121">Sürüm</span><span class="sxs-lookup"><span data-stu-id="1e7a5-121">Version</span></span>|<span data-ttu-id="1e7a5-122">4,5</span><span class="sxs-lookup"><span data-stu-id="1e7a5-122">4.5</span></span>|
|<span data-ttu-id="1e7a5-123">Tür</span><span class="sxs-lookup"><span data-stu-id="1e7a5-123">Type</span></span>|<span data-ttu-id="1e7a5-124">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="1e7a5-124">Runtime</span></span>|
