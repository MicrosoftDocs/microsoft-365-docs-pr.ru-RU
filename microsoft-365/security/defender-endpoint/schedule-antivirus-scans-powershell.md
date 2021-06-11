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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="207e2-104">Расписание антивирусных сканов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="207e2-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="207e2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="207e2-105">**Applies to:**</span></span>

- [<span data-ttu-id="207e2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="207e2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="207e2-107">В этой статье описывается настройка запланированных сканирований с помощью cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="207e2-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="207e2-108">Дополнительные новости о планировании сканирования и типах сканирования см. в обзоре [Configure scheduled quick or full антивирусная программа в Microsoft Defender проверки.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="207e2-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="207e2-109">Использование cmdlets PowerShell для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="207e2-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="207e2-110">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="207e2-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="207e2-111">Дополнительные сведения см. в дополнительных сведениях о том, как [](/powershell/module/defender/) использовать [cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусная программа в Microsoft Defender и defender для получения дополнительных сведений о том, как использовать PowerShell с антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="207e2-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="207e2-112">Cmdlets PowerShell для планирования сканирования, когда конечная точка не используется</span><span class="sxs-lookup"><span data-stu-id="207e2-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="207e2-113">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="207e2-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="207e2-114">Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="207e2-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="207e2-115">Когда вы запланируете сканирование на периоды, когда конечные точки не используются, сканы не будут соблюдать конфигурацию регулирования ЦП и будут в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="207e2-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="207e2-116">Cmdlets PowerShell для планирования сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="207e2-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="207e2-117">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="207e2-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="207e2-118">Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="207e2-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="207e2-119">Cmdlets PowerShell для планирования ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="207e2-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="207e2-120">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="207e2-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="207e2-121">Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="207e2-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


