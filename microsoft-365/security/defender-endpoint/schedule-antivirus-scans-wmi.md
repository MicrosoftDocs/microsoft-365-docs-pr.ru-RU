---
title: Расписание антивирусных сканов с Windows инструментов управления
description: Расписание антивирусных сканов с использованием WMI
keywords: быстрое сканирование, полное сканирование, WMI, расписание, антивирус
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879770"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Расписание антивирусных сканов с Windows инструментов управления (WMI)

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В этой статье описывается настройка запланированных сканов с помощью WMI. Дополнительные новости о планировании сканирования и типах сканирования см. в обзоре [Configure scheduled quick or full антивирусная программа в Microsoft Defender проверки.](schedule-antivirus-scans.md) 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Используйте Windows управления (WMI) для расписания сканирования

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI для планирования сканирования, когда конечная точка не используется

Используйте [метод Set класса MSFT_MpPreference для](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) следующих свойств:

```WMI
ScanOnlyIfIdleEnabled
```

Дополнительные сведения об API и разрешенных параметрах см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> Когда вы запланируете сканирование на периоды, когда конечные точки не используются, сканы не будут соблюдать конфигурацию регулирования ЦП и будут в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI для планирования сканирования для завершения восстановления

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-daily-scans"></a>WMI для планирования ежедневных сканов

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
ScanScheduleQuickScanTime
```

Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

