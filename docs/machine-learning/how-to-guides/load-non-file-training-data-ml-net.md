---
title: Metin dosyasında olmayan veri ile bir makine öğrenmesi modeli eğitme - ML.NET
description: ML.NET'i dosyada olmayan eğitim verisi kullanarak, tahmin amaçlı bir makine öğrenmesi modelinin iş hattında nasıl kullanacağınızı keşfedin.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 971c5c62acc9dd7bf29aa11ce898c2b76822c3d7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125408"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>Metin dosyasında olmayan veri ile bir makine öğrenmesi modeli eğitme - ML.NET

ML.NET için yaygın olarak gösterilen kullanım senaryosu, eğitim verilerini bir dosyadan okumak için `TextLoader`'ı kullanmaktır.
Ancak, pratikte eğitim verileri farklı kaynaklardan gelebilir. Bu kaynaklar aşağıdaki gibi olabilir:

* SQL tablolarından
* Log dosyalarından ayıklanan
* Çalışma sırasında oluşturulan

Kullanım [şema kavramayı](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) varolan getirmek için C# `IEnumerable` ML.NET içine bir `DataView`.

Bu örnekte, müşteri karmaşıklığı tahmin modeli ve aşağıdaki özellikleri ayıklama üretim sisteminizde oluşturacaksınız:

* Müşteri Kimliği (model tarafından göz ardı)
* Müşteri (hedef 'etiketi') çoğaltılmaları olup olmadığı
* 'Demografik kategori' ('genç yetişkin' gibi bir dize vs.)
* Son 5 gün ziyaret sayısı.

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

Bu veri yükleme `DataView` ve aşağıdaki kodu kullanarak bir model eğitip:

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
