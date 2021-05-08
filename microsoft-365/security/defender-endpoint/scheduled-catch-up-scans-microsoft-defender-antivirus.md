---
title: Запланируйте регулярные быстрые и полные проверки с помощью антивирусная программа в Microsoft Defender
description: Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.
keywords: быстрое сканирование, полное сканирование, быстрый vs полный, сканирование расписания, ежедневно, еженедельно, время, запланированное, повторяющиеся, регулярные
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245904"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="69d1f-104">Настройка запланированного быстрого или полного сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="69d1f-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="69d1f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="69d1f-105">**Applies to:**</span></span>

- [<span data-ttu-id="69d1f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="69d1f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="69d1f-107">По умолчанию антивирусная программа в Microsoft Defender для обновления за 15 минут до времени запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="69d1f-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="69d1f-108">Для [переопределения](manage-protection-update-schedule-microsoft-defender-antivirus.md) этого по умолчанию можно управлять расписанием загрузки обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="69d1f-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="69d1f-109">Помимо постоянной защиты в режиме [](run-scan-microsoft-defender-antivirus.md) реального времени и проверки по запросу можно настроить регулярные запланированные проверки.</span><span class="sxs-lookup"><span data-stu-id="69d1f-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="69d1f-110">Вы можете настроить тип сканирования, когда должно происходить сканирование, и [](manage-protection-updates-microsoft-defender-antivirus.md) если сканирование должно происходить после обновления защиты или если используется конечная точка.</span><span class="sxs-lookup"><span data-stu-id="69d1f-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="69d1f-111">Вы также можете указать, когда должны происходить специальные проверки для завершения восстановления.</span><span class="sxs-lookup"><span data-stu-id="69d1f-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="69d1f-112">В этой статье описывается настройка запланированных сканов с помощью групповая политика, cmdlets PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="69d1f-113">Вы также можете настроить проверки расписания с [помощью](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) Microsoft Endpoint Configuration Manager [или Microsoft Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="69d1f-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="69d1f-114">Настройка параметров групповой политики, описанных в этой статье</span><span class="sxs-lookup"><span data-stu-id="69d1f-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="69d1f-115">На компьютере управления групповой политикой в редакторе групповой политики перейдите к компьютерной конфигурации Административные шаблоны Windows  >    >  **компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сканирование.**</span><span class="sxs-lookup"><span data-stu-id="69d1f-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="69d1f-116">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="69d1f-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="69d1f-117">Укажите параметры объекта групповой политики и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="69d1f-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="69d1f-118">Повторите действия по 1-4 для каждого параметра, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="69d1f-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="69d1f-119">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="69d1f-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="69d1f-120">Если вам нужна помощь с объектами групповой политики, см. [в справке Создание объекта групповой политики.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="69d1f-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="69d1f-121">Также см. [раздел Управление,](manage-protection-update-schedule-microsoft-defender-antivirus.md) когда обновления защиты должны быть загружены и применены, и Запретить или разрешить пользователям локально изменять [параметры политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="69d1f-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="69d1f-122">Быстрое сканирование по сравнению с полным сканированием и пользовательским сканированием</span><span class="sxs-lookup"><span data-stu-id="69d1f-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="69d1f-123">При настройках плановой проверки можно настроить полное или быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="69d1f-124">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-124">Quick scan</span></span>  |<span data-ttu-id="69d1f-125">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-125">Full scan</span></span>  | <span data-ttu-id="69d1f-126">Настраиваемая проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="69d1f-127">Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрировано вредоносное ПО, например ключи реестра и известные папки Windows запуска.</span><span class="sxs-lookup"><span data-stu-id="69d1f-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="69d1f-128">В большинстве случаев для плановой проверки достаточно быстрой проверки.</span><span class="sxs-lookup"><span data-stu-id="69d1f-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="69d1f-129">Полное сканирование начинается с быстрого сканирования, а затем продолжается последовательной проверкой файлов всех установленных фиксированных дисков и съемных/сетевых дисков (если для этого настроено полное сканирование).</span><span class="sxs-lookup"><span data-stu-id="69d1f-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="69d1f-130">Полное сканирование может занять несколько часов или дней в зависимости от количества и типа данных, которые необходимо отсканировать.</span><span class="sxs-lookup"><span data-stu-id="69d1f-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="69d1f-131">По завершению полного сканирования будет доступна новая разведка безопасности, и необходимо выполнить новое сканирование, чтобы убедиться, что с помощью новой разведки безопасности другие угрозы не будут обнаружены.</span><span class="sxs-lookup"><span data-stu-id="69d1f-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="69d1f-132">Настраиваемая проверка — это быстрое сканирование, которое выполняется на файлах и папках, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="69d1f-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="69d1f-133">Например, вы можете выбрать для сканирования USB-накопителя или определенной папки на локальном диске устройства.</span><span class="sxs-lookup"><span data-stu-id="69d1f-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="69d1f-134">По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.</span><span class="sxs-lookup"><span data-stu-id="69d1f-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="69d1f-135">Как узнать, какой тип сканирования выбрать?</span><span class="sxs-lookup"><span data-stu-id="69d1f-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="69d1f-136">Чтобы выбрать тип сканирования, используйте следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="69d1f-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="69d1f-137">Сценарий</span><span class="sxs-lookup"><span data-stu-id="69d1f-137">Scenario</span></span>  |<span data-ttu-id="69d1f-138">Рекомендуемый тип сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="69d1f-139">Необходимо настроить регулярные запланированные проверки</span><span class="sxs-lookup"><span data-stu-id="69d1f-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="69d1f-140">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-140">Quick scan</span></span> <p><span data-ttu-id="69d1f-141">Быстрое сканирование проверяет процессы, память, профили и определенные расположения на устройстве.</span><span class="sxs-lookup"><span data-stu-id="69d1f-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="69d1f-142">В сочетании [с постоянной защитой](configure-real-time-protection-microsoft-defender-antivirus.md)в режиме реального времени быстрое сканирование позволяет обеспечить широкое освещение вредоносных программ, которые начинаются с вредоносных программ на уровне системы и на уровне ядра.</span><span class="sxs-lookup"><span data-stu-id="69d1f-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="69d1f-143">Защита в режиме реального времени проверяет файлы, когда они открываются и закрываются, а также при переходе пользователя в папку.</span><span class="sxs-lookup"><span data-stu-id="69d1f-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="69d1f-144">Угрозы, такие как вредоносные программы, обнаруживаются на устройстве</span><span class="sxs-lookup"><span data-stu-id="69d1f-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="69d1f-145">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-145">Full scan</span></span> <p><span data-ttu-id="69d1f-146">Полное сканирование поможет определить, есть ли какие-либо неактивные компоненты, которые требуют более тщательной очистки.</span><span class="sxs-lookup"><span data-stu-id="69d1f-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="69d1f-147">Необходимо выполнить проверку [по запросу](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="69d1f-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="69d1f-148">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-148">Full scan</span></span>  <p><span data-ttu-id="69d1f-149">Полное сканирование просматривает все файлы на диске устройства, включая файлы, которые устарели, архивированы и не имеют ежедневного доступа.</span><span class="sxs-lookup"><span data-stu-id="69d1f-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="69d1f-150">Необходимо убедиться, что портативное устройство, например USB-накопитель, не содержит вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="69d1f-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="69d1f-151">Настраиваемая проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-151">Custom scan</span></span> <p><span data-ttu-id="69d1f-152">Настраиваемая проверка позволяет выбрать определенные расположения, папки или файлы и выполняет быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="69d1f-153">Что еще нужно знать о быстром и полном сканировании?</span><span class="sxs-lookup"><span data-stu-id="69d1f-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="69d1f-154">Вредоносные файлы можно хранить в местах, не включенных в быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="69d1f-155">Однако защита всегда в режиме реального времени проверяет все открытые и закрытые файлы, а также все файлы, которые находятся в папках, к ним имеет доступ пользователь.</span><span class="sxs-lookup"><span data-stu-id="69d1f-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="69d1f-156">Сочетание защиты в режиме реального времени и быстрого сканирования помогает обеспечить надувную защиту от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="69d1f-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="69d1f-157">Защита от доступа [](cloud-protection-microsoft-defender-antivirus.md) с облачной защитой обеспечивает проверку всех файлов, доступных в системе, с помощью новейших моделей аналитики безопасности и облачного машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="69d1f-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="69d1f-158">Если защита в режиме реального времени обнаруживает вредоносные программы и размер затронутых файлов не определяется изначально, антивирусная программа в Microsoft Defender в рамках процесса восстановления начинается полное сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="69d1f-159">Полное сканирование может обнаруживать вредоносные файлы, которые не были обнаружены другими сканами, например быстрым сканированием.</span><span class="sxs-lookup"><span data-stu-id="69d1f-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="69d1f-160">Однако полное сканирование может занять некоторое время и использовать ценные системные ресурсы для завершения.</span><span class="sxs-lookup"><span data-stu-id="69d1f-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="69d1f-161">Если устройство находится в автономном режиме в течение длительного периода времени, полное сканирование может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="69d1f-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="69d1f-162">Настройка запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="69d1f-162">Set up scheduled scans</span></span>

<span data-ttu-id="69d1f-163">Запланированные проверки будут запускаться в день и время, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="69d1f-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="69d1f-164">Для настройки запланированных сканов можно использовать групповую политику, PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="69d1f-165">Если устройство отключено и работает на батарее во время запланированного полного сканирования, запланированное сканирование остановится с событием 1002, в котором говорится, что проверка остановлена до завершения.</span><span class="sxs-lookup"><span data-stu-id="69d1f-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="69d1f-166">антивирусная программа в Microsoft Defender будет выполнить полное сканирование в следующее запланированное время.</span><span class="sxs-lookup"><span data-stu-id="69d1f-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="69d1f-167">Использование групповой политики для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="69d1f-168">Расположение</span><span class="sxs-lookup"><span data-stu-id="69d1f-168">Location</span></span> | <span data-ttu-id="69d1f-169">Параметр</span><span class="sxs-lookup"><span data-stu-id="69d1f-169">Setting</span></span> | <span data-ttu-id="69d1f-170">Описание</span><span class="sxs-lookup"><span data-stu-id="69d1f-170">Description</span></span> | <span data-ttu-id="69d1f-171">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="69d1f-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="69d1f-172">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-172">Scan</span></span> | <span data-ttu-id="69d1f-173">Укажите тип сканирования, который необходимо использовать для запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="69d1f-174">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="69d1f-174">Quick scan</span></span> |
|<span data-ttu-id="69d1f-175">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-175">Scan</span></span> | <span data-ttu-id="69d1f-176">Укажите день недели для запуска запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="69d1f-177">Укажите день (или никогда) для запуска сканирования.</span><span class="sxs-lookup"><span data-stu-id="69d1f-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="69d1f-178">Никогда</span><span class="sxs-lookup"><span data-stu-id="69d1f-178">Never</span></span> |
|<span data-ttu-id="69d1f-179">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-179">Scan</span></span> | <span data-ttu-id="69d1f-180">Укажите время суток для запуска запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="69d1f-181">Укажите количество минут после полуночи (например, введите **60** для 1:00).</span><span class="sxs-lookup"><span data-stu-id="69d1f-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="69d1f-182">02:00.</span><span class="sxs-lookup"><span data-stu-id="69d1f-182">2 a.m.</span></span> |
|<span data-ttu-id="69d1f-183">Root</span><span class="sxs-lookup"><span data-stu-id="69d1f-183">Root</span></span> | <span data-ttu-id="69d1f-184">Рандомизация запланированного времени задач</span><span class="sxs-lookup"><span data-stu-id="69d1f-184">Randomize scheduled task times</span></span> |<span data-ttu-id="69d1f-185">В антивирусная программа в Microsoft Defender рандомизируйте время начала сканирования с интервалом от 0 до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="69d1f-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="69d1f-186">В [SCEP](/mem/intune/protect/certificates-scep-configure)случайные сканы для любого интервала плюс или минус 30 минут.</span><span class="sxs-lookup"><span data-stu-id="69d1f-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="69d1f-187">Это может быть полезно в виртуальных машинах или развертываниях VDI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="69d1f-188">Включен</span><span class="sxs-lookup"><span data-stu-id="69d1f-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="69d1f-189">Использование cmdlets PowerShell для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="69d1f-190">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="69d1f-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="69d1f-191">Дополнительные сведения см. в дополнительных сведениях о том, как [](/powershell/module/defender/) использовать [cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусная программа в Microsoft Defender и defender для получения дополнительных сведений о том, как использовать PowerShell с антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="69d1f-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="69d1f-192">Используйте Windows управления (WMI) для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="69d1f-193">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="69d1f-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="69d1f-194">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="69d1f-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="69d1f-195">Запуск запланированных сканов только в том случае, если конечная точка не используется</span><span class="sxs-lookup"><span data-stu-id="69d1f-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="69d1f-196">Вы можете настроить запланированное сканирование только при включении конечной точки, но не в использовании с групповой политикой, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="69d1f-197">Эти проверки не будут соблюдать конфигурацию регулирования ЦП и в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="69d1f-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="69d1f-198">Использование групповой политики для расписания сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="69d1f-199">Расположение</span><span class="sxs-lookup"><span data-stu-id="69d1f-199">Location</span></span> | <span data-ttu-id="69d1f-200">Параметр</span><span class="sxs-lookup"><span data-stu-id="69d1f-200">Setting</span></span> | <span data-ttu-id="69d1f-201">Описание</span><span class="sxs-lookup"><span data-stu-id="69d1f-201">Description</span></span> | <span data-ttu-id="69d1f-202">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="69d1f-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="69d1f-203">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-203">Scan</span></span> | <span data-ttu-id="69d1f-204">Запуск запланированного сканирования только в том случае, если компьютер находится на компьютере, но не используется</span><span class="sxs-lookup"><span data-stu-id="69d1f-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="69d1f-205">Запланированные проверки не будут запускаться, если компьютер не работает, но не используется</span><span class="sxs-lookup"><span data-stu-id="69d1f-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="69d1f-206">Включен</span><span class="sxs-lookup"><span data-stu-id="69d1f-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="69d1f-207">Использование cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d1f-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="69d1f-208">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="69d1f-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="69d1f-209">Дополнительные сведения см. в дополнительных сведениях, которые см. в см. в рублях [Использование cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусная программа в Microsoft Defender и [defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="69d1f-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="69d1f-210">Использование Windows управления (WMI)</span><span class="sxs-lookup"><span data-stu-id="69d1f-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="69d1f-211">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="69d1f-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="69d1f-212">Дополнительные сведения об API и разрешенных параметрах см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="69d1f-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="69d1f-213">Настройка при запуске полного сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="69d1f-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="69d1f-214">Для устранения и устранения некоторых угроз может потребоваться полное сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="69d1f-215">Вы можете указать, когда эти проверки должны происходить с помощью групповой политики, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="69d1f-216">Использование групповой политики для расписания сканов, необходимых для восстановления</span><span class="sxs-lookup"><span data-stu-id="69d1f-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="69d1f-217">Расположение</span><span class="sxs-lookup"><span data-stu-id="69d1f-217">Location</span></span> | <span data-ttu-id="69d1f-218">Параметр</span><span class="sxs-lookup"><span data-stu-id="69d1f-218">Setting</span></span> | <span data-ttu-id="69d1f-219">Описание</span><span class="sxs-lookup"><span data-stu-id="69d1f-219">Description</span></span> | <span data-ttu-id="69d1f-220">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="69d1f-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="69d1f-221">Исправление</span><span class="sxs-lookup"><span data-stu-id="69d1f-221">Remediation</span></span> | <span data-ttu-id="69d1f-222">Укажите день недели для выполнения запланированного полного сканирования для завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="69d1f-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="69d1f-223">Укажите день (или никогда) для запуска сканирования.</span><span class="sxs-lookup"><span data-stu-id="69d1f-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="69d1f-224">Никогда</span><span class="sxs-lookup"><span data-stu-id="69d1f-224">Never</span></span> |
|<span data-ttu-id="69d1f-225">Исправление</span><span class="sxs-lookup"><span data-stu-id="69d1f-225">Remediation</span></span> | <span data-ttu-id="69d1f-226">Укажите время суток для выполнения запланированного полного сканирования, чтобы завершить исправление</span><span class="sxs-lookup"><span data-stu-id="69d1f-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="69d1f-227">Укажите количество минут после полуночи (например, введите **60** в час ночи)</span><span class="sxs-lookup"><span data-stu-id="69d1f-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="69d1f-228">02:00.</span><span class="sxs-lookup"><span data-stu-id="69d1f-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="69d1f-229">Использование cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d1f-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="69d1f-230">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="69d1f-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="69d1f-231">Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="69d1f-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="69d1f-232">Использование Windows управления (WMI)</span><span class="sxs-lookup"><span data-stu-id="69d1f-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="69d1f-233">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="69d1f-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="69d1f-234">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="69d1f-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="69d1f-235">Настройка ежедневных быстрых сканов</span><span class="sxs-lookup"><span data-stu-id="69d1f-235">Set up daily quick scans</span></span>

<span data-ttu-id="69d1f-236">Вы можете включить ежедневное быстрое сканирование, которое можно выполнить в дополнение к другим запланированным проверкам с помощью групповой политики, PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="69d1f-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="69d1f-237">Использование групповой политики для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="69d1f-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="69d1f-238">Расположение</span><span class="sxs-lookup"><span data-stu-id="69d1f-238">Location</span></span> | <span data-ttu-id="69d1f-239">Параметр</span><span class="sxs-lookup"><span data-stu-id="69d1f-239">Setting</span></span> | <span data-ttu-id="69d1f-240">Описание</span><span class="sxs-lookup"><span data-stu-id="69d1f-240">Description</span></span> | <span data-ttu-id="69d1f-241">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="69d1f-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="69d1f-242">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-242">Scan</span></span> | <span data-ttu-id="69d1f-243">Укажите интервал для быстрого сканирования в день</span><span class="sxs-lookup"><span data-stu-id="69d1f-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="69d1f-244">Укажите, сколько часов должно быть у вас до следующего быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="69d1f-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="69d1f-245">Например, чтобы выполнить каждые два часа, введите **2**, раз в день введите **24**.</span><span class="sxs-lookup"><span data-stu-id="69d1f-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="69d1f-246">Введите **0,** чтобы никогда не запускать ежедневное быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="69d1f-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="69d1f-247">Никогда</span><span class="sxs-lookup"><span data-stu-id="69d1f-247">Never</span></span> |
|<span data-ttu-id="69d1f-248">Проверка</span><span class="sxs-lookup"><span data-stu-id="69d1f-248">Scan</span></span> | <span data-ttu-id="69d1f-249">Укажите время ежедневного быстрого сканирования</span><span class="sxs-lookup"><span data-stu-id="69d1f-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="69d1f-250">Укажите количество минут после полуночи (например, введите **60** в час ночи)</span><span class="sxs-lookup"><span data-stu-id="69d1f-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="69d1f-251">02:00.</span><span class="sxs-lookup"><span data-stu-id="69d1f-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="69d1f-252">Использование cmdlets PowerShell для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="69d1f-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="69d1f-253">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="69d1f-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="69d1f-254">Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="69d1f-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="69d1f-255">Используйте Windows управления (WMI) для расписания ежедневных сканов</span><span class="sxs-lookup"><span data-stu-id="69d1f-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="69d1f-256">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="69d1f-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="69d1f-257">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="69d1f-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="69d1f-258">Включить сканирование после обновления защиты</span><span class="sxs-lookup"><span data-stu-id="69d1f-258">Enable scans after protection updates</span></span>

<span data-ttu-id="69d1f-259">Проверку можно принудить к проверке после [каждого обновления защиты](manage-protection-updates-microsoft-defender-antivirus.md) с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="69d1f-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="69d1f-260">Использование групповой политики для расписания сканирования после обновления защиты</span><span class="sxs-lookup"><span data-stu-id="69d1f-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="69d1f-261">Расположение</span><span class="sxs-lookup"><span data-stu-id="69d1f-261">Location</span></span> | <span data-ttu-id="69d1f-262">Параметр</span><span class="sxs-lookup"><span data-stu-id="69d1f-262">Setting</span></span> | <span data-ttu-id="69d1f-263">Описание</span><span class="sxs-lookup"><span data-stu-id="69d1f-263">Description</span></span> | <span data-ttu-id="69d1f-264">Параметр по умолчанию (если не настроен)</span><span class="sxs-lookup"><span data-stu-id="69d1f-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="69d1f-265">Обновления подписи</span><span class="sxs-lookup"><span data-stu-id="69d1f-265">Signature updates</span></span> | <span data-ttu-id="69d1f-266">Включив сканирование после обновления сведении безопасности</span><span class="sxs-lookup"><span data-stu-id="69d1f-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="69d1f-267">Сканирование будет происходить сразу после загрузки нового обновления защиты</span><span class="sxs-lookup"><span data-stu-id="69d1f-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="69d1f-268">Включен</span><span class="sxs-lookup"><span data-stu-id="69d1f-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="69d1f-269">См. также</span><span class="sxs-lookup"><span data-stu-id="69d1f-269">See also</span></span>

- [<span data-ttu-id="69d1f-270">Предотвращение или разрешение пользователям локально изменять параметры политики</span><span class="sxs-lookup"><span data-stu-id="69d1f-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- <span data-ttu-id="69d1f-271">[Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию](run-scan-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="69d1f-271">[Configure and run on-demand Microsoft Defender Antivirus scans](run-scan-microsoft-defender-antivirus.md)</span></span>
- [<span data-ttu-id="69d1f-272">Настройка параметров сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="69d1f-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="69d1f-273">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="69d1f-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="69d1f-274">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="69d1f-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="69d1f-275">антивирусная программа в Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="69d1f-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)