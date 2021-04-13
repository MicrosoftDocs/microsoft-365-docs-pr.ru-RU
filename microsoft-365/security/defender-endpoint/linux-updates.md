---
title: Развертывание обновлений для ATP Защитника Майкрософт для Linux
ms.reviewer: ''
description: Описывает, как развертывать обновления для ATP Microsoft Defender для Linux в корпоративных средах.
keywords: Microsoft, defender, atp, Linux, updates, deploy
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
ms.openlocfilehash: 2e4ea4942446317aef90288da9fb181935503fa9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687470"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="3e391-104">Развертывание обновлений для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="3e391-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3e391-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e391-105">**Applies to:**</span></span>
- [<span data-ttu-id="3e391-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e391-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3e391-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e391-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e391-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3e391-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3e391-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3e391-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="3e391-110">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="3e391-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="3e391-111">Каждая версия Defender для конечной точки для Linux имеет срок действия, после которого он больше не будет продолжать защищать ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="3e391-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="3e391-112">Необходимо обновить продукт до этой даты.</span><span class="sxs-lookup"><span data-stu-id="3e391-112">You must update the product prior to this date.</span></span> <span data-ttu-id="3e391-113">Чтобы проверить срок действия, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e391-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="3e391-114">Чтобы обновить defender for Endpoint для Linux вручную, выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="3e391-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="3e391-115">RHEL и варианты (CentOS и Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="3e391-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="3e391-116">SLES и варианты</span><span class="sxs-lookup"><span data-stu-id="3e391-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="3e391-117">Системы Ubuntu и Debian</span><span class="sxs-lookup"><span data-stu-id="3e391-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
