---
title: 使用 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器（基于 Docker 标准）
description: 了解在 Windows 容器中使用 Docker 时如何使用 PowerShell
ms.date: 08/06/2020
ms.openlocfilehash: 4e7b9e7fedf11b97b3f468aef541bf72a4e88ebc
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915393"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>使用 DockerFile 中的 Windows PowerShell 命令来设置 Windows 容器（基于 Docker 标准）

使用 [Windows 容器](/virtualization/windowscontainers/about/index)可将现有 Windows 应用程序转换为 Docker 映像，并使用与 Docker 生态系统其余部分相同的工具进行部署。

要使用 Windows 容器，只需在 DockerFile 中编写 Windows PowerShell 命令，如以下示例所示：

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

在此示例中，我们将使用 Windows PowerShell 来安装 Windows Server Core 基础映像以及 IIS。

同样，也可使用 Windows PowerShell 命令来设置其他组件，如传统的 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件，如下所示：

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[上一页](visual-studio-tools-for-docker.md)
>[下一页](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
