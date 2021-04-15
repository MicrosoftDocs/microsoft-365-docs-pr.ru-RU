---
title: Запуск и настройка проверки по запросу в microsoft Defender AV
description: Запуск и настройка сканирования по запросу с помощью PowerShell, инструментов управления Windows или отдельно на конечных точках с помощью приложения Безопасности Windows
keywords: сканирование, по требованию, dos, intune, моментальное сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 976531e1b7e1b87c4cd2dd2af66f294f68c5d4f1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764403"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="8e991-104">Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию.</span><span class="sxs-lookup"><span data-stu-id="8e991-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e991-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8e991-105">**Applies to:**</span></span>

- [<span data-ttu-id="8e991-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8e991-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8e991-107">Можно выполнить проверку по запросу на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="8e991-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="8e991-108">Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип.</span><span class="sxs-lookup"><span data-stu-id="8e991-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="8e991-109">Быстрое сканирование по сравнению с полным сканированием</span><span class="sxs-lookup"><span data-stu-id="8e991-109">Quick scan versus full scan</span></span>

<span data-ttu-id="8e991-110">Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрирована вредоносная программа, например ключи реестра и известные папки запуска Windows.</span><span class="sxs-lookup"><span data-stu-id="8e991-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e991-111">Антивирус Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования.</span><span class="sxs-lookup"><span data-stu-id="8e991-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="8e991-112">Для сканирования сети используется контекст учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="8e991-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="8e991-113">Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать.</span><span class="sxs-lookup"><span data-stu-id="8e991-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="8e991-114">Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.</span><span class="sxs-lookup"><span data-stu-id="8e991-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="8e991-115">В [](configure-real-time-protection-microsoft-defender-antivirus.md)сочетании с возможностью защиты в режиме реального времени , которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование обеспечивает высокий уровень защиты как для вредоносных программ, которые начинаются с системного, так и для вредоносных программ на уровне ядра.</span><span class="sxs-lookup"><span data-stu-id="8e991-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="8e991-116">В большинстве случаев для обнаружения вредоносных программ, которые не были подхватлены защитой в режиме реального времени, достаточно быстрой проверки.</span><span class="sxs-lookup"><span data-stu-id="8e991-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="8e991-117">Полное сканирование может быть полезно для конечных точек, которые сообщили об угрозе вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="8e991-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="8e991-118">Сканирование может определить, есть ли неактивные компоненты, которые требуют более тщательной очистки.</span><span class="sxs-lookup"><span data-stu-id="8e991-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="8e991-119">Это идеальное решение, если ваша организация работает по запросу.</span><span class="sxs-lookup"><span data-stu-id="8e991-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="8e991-120">По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.</span><span class="sxs-lookup"><span data-stu-id="8e991-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="8e991-121">Используйте Microsoft Endpoint Manager для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="8e991-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="8e991-122">Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="8e991-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="8e991-123">Выберите **антивирус безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="8e991-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="8e991-124">В списке вкладок выберите **windows 10 нездоровые конечные точки.**</span><span class="sxs-lookup"><span data-stu-id="8e991-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="8e991-125">Из представленного списка действий выберите **быстрое** сканирование или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="8e991-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="8e991-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8e991-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="8e991-127">Дополнительные сведения об использовании Microsoft Endpoint Manager для выполнения проверки см. в статью Задачи по борьбе с антивирусом и брандмауэром: как выполнить проверку по [запросу.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="8e991-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="8e991-128">Используйте утилиту mpcmdrun.exe командной строки для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="8e991-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="8e991-129">Используйте следующий `-scan` параметр:</span><span class="sxs-lookup"><span data-stu-id="8e991-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="8e991-130">Дополнительные сведения об использовании средства и дополнительных параметров, включая запуск полного сканирования или определение путей, см. в mpcmdrun.exe средства командной линии для настройки и управления антивирусом [Microsoft Defender.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8e991-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="8e991-131">Используйте Microsoft Intune для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="8e991-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="8e991-132">Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="8e991-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="8e991-133">На боковой панели выберите **устройства > все устройства** и выберите устройство, которое необходимо сканировать.</span><span class="sxs-lookup"><span data-stu-id="8e991-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="8e991-134">Выберите **... Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="8e991-134">Select **...More**.</span></span> <span data-ttu-id="8e991-135">Из параметров выберите **быстрое сканирование** или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="8e991-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="8e991-136">С помощью приложения Windows Security можно выполнить сканирование</span><span class="sxs-lookup"><span data-stu-id="8e991-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="8e991-137">См. [в приложении Run a scan in the Windows Security](microsoft-defender-security-center-antivirus.md) для инструкций по запуску сканирования на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="8e991-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="8e991-138">Чтобы выполнить сканирование, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e991-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="8e991-139">Используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8e991-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="8e991-140">Дополнительные сведения о том, как использовать PowerShell с антивирусной программой Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="8e991-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="8e991-141">Использование инструкции по управлению Windows (WMI) для проверки</span><span class="sxs-lookup"><span data-stu-id="8e991-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="8e991-142">Используйте метод [ **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) **класса MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="8e991-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="8e991-143">Дополнительные сведения о том, какие параметры разрешены, см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="8e991-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="8e991-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8e991-144">Related articles</span></span>

- [<span data-ttu-id="8e991-145">Настройка параметров сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8e991-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e991-146">Настройка запланированных антивирусных сканов Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8e991-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e991-147">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="8e991-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)