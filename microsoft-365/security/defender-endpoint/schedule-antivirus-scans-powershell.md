---
title: Расписание антивирусных сканов с помощью PowerShell
description: Расписание антивирусных сканов с помощью PowerShell
keywords: быстрое сканирование, полное сканирование, антивирус, расписание, PowerShell
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
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879775"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Расписание антивирусных сканов с помощью PowerShell

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В этой статье описывается настройка запланированных сканирований с помощью cmdlets PowerShell. Дополнительные новости о планировании сканирования и типах сканирования см. в обзоре [Configure scheduled quick or full антивирусная программа в Microsoft Defender проверки.](schedule-antivirus-scans.md) 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Использование cmdlets PowerShell для расписания сканирования

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Дополнительные сведения см. в дополнительных сведениях о том, как [](/powershell/module/defender/) использовать [cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусная программа в Microsoft Defender и defender для получения дополнительных сведений о том, как использовать PowerShell с антивирусная программа в Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Cmdlets PowerShell для планирования сканирования, когда конечная точка не используется

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

> [!NOTE]
> Когда вы запланируете сканирование на периоды, когда конечные точки не используются, сканы не будут соблюдать конфигурацию регулирования ЦП и будут в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Cmdlets PowerShell для планирования сканирования для завершения восстановления

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Cmdlets PowerShell для планирования ежедневных сканов

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)


