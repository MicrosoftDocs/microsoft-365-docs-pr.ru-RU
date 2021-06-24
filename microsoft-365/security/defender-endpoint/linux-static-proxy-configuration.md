---
title: Microsoft Defender для конечной точки при обнаружении статического прокси-сервера Linux
ms.reviewer: ''
description: Описывает, как настроить Microsoft Defender для конечной точки на Linux для обнаружения статического прокси-сервера.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, proxy
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6dca58070d21271ffc832bcd628679303736f99e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108144"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Настройка Microsoft Defender для конечной точки в Linux для обнаружения статических прокси-серверов

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender для конечной точки может открыть прокси-сервер с помощью ```HTTPS_PROXY``` переменной среды. Этот параметр необходимо настроить как **во** время установки, так и после установки продукта.

## <a name="installation-time-configuration"></a>Конфигурация времени установки

Во время установки ```HTTPS_PROXY``` переменная среды должна быть передана диспетчеру пакетов. Диспетчер пакетов может читать эту переменную любым из следующих способов:

- Переменная ```HTTPS_PROXY``` определяется в ```/etc/environment``` следующей строке:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- Переменная `HTTPS_PROXY` определяется в глобальной конфигурации диспетчера пакетов. Например, в Ubuntu 18.04 можно добавить следующую `/etc/apt/apt.conf.d/proxy.conf` строку:
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Обратите внимание, что выше двух методов можно определить прокси-сервер для использования для других приложений в вашей системе. Используйте этот метод с осторожностью или только в том случае, если он предназначен для глобальной конфигурации.
  
- Переменная предоплачена к командам установки или `HTTPS_PROXY` деинсталлации. Например, с помощью диспетчера пакетов APT при установке Microsoft Defender для конечной точки предопламеняйте переменную следующим образом: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Не добавляйте судо между определением переменной среды и apt, в противном случае переменная не будет распространяться.

Переменная `HTTPS_PROXY` среды также может быть определена во время деинсталлации.

Обратите внимание, что установка и удалить не обязательно сбой, если прокси-сервер не требуется, но не настроен. Однако телеметрия не будет отправлена, и операция может занять гораздо больше времени из-за времени работы сети.

## <a name="post-installation-configuration"></a>Конфигурация установки post
  
После установки `HTTPS_PROXY` переменная среды должна быть определена в файле службы Defender для конечных точек. Для этого откройте в `/lib/systemd/system/mdatp.service` текстовом редакторе во время работы в качестве корневого пользователя. Затем переменную можно распространять в службу одним из двух способов:

    > [!NOTE]
    > On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.

- Откажитесь от строки `#Environment="HTTPS_PROXY=http://address:port"` и укажите свой статичный прокси-адрес.

- Добавьте строку `EnvironmentFile=/path/to/env/file` . Этот путь может указать на или настраиваемый файл, любой из которых должен `/etc/environment` добавить следующую строку:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

После изменения файла `mdatp.service` сохраните и закройте его. Перезапустите службу, чтобы можно было применить изменения. В Ubuntu это включает две команды:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
