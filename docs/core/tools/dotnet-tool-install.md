---
title: DotNet aracı yükleme komutu
description: Dotnet araç belirtilen .NET Core genel aracı komut yükler makinenize yükleyin.
ms.date: 05/29/2018
ms.openlocfilehash: 251e7b04be96ac2340727fa03dbaa2d548110fa9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168721"
---
# <a name="dotnet-tool-install"></a>DotNet aracı yükleme

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>Ad

`dotnet tool install` -Belirtilen yükler [.NET Core genel aracı](global-tools.md) makinenizde.

## <a name="synopsis"></a>Özeti

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Açıklama

`dotnet tool install` Komutu, makinenizde .NET Core genel Araçları'nı yüklemek bir yol sağlar. Komutunu kullanmak için ya da kullanarak bir kullanıcı genelinde yükleme istediğinizi belirtmek zorunda `--global` kullanarak yüklemek için bir yol belirtin veya seçeneği `--tool-path` seçeneği.

Genel araçları yüklü aşağıdaki dizinlerindeki varsayılan olarak belirttiğinizde `-g` (veya `--global`) seçeneği:

| İşletim Sistemi          | Yol                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a>Arguments

`PACKAGE_NAME`

.NET Core genel yüklemek için aracı içeren NuGet paket adı/kimliği.

## <a name="options"></a>Seçenekler

`--add-source <SOURCE>`

Yükleme sırasında kullanmak üzere ek bir NuGet paket kaynağı ekler.

`--configfile <FILE>`

NuGet yapılandırma (*nuget.config*) dosyasını kullanın.

`--framework <FRAMEWORK>`

Belirtir [hedef Framework'ü](../../standard/frameworks.md) için aracı yüklemek için. Varsayılan olarak, .NET Core SDK'sını en uygun hedef Framework'ü seçmek çalışır.

`-g|--global`

Yükleme kullanıcı geniş olduğunu belirtir. İle birleştirilemez `--tool-path` seçeneği. Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--tool-path` seçeneği.

`-h|--help`

Komut için kısa bir Yardım yazdırır.

`--tool-path <PATH>`

Genel aracı yükleneceği konumu belirtir. YOL mutlak veya göreli olabilir. YOL mevcut değilse komut onu oluşturmaya çalışır. İle birleştirilemez `--global` seçeneği. Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--global` seçeneği.

`-v|--verbosity <LEVEL>`

Komutun ayrıntı düzeyini ayarlar. İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.

`--version <VERSION_NUMBER>`

Yüklenecek aracı sürümü. Varsayılan olarak, en son kararlı Paket sürümü yüklenir. Önizleme veya aracın eski sürümlerini yüklemek için bu seçeneği kullanın.

## <a name="examples"></a>Örnekler

Yükler [dotnetsay](https://www.nuget.org/packages/dotnetsay/) genel araç varsayılan konumda:

`dotnet tool install -g dotnetsay`

Yükler [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli bir Windows klasöründeki Genel aracı:

`dotnet tool install dotnetsay --tool-path c:\global-tools`

Yükler [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli bir Linux/macOS klasöründe genel aracı:

`dotnet tool install dotnetsay --tool-path ~/bin`

2.0.0 sürümü yükler [dotnetsay](https://www.nuget.org/packages/dotnetsay/) genel aracı:

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a>Ayrıca bkz.

* [.NET core Araçları Genel](global-tools.md)