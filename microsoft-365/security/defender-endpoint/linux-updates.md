---
title: Развертывание обновлений Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Описывает развертывание обновлений для Microsoft Defender для конечной точки на Linux в корпоративных средах.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, updates, deploy
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274728"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="10c17-104">Развертывание обновлений Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="10c17-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="10c17-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="10c17-105">**Applies to:**</span></span>
- [<span data-ttu-id="10c17-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="10c17-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10c17-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10c17-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="10c17-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="10c17-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10c17-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="10c17-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="10c17-110">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="10c17-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="10c17-111">Каждая версия Defender для конечной точки на Linux имеет срок действия, после которого оно больше не будет продолжать защищать ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="10c17-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="10c17-112">Необходимо обновить продукт до этой даты.</span><span class="sxs-lookup"><span data-stu-id="10c17-112">You must update the product prior to this date.</span></span> <span data-ttu-id="10c17-113">Чтобы проверить срок действия, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="10c17-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="10c17-114">Общедоступные возможности Microsoft Defender для конечных точек эквивалентны независимо от канала обновления, используемого для развертывания (Beta (Insider), Preview (External), Current (Production)).</span><span class="sxs-lookup"><span data-stu-id="10c17-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="10c17-115">Чтобы обновить Defender для конечной точки на Linux вручную, выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="10c17-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="10c17-116">RHEL и варианты (CentOS и Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="10c17-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="10c17-117">SLES и варианты</span><span class="sxs-lookup"><span data-stu-id="10c17-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="10c17-118">Системы Ubuntu и Debian</span><span class="sxs-lookup"><span data-stu-id="10c17-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
