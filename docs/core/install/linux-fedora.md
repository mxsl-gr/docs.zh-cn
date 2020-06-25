---
title: 在 Fedora 上安装 .NET Core - .NET Core
description: 演示在 Fedora 上安装 .NET Core SDK 和 .NET Core 运行时的各种方法。
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 52aa9409ec876e0d1eaef22fb739046941fda897
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602836"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="d76f1-103">在 Fedora 上安装 .NET Core SDK 或 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="d76f1-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="d76f1-104">Fedora 支持 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d76f1-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="d76f1-105">本文介绍如何在 Fedora 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d76f1-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="d76f1-106">如果 Fedora 版本不受支持，则该版本不再支持 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d76f1-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="d76f1-107">不过，这些说明可帮助你在这些版本上运行 .NET Core，即使它不受支持。</span><span class="sxs-lookup"><span data-stu-id="d76f1-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="d76f1-108">支持的发行版</span><span class="sxs-lookup"><span data-stu-id="d76f1-108">Supported distributions</span></span>

<span data-ttu-id="d76f1-109">下表列出了当前支持的 .NET Core 版本以及支持它们的 Fedora 版本。</span><span class="sxs-lookup"><span data-stu-id="d76f1-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="d76f1-110">这些版本在 [.NET Core 版本达到支持终止日期](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)或 [Fedora 版本达到生命周期](https://fedoraproject.org/wiki/End_of_life)之前仍受支持。</span><span class="sxs-lookup"><span data-stu-id="d76f1-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="d76f1-111">✔️ 指示 Fedora 或 .NET Core 版本仍受支持。</span><span class="sxs-lookup"><span data-stu-id="d76f1-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="d76f1-112">❌ 指示 Fedora 或 .NET Core 版本在该 Fedora 版本上不受支持。</span><span class="sxs-lookup"><span data-stu-id="d76f1-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="d76f1-113">当 Fedora 版本和 .NET Core 版本都有 ✔️ 时，将支持该 OS 和 .NET 组合。</span><span class="sxs-lookup"><span data-stu-id="d76f1-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="d76f1-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="d76f1-114">Fedora</span></span>                   | <span data-ttu-id="d76f1-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-115">.NET Core 2.1</span></span> | <span data-ttu-id="d76f1-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-116">.NET Core 3.1</span></span> | <span data-ttu-id="d76f1-117">.NET 5 预览版（仅限手动安装）</span><span class="sxs-lookup"><span data-stu-id="d76f1-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="d76f1-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="d76f1-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-119">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-120">✔️ 3.1</span></span>        | <span data-ttu-id="d76f1-121">✔️ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="d76f1-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="d76f1-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-123">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-124">✔️ 3.1</span></span>        | <span data-ttu-id="d76f1-125">✔️ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="d76f1-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="d76f1-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-127">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-128">✔️ 3.1</span></span>        | <span data-ttu-id="d76f1-129">❌ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="d76f1-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="d76f1-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-131">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-132">✔️ 3.1</span></span>        | <span data-ttu-id="d76f1-133">❌ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="d76f1-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="d76f1-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-135">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-136">❌ 3.1</span></span>        | <span data-ttu-id="d76f1-137">❌ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="d76f1-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="d76f1-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="d76f1-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-139">✔️ 2.1</span></span>        | <span data-ttu-id="d76f1-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="d76f1-140">❌ 3.1</span></span>        | <span data-ttu-id="d76f1-141">❌ 5.0 预览版</span><span class="sxs-lookup"><span data-stu-id="d76f1-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="d76f1-142">以下版本的 .NET Core 不再受到支持。</span><span class="sxs-lookup"><span data-stu-id="d76f1-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="d76f1-143">这些版本的下载仍保持发布状态：</span><span class="sxs-lookup"><span data-stu-id="d76f1-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="d76f1-144">3.0</span><span class="sxs-lookup"><span data-stu-id="d76f1-144">3.0</span></span>
- <span data-ttu-id="d76f1-145">2.2</span><span class="sxs-lookup"><span data-stu-id="d76f1-145">2.2</span></span>
- <span data-ttu-id="d76f1-146">2.0</span><span class="sxs-lookup"><span data-stu-id="d76f1-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d76f1-147">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="d76f1-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="d76f1-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="d76f1-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="d76f1-149">.NET Core 3.1 在 Fedora 32 的默认包存储库中提供。</span><span class="sxs-lookup"><span data-stu-id="d76f1-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="d76f1-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="d76f1-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="d76f1-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="d76f1-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="d76f1-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="d76f1-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="d76f1-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="d76f1-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="d76f1-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="d76f1-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d76f1-155">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="d76f1-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="d76f1-156">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d76f1-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d76f1-157">未能提取</span><span class="sxs-lookup"><span data-stu-id="d76f1-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="d76f1-158">Snap</span><span class="sxs-lookup"><span data-stu-id="d76f1-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="d76f1-159">依赖项</span><span class="sxs-lookup"><span data-stu-id="d76f1-159">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="d76f1-160">脚本安装</span><span class="sxs-lookup"><span data-stu-id="d76f1-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="d76f1-161">手动安装</span><span class="sxs-lookup"><span data-stu-id="d76f1-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="d76f1-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d76f1-162">Next steps</span></span>

- [<span data-ttu-id="d76f1-163">教程：使用 Visual Studio Code 通过 .NET Core SDK 创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d76f1-163">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)