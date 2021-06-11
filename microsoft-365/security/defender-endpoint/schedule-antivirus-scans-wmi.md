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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="26afc-104">Расписание антивирусных сканов с Windows инструментов управления (WMI)</span><span class="sxs-lookup"><span data-stu-id="26afc-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="26afc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="26afc-105">**Applies to:**</span></span>

- [<span data-ttu-id="26afc-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="26afc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="26afc-107">В этой статье описывается настройка запланированных сканов с помощью WMI.</span><span class="sxs-lookup"><span data-stu-id="26afc-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="26afc-108">Дополнительные новости о планировании сканирования и типах сканирования см. в обзоре [Configure scheduled quick or full антивирусная программа в Microsoft Defender проверки.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="26afc-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="26afc-109">Используйте Windows управления (WMI) для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="26afc-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="26afc-110">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="26afc-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="26afc-111">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="26afc-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="26afc-112">WMI для планирования сканирования, когда конечная точка не используется</span><span class="sxs-lookup"><span data-stu-id="26afc-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="26afc-113">Используйте [метод Set класса MSFT_MpPreference для](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="26afc-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="26afc-114">Дополнительные сведения об API и разрешенных параметрах см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="26afc-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="26afc-115">Когда вы запланируете сканирование на периоды, когда конечные точки не используются, сканы не будут соблюдать конфигурацию регулирования ЦП и будут в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="26afc-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="26afc-116">WMI для планирования сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="26afc-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="26afc-117">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="26afc-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="26afc-118">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="26afc-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="26afc-119">WMI для планирования ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="26afc-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="26afc-120">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="26afc-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="26afc-121">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="26afc-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

