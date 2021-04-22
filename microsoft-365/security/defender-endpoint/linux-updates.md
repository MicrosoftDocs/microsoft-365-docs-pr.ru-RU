---
title: Развертывание обновлений для Microsoft Defender для конечной точки в Linux
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
ms.openlocfilehash: 9cb0c7375b538f502cf6165f13c68fd4b2fdcc64
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934757"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Развертывание обновлений для Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.

> [!WARNING]
> Каждая версия Defender для конечной точки на Linux имеет срок действия, после которого оно больше не будет продолжать защищать ваше устройство. Необходимо обновить продукт до этой даты. Чтобы проверить срок действия, запустите следующую команду:
> ```bash
> mdatp health --field product_expiration
> ```

Чтобы обновить Defender для конечной точки на Linux вручную, выполните одну из следующих команд:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL и варианты (CentOS и Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES и варианты

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Системы Ubuntu и Debian

```bash
sudo apt-get install --only-upgrade mdatp
```
