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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187725"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a>Развертывание обновлений для Microsoft Defender для конечной точки для Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.

> [!WARNING]
> Каждая версия Defender для конечной точки для Linux имеет срок действия, после которого он больше не будет продолжать защищать ваше устройство. Необходимо обновить продукт до этой даты. Чтобы проверить срок действия, запустите следующую команду:
> ```bash
> mdatp health --field product_expiration
> ```

Чтобы обновить defender for Endpoint для Linux вручную, выполните одну из следующих команд:

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
