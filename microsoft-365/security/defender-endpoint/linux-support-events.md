---
title: Устранение неполадок с отсутствующих событиями или оповещений о проблемах atP Microsoft Defender для Linux
description: Устранение неполадок, отсутствующих событий или оповещений о проблемах в MICROSOFT Defender ATP для Linux.
keywords: Microsoft, defender, atp, linux, events
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
ms.openlocfilehash: e489d5bece292065ad2e82a7eb9011747733b4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073742"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="9905d-104">Устранение неполадок с отсутствующих событиями или оповещений о проблемах для Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="9905d-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9905d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9905d-105">**Applies to:**</span></span>

- [<span data-ttu-id="9905d-106">Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="9905d-106">Microsoft Defender for Endpoint for Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="9905d-107">В этой статье приводится ряд общих действий по снижению отсутствующих событий или оповещений на [портале центра](https://securitycenter.windows.com/) безопасности.</span><span class="sxs-lookup"><span data-stu-id="9905d-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="9905d-108">После **правильного установки** microsoft Defender для конечной  точки на устройстве на портале будет сгенерирована страница устройства.</span><span class="sxs-lookup"><span data-stu-id="9905d-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="9905d-109">Вы можете просмотреть все записанные события на вкладке Timeline на странице устройства или на странице предварительной охоты.</span><span class="sxs-lookup"><span data-stu-id="9905d-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="9905d-110">В этом разделе устраняется случай, когда отсутствуют некоторые или все ожидаемые события.</span><span class="sxs-lookup"><span data-stu-id="9905d-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="9905d-111">Например, если отсутствуют все _события CreatedFile._</span><span class="sxs-lookup"><span data-stu-id="9905d-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="9905d-112">Отсутствующие события сети и входа</span><span class="sxs-lookup"><span data-stu-id="9905d-112">Missing network and login events</span></span>

<span data-ttu-id="9905d-113">Microsoft Defender для конечной точки использовал `audit` фреймворки из Linux для отслеживания сетевой и входной активности.</span><span class="sxs-lookup"><span data-stu-id="9905d-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="9905d-114">Убедитесь, что структура аудита работает.</span><span class="sxs-lookup"><span data-stu-id="9905d-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="9905d-115">ожидаемый выход:</span><span class="sxs-lookup"><span data-stu-id="9905d-115">expected output:</span></span>

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

2. <span data-ttu-id="9905d-116">Если `auditd` отмечено как остановлено, запустите его.</span><span class="sxs-lookup"><span data-stu-id="9905d-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="9905d-117">**В системах SLES** аудит SYSCALL может быть отключен по умолчанию и может быть учтен для отсутствующих `auditd` событий.</span><span class="sxs-lookup"><span data-stu-id="9905d-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="9905d-118">Чтобы проверить, что аудит SYSCALL не отключен, перечислить текущие правила аудита:</span><span class="sxs-lookup"><span data-stu-id="9905d-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="9905d-119">если следующая строка присутствует, удалите ее или отредактировать, чтобы microsoft Defender для конечной точки отслеживала определенные SYSCALLs.</span><span class="sxs-lookup"><span data-stu-id="9905d-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="9905d-120">Правила аудита расположены по адресу `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="9905d-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="9905d-121">Отсутствующие события файлов</span><span class="sxs-lookup"><span data-stu-id="9905d-121">Missing file events</span></span>

<span data-ttu-id="9905d-122">События файлов собираются с помощью `fanotify` фреймворка.</span><span class="sxs-lookup"><span data-stu-id="9905d-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="9905d-123">В случае, если некоторые или все события файла отсутствуют, убедитесь, что включено на устройстве и `fanotify` поддерживается файловая [система.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="9905d-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="9905d-124">Список файловойсистемы на компьютере с помощью:</span><span class="sxs-lookup"><span data-stu-id="9905d-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
