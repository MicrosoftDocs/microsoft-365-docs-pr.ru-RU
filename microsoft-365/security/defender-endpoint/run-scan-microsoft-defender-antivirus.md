---
title: Запуск и настройка сканирования по запросу в антивирусная программа в Microsoft Defender
description: Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения
keywords: сканирование, по требованию, dos, intune, моментальное сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925735"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="ee01a-104">Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию.</span><span class="sxs-lookup"><span data-stu-id="ee01a-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="ee01a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ee01a-105">**Applies to:**</span></span>

- [<span data-ttu-id="ee01a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ee01a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ee01a-107">Можно выполнить проверку по запросу на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="ee01a-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="ee01a-108">Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип.</span><span class="sxs-lookup"><span data-stu-id="ee01a-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="ee01a-109">При запуске сканирования можно выбрать один из трех типов: быстрое сканирование, полное сканирование и настраиваемая проверка.</span><span class="sxs-lookup"><span data-stu-id="ee01a-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="ee01a-110">В большинстве случаев используйте быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="ee01a-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="ee01a-111">Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрировано вредоносное ПО, например ключи реестра и известные папки Windows запуска.</span><span class="sxs-lookup"><span data-stu-id="ee01a-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="ee01a-112">В сочетании с постоянной защитой в режиме реального времени, которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование помогает обеспечить надувную защиту от вредоносных программ, которые начинаются с системной и вредоносной программы на уровне ядра.</span><span class="sxs-lookup"><span data-stu-id="ee01a-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="ee01a-113">В большинстве случаев достаточно быстрой проверки, что является рекомендуемой возможностью для планового или по требованию сканирования.</span><span class="sxs-lookup"><span data-stu-id="ee01a-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="ee01a-114">[Узнайте больше о типах сканирования.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="ee01a-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee01a-115">антивирусная программа в Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования.</span><span class="sxs-lookup"><span data-stu-id="ee01a-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="ee01a-116">Для сканирования сети используется контекст учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="ee01a-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="ee01a-117">Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать.</span><span class="sxs-lookup"><span data-stu-id="ee01a-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="ee01a-118">Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.</span><span class="sxs-lookup"><span data-stu-id="ee01a-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="ee01a-119">Использование Microsoft Endpoint Manager для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="ee01a-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="ee01a-120">Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="ee01a-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="ee01a-121">Выберите **антивирус безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="ee01a-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="ee01a-122">В списке вкладок выберите Windows 10 **нездоровые конечные точки.**</span><span class="sxs-lookup"><span data-stu-id="ee01a-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="ee01a-123">Из представленного списка действий выберите **быстрый скан** (рекомендуется) или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="ee01a-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="ee01a-124">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ee01a-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="ee01a-125">Дополнительные сведения об использовании Microsoft Endpoint Manager для выполнения проверки см. в статью [Antimalware and firewall tasks: How to perform an on-demand scan.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="ee01a-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="ee01a-126">Используйте утилиту mpcmdrun.exe командной строки для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="ee01a-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="ee01a-127">Используйте следующий `-scan` параметр:</span><span class="sxs-lookup"><span data-stu-id="ee01a-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="ee01a-128">Дополнительные сведения об использовании средства и дополнительных параметров, включая запуск полного сканирования или определение путей, см. в mpcmdrun.exe средства командной линии для настройки и управления [антивирусная программа в Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="ee01a-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="ee01a-129">Используйте Microsoft Intune для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="ee01a-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="ee01a-130">Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="ee01a-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="ee01a-131">На боковой панели выберите **устройства**  >  **всех устройств** и выберите устройство, которое необходимо сканировать.</span><span class="sxs-lookup"><span data-stu-id="ee01a-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="ee01a-132">Выберите **... Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ee01a-132">Select **...More**.</span></span> <span data-ttu-id="ee01a-133">Из параметров выберите **быстрый скан** (рекомендуется) или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="ee01a-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="ee01a-134">Используйте приложение Безопасность Windows для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="ee01a-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="ee01a-135">См. [в приложении Run a scan in the Безопасность Windows](microsoft-defender-security-center-antivirus.md) инструкции по запуску сканирования на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="ee01a-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="ee01a-136">Чтобы выполнить сканирование, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee01a-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="ee01a-137">Используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee01a-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="ee01a-138">Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="ee01a-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="ee01a-139">Используйте Windows управления (WMI) для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="ee01a-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="ee01a-140">Используйте метод [ **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) **класса MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="ee01a-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="ee01a-141">Дополнительные сведения о том, какие параметры разрешены, см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="ee01a-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

