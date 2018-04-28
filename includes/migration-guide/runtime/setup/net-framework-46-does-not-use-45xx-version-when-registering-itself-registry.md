### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="acd73-101">.NET Framework 4.6 4.5.x.x sürüm kendisini kayıt defterine kaydedilirken kullanmaz</span><span class="sxs-lookup"><span data-stu-id="acd73-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="acd73-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="acd73-102">Details</span></span>|<span data-ttu-id="acd73-103">Sürüm anahtarı bir bekleyebilirsiniz gibi kayıt defterinde ayarlayın (adresindeki <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) için .NET Framework 4.6 '4.6 ile', '4.5' değil başlar.</span><span class="sxs-lookup"><span data-stu-id="acd73-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="acd73-104">4.6 bir yeni olası sürümüdür ve önceki 4.5.x ile uyumlu bir serbest anlamak için hangi .NET Framework sürümlerinin bir makinede yüklü olduğunu öğrenmek için bu kayıt defteri anahtarları bağımlı uygulamalar güncelleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="acd73-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="acd73-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="acd73-105">Suggestion</span></span>|<span data-ttu-id="acd73-106">.NET Framework 4.5 için yoklama güncelleştirme uygulamalar ayrıca 4.6 kabul etmek 4.5 kayıt defteri anahtarları için bakarak yükleyin.</span><span class="sxs-lookup"><span data-stu-id="acd73-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="acd73-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="acd73-107">Scope</span></span>|<span data-ttu-id="acd73-108">Kenar</span><span class="sxs-lookup"><span data-stu-id="acd73-108">Edge</span></span>|
|<span data-ttu-id="acd73-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="acd73-109">Version</span></span>|<span data-ttu-id="acd73-110">4.6</span><span class="sxs-lookup"><span data-stu-id="acd73-110">4.6</span></span>|
|<span data-ttu-id="acd73-111">Tür</span><span class="sxs-lookup"><span data-stu-id="acd73-111">Type</span></span>|<span data-ttu-id="acd73-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="acd73-112">Runtime</span></span>|
