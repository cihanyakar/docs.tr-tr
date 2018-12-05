---
title: Bir metin dosyasına - ML.NET olmayan veriler ile machine learning modeli eğitme
description: ML.NET machine learning modeli eğitimi tahmin işlem hattının parçası olarak dosya olmayan eğitim verilerini yüklemek için nasıl kullanılacağını keşfedin.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 971c5c62acc9dd7bf29aa11ce898c2b76822c3d7
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672088"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="eff04-103">Bir metin dosyasına - ML.NET olmayan veriler ile machine learning modeli eğitme</span><span class="sxs-lookup"><span data-stu-id="eff04-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

<span data-ttu-id="eff04-104">ML.NET kanıtlanabilir yaygın olarak kullanıldığı yerler kullanılmasıdır `TextLoader` eğitim verilerini bir dosyadan okuma için.</span><span class="sxs-lookup"><span data-stu-id="eff04-104">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="eff04-105">Ancak, gerçek zamanlı eğitim senaryolarda veri başka bir yerde, aşağıdaki gibi olabilir:</span><span class="sxs-lookup"><span data-stu-id="eff04-105">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="eff04-106">SQL tablolarında</span><span class="sxs-lookup"><span data-stu-id="eff04-106">in SQL tables</span></span>
* <span data-ttu-id="eff04-107">günlük dosyalarından ayıklanan</span><span class="sxs-lookup"><span data-stu-id="eff04-107">extracted from log files</span></span>
* <span data-ttu-id="eff04-108">çalışma sırasında oluşturulan</span><span class="sxs-lookup"><span data-stu-id="eff04-108">generated on the fly</span></span>

<span data-ttu-id="eff04-109">Kullanım [şema kavramayı](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) varolan getirmek için C# `IEnumerable` ML.NET içine bir `DataView`.</span><span class="sxs-lookup"><span data-stu-id="eff04-109">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="eff04-110">Bu örnekte, müşteri karmaşıklığı tahmin modeli ve aşağıdaki özellikleri ayıklama üretim sisteminizde oluşturacaksınız:</span><span class="sxs-lookup"><span data-stu-id="eff04-110">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="eff04-111">Müşteri Kimliği (model tarafından göz ardı)</span><span class="sxs-lookup"><span data-stu-id="eff04-111">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="eff04-112">Müşteri (hedef 'etiketi') çoğaltılmaları olup olmadığı</span><span class="sxs-lookup"><span data-stu-id="eff04-112">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="eff04-113">'Demografik kategori' ('genç yetişkin' gibi bir dize vs.)</span><span class="sxs-lookup"><span data-stu-id="eff04-113">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="eff04-114">Son 5 gün ziyaret sayısı.</span><span class="sxs-lookup"><span data-stu-id="eff04-114">The number of visits from the last 5 days.</span></span>

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

<span data-ttu-id="eff04-115">Bu veri yükleme `DataView` ve aşağıdaki kodu kullanarak bir model eğitip:</span><span class="sxs-lookup"><span data-stu-id="eff04-115">Load this data into the `DataView` and train the model, using the following code:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.CreateStreamingDataView(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```