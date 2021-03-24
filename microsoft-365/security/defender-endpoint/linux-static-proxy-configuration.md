---
title: Microsoft Defender ATP для обнаружения статического прокси-сервера Linux
ms.reviewer: ''
description: Описывает настройку ATP Защитника Майкрософт для обнаружения статических прокси.
keywords: Microsoft, defender, atp, linux, installation, proxy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 841e5d5169469edb804514458760c5f52e66edaa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073757"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a><span data-ttu-id="1f0b5-104">Настройка Microsoft Defender для конечной точки для Linux для обнаружения статических прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="1f0b5-104">Configure Microsoft Defender for Endpoint for Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1f0b5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1f0b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f0b5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1f0b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1f0b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f0b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1f0b5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1f0b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1f0b5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1f0b5-110">ATP Microsoft Defender может открыть прокси-сервер с помощью ```HTTPS_PROXY``` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="1f0b5-111">Этот параметр необходимо настроить как **во** время установки, так и после установки продукта.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="1f0b5-112">Конфигурация времени установки</span><span class="sxs-lookup"><span data-stu-id="1f0b5-112">Installation time configuration</span></span>

<span data-ttu-id="1f0b5-113">Во время установки ```HTTPS_PROXY``` переменная среды должна быть передана диспетчеру пакетов.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="1f0b5-114">Диспетчер пакетов может читать эту переменную любым из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="1f0b5-115">Переменная ```HTTPS_PROXY``` определяется в ```/etc/environment``` следующей строке:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="1f0b5-116">Переменная `HTTPS_PROXY` определяется в глобальной конфигурации диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="1f0b5-117">Например, в Ubuntu 18.04 можно добавить следующую `/etc/apt/apt.conf.d/proxy.conf` строку:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="1f0b5-118">Обратите внимание, что выше двух методов можно определить прокси-сервер для использования для других приложений в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="1f0b5-119">Используйте этот метод с осторожностью или только в том случае, если он предназначен для глобальной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="1f0b5-120">Переменная предоплачена к командам установки или `HTTPS_PROXY` деинсталлации.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="1f0b5-121">Например, с помощью диспетчера пакетов APT при установке Microsoft Defender для конечной точки предопламеняйте переменную следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="1f0b5-122">Не добавляйте судо между определением переменной среды и apt, в противном случае переменная не будет распространяться.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="1f0b5-123">Переменная `HTTPS_PROXY` среды также может быть определена во время деинсталлации.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="1f0b5-124">Обратите внимание, что установка и удалить не обязательно сбой, если прокси-сервер не требуется, но не настроен.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="1f0b5-125">Однако телеметрия не будет отправлена, и операция может занять гораздо больше времени из-за времени работы сети.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="1f0b5-126">Конфигурация установки post</span><span class="sxs-lookup"><span data-stu-id="1f0b5-126">Post installation configuration</span></span>
  
<span data-ttu-id="1f0b5-127">После установки `HTTPS_PROXY` переменная среды должна быть определена в файле службы Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="1f0b5-128">Для этого откройте в `/lib/systemd/system/mdatp.service` текстовом редакторе во время работы в качестве корневого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="1f0b5-129">Затем переменную можно распространять в службу одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="1f0b5-130">Откажитесь от строки `#Environment="HTTPS_PROXY=http://address:port"` и укажите свой статичный прокси-адрес.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="1f0b5-131">Добавьте строку `EnvironmentFile=/path/to/env/file` .</span><span class="sxs-lookup"><span data-stu-id="1f0b5-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="1f0b5-132">Этот путь может указать на или настраиваемый файл, любой из которых должен `/etc/environment` добавить следующую строку:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="1f0b5-133">После изменения файла `mdatp.service` сохраните и закройте его.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="1f0b5-134">Перезапустите службу, чтобы можно было применить изменения.</span><span class="sxs-lookup"><span data-stu-id="1f0b5-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="1f0b5-135">В Ubuntu это включает две команды:</span><span class="sxs-lookup"><span data-stu-id="1f0b5-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
