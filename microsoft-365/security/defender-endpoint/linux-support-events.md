---
title: Устранение неполадок с отсутствующих событиями или оповещений о проблемах для Microsoft Defender для конечной точки в Linux
description: Устранение неполадок, отсутствующих событий или оповещений о проблемах в Microsoft Defender для конечной точки на Linux.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, events
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933317"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Устранение неполадок с отсутствующих событиями или оповещений о проблемах для Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки в Linux](microsoft-defender-endpoint-linux.md)

В этой статье приводится ряд общих действий по снижению отсутствующих событий или оповещений на [портале центра](https://securitycenter.windows.com/) безопасности.

После **правильного установки** microsoft Defender для конечной  точки на устройстве на портале будет сгенерирована страница устройства. Вы можете просмотреть все записанные события на вкладке Timeline на странице устройства или на странице предварительной охоты. В этом разделе устраняется случай, когда отсутствуют некоторые или все ожидаемые события.
Например, если отсутствуют все _события CreatedFile._

## <a name="missing-network-and-login-events"></a>Отсутствующие события сети и входа

Microsoft Defender для конечной точки использовал `audit` фреймворки из Linux для отслеживания сетевой и входной активности.

1. Убедитесь, что структура аудита работает.

    ```bash
    service auditd status
    ```

    ожидаемый выход:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Если `auditd` отмечено как остановлено, запустите его.

    ```bash
    service auditd start
    ```

**В системах SLES** аудит SYSCALL может быть отключен по умолчанию и может быть учтен для отсутствующих `auditd` событий.

1. Чтобы проверить, что аудит SYSCALL не отключен, перечислить текущие правила аудита:

    ```bash
    sudo auditctl -l
    ```

    если следующая строка присутствует, удалите ее или отредактировать, чтобы microsoft Defender для конечной точки отслеживала определенные SYSCALLs.

    ```output
    -a task, never
    ```

    Правила аудита расположены по адресу `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Отсутствующие события файлов

События файлов собираются с помощью `fanotify` фреймворка. В случае, если некоторые или все события файла отсутствуют, убедитесь, что включено на устройстве и `fanotify` поддерживается файловая [система.](microsoft-defender-endpoint-linux.md#system-requirements)

Список файловойсистемы на компьютере с помощью:

```bash
df -Th
```
