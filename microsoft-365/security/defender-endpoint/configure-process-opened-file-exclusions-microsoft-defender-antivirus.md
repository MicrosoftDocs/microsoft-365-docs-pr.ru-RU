---
title: Настройка исключений для файлов, открытых определенными процессами
description: Вы можете исключить файлы из сканирования, если они были открыты определенным процессом.
keywords: антивирусная программа в Microsoft Defender, процесс, исключение, файлы, проверки
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274620"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="dcc18-104">Настройка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="dcc18-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dcc18-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dcc18-105">**Applies to:**</span></span>

- [<span data-ttu-id="dcc18-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dcc18-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dcc18-107">Можно исключить файлы, открытые определенными процессами, из антивирусная программа в Microsoft Defender проверки.</span><span class="sxs-lookup"><span data-stu-id="dcc18-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="dcc18-108">См. [Рекомендации для определения исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.</span><span class="sxs-lookup"><span data-stu-id="dcc18-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="dcc18-109">В этой статье описывается настройка списков исключений.</span><span class="sxs-lookup"><span data-stu-id="dcc18-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="dcc18-110">Примеры исключений</span><span class="sxs-lookup"><span data-stu-id="dcc18-110">Examples of exclusions</span></span>

|<span data-ttu-id="dcc18-111">Исключения</span><span class="sxs-lookup"><span data-stu-id="dcc18-111">Exclusion</span></span> | <span data-ttu-id="dcc18-112">Пример</span><span class="sxs-lookup"><span data-stu-id="dcc18-112">Example</span></span> |
|---|---|
|<span data-ttu-id="dcc18-113">Любой файл на компьютере, открываемом любым процессом с определенным именем файла</span><span class="sxs-lookup"><span data-stu-id="dcc18-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="dcc18-114">При `test.exe` указании исключены файлы, открытые по:</span><span class="sxs-lookup"><span data-stu-id="dcc18-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="dcc18-115">Любой файл на компьютере, открываемом любым процессом в определенной папке</span><span class="sxs-lookup"><span data-stu-id="dcc18-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="dcc18-116">При `c:\test\sample\*` указании исключены файлы, открытые по:</span><span class="sxs-lookup"><span data-stu-id="dcc18-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="dcc18-117">Любой файл на компьютере, открытый определенным процессом в определенной папке</span><span class="sxs-lookup"><span data-stu-id="dcc18-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="dcc18-118">Указание `c:\test\process.exe` исключит файлы, открытые только `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="dcc18-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="dcc18-119">При добавлении процесса в список исключений процесса антивирусная программа в Microsoft Defender файлы, открытые этим процессом, независимо от того, где находятся файлы.</span><span class="sxs-lookup"><span data-stu-id="dcc18-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="dcc18-120">Однако сам процесс будет отсканирован, если он не будет добавлен в список [исключений файлов.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dcc18-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="dcc18-121">Исключения применяются только к защите и мониторингу в режиме реального времени в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dcc18-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="dcc18-122">Они не применяются к запланированным проверкам или проверкам по запросу.</span><span class="sxs-lookup"><span data-stu-id="dcc18-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="dcc18-123">Изменения, внесенные с групповой политикой в списки исключений, будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md) </span><span class="sxs-lookup"><span data-stu-id="dcc18-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="dcc18-124">Однако изменения, внесенные в Безопасность Windows, **не будут указаны** в списках групповой политики.</span><span class="sxs-lookup"><span data-stu-id="dcc18-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="dcc18-125">Можно добавить, удалить и просмотреть списки исключений в групповой политике, Microsoft Endpoint Configuration Manager, Microsoft Intune и в приложении Безопасность Windows, а также использовать подгруппы для дальнейшей настройки списков.</span><span class="sxs-lookup"><span data-stu-id="dcc18-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="dcc18-126">Для настройки списков исключений, включая просмотр списков, можно также использовать cmdlets PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="dcc18-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="dcc18-127">По умолчанию локальные изменения, внесенные в списки (пользователями с привилегиями администратора; изменения, внесенные с PowerShell и WMI), будут объединены со списками в качестве определенных (и развернутых) групповой политикой, диспетчером конфигурации или Intune.</span><span class="sxs-lookup"><span data-stu-id="dcc18-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="dcc18-128">Списки групповой политики будут иметь приоритет в случае конфликтов.</span><span class="sxs-lookup"><span data-stu-id="dcc18-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="dcc18-129">Можно настроить [слияние](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) локальных и глобальных списков исключений, чтобы разрешить локальным изменениям переопределять параметры управляемого развертывания.</span><span class="sxs-lookup"><span data-stu-id="dcc18-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="dcc18-130">Настройка списка исключений для файлов, открытых указанными процессами</span><span class="sxs-lookup"><span data-stu-id="dcc18-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-131">Используйте Microsoft Intune, чтобы исключить файлы, открытые указанными процессами, из сканов</span><span class="sxs-lookup"><span data-stu-id="dcc18-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="dcc18-132">Дополнительные сведения см. в статьях [Настройка параметров ограничения устройств в Microsoft Intune](/intune/device-restrictions-configure) и [Параметры ограничений устройств антивирусной программы в Microsoft Defender для Windows 10 в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="dcc18-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-133">Используйте Microsoft Endpoint Manager, чтобы исключить файлы, открытые указанными процессами, из сканирований</span><span class="sxs-lookup"><span data-stu-id="dcc18-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="dcc18-134">Сведения [о настройке](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (текущая ветвь) см. в материале "Создание и развертывание политик противомалярийных программ: параметры исключения".</span><span class="sxs-lookup"><span data-stu-id="dcc18-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-135">Использование групповой политики для исключения файлов, открытых указанными процессами из сканов</span><span class="sxs-lookup"><span data-stu-id="dcc18-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="dcc18-136">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="dcc18-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dcc18-137">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="dcc18-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="dcc18-138">Расширь **дерево до Windows компонентов > антивирусная программа в Microsoft Defender > исключений.**</span><span class="sxs-lookup"><span data-stu-id="dcc18-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="dcc18-139">Дважды **щелкните исключения процесса** и добавьте исключения:</span><span class="sxs-lookup"><span data-stu-id="dcc18-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="dcc18-140">Установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="dcc18-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="dcc18-141">В разделе **Параметры** щелкните **Показать...**.</span><span class="sxs-lookup"><span data-stu-id="dcc18-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="dcc18-142">Введите каждый процесс по своей строке в столбце **Имя значения.**</span><span class="sxs-lookup"><span data-stu-id="dcc18-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="dcc18-143">В примере см. таблицу различных типов исключений процессов.</span><span class="sxs-lookup"><span data-stu-id="dcc18-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="dcc18-144">Введите **0** в **столбце Значение** для всех процессов.</span><span class="sxs-lookup"><span data-stu-id="dcc18-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="dcc18-145">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcc18-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-146">Чтобы исключить файлы, открытые указанными процессами, из сканов используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcc18-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="dcc18-147">Использование PowerShell для добавления или удаления исключений для файлов, открытых процессами, требует сочетания трех cmdlets с `-ExclusionProcess` параметром.</span><span class="sxs-lookup"><span data-stu-id="dcc18-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="dcc18-148">Все командлеты находятся в модуле [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="dcc18-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="dcc18-149">Формат для cmdlets:</span><span class="sxs-lookup"><span data-stu-id="dcc18-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="dcc18-150">Разрешено \<cmdlet> следующее:</span><span class="sxs-lookup"><span data-stu-id="dcc18-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="dcc18-151">Действие конфигурации</span><span class="sxs-lookup"><span data-stu-id="dcc18-151">Configuration action</span></span> | <span data-ttu-id="dcc18-152">Cmdlet PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcc18-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="dcc18-153">Создание или переописывание списка</span><span class="sxs-lookup"><span data-stu-id="dcc18-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="dcc18-154">Добавление в список</span><span class="sxs-lookup"><span data-stu-id="dcc18-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="dcc18-155">Удаление элементов из списка</span><span class="sxs-lookup"><span data-stu-id="dcc18-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="dcc18-156">Если вы создали список, с помощью или с помощью `Set-MpPreference` `Add-MpPreference` cmdlet снова `Set-MpPreference` переопишет существующий список.</span><span class="sxs-lookup"><span data-stu-id="dcc18-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="dcc18-157">Например, следующий фрагмент кода приведет к тому, что сканы av Microsoft Defender исключают любой файл, открытый указанным процессом:</span><span class="sxs-lookup"><span data-stu-id="dcc18-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="dcc18-158">Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в рублях Управление антивирусными программами с помощью cmdlets и [антивирусная программа в Microsoft Defender](/powershell/module/defender)PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcc18-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-159">Используйте Windows управления (WMI), чтобы исключить файлы, открытые указанными процессами, из сканирований</span><span class="sxs-lookup"><span data-stu-id="dcc18-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="dcc18-160">Используйте [ **методы Set,** **Add** и **Remove** **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) класса для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="dcc18-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="dcc18-161">Использование **набора,** **добавления** и  удаления аналогично их аналогам в PowerShell: `Set-MpPreference` , и `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="dcc18-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="dcc18-162">Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="dcc18-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="dcc18-163">Используйте приложение Безопасность Windows, чтобы исключить файлы, открытые указанными процессами, из сканирования</span><span class="sxs-lookup"><span data-stu-id="dcc18-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="dcc18-164">Дополнительные [исключения см. в Безопасность Windows для](microsoft-defender-security-center-antivirus.md) инструкций.</span><span class="sxs-lookup"><span data-stu-id="dcc18-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="dcc18-165">Использование подкардов в списке исключений процесса</span><span class="sxs-lookup"><span data-stu-id="dcc18-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="dcc18-166">Использование подкардов в списке исключений процессов отличается от использования в других списках исключений.</span><span class="sxs-lookup"><span data-stu-id="dcc18-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="dcc18-167">В частности, нельзя использовать знак вопроса () подкард, а подпольную звездочку () можно использовать только в конце `?` `*` полного пути.</span><span class="sxs-lookup"><span data-stu-id="dcc18-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="dcc18-168">При определении элементов в списке исключений процесса можно использовать переменные среды (например) в качестве `%ALLUSERSPROFILE%` поддиальдов.</span><span class="sxs-lookup"><span data-stu-id="dcc18-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="dcc18-169">В следующей таблице описывается, как можно использовать подкарды в списке исключений процесса:</span><span class="sxs-lookup"><span data-stu-id="dcc18-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="dcc18-170">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="dcc18-170">Wildcard</span></span> | <span data-ttu-id="dcc18-171">Пример использования</span><span class="sxs-lookup"><span data-stu-id="dcc18-171">Example use</span></span> | <span data-ttu-id="dcc18-172">Примеры совпадений</span><span class="sxs-lookup"><span data-stu-id="dcc18-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="dcc18-173">`*` (звездочка)</span><span class="sxs-lookup"><span data-stu-id="dcc18-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="dcc18-174">Заменяет любое количество символов</span><span class="sxs-lookup"><span data-stu-id="dcc18-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="dcc18-175">Любой файл, открытый `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="dcc18-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="dcc18-176">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="dcc18-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="dcc18-177">Заопределенная переменная заполняется как путь при оценке исключения</span><span class="sxs-lookup"><span data-stu-id="dcc18-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="dcc18-178">Любой файл, открытый `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="dcc18-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="dcc18-179">Просмотр списка исключений</span><span class="sxs-lookup"><span data-stu-id="dcc18-179">Review the list of exclusions</span></span>

<span data-ttu-id="dcc18-180">Элементы из списка исключений можно получить с помощью MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure) [или приложения Безопасность Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dcc18-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="dcc18-181">Если вы используете PowerShell, вы можете получить список двумя способами:</span><span class="sxs-lookup"><span data-stu-id="dcc18-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="dcc18-182">Извлечение состояния всех антивирусная программа в Microsoft Defender личных предпочтений.</span><span class="sxs-lookup"><span data-stu-id="dcc18-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="dcc18-183">Каждый из списков будет отображаться по отдельным строкам, но элементы в каждом списке будут объединены в ту же строку.</span><span class="sxs-lookup"><span data-stu-id="dcc18-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="dcc18-184">Напишите состояние всех предпочтений переменной и используйте эту переменную для вызова только заинтересованного списка.</span><span class="sxs-lookup"><span data-stu-id="dcc18-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="dcc18-185">Каждое использование `Add-MpPreference` записано на новую строку.</span><span class="sxs-lookup"><span data-stu-id="dcc18-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="dcc18-186">Проверка списка исключений с помощью MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="dcc18-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="dcc18-187">Чтобы проверить исключения с помощью выделенного средства [командной строки ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dcc18-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="dcc18-188">Проверка исключений с помощью MpCmdRun антивирусная программа в Microsoft Defender camp версии 4.18.1812.3 (выпущена в декабре 2018 г.) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dcc18-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="dcc18-189">Просмотрите список исключений вместе со всеми другими антивирусная программа в Microsoft Defender с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcc18-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="dcc18-190">Используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dcc18-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="dcc18-191">Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender).</span><span class="sxs-lookup"><span data-stu-id="dcc18-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="dcc18-192">Извлечение определенного списка исключений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcc18-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="dcc18-193">Используйте следующий фрагмент кода (введите каждую строку в качестве отдельной команды); замените **WDAVprefs** любой меткой, которая будет называться переменной:</span><span class="sxs-lookup"><span data-stu-id="dcc18-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="dcc18-194">Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender).</span><span class="sxs-lookup"><span data-stu-id="dcc18-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dcc18-195">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="dcc18-195">Related articles</span></span>

- [<span data-ttu-id="dcc18-196">Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="dcc18-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dcc18-197">Настройка и проверка исключений на основе имени, расширения и расположения папки</span><span class="sxs-lookup"><span data-stu-id="dcc18-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dcc18-198">Настройка антивирусная программа в Microsoft Defender исключений на Windows Server</span><span class="sxs-lookup"><span data-stu-id="dcc18-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dcc18-199">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="dcc18-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dcc18-200">Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений</span><span class="sxs-lookup"><span data-stu-id="dcc18-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dcc18-201">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="dcc18-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)