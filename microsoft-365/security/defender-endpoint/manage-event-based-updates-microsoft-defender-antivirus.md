---
title: Применение обновлений антивируса Microsoft Defender после определенных событий
description: Управление тем, как антивирус Microsoft Defender применяет обновления аналитики безопасности после запуска или получения отчетов об обнаружении с облачными данными.
keywords: обновления, защита, силовые обновления, события, запуск, проверка последних уведомлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 78a04105fce0a3a1f9f7ea3f9ee993dd53750f3f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764559"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="a9e9d-104">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="a9e9d-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a9e9d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-105">**Applies to:**</span></span>

- [<span data-ttu-id="a9e9d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a9e9d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a9e9d-107">Антивирус Microsoft Defender позволяет определить, должны ли обновления (или не должны) происходить после определенных событий, например при запуске или после получения определенных отчетов от службы защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="a9e9d-108">Проверка обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="a9e9d-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="a9e9d-109">Вы можете использовать Microsoft Endpoint Configuration Manager, групповые политики, команды PowerShell и WMI, чтобы заставить антивирус Microsoft Defender проверять и скачивать обновления защиты перед запуском запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="a9e9d-110">Используйте диспетчер конфигурации для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="a9e9d-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="a9e9d-111">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ, которые необходимо изменить (нажмите кнопку Активы и соответствие требованиям в области навигации слева, а затем расширите дерево до Обзор политики защиты конечных   >    >  точек)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="a9e9d-112">Перейдите в раздел **Запланированные** проверки и установите **Проверку** последних обновлений разведки безопасности перед запуском проверки **на да**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="a9e9d-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-113">Click **OK**.</span></span>

4. <span data-ttu-id="a9e9d-114">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="a9e9d-115">Используйте групповую политику для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="a9e9d-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="a9e9d-116">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a9e9d-117">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a9e9d-118">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="a9e9d-119">Расширь дерево до **компонентов**  >  **Антивирусной проверки Microsoft Defender**  >  **Microsoft** Defender.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="a9e9d-120">Дважды **щелкните Проверить последние** определения вирусов и программ-шпионов перед запуском запланированного сканирования и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="a9e9d-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="a9e9d-122">Перед запуском сканирования используйте cmdlets PowerShell для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a9e9d-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="a9e9d-123">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a9e9d-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="a9e9d-124">Дополнительные сведения см. в дополнительных сведениях, которые [см.](/powershell/module/defender/index)в см. в рублях [Использование cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусных и защитников Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="a9e9d-125">Используйте инструкцию по управлению Windows (WMI) для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="a9e9d-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="a9e9d-126">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="a9e9d-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="a9e9d-127">Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="a9e9d-128">Проверка обновлений защиты при запуске</span><span class="sxs-lookup"><span data-stu-id="a9e9d-128">Check for protection updates on startup</span></span>

<span data-ttu-id="a9e9d-129">С помощью групповой политики можно заставить антивирус Microsoft Defender проверять и скачивать обновления защиты при работе компьютера.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="a9e9d-130">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a9e9d-131">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a9e9d-132">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="a9e9d-133">Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="a9e9d-134">Дважды **щелкните Проверьте последние** определения вирусов и программ-шпионов при запуске и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="a9e9d-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-135">Click **OK**.</span></span>

<span data-ttu-id="a9e9d-136">Вы также можете использовать групповую политику, PowerShell или WMI для настройки антивируса Microsoft Defender для проверки обновлений при запуске, даже если он не запущен.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="a9e9d-137">Используйте групповую политику для скачивания обновлений, когда антивирус Microsoft Defender не присутствует</span><span class="sxs-lookup"><span data-stu-id="a9e9d-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="a9e9d-138">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a9e9d-139">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a9e9d-140">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="a9e9d-141">Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="a9e9d-142">Дважды **щелкните Инициировать обновление** сведении о безопасности при запуске и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="a9e9d-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="a9e9d-144">Используйте cmdlets PowerShell для скачивания обновлений при неявке антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a9e9d-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="a9e9d-145">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a9e9d-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="a9e9d-146">Дополнительные сведения см. в [cmdlets Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для управления антивирусными и защитниками Microsoft Defender, чтобы получить дополнительные сведения о том, как использовать PowerShell с антивирусом Microsoft Defender. [](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="a9e9d-147">Используйте инструкцию по управлению Windows (WMI) для скачивания обновлений, когда антивирус Microsoft Defender не присутствует</span><span class="sxs-lookup"><span data-stu-id="a9e9d-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="a9e9d-148">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="a9e9d-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="a9e9d-149">Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="a9e9d-150">Разрешить ad hoc changes to protection based on cloud-delivered protection</span><span class="sxs-lookup"><span data-stu-id="a9e9d-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="a9e9d-151">Microsoft Defender AV может вносить изменения в свою защиту на основе облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="a9e9d-152">Такие изменения могут происходить вне обычных или запланированных обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="a9e9d-153">Если у вас включена облачная защита, microsoft Defender AV отправляет файлы, подозрительные для Защитник Windows облака.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="a9e9d-154">Если облачная служба сообщает о том, что файл вредоносный, а файл обнаружен в недавнем обновлении защиты, можно использовать групповую политику для настройки microsoft Defender AV для автоматического получения этого обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="a9e9d-155">Также можно применить другие важные обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="a9e9d-156">Использование групповой политики для автоматической загрузки последних обновлений на основе облачной защиты</span><span class="sxs-lookup"><span data-stu-id="a9e9d-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="a9e9d-157">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a9e9d-158">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a9e9d-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a9e9d-159">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="a9e9d-160">Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="a9e9d-161">Дважды **щелкните Разрешить обновления** сведении о безопасности в режиме реального времени на основе отчетов в Microsoft MAPS и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="a9e9d-162">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-162">Then click **OK**.</span></span>

6. <span data-ttu-id="a9e9d-163">**Разрешить уведомления для отключения отчетов** на основе определений в Microsoft MAPS и установить параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="a9e9d-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a9e9d-165">**Разрешение уведомлений для отключения** отчетов на основе определений позволяет Microsoft MAPS отключить эти определения, которые, как известно, вызывают ложные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="a9e9d-166">Для работы этой функции необходимо настроить компьютер, чтобы присоединиться к Microsoft MAPS.</span><span class="sxs-lookup"><span data-stu-id="a9e9d-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9e9d-167">См. также</span><span class="sxs-lookup"><span data-stu-id="a9e9d-167">See also</span></span>

- [<span data-ttu-id="a9e9d-168">Развертывание антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a9e9d-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9e9d-169">Управление обновлениями антивируса Microsoft Defender и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="a9e9d-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9e9d-170">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a9e9d-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9e9d-171">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="a9e9d-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9e9d-172">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="a9e9d-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9e9d-173">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9e9d-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)