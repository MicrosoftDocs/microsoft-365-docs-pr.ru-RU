---
title: Просмотр результатов проверки авт.) Microsoft Defender
description: Просмотрите результаты сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или приложения безопасности Windows
keywords: результаты сканирования, исправление, полное сканирование, быстрое сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764149"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="3cc97-104">Просмотр результатов проверки антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3cc97-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3cc97-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3cc97-105">**Applies to:**</span></span>

- [<span data-ttu-id="3cc97-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3cc97-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3cc97-107">После завершения антивирусного сканирования Защитника Майкрософт, [](run-scan-microsoft-defender-antivirus.md) будь то проверка по запросу или запланированное, [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)результаты записывают, и вы можете просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="3cc97-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="3cc97-108">Использование диспетчера конфигурации для проверки результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="3cc97-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="3cc97-109">Узнайте, [как отслеживать состояние защиты конечных точек.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="3cc97-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="3cc97-110">Использование cmdlets PowerShell для проверки результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="3cc97-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="3cc97-111">Следующий кодлет возвращает каждое обнаружение на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="3cc97-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="3cc97-112">Если существует несколько обнаружения одной и той же угрозы, каждое обнаружение будет перечислены отдельно, в зависимости от времени каждого обнаружения:</span><span class="sxs-lookup"><span data-stu-id="3cc97-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![снимок экрана cmdlets и выходов PowerShell](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="3cc97-114">Можно указать, чтобы ограничить выход только для обнаружения `-ThreatID` определенной угрозы.</span><span class="sxs-lookup"><span data-stu-id="3cc97-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="3cc97-115">Если вы хотите перечислить обнаружения угроз, но объединить обнаружения одной и той же угрозы в один элемент, можно использовать следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3cc97-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![скриншот PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="3cc97-117">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="3cc97-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="3cc97-118">Использование инструкции по управлению Windows (WMI) для проверки результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="3cc97-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="3cc97-119">Используйте [ **метод Get** классов **MSFT_MpThreat** **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="3cc97-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="3cc97-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3cc97-120">Related articles</span></span>

- [<span data-ttu-id="3cc97-121">Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3cc97-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3cc97-122">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="3cc97-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)