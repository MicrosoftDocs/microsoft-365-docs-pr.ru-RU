---
title: Регулярное быстрое и полное сканирование с помощью антивируса Microsoft Defender
description: Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.
keywords: быстрое сканирование, полное сканирование, быстрый vs полный, сканирование расписания, ежедневно, еженедельно, время, запланированное, повторяющиеся, регулярные
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691302"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="6bb44-104">Настройка запланированных быстрых или полных антивирусных сканов Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6bb44-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6bb44-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6bb44-105">**Applies to:**</span></span>

- [<span data-ttu-id="6bb44-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6bb44-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="6bb44-107">Антивирус Microsoft Defender по умолчанию проверяет обновление за 15 минут до времени запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="6bb44-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="6bb44-108">Для [переопределения](manage-protection-update-schedule-microsoft-defender-antivirus.md) этого по умолчанию можно управлять расписанием загрузки обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="6bb44-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="6bb44-109">Помимо постоянной защиты в режиме [](run-scan-microsoft-defender-antivirus.md) реального времени и проверки по запросу можно настроить регулярные запланированные проверки.</span><span class="sxs-lookup"><span data-stu-id="6bb44-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="6bb44-110">Вы можете настроить тип сканирования, когда должно происходить сканирование, и [](manage-protection-updates-microsoft-defender-antivirus.md) если сканирование должно происходить после обновления защиты или если используется конечная точка.</span><span class="sxs-lookup"><span data-stu-id="6bb44-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="6bb44-111">Вы также можете указать, когда должны происходить специальные проверки для завершения восстановления.</span><span class="sxs-lookup"><span data-stu-id="6bb44-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="6bb44-112">В этой статье описывается настройка запланированных сканов с помощью групповая политика, cmdlets PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="6bb44-113">Вы также можете настроить проверки расписания с [помощью Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) или Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="6bb44-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="6bb44-114">Настройка параметров групповой политики, описанных в этой статье</span><span class="sxs-lookup"><span data-stu-id="6bb44-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="6bb44-115">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6bb44-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="6bb44-116">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="6bb44-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="6bb44-117">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="6bb44-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="6bb44-118">Расширь дерево до компонентов **Windows > антивируса Microsoft Defender** и далее в указанном ниже расположении. </span><span class="sxs-lookup"><span data-stu-id="6bb44-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="6bb44-119">Дважды щелкните параметр **политики,** указанный в таблице ниже, и установите параметр в нужную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6bb44-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="6bb44-120">Нажмите **кнопку ОК** и повторите для любых других параметров.</span><span class="sxs-lookup"><span data-stu-id="6bb44-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="6bb44-121">Также см. [раздел Управление,](manage-protection-update-schedule-microsoft-defender-antivirus.md) когда обновления защиты должны быть загружены и применены, и Запретить или разрешить пользователям локально изменять [параметры политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6bb44-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="6bb44-122">Быстрое сканирование по сравнению с полным сканированием и пользовательским сканированием</span><span class="sxs-lookup"><span data-stu-id="6bb44-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="6bb44-123">При настройках плановой проверки можно настроить полное или быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="6bb44-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="6bb44-124">При быстром сканировании просматриваются все расположения, в которых могут быть зарегистрированы вредоносные программы, например ключи реестра и известные папки запуска Windows.</span><span class="sxs-lookup"><span data-stu-id="6bb44-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="6bb44-125">В сочетании с возможностью защиты в режиме реального [времени,](configure-real-time-protection-microsoft-defender-antivirus.md) которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование помогает обеспечить широкое освещение вредоносных программ, которые начинаются с системной и вредоносной программы на уровне ядра.</span><span class="sxs-lookup"><span data-stu-id="6bb44-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="6bb44-126">В большинстве случаев это означает, что для обнаружения вредоносных программ, которые не были подхватлены средствами защиты в режиме реального времени, достаточно быстрой проверки.</span><span class="sxs-lookup"><span data-stu-id="6bb44-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="6bb44-127">Полное сканирование может быть полезно для конечных точек, которые столкнулись с угрозой вредоносных программ, чтобы определить, есть ли какие-либо неактивные компоненты, которые требуют более тщательной очистки.</span><span class="sxs-lookup"><span data-stu-id="6bb44-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="6bb44-128">В этом случае при запуске проверки по запросу может потребоваться полное [сканирование.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6bb44-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="6bb44-129">Настраиваемая проверка позволяет указать файлы и папки для сканирования, например USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="6bb44-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="6bb44-130">По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.</span><span class="sxs-lookup"><span data-stu-id="6bb44-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="6bb44-131">Настройка запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="6bb44-131">Set up scheduled scans</span></span>

<span data-ttu-id="6bb44-132">Запланированные проверки будут запускаться в течение дня и времени, за который вы указываете.</span><span class="sxs-lookup"><span data-stu-id="6bb44-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="6bb44-133">Для настройки запланированных сканов можно использовать групповую политику, PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="6bb44-134">Если компьютер отключен и запущен на батарее во время запланированного полного сканирования, запланированное сканирование остановится с событием 1002, в котором говорится, что проверка остановлена до завершения.</span><span class="sxs-lookup"><span data-stu-id="6bb44-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="6bb44-135">Антивирус Microsoft Defender запустит полное сканирование в назначенное время.</span><span class="sxs-lookup"><span data-stu-id="6bb44-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="6bb44-136">Использование групповой политики для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="6bb44-137">Расположение</span><span class="sxs-lookup"><span data-stu-id="6bb44-137">Location</span></span> | <span data-ttu-id="6bb44-138">Setting</span><span class="sxs-lookup"><span data-stu-id="6bb44-138">Setting</span></span> | <span data-ttu-id="6bb44-139">Описание</span><span class="sxs-lookup"><span data-stu-id="6bb44-139">Description</span></span> | <span data-ttu-id="6bb44-140">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="6bb44-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="6bb44-141">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-141">Scan</span></span> | <span data-ttu-id="6bb44-142">Укажите тип сканирования, который необходимо использовать для запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="6bb44-143">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="6bb44-143">Quick scan</span></span> |
|<span data-ttu-id="6bb44-144">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-144">Scan</span></span> | <span data-ttu-id="6bb44-145">Укажите день недели для запуска запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="6bb44-146">Укажите день (или никогда) для запуска сканирования.</span><span class="sxs-lookup"><span data-stu-id="6bb44-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="6bb44-147">Никогда</span><span class="sxs-lookup"><span data-stu-id="6bb44-147">Never</span></span> |
|<span data-ttu-id="6bb44-148">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-148">Scan</span></span> | <span data-ttu-id="6bb44-149">Укажите время суток для запуска запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="6bb44-150">Укажите количество минут после полуночи (например, введите **60** для 1:00).</span><span class="sxs-lookup"><span data-stu-id="6bb44-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="6bb44-151">02:00.</span><span class="sxs-lookup"><span data-stu-id="6bb44-151">2 a.m.</span></span> |
|<span data-ttu-id="6bb44-152">Root</span><span class="sxs-lookup"><span data-stu-id="6bb44-152">Root</span></span> | <span data-ttu-id="6bb44-153">Рандомизация запланированного времени задач</span><span class="sxs-lookup"><span data-stu-id="6bb44-153">Randomize scheduled task times</span></span> |<span data-ttu-id="6bb44-154">В антивирусе Microsoft Defender: рандомизируйте время начала сканирования с интервалом от 0 до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="6bb44-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="6bb44-155">В FEP/SCEP: рандомизировать любой интервал плюс или минус 30 минут.</span><span class="sxs-lookup"><span data-stu-id="6bb44-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="6bb44-156">Это может быть полезно в развертываниях VM или VDI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="6bb44-157">Включено</span><span class="sxs-lookup"><span data-stu-id="6bb44-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="6bb44-158">Использование cmdlets PowerShell для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="6bb44-159">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6bb44-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="6bb44-160">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6bb44-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="6bb44-161">Использование инструкции по управлению Windows (WMI) для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="6bb44-162">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6bb44-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="6bb44-163">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6bb44-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6bb44-164">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6bb44-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="6bb44-165">Запуск запланированных сканов только в том случае, если конечная точка не используется</span><span class="sxs-lookup"><span data-stu-id="6bb44-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="6bb44-166">Вы можете настроить запланированное сканирование только при включении конечной точки, но не в использовании с групповой политикой, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="6bb44-167">Эти проверки не будут соблюдать конфигурацию регулирования ЦП и в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="6bb44-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="6bb44-168">Использование групповой политики для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="6bb44-169">Расположение</span><span class="sxs-lookup"><span data-stu-id="6bb44-169">Location</span></span> | <span data-ttu-id="6bb44-170">Setting</span><span class="sxs-lookup"><span data-stu-id="6bb44-170">Setting</span></span> | <span data-ttu-id="6bb44-171">Описание</span><span class="sxs-lookup"><span data-stu-id="6bb44-171">Description</span></span> | <span data-ttu-id="6bb44-172">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="6bb44-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="6bb44-173">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-173">Scan</span></span> | <span data-ttu-id="6bb44-174">Запуск запланированного сканирования только в том случае, если компьютер находится на компьютере, но не используется</span><span class="sxs-lookup"><span data-stu-id="6bb44-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="6bb44-175">Запланированные проверки не будут запускаться, если компьютер не работает, но не используется</span><span class="sxs-lookup"><span data-stu-id="6bb44-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="6bb44-176">Включено</span><span class="sxs-lookup"><span data-stu-id="6bb44-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="6bb44-177">Использование cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bb44-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="6bb44-178">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6bb44-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="6bb44-179">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6bb44-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="6bb44-180">Использование инструкции по управлению Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="6bb44-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="6bb44-181">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6bb44-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="6bb44-182">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6bb44-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6bb44-183">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6bb44-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="6bb44-184">Настройка при запуске полного сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="6bb44-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="6bb44-185">Для устранения и устранения некоторых угроз может потребоваться полное сканирование.</span><span class="sxs-lookup"><span data-stu-id="6bb44-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="6bb44-186">Вы можете запланировать, когда эти проверки должны происходить с помощью групповой политики, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="6bb44-187">Использование групповой политики для расписания сканов, необходимых для восстановления</span><span class="sxs-lookup"><span data-stu-id="6bb44-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="6bb44-188">Расположение</span><span class="sxs-lookup"><span data-stu-id="6bb44-188">Location</span></span> | <span data-ttu-id="6bb44-189">Setting</span><span class="sxs-lookup"><span data-stu-id="6bb44-189">Setting</span></span> | <span data-ttu-id="6bb44-190">Описание</span><span class="sxs-lookup"><span data-stu-id="6bb44-190">Description</span></span> | <span data-ttu-id="6bb44-191">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="6bb44-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="6bb44-192">Исправление</span><span class="sxs-lookup"><span data-stu-id="6bb44-192">Remediation</span></span> | <span data-ttu-id="6bb44-193">Укажите день недели для выполнения запланированного полного сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="6bb44-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="6bb44-194">Укажите день (или никогда) для запуска сканирования.</span><span class="sxs-lookup"><span data-stu-id="6bb44-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="6bb44-195">Никогда</span><span class="sxs-lookup"><span data-stu-id="6bb44-195">Never</span></span> |
|<span data-ttu-id="6bb44-196">Исправление</span><span class="sxs-lookup"><span data-stu-id="6bb44-196">Remediation</span></span> | <span data-ttu-id="6bb44-197">Укажите время суток для выполнения запланированного полного сканирования, чтобы завершить исправление</span><span class="sxs-lookup"><span data-stu-id="6bb44-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="6bb44-198">Укажите количество минут после полуночи (например, введите **60** в час ночи)</span><span class="sxs-lookup"><span data-stu-id="6bb44-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="6bb44-199">02:00.</span><span class="sxs-lookup"><span data-stu-id="6bb44-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="6bb44-200">Использование cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bb44-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="6bb44-201">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6bb44-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="6bb44-202">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6bb44-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="6bb44-203">Использование инструкции по управлению Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="6bb44-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="6bb44-204">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6bb44-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="6bb44-205">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6bb44-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6bb44-206">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6bb44-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="6bb44-207">Настройка ежедневных быстрых сканов</span><span class="sxs-lookup"><span data-stu-id="6bb44-207">Set up daily quick scans</span></span>

<span data-ttu-id="6bb44-208">Вы можете включить ежедневное быстрое сканирование, которое можно выполнить в дополнение к другим запланированным проверкам с помощью групповой политики, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="6bb44-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="6bb44-209">Использование групповой политики для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="6bb44-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="6bb44-210">Расположение</span><span class="sxs-lookup"><span data-stu-id="6bb44-210">Location</span></span> | <span data-ttu-id="6bb44-211">Setting</span><span class="sxs-lookup"><span data-stu-id="6bb44-211">Setting</span></span> | <span data-ttu-id="6bb44-212">Описание</span><span class="sxs-lookup"><span data-stu-id="6bb44-212">Description</span></span> | <span data-ttu-id="6bb44-213">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="6bb44-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="6bb44-214">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-214">Scan</span></span> | <span data-ttu-id="6bb44-215">Укажите интервал для быстрого сканирования в день</span><span class="sxs-lookup"><span data-stu-id="6bb44-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="6bb44-216">Укажите, сколько часов должно быть у вас до следующего быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="6bb44-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="6bb44-217">Например, чтобы выполнить каждые два часа, введите **2**, раз в день введите **24**.</span><span class="sxs-lookup"><span data-stu-id="6bb44-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="6bb44-218">Введите **0,** чтобы никогда не запускать ежедневное быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="6bb44-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="6bb44-219">Никогда</span><span class="sxs-lookup"><span data-stu-id="6bb44-219">Never</span></span> |
|<span data-ttu-id="6bb44-220">Проверка</span><span class="sxs-lookup"><span data-stu-id="6bb44-220">Scan</span></span> | <span data-ttu-id="6bb44-221">Укажите время ежедневного быстрого сканирования</span><span class="sxs-lookup"><span data-stu-id="6bb44-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="6bb44-222">Укажите количество минут после полуночи (например, введите **60** в час ночи)</span><span class="sxs-lookup"><span data-stu-id="6bb44-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="6bb44-223">02:00.</span><span class="sxs-lookup"><span data-stu-id="6bb44-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="6bb44-224">Использование cmdlets PowerShell для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="6bb44-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="6bb44-225">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6bb44-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="6bb44-226">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6bb44-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="6bb44-227">Использование инструкции по управлению Windows (WMI) для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="6bb44-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="6bb44-228">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6bb44-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="6bb44-229">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6bb44-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6bb44-230">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6bb44-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="6bb44-231">Включить сканирование после обновления защиты</span><span class="sxs-lookup"><span data-stu-id="6bb44-231">Enable scans after protection updates</span></span>

<span data-ttu-id="6bb44-232">Проверку можно принудить к проверке после [каждого обновления защиты](manage-protection-updates-microsoft-defender-antivirus.md) с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="6bb44-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="6bb44-233">Использование групповой политики для расписания сканирования после обновления защиты</span><span class="sxs-lookup"><span data-stu-id="6bb44-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="6bb44-234">Расположение</span><span class="sxs-lookup"><span data-stu-id="6bb44-234">Location</span></span> | <span data-ttu-id="6bb44-235">Setting</span><span class="sxs-lookup"><span data-stu-id="6bb44-235">Setting</span></span> | <span data-ttu-id="6bb44-236">Описание</span><span class="sxs-lookup"><span data-stu-id="6bb44-236">Description</span></span> | <span data-ttu-id="6bb44-237">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="6bb44-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="6bb44-238">Обновления подписи</span><span class="sxs-lookup"><span data-stu-id="6bb44-238">Signature updates</span></span> | <span data-ttu-id="6bb44-239">Включив сканирование после обновления сведении безопасности</span><span class="sxs-lookup"><span data-stu-id="6bb44-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="6bb44-240">Сканирование будет происходить сразу после загрузки нового обновления защиты</span><span class="sxs-lookup"><span data-stu-id="6bb44-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="6bb44-241">Включено</span><span class="sxs-lookup"><span data-stu-id="6bb44-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="6bb44-242">См. также</span><span class="sxs-lookup"><span data-stu-id="6bb44-242">See also</span></span>
- [<span data-ttu-id="6bb44-243">Предотвращение или разрешение пользователям локально изменять параметры политики</span><span class="sxs-lookup"><span data-stu-id="6bb44-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6bb44-244">Настройка и запуск антивирусных сканов Microsoft Defender по запросу</span><span class="sxs-lookup"><span data-stu-id="6bb44-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6bb44-245">Настройка параметров антивирусного сканирования Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6bb44-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6bb44-246">Управление обновлениями антивируса Microsoft Defender и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="6bb44-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6bb44-247">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="6bb44-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="6bb44-248">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="6bb44-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)