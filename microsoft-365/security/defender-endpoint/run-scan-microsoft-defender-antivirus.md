---
title: Запуск и настройка сканирования по запросу в антивирусная программа в Microsoft Defender
description: Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения
keywords: сканирование, по требованию, dos, intune, моментальное сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789175"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="53454-104">Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию.</span><span class="sxs-lookup"><span data-stu-id="53454-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="53454-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="53454-105">**Applies to:**</span></span>

- [<span data-ttu-id="53454-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="53454-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="53454-107">Можно выполнить проверку по запросу на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="53454-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="53454-108">Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип.</span><span class="sxs-lookup"><span data-stu-id="53454-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="53454-109">Быстрое сканирование по сравнению с полным сканированием</span><span class="sxs-lookup"><span data-stu-id="53454-109">Quick scan versus full scan</span></span>

<span data-ttu-id="53454-110">Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрировано вредоносное ПО, например ключи реестра и известные папки Windows запуска.</span><span class="sxs-lookup"><span data-stu-id="53454-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53454-111">антивирусная программа в Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования.</span><span class="sxs-lookup"><span data-stu-id="53454-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="53454-112">Для сканирования сети используется контекст учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="53454-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="53454-113">Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать.</span><span class="sxs-lookup"><span data-stu-id="53454-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="53454-114">Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.</span><span class="sxs-lookup"><span data-stu-id="53454-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="53454-115">В сочетании [с возможностью](configure-real-time-protection-microsoft-defender-antivirus.md)защиты в режиме реального времени быстрое сканирование позволяет обеспечить широкое освещение вредоносных программ, которые начинаются с вредоносных программ на уровне системы и на уровне ядра.</span><span class="sxs-lookup"><span data-stu-id="53454-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="53454-116">Всегда в режиме реального времени файлы защиты рассматриваются при их открытом и закрытом режиме, а также при переходе пользователя в папку.</span><span class="sxs-lookup"><span data-stu-id="53454-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="53454-117">По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.</span><span class="sxs-lookup"><span data-stu-id="53454-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="53454-118">В большинстве случаев для обнаружения вредоносных программ, которые не были подхватлены защитой в режиме реального времени, достаточно быстрой проверки.</span><span class="sxs-lookup"><span data-stu-id="53454-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="53454-119">Полное сканирование может быть полезно при сообщении об угрозе вредоносных программ на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="53454-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="53454-120">Проверка может определить, есть ли какие-либо неактивные компоненты, которые требуют более тщательной очистки.</span><span class="sxs-lookup"><span data-stu-id="53454-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="53454-121">Однако Корпорация Майкрософт обычно рекомендует использовать быстрые проверки вместо полного сканирования.</span><span class="sxs-lookup"><span data-stu-id="53454-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="53454-122">Полное сканирование может занять несколько часов или дней в зависимости от количества и типа данных, которые необходимо отсканировать.</span><span class="sxs-lookup"><span data-stu-id="53454-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="53454-123">Дополнительные дополнительные информацию о различиях между быстрым и полным сканированием см. в обзоре Быстрого сканирования и полного сканирования [и настраиваемой проверки.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="53454-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="53454-124">Использование Microsoft Endpoint Manager для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="53454-125">Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="53454-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="53454-126">Выберите **антивирус безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="53454-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="53454-127">В списке вкладок выберите Windows 10 **нездоровые конечные точки.**</span><span class="sxs-lookup"><span data-stu-id="53454-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="53454-128">Из представленного списка действий выберите **быстрое** сканирование или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="53454-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="53454-129">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="53454-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="53454-130">Дополнительные сведения об использовании Microsoft Endpoint Manager для выполнения проверки см. в статью [Antimalware and firewall tasks: How to perform an on-demand scan.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="53454-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="53454-131">Используйте утилиту mpcmdrun.exe командной строки для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="53454-132">Используйте следующий `-scan` параметр:</span><span class="sxs-lookup"><span data-stu-id="53454-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="53454-133">Дополнительные сведения об использовании средства и дополнительных параметров, включая запуск полного сканирования или определение путей, см. в mpcmdrun.exe средства командной линии для настройки и управления [антивирусная программа в Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="53454-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="53454-134">Используйте Microsoft Intune для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="53454-135">Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="53454-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="53454-136">На боковой панели выберите **устройства > все устройства** и выберите устройство, которое необходимо сканировать.</span><span class="sxs-lookup"><span data-stu-id="53454-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="53454-137">Выберите **... Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="53454-137">Select **...More**.</span></span> <span data-ttu-id="53454-138">Из параметров выберите **быстрое сканирование** или **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="53454-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="53454-139">Используйте приложение Безопасность Windows для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="53454-140">См. [в приложении Run a scan in the Безопасность Windows](microsoft-defender-security-center-antivirus.md) инструкции по запуску сканирования на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="53454-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="53454-141">Чтобы выполнить сканирование, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="53454-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="53454-142">Используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="53454-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="53454-143">Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="53454-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="53454-144">Используйте Windows управления (WMI) для запуска сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="53454-145">Используйте метод [ **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) **класса MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="53454-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="53454-146">Дополнительные сведения о том, какие параметры разрешены, см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="53454-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="53454-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="53454-147">Related articles</span></span>

- [<span data-ttu-id="53454-148">Настройка параметров сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="53454-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="53454-149">Настройка запланированных антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="53454-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="53454-150">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="53454-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)