---
title: Применение антивирусная программа в Microsoft Defender обновлений после определенных событий
description: Управление тем, антивирусная программа в Microsoft Defender применяет обновления разведки безопасности после запуска или получения отчетов об обнаружении с облачными данными.
keywords: обновления, защита, силовые обновления, события, запуск, проверка последних уведомлений
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
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926083"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="b6be1-104">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="b6be1-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b6be1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b6be1-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6be1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b6be1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b6be1-107">антивирусная программа в Microsoft Defender позволяет определить, должны ли обновления (или не должны) возникать после определенных событий, например при запуске или после получения определенных отчетов от службы защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="b6be1-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b6be1-108">Проверка обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="b6be1-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="b6be1-109">Вы можете использовать Microsoft Endpoint Configuration Manager, групповые политики, powerShell и WMI, чтобы заставить антивирусная программа в Microsoft Defender проверять и скачивать обновления защиты перед запуском запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="b6be1-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b6be1-110">Используйте диспетчер конфигурации для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="b6be1-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="b6be1-111">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="b6be1-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="b6be1-112">Перейдите в раздел **Запланированные** проверки и установите **Проверку** последних обновлений разведки безопасности перед запуском проверки **на да**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="b6be1-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-113">Click **OK**.</span></span>

4. <span data-ttu-id="b6be1-114">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="b6be1-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b6be1-115">Используйте групповую политику для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="b6be1-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="b6be1-116">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b6be1-117">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b6be1-118">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b6be1-119">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сканирование.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="b6be1-120">Дважды **щелкните Проверить последние** определения вирусов и программ-шпионов перед запуском запланированного сканирования и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="b6be1-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b6be1-122">Перед запуском сканирования используйте cmdlets PowerShell для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="b6be1-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="b6be1-123">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b6be1-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="b6be1-124">Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="b6be1-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b6be1-125">Используйте Windows управления (WMI) для проверки обновлений защиты перед запуском сканирования</span><span class="sxs-lookup"><span data-stu-id="b6be1-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="b6be1-126">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="b6be1-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="b6be1-127">Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b6be1-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="b6be1-128">Проверка обновлений защиты при запуске</span><span class="sxs-lookup"><span data-stu-id="b6be1-128">Check for protection updates on startup</span></span>

<span data-ttu-id="b6be1-129">Можно использовать групповую политику для антивирусная программа в Microsoft Defender проверки и загрузки обновлений защиты при работе компьютера.</span><span class="sxs-lookup"><span data-stu-id="b6be1-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="b6be1-130">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b6be1-131">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b6be1-132">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b6be1-133">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b6be1-134">Дважды **щелкните Проверьте последние** определения вирусов и программ-шпионов при запуске и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="b6be1-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-135">Click **OK**.</span></span>

<span data-ttu-id="b6be1-136">Можно также использовать групповую политику, PowerShell или WMI для настройки антивирусная программа в Microsoft Defender для проверки обновлений при запуске, даже если она не запущена.</span><span class="sxs-lookup"><span data-stu-id="b6be1-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b6be1-137">Используйте групповую политику для скачивания обновлений, антивирусная программа в Microsoft Defender нет</span><span class="sxs-lookup"><span data-stu-id="b6be1-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="b6be1-138">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b6be1-139">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b6be1-140">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b6be1-141">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b6be1-142">Дважды **щелкните Инициировать обновление** сведении о безопасности при запуске и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="b6be1-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b6be1-144">Используйте cmdlets PowerShell для скачивания обновлений, антивирусная программа в Microsoft Defender нет</span><span class="sxs-lookup"><span data-stu-id="b6be1-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="b6be1-145">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b6be1-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="b6be1-146">Дополнительные сведения см. в дополнительных сведениях о том, как использовать [cmdlets PowerShell для](use-powershell-cmdlets-microsoft-defender-antivirus.md) управления антивирусная программа в Microsoft Defender и [defender](/powershell/module/defender/index) для получения дополнительных сведений о том, как использовать PowerShell с антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6be1-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b6be1-147">Используйте Windows управления (WMI) для скачивания обновлений, антивирусная программа в Microsoft Defender нет</span><span class="sxs-lookup"><span data-stu-id="b6be1-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="b6be1-148">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="b6be1-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="b6be1-149">Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b6be1-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="b6be1-150">Разрешить ad hoc changes to protection based on cloud-delivered protection</span><span class="sxs-lookup"><span data-stu-id="b6be1-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="b6be1-151">Microsoft Defender AV может вносить изменения в свою защиту на основе облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="b6be1-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="b6be1-152">Такие изменения могут происходить вне обычных или запланированных обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="b6be1-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="b6be1-153">Если у вас включена облачная защита, Microsoft Defender AV отправляет файлы, подозрительные для Защитник Windows облака.</span><span class="sxs-lookup"><span data-stu-id="b6be1-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="b6be1-154">Если облачная служба сообщает о том, что файл вредоносный, а файл обнаружен в недавнем обновлении защиты, можно использовать групповую политику для настройки microsoft Defender AV для автоматического получения этого обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="b6be1-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="b6be1-155">Также можно применить другие важные обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="b6be1-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="b6be1-156">Использование групповой политики для автоматической загрузки последних обновлений на основе облачной защиты</span><span class="sxs-lookup"><span data-stu-id="b6be1-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="b6be1-157">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b6be1-158">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b6be1-159">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b6be1-160">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**</span><span class="sxs-lookup"><span data-stu-id="b6be1-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b6be1-161">Дважды **щелкните Разрешить обновления** сведении о безопасности в режиме реального времени на основе отчетов в Microsoft MAPS и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="b6be1-162">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-162">Then click **OK**.</span></span>

6. <span data-ttu-id="b6be1-163">**Разрешить уведомления для отключения отчетов** на основе определений в Microsoft MAPS и установить параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="b6be1-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6be1-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6be1-165">**Разрешение уведомлений для отключения** отчетов на основе определений позволяет Microsoft MAPS отключить эти определения, которые, как известно, вызывают ложные сообщения.</span><span class="sxs-lookup"><span data-stu-id="b6be1-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="b6be1-166">Для работы этой функции необходимо настроить компьютер, чтобы присоединиться к Microsoft MAPS.</span><span class="sxs-lookup"><span data-stu-id="b6be1-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6be1-167">См. также</span><span class="sxs-lookup"><span data-stu-id="b6be1-167">See also</span></span>

- [<span data-ttu-id="b6be1-168">Развертывание антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6be1-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6be1-169">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="b6be1-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6be1-170">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="b6be1-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6be1-171">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="b6be1-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6be1-172">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="b6be1-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6be1-173">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="b6be1-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)