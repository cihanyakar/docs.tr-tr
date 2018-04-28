### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a><span data-ttu-id="538b4-101">Yanlış kod oluşturma geçirme ve UInt16 değerleri karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="538b4-101">Incorrect code generation when passing and comparing UInt16 values</span></span>

|   |   |
|---|---|
|<span data-ttu-id="538b4-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="538b4-102">Details</span></span>|<span data-ttu-id="538b4-103">Bazı durumlarda .NET Framework 4.7 sunulan değişiklikler nedeniyle, .NET Framework 4.7 üzerinde hatalı çalışan uygulamalardaki JIT Derleyici tarafından üretilen kod iki karşılaştırır <code>T:System.UInt16</code> değerleri.</span><span class="sxs-lookup"><span data-stu-id="538b4-103">Because of changes introduced in the .NET Framework 4.7, in some cases the code generated by the JIT compiler in applications running on the .NET Framework 4.7 incorrectly compares two <code>T:System.UInt16</code> values.</span></span> <span data-ttu-id="538b4-104">Daha fazla bilgi için bkz: [sorunu #11508: geçirme ve karşılaştırma ushort args sessiz hatalı codegen](https://github.com/dotnet/coreclr/issues/11508) Github.com'u üzerinde.</span><span class="sxs-lookup"><span data-stu-id="538b4-104">For more information, see [Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) on GitHub.com.</span></span>|
|<span data-ttu-id="538b4-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="538b4-105">Suggestion</span></span>|<span data-ttu-id="538b4-106">.NET Framework 4.7 16 bit işaretsiz değerleri karşılaştırma sorunlarla karşılaşırsanız, .NET Framework 4.7.1 yükseltin.</span><span class="sxs-lookup"><span data-stu-id="538b4-106">If you encounter issues in the comparison of 16-bit unsigned values in the .NET Framework 4.7, upgrade to the .NET Framework 4.7.1.</span></span>|
|<span data-ttu-id="538b4-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="538b4-107">Scope</span></span>|<span data-ttu-id="538b4-108">Kenar</span><span class="sxs-lookup"><span data-stu-id="538b4-108">Edge</span></span>|
|<span data-ttu-id="538b4-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="538b4-109">Version</span></span>|<span data-ttu-id="538b4-110">4.7</span><span class="sxs-lookup"><span data-stu-id="538b4-110">4.7</span></span>|
|<span data-ttu-id="538b4-111">Tür</span><span class="sxs-lookup"><span data-stu-id="538b4-111">Type</span></span>|<span data-ttu-id="538b4-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="538b4-112">Runtime</span></span>|
