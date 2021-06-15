---
title: Настройка и проверка исключений на основе расширения, имени или расположения
description: Исключить файлы из антивирусная программа в Microsoft Defender на основе расширения файла, имени файла или расположения.
keywords: исключения, файлы, расширение, тип файла, имя папки, имя файла, сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 71df43639a719acb9436f64deba6b6c5cc9317f5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924283"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="eab6b-104">Настройка и проверка исключений в зависимости от расположения расширения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="eab6b-104">Configure and validate exclusions based on file extension and folder location</span></span>



<span data-ttu-id="eab6b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="eab6b-105">**Applies to:**</span></span>

- [<span data-ttu-id="eab6b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="eab6b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="eab6b-107">антивирусная программа в Microsoft Defender исключений не применяются к другим возможностям Microsoft Defender для конечных точек, в том числе обнаружение и нейтрализация атак на конечные точки [(EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)правилам уменьшения поверхности атаки [(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)и управляемому доступу к папкам. [](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="eab6b-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="eab6b-108">Файлы, исключаемые с помощью методов, описанных в этой статье, по-прежнему могут вызывать EDR оповещения и другие обнаружения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="eab6b-109">Чтобы исключить файлы в широком масштабе, добавьте их в настраиваемые индикаторы Microsoft Defender для [конечных точек.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="eab6b-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="eab6b-110">Списки исключений</span><span class="sxs-lookup"><span data-stu-id="eab6b-110">Exclusion lists</span></span>

<span data-ttu-id="eab6b-111">Некоторые файлы можно исключить из антивирусная программа в Microsoft Defender, изменяя списки исключений.</span><span class="sxs-lookup"><span data-stu-id="eab6b-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="eab6b-112">**Как правило, вам не нужно** применять исключения .</span><span class="sxs-lookup"><span data-stu-id="eab6b-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="eab6b-113">антивирусная программа в Microsoft Defender включает множество автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в управлении предприятиями, управлении базами данных и других корпоративных сценариях и ситуациях.</span><span class="sxs-lookup"><span data-stu-id="eab6b-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="eab6b-114">Исключения применяются и к обнаружениям потенциально нежелательных приложений (PUA).</span><span class="sxs-lookup"><span data-stu-id="eab6b-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="eab6b-115">Автоматические исключения применяются только к Windows Server 2016 и выше.</span><span class="sxs-lookup"><span data-stu-id="eab6b-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="eab6b-116">Эти исключения не видны в приложении Безопасность Windows и в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eab6b-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="eab6b-117">В этой статье описывается настройка списков исключений для файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="eab6b-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="eab6b-118">См. [Рекомендации для определения исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.</span><span class="sxs-lookup"><span data-stu-id="eab6b-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="eab6b-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="eab6b-119">Exclusion</span></span> | <span data-ttu-id="eab6b-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="eab6b-120">Examples</span></span> | <span data-ttu-id="eab6b-121">Список исключений</span><span class="sxs-lookup"><span data-stu-id="eab6b-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="eab6b-122">Любой файл с определенным расширением</span><span class="sxs-lookup"><span data-stu-id="eab6b-122">Any file with a specific extension</span></span> | <span data-ttu-id="eab6b-123">Все файлы с указанным расширением в любом месте на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eab6b-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="eab6b-124">Допустимый синтаксис: `.test` и `test`</span><span class="sxs-lookup"><span data-stu-id="eab6b-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="eab6b-125">Исключения расширения</span><span class="sxs-lookup"><span data-stu-id="eab6b-125">Extension exclusions</span></span> |
|<span data-ttu-id="eab6b-126">Любой файл в определенной папке</span><span class="sxs-lookup"><span data-stu-id="eab6b-126">Any file under a specific folder</span></span> | <span data-ttu-id="eab6b-127">Все файлы в `c:\test\sample` папке</span><span class="sxs-lookup"><span data-stu-id="eab6b-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="eab6b-128">Исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="eab6b-128">File and folder exclusions</span></span> |
| <span data-ttu-id="eab6b-129">Определенный файл в определенной папке</span><span class="sxs-lookup"><span data-stu-id="eab6b-129">A specific file in a specific folder</span></span> | <span data-ttu-id="eab6b-130">Только `c:\sample\sample.test` файл</span><span class="sxs-lookup"><span data-stu-id="eab6b-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="eab6b-131">Исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="eab6b-131">File and folder exclusions</span></span> |
| <span data-ttu-id="eab6b-132">Определенный процесс</span><span class="sxs-lookup"><span data-stu-id="eab6b-132">A specific process</span></span> | <span data-ttu-id="eab6b-133">Исполняемый файл `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="eab6b-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="eab6b-134">Исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="eab6b-134">File and folder exclusions</span></span> |

<span data-ttu-id="eab6b-135">Списки исключений имеют следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="eab6b-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="eab6b-136">Исключения папок применяются к всем файлам и папочкам в этой папке, если подмостки не является точкой репара.</span><span class="sxs-lookup"><span data-stu-id="eab6b-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="eab6b-137">Раздельные подмостки точки репаража должны быть исключены отдельно.</span><span class="sxs-lookup"><span data-stu-id="eab6b-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="eab6b-138">Расширения файлов применяются к любому имени файла с определенным расширением, если путь или папка не определены.</span><span class="sxs-lookup"><span data-stu-id="eab6b-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="eab6b-139">Использование подкардов, таких как звездочка ( ) изменит интерпретировать правила \* исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="eab6b-140">Сведения о [том,](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) как работают подкарды, см. в разделе Использование подкардов в пути имени файла и пути к папке или в разделе списки исключений расширения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="eab6b-141">Нельзя исключать отметь сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="eab6b-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="eab6b-142">Необходимо указать фактический сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="eab6b-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="eab6b-143">Папки, которые являются точками репаража, созданными после антивирусная программа в Microsoft Defender службы и добавленными в список исключений, не будут включены.</span><span class="sxs-lookup"><span data-stu-id="eab6b-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="eab6b-144">Необходимо перезапустить службу (перезапустив Windows), чтобы новые точки репаража были признаны допустимой целью исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="eab6b-145">Чтобы исключить файлы, открытые определенным процессом, см. в руб. Настройка и проверка исключений для файлов, [открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eab6b-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="eab6b-146">Исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и защите [в режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eab6b-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eab6b-147">Изменения списка исключений, внесенные с помощью групповой **политики,** будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eab6b-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="eab6b-148">Изменения, внесенные в **Безопасность Windows, не будут показываться** в списках групповой политики.</span><span class="sxs-lookup"><span data-stu-id="eab6b-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="eab6b-149">По умолчанию локальные изменения, внесенные в списки (пользователями с привилегиями администратора, включая изменения, внесенные с PowerShell и WMI), будут объединены со списками в качестве определенных (и развернутых) групповой политикой, диспетчером конфигурации или Intune.</span><span class="sxs-lookup"><span data-stu-id="eab6b-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="eab6b-150">Списки групповой политики имеют приоритет при конфликте.</span><span class="sxs-lookup"><span data-stu-id="eab6b-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="eab6b-151">Можно настроить [слияние](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) локальных и глобальных списков исключений, чтобы разрешить локальным изменениям переопределять параметры управляемого развертывания.</span><span class="sxs-lookup"><span data-stu-id="eab6b-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="eab6b-152">Настройка списка исключений на основе имени папки или расширения файла</span><span class="sxs-lookup"><span data-stu-id="eab6b-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-153">Используйте Intune для настройки исключений из расширения файла, имени файла, папки или расширения файлов</span><span class="sxs-lookup"><span data-stu-id="eab6b-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="eab6b-154">См. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="eab6b-154">See the following articles:</span></span>
- [<span data-ttu-id="eab6b-155">Настройка параметров ограничения устройств в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eab6b-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="eab6b-156">антивирусная программа в Microsoft Defender параметров ограничения устройств для Windows 10 в Intune</span><span class="sxs-lookup"><span data-stu-id="eab6b-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-157">Использование Диспетчер конфигурации для настройки исключений из расширения файлов, имени, папки или файла</span><span class="sxs-lookup"><span data-stu-id="eab6b-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="eab6b-158">Сведения [о настройке](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (текущая ветвь) см. в материале "Создание и развертывание политик противомалярийных программ: параметры исключения".</span><span class="sxs-lookup"><span data-stu-id="eab6b-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-159">Использование групповой политики для настройки исключений папок или расширений файлов</span><span class="sxs-lookup"><span data-stu-id="eab6b-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="eab6b-160">Если вы указываете полностью квалифицированный путь к файлу, то исключается только этот файл.</span><span class="sxs-lookup"><span data-stu-id="eab6b-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="eab6b-161">Если папка определена в исключении, все файлы и подтеки в этой папке исключены.</span><span class="sxs-lookup"><span data-stu-id="eab6b-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="eab6b-162">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="eab6b-163">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="eab6b-164">Расширь **дерево до Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **исключений.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="eab6b-165">Откройте параметр **"Исключения пути"** для редактирования и добавьте исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="eab6b-166">Установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="eab6b-167">В разделе **Параметры** нажмите **кнопку Показать**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="eab6b-168">Укажите каждую папку по своей строке в столбце **Имя значения.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="eab6b-169">Если вы указываете файл, убедитесь, что вы введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение.</span><span class="sxs-lookup"><span data-stu-id="eab6b-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="eab6b-170">Введите **0** в **столбце Значение.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="eab6b-171">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-171">Choose **OK**.</span></span>

6. <span data-ttu-id="eab6b-172">Откройте параметр **Исключения расширения для** редактирования и добавьте исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="eab6b-173">Установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="eab6b-174">В разделе **Параметры** выберите **Показать**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="eab6b-175">Введите каждое расширение файла по своей строке в столбце **Имя значения.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="eab6b-176">Введите **0** в **столбце Значение.**</span><span class="sxs-lookup"><span data-stu-id="eab6b-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="eab6b-177">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="eab6b-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-178">Использование cmdlets PowerShell для настройки исключений из расширения файла, имени файла, папки или расширения файлов</span><span class="sxs-lookup"><span data-stu-id="eab6b-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="eab6b-179">Использование PowerShell для добавления или удаления исключений для файлов на основе расширения, расположения или имени файла требует сочетания трех cmdlets и соответствующего параметра списка исключений.</span><span class="sxs-lookup"><span data-stu-id="eab6b-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="eab6b-180">Все командлеты находятся в модуле [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="eab6b-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="eab6b-181">Формат для cmdlets следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eab6b-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="eab6b-182">Разрешено `<cmdlet>` следующее:</span><span class="sxs-lookup"><span data-stu-id="eab6b-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="eab6b-183">Действие конфигурации</span><span class="sxs-lookup"><span data-stu-id="eab6b-183">Configuration action</span></span> | <span data-ttu-id="eab6b-184">Cmdlet PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab6b-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="eab6b-185">Создание или переописывание списка</span><span class="sxs-lookup"><span data-stu-id="eab6b-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="eab6b-186">Добавление в список</span><span class="sxs-lookup"><span data-stu-id="eab6b-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="eab6b-187">Удаление элемента из списка</span><span class="sxs-lookup"><span data-stu-id="eab6b-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="eab6b-188">Разрешено `<exclusion list>` следующее:</span><span class="sxs-lookup"><span data-stu-id="eab6b-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="eab6b-189">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="eab6b-189">Exclusion type</span></span> | <span data-ttu-id="eab6b-190">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab6b-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="eab6b-191">Все файлы с указанным расширением файла</span><span class="sxs-lookup"><span data-stu-id="eab6b-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="eab6b-192">Все файлы в папке (включая файлы в подуправлениях) или определенный файл</span><span class="sxs-lookup"><span data-stu-id="eab6b-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="eab6b-193">Если вы создали список, с помощью или с помощью `Set-MpPreference` `Add-MpPreference` cmdlet снова `Set-MpPreference` переопишет существующий список.</span><span class="sxs-lookup"><span data-stu-id="eab6b-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="eab6b-194">Например, следующий фрагмент кода приведет к антивирусная программа в Microsoft Defender, чтобы исключить любой файл с `.test` расширением файла:</span><span class="sxs-lookup"><span data-stu-id="eab6b-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="eab6b-195">Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="eab6b-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-196">Используйте Windows управления (WMI) для настройки исключений из файла, папок или расширений файлов</span><span class="sxs-lookup"><span data-stu-id="eab6b-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="eab6b-197">Используйте [ **методы Set,** **Add** и **Remove** **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) класса для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="eab6b-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="eab6b-198">Использование **набора,** **добавления** и  удаления аналогично их аналогам в PowerShell: `Set-MpPreference` , и `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="eab6b-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="eab6b-199">Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="eab6b-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="eab6b-200">Используйте приложение Безопасность Windows для настройки исключений из расширения файла, имени файла, папки или расширения файлов</span><span class="sxs-lookup"><span data-stu-id="eab6b-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="eab6b-201">Дополнительные [исключения см. в Безопасность Windows для](microsoft-defender-security-center-antivirus.md) инструкций.</span><span class="sxs-lookup"><span data-stu-id="eab6b-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="eab6b-202">Использование подмастерьев в пути имени файла и пути папок или списках исключений расширения</span><span class="sxs-lookup"><span data-stu-id="eab6b-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="eab6b-203">Вы можете использовать звездочки, знак вопросов или переменные среды (например) в качестве подкардов при определении элементов в списке исключения пути к файлу или `*` `?` имени `%ALLUSERSPROFILE%` папки.</span><span class="sxs-lookup"><span data-stu-id="eab6b-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="eab6b-204">Способ интерпретации этих подкардов отличается от обычного использования в других приложениях и языках.</span><span class="sxs-lookup"><span data-stu-id="eab6b-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="eab6b-205">Ознакомьтесь с этим разделом, чтобы понять их определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eab6b-206">Существуют основные ограничения и сценарии использования для этих подкардов:</span><span class="sxs-lookup"><span data-stu-id="eab6b-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="eab6b-207">Использование переменной среды ограничено переменными машин и теми, которые применимы к процессам, запущенным в качестве учетной записи NT AUTHORITY\SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="eab6b-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="eab6b-208">Нельзя использовать под диктовую карточку на месте буквы диска.</span><span class="sxs-lookup"><span data-stu-id="eab6b-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="eab6b-209">Звездочка в `*` исключении папки стоит на месте для одной папки.</span><span class="sxs-lookup"><span data-stu-id="eab6b-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="eab6b-210">Используйте несколько экземпляров, чтобы указать несколько вложенных `\*\` папок с неустановленными именами.</span><span class="sxs-lookup"><span data-stu-id="eab6b-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="eab6b-211">В следующей таблице описывается, как можно использовать поддиальды, и приводится несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="eab6b-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="eab6b-212">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="eab6b-212">Wildcard</span></span>  |<span data-ttu-id="eab6b-213">Примеры</span><span class="sxs-lookup"><span data-stu-id="eab6b-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="eab6b-214">`*` (звездочка)</span><span class="sxs-lookup"><span data-stu-id="eab6b-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="eab6b-215">В **включениях** имен файлов и расширений файлов звездочка заменяет любое количество символов и применяется только к файлам в последней папке, определенной в аргументе.</span><span class="sxs-lookup"><span data-stu-id="eab6b-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="eab6b-216">В **исключениях папок** звездочка заменяет одну папку.</span><span class="sxs-lookup"><span data-stu-id="eab6b-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="eab6b-217">Используйте несколько `*` со срезами папок, `\` чтобы указать несколько вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="eab6b-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="eab6b-218">После совпадения числа папок с wild carded и именными именами все подмостки также включаются.</span><span class="sxs-lookup"><span data-stu-id="eab6b-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="eab6b-219">`C:\MyData\*.txt` включает в себя `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="eab6b-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="eab6b-220">`C:\somepath\*\Data` включает в себя любой файл `C:\somepath\Archives\Data` и его подмостки, `C:\somepath\Authorized\Data` а также подмостки</span><span class="sxs-lookup"><span data-stu-id="eab6b-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="eab6b-221">`C:\Serv\*\*\Backup` включает в себя любой файл, `C:\Serv\Primary\Denied\Backup` его подмостки и `C:\Serv\Secondary\Allowed\Backup` подмостки</span><span class="sxs-lookup"><span data-stu-id="eab6b-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="eab6b-222">`?` (знак вопроса)</span><span class="sxs-lookup"><span data-stu-id="eab6b-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="eab6b-223">В **включениях имен** файлов и расширений файлов знак вопроса заменяет один символ и применяется только к файлам в последней папке, определенной в аргументе.</span><span class="sxs-lookup"><span data-stu-id="eab6b-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="eab6b-224">В **исключениях папок** знак вопроса заменяет один символ в имени папки.</span><span class="sxs-lookup"><span data-stu-id="eab6b-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="eab6b-225">После совпадения числа папок с wild carded и именными именами все подмостки также включаются.</span><span class="sxs-lookup"><span data-stu-id="eab6b-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="eab6b-226">`C:\MyData\my?.zip` включает в себя `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="eab6b-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="eab6b-227">`C:\somepath\?\Data` включает любой файл и `C:\somepath\P\Data` его подмостки</span><span class="sxs-lookup"><span data-stu-id="eab6b-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="eab6b-228">`C:\somepath\test0?\Data` включит любой файл `C:\somepath\test01\Data` и его подмостки</span><span class="sxs-lookup"><span data-stu-id="eab6b-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="eab6b-229">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="eab6b-229">Environment variables</span></span> <p> <span data-ttu-id="eab6b-230">Определяемая переменная заполняется как путь при оценке исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="eab6b-231">`%ALLUSERSPROFILE%\CustomLogFiles` будет включать в себя `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="eab6b-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="eab6b-232">Если смешать аргумент исключения файлов с аргументом исключения папок, правила будут останавливаться на совпадении аргументов файлов в подгруппах и не будут искать совпадения файлов в подмостках.</span><span class="sxs-lookup"><span data-stu-id="eab6b-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="eab6b-233">Например, можно исключить все файлы, которые начинаются с "даты" в папках и `c:\data\final\marked` `c:\data\review\marked` с помощью аргумента правила `c:\data\*\marked\date*` .</span><span class="sxs-lookup"><span data-stu-id="eab6b-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="eab6b-234">Этот аргумент, однако, не будет соответствовать любым файлам в подмостки под `c:\data\final\marked` или `c:\data\review\marked` .</span><span class="sxs-lookup"><span data-stu-id="eab6b-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="eab6b-235">Переменные системной среды</span><span class="sxs-lookup"><span data-stu-id="eab6b-235">System environment variables</span></span>

<span data-ttu-id="eab6b-236">В следующей таблице перечислены и описываются переменные среды учетной записи системы.</span><span class="sxs-lookup"><span data-stu-id="eab6b-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="eab6b-237">Эта переменная среды системы...</span><span class="sxs-lookup"><span data-stu-id="eab6b-237">This system environment variable...</span></span> | <span data-ttu-id="eab6b-238">Перенаправление на это</span><span class="sxs-lookup"><span data-stu-id="eab6b-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="eab6b-239">C:\ProgramData\Start Menu\Programs</span><span class="sxs-lookup"><span data-stu-id="eab6b-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="eab6b-240">Просмотр списка исключений</span><span class="sxs-lookup"><span data-stu-id="eab6b-240">Review the list of exclusions</span></span>

<span data-ttu-id="eab6b-241">Элементы из списка исключений можно получить с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="eab6b-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="eab6b-242">Intune</span><span class="sxs-lookup"><span data-stu-id="eab6b-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="eab6b-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eab6b-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="eab6b-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="eab6b-244">MpCmdRun</span></span>
- <span data-ttu-id="eab6b-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab6b-245">PowerShell</span></span>
- [<span data-ttu-id="eab6b-246">Безопасность Windows приложение</span><span class="sxs-lookup"><span data-stu-id="eab6b-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="eab6b-247">Изменения списка исключений, внесенные с помощью групповой **политики,** будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eab6b-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="eab6b-248">Изменения, внесенные в **Безопасность Windows, не будут показываться** в списках групповой политики.</span><span class="sxs-lookup"><span data-stu-id="eab6b-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="eab6b-249">Если вы используете PowerShell, вы можете получить список двумя способами:</span><span class="sxs-lookup"><span data-stu-id="eab6b-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="eab6b-250">Извлечение состояния всех антивирусная программа в Microsoft Defender личных предпочтений.</span><span class="sxs-lookup"><span data-stu-id="eab6b-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="eab6b-251">Каждый список отображается в отдельных строках, но элементы в каждом списке объединены в ту же строку.</span><span class="sxs-lookup"><span data-stu-id="eab6b-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="eab6b-252">Напишите состояние всех предпочтений переменной и используйте эту переменную для вызова только заинтересованного списка.</span><span class="sxs-lookup"><span data-stu-id="eab6b-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="eab6b-253">Каждое использование `Add-MpPreference` записано на новую строку.</span><span class="sxs-lookup"><span data-stu-id="eab6b-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="eab6b-254">Проверка списка исключений с помощью MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="eab6b-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="eab6b-255">Чтобы проверить исключения с помощью выделенного средства [командной строки ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eab6b-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="eab6b-256">Проверка исключений с помощью MpCmdRun антивирусная программа в Microsoft Defender camp версии 4.18.1812.3 (выпущена в декабре 2018 г.) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="eab6b-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="eab6b-257">Просмотрите список исключений вместе со всеми другими антивирусная программа в Microsoft Defender с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab6b-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="eab6b-258">Используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="eab6b-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="eab6b-259">В следующем примере выделяются элементы, содержащиеся в `ExclusionExtension` списке:</span><span class="sxs-lookup"><span data-stu-id="eab6b-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![Выход PowerShell для Get-MpPreference списка исключений наряду с другими предпочтениями](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="eab6b-261">Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="eab6b-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="eab6b-262">Извлечение определенного списка исключений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eab6b-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="eab6b-263">Используйте следующий фрагмент кода (введите каждую строку в качестве отдельной команды); замените **WDAVprefs** любой меткой, которая будет называться переменной:</span><span class="sxs-lookup"><span data-stu-id="eab6b-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="eab6b-264">В следующем примере список делится на новые строки для каждого использования `Add-MpPreference` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="eab6b-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![Выход PowerShell, показывающий только записи в списке исключений](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="eab6b-266">Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="eab6b-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="eab6b-267">Проверка списков исключений в тестовом файле EICAR</span><span class="sxs-lookup"><span data-stu-id="eab6b-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="eab6b-268">Вы можете проверить, работают ли списки исключений с помощью PowerShell с помощью cmdlet или класса .NET WebClient для скачивания `Invoke-WebRequest` тестового файла.</span><span class="sxs-lookup"><span data-stu-id="eab6b-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="eab6b-269">В следующем фрагменте PowerShell *замените* test.txtфайлом, соответствующим правилам исключения.</span><span class="sxs-lookup"><span data-stu-id="eab6b-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="eab6b-270">Например, если вы исключили `.testing` расширение, замените `test.txt` `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="eab6b-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="eab6b-271">Если вы тестируете путь, убедитесь, что вы запустите этот кодлет в этом пути.</span><span class="sxs-lookup"><span data-stu-id="eab6b-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="eab6b-272">Если антивирусная программа в Microsoft Defender сообщает о вредоносных программах, то правило не работает.</span><span class="sxs-lookup"><span data-stu-id="eab6b-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="eab6b-273">Если нет отчета о вредоносных программах и загруженный файл существует, то исключение работает.</span><span class="sxs-lookup"><span data-stu-id="eab6b-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="eab6b-274">Вы можете открыть файл, чтобы подтвердить, что содержимое будет таким же, как описано на веб-сайте [тестового файла EICAR.](http://www.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="eab6b-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="eab6b-275">Вы также можете использовать следующий код PowerShell, который вызывает класс .NET WebClient, чтобы скачать тестовый файл , как и в cmdlet; заменитьc:\test.txtфайлом, который соответствует правилу, которое вы `Invoke-WebRequest` проверяете: </span><span class="sxs-lookup"><span data-stu-id="eab6b-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="eab6b-276">Если у вас нет доступа к Интернету, вы можете создать собственный тестовый файл EICAR, написав строку EICAR в новый текстовый файл со следующей командой PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eab6b-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="eab6b-277">Вы также можете скопировать строку в пустой текстовый файл и попытаться сохранить ее с именем файла или в папке, вы пытаетсяе исключить.</span><span class="sxs-lookup"><span data-stu-id="eab6b-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eab6b-278">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="eab6b-278">Related topics</span></span>

- [<span data-ttu-id="eab6b-279">Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="eab6b-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eab6b-280">Настройка и проверка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="eab6b-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eab6b-281">Настройка антивирусная программа в Microsoft Defender исключений на Windows Server</span><span class="sxs-lookup"><span data-stu-id="eab6b-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eab6b-282">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="eab6b-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
