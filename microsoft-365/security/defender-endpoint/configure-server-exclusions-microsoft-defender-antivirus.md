---
title: Настройка антивирусная программа в Microsoft Defender исключений на Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Сервер включает автоматические исключения, основанные на роли сервера. Можно также добавить настраиваемые исключения.
keywords: исключения, сервер, автоматические исключения, автоматические, настраиваемые, сканы, антивирусная программа в Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274764"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="50957-105">Настройка антивирусная программа в Microsoft Defender исключений на Windows Server</span><span class="sxs-lookup"><span data-stu-id="50957-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50957-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="50957-106">**Applies to:**</span></span>

- [<span data-ttu-id="50957-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="50957-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="50957-108">антивирусная программа в Microsoft Defender на Windows Server 2016 и Windows Server 2019 автоматически регистрируется в определенных исключениях, определенных указанной ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="50957-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="50957-109">Эти исключения не отображаются в стандартных списках исключений, которые отображаются в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="50957-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="50957-110">Автоматические исключения применяются только к проверке защиты в режиме реального времени (RTP).</span><span class="sxs-lookup"><span data-stu-id="50957-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="50957-111">Автоматические исключения не будут соблюдаться во время проверки full/quick или on-demand.</span><span class="sxs-lookup"><span data-stu-id="50957-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="50957-112">Помимо автоматических исключений, определенных ролью сервера, можно добавить или удалить настраиваемые исключения.</span><span class="sxs-lookup"><span data-stu-id="50957-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="50957-113">Для этого обратитесь к этим статьям:</span><span class="sxs-lookup"><span data-stu-id="50957-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="50957-114">Настройка и проверка исключений на основе имени, расширения и расположения папки</span><span class="sxs-lookup"><span data-stu-id="50957-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-115">Настройка и проверка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="50957-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="50957-116">Несколько моментов, которые необходимо иметь в виду</span><span class="sxs-lookup"><span data-stu-id="50957-116">A few points to keep in mind</span></span>

<span data-ttu-id="50957-117">Имейте в виду следующие важные моменты:</span><span class="sxs-lookup"><span data-stu-id="50957-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="50957-118">Пользовательские исключения имеют приоритет над автоматическими исключениями.</span><span class="sxs-lookup"><span data-stu-id="50957-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="50957-119">Автоматические исключения применяются только к проверке защиты в режиме реального времени (RTP).</span><span class="sxs-lookup"><span data-stu-id="50957-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="50957-120">Автоматические исключения не будут соблюдаться во время проверки full/quick или on-demand.</span><span class="sxs-lookup"><span data-stu-id="50957-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="50957-121">Настраиваемые и дублирующиеся исключения не конфликтуют с автоматическими исключениями.</span><span class="sxs-lookup"><span data-stu-id="50957-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="50957-122">антивирусная программа в Microsoft Defender средства обслуживания и управления изображениями развертывания (DISM) для определения ролей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="50957-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="50957-123">Отказ от автоматических исключений</span><span class="sxs-lookup"><span data-stu-id="50957-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="50957-124">В Windows Server 2016 и Windows Server 2019 предопределяемые исключения, доставленные обновлениями разведки безопасности, исключают только пути по умолчанию для роли или функции.</span><span class="sxs-lookup"><span data-stu-id="50957-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="50957-125">Если вы установили роль или функцию на настраиваемом пути или хотите вручную управлять набором исключений, не забудьте отказаться от автоматических исключений, доставленных в обновлениях разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="50957-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="50957-126">Но помните, что автоматически доставляемые исключения оптимизируются для ролей Windows Server 2016 и 2019 года.</span><span class="sxs-lookup"><span data-stu-id="50957-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="50957-127">См. [Рекомендации для определения исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.</span><span class="sxs-lookup"><span data-stu-id="50957-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="50957-128">Отказ от автоматических исключений может отрицательно сказаться на производительности или привести к повреждениям данных.</span><span class="sxs-lookup"><span data-stu-id="50957-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="50957-129">Автоматически доставляемые исключения оптимизированы для ролей Windows Server 2016 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="50957-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="50957-130">Так как предопределение исключений исключает только пути по **умолчанию,** если переместить NTDS и SYSVOL на другой диск или путь, который отличается от исходного *пути,* необходимо добавить исключения вручную с помощью сведений [здесь](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span><span class="sxs-lookup"><span data-stu-id="50957-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="50957-131">Автоматические списки исключений можно отключить с помощью групп Политик, PowerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="50957-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="50957-132">Использование групповой политики для отключения списка автоматических исключений на Windows Server 2016 и Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="50957-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="50957-133">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="50957-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="50957-134">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="50957-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="50957-135">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и нажмите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="50957-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="50957-136">Расширь **дерево до Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **исключений.**</span><span class="sxs-lookup"><span data-stu-id="50957-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="50957-137">Дважды **щелкните Кнопку Отключение автоматических исключений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="50957-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="50957-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50957-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="50957-139">Чтобы отключить список автоматических исключений на Windows Server 2016 2019 г., используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="50957-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="50957-140">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="50957-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="50957-141">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="50957-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="50957-142">[Используйте cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)для настройки и запуска антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="50957-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="50957-143">[Использование PowerShell с антивирусная программа в Microsoft Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="50957-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="50957-144">Используйте Windows управления (WMI), чтобы отключить список автоматических исключений на Windows Server 2016 и Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="50957-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="50957-145">Используйте метод **Set** класса [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="50957-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="50957-146">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="50957-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="50957-147">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="50957-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="50957-148">Список автоматических исключений</span><span class="sxs-lookup"><span data-stu-id="50957-148">List of automatic exclusions</span></span>

<span data-ttu-id="50957-149">В следующих разделах содержатся исключения, доставляемые с автоматическими путями файлов исключений и типами файлов.</span><span class="sxs-lookup"><span data-stu-id="50957-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="50957-150">Исключения по умолчанию для всех ролей</span><span class="sxs-lookup"><span data-stu-id="50957-150">Default exclusions for all roles</span></span>

<span data-ttu-id="50957-151">В этом разделе перечислены исключения по умолчанию для всех ролей Windows Server 2016 и 2019 года.</span><span class="sxs-lookup"><span data-stu-id="50957-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="50957-152">Расположение по умолчанию может быть иным, чем то, что указано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="50957-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="50957-153">Windows Файлы "temp.edb"</span><span class="sxs-lookup"><span data-stu-id="50957-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="50957-154">Windows Файлы обновления или файлы автоматического обновления</span><span class="sxs-lookup"><span data-stu-id="50957-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="50957-155">Безопасность Windows файлы</span><span class="sxs-lookup"><span data-stu-id="50957-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="50957-156">Файлы групповой политики</span><span class="sxs-lookup"><span data-stu-id="50957-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="50957-157">WINS files</span><span class="sxs-lookup"><span data-stu-id="50957-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="50957-158">Исключения службы репликации файлов (FRS)</span><span class="sxs-lookup"><span data-stu-id="50957-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="50957-159">Файлы в рабочей папке службы репликации файлов (FRS).</span><span class="sxs-lookup"><span data-stu-id="50957-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="50957-160">Рабочая папка FRS указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="50957-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="50957-161">Файлы журналов баз данных FRS.</span><span class="sxs-lookup"><span data-stu-id="50957-161">FRS Database log files.</span></span> <span data-ttu-id="50957-162">Папка файлов журнала данных FRS задана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="50957-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="50957-163">Папка постановок FRS.</span><span class="sxs-lookup"><span data-stu-id="50957-163">The FRS staging folder.</span></span> <span data-ttu-id="50957-164">Папка постановки указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="50957-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="50957-165">Папка preinstall FRS.</span><span class="sxs-lookup"><span data-stu-id="50957-165">The FRS preinstall folder.</span></span> <span data-ttu-id="50957-166">Эта папка указана в папке `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="50957-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="50957-167">База данных репликации распределенной файловой системы (DFSR) и рабочие папки.</span><span class="sxs-lookup"><span data-stu-id="50957-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="50957-168">Эти папки указаны ключом реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="50957-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="50957-169">Для настраиваемого расположения [см. пункт Отказ от автоматических исключений.](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="50957-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="50957-170">Исключения для процессов</span><span class="sxs-lookup"><span data-stu-id="50957-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="50957-171">Hyper-V исключений</span><span class="sxs-lookup"><span data-stu-id="50957-171">Hyper-V exclusions</span></span>

<span data-ttu-id="50957-172">В следующей таблице перечислены исключения типа файлов, исключения папок и исключения процессов, которые автоматически доставляются при установке Hyper-V роли.</span><span class="sxs-lookup"><span data-stu-id="50957-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="50957-173">Исключения типа файлов</span><span class="sxs-lookup"><span data-stu-id="50957-173">File type exclusions</span></span> |<span data-ttu-id="50957-174">Исключения папок</span><span class="sxs-lookup"><span data-stu-id="50957-174">Folder exclusions</span></span>  | <span data-ttu-id="50957-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="50957-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="50957-176">Файлы SYSVOL</span><span class="sxs-lookup"><span data-stu-id="50957-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="50957-177">Исключения Active Directory</span><span class="sxs-lookup"><span data-stu-id="50957-177">Active Directory exclusions</span></span>

<span data-ttu-id="50957-178">В этом разделе перечислены исключения, которые доставляются автоматически при установке служб домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50957-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="50957-179">Файлы баз данных NTDS</span><span class="sxs-lookup"><span data-stu-id="50957-179">NTDS database files</span></span>

<span data-ttu-id="50957-180">Файлы базы данных указаны в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="50957-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="50957-181">Файлы журнала транзакций AD DS</span><span class="sxs-lookup"><span data-stu-id="50957-181">The AD DS transaction log files</span></span>

<span data-ttu-id="50957-182">Файлы журнала транзакций указаны в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="50957-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="50957-183">Рабочая папка NTDS</span><span class="sxs-lookup"><span data-stu-id="50957-183">The NTDS working folder</span></span>

<span data-ttu-id="50957-184">Эта папка указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="50957-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="50957-185">Исключения процесса для файлов поддержки AD DS и AD DS</span><span class="sxs-lookup"><span data-stu-id="50957-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="50957-186">Исключения DHCP Server</span><span class="sxs-lookup"><span data-stu-id="50957-186">DHCP Server exclusions</span></span>

<span data-ttu-id="50957-187">В этом разделе перечислены исключения, которые доставляются автоматически при установке роли DHCP Server.</span><span class="sxs-lookup"><span data-stu-id="50957-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="50957-188">Расположения файлов DHCP Server указаны параметрами *DatabasePath,* *DhcpLogFilePath* и *BackupDatabasePath* в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="50957-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="50957-189">Исключения DNS Server</span><span class="sxs-lookup"><span data-stu-id="50957-189">DNS Server exclusions</span></span>

<span data-ttu-id="50957-190">В этом разделе перечислены исключения файлов и папок, а также исключения процессов, которые доставляются автоматически при установке роли DNS Server.</span><span class="sxs-lookup"><span data-stu-id="50957-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="50957-191">Исключения файлов и папок для роли DNS Server</span><span class="sxs-lookup"><span data-stu-id="50957-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="50957-192">Исключения процесса для роли DNS Server</span><span class="sxs-lookup"><span data-stu-id="50957-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="50957-193">Исключения файлов и служба хранилища служб</span><span class="sxs-lookup"><span data-stu-id="50957-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="50957-194">В этом разделе перечислены исключения файлов и папок, которые доставляются автоматически при установке роли File и служба хранилища Services.</span><span class="sxs-lookup"><span data-stu-id="50957-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="50957-195">Перечисленные ниже исключения не содержат исключений для роли Кластеризация.</span><span class="sxs-lookup"><span data-stu-id="50957-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="50957-196">Исключения print Server</span><span class="sxs-lookup"><span data-stu-id="50957-196">Print Server exclusions</span></span>

<span data-ttu-id="50957-197">В этом разделе перечислены исключения типа файлов, исключения папок и исключения процессов, которые доставляются автоматически при установке роли Print Server.</span><span class="sxs-lookup"><span data-stu-id="50957-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="50957-198">Исключения типа файлов</span><span class="sxs-lookup"><span data-stu-id="50957-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="50957-199">Исключения папок</span><span class="sxs-lookup"><span data-stu-id="50957-199">Folder exclusions</span></span>

<span data-ttu-id="50957-200">Эта папка указана в ключе реестра `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="50957-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="50957-201">Исключения для процессов</span><span class="sxs-lookup"><span data-stu-id="50957-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="50957-202">Исключения веб-сервера</span><span class="sxs-lookup"><span data-stu-id="50957-202">Web Server exclusions</span></span>

<span data-ttu-id="50957-203">В этом разделе перечислены исключения папок и исключения процессов, которые доставляются автоматически при установке роли веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="50957-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="50957-204">Исключения папок</span><span class="sxs-lookup"><span data-stu-id="50957-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="50957-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="50957-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="50957-206">Отключение сканирования файлов в папке Sysvol\Sysvol или папке SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="50957-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="50957-207">Текущее расположение папки и всех подмостков — это цель репараса файловой системы корневого `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` набора реплики.</span><span class="sxs-lookup"><span data-stu-id="50957-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="50957-208">В папках по умолчанию `Sysvol\Sysvol` используются следующие `SYSVOL_DFSR\Sysvol` расположения:</span><span class="sxs-lookup"><span data-stu-id="50957-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="50957-209">Путь к активному в настоящее время ссылается на долю NETLOGON и может быть определен именем `SYSVOL` значения SysVol в следующем подкайке: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="50957-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="50957-210">Исключите следующие файлы из этой папки и всех ее подвещений:</span><span class="sxs-lookup"><span data-stu-id="50957-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="50957-211">Windows Server Update Services исключений</span><span class="sxs-lookup"><span data-stu-id="50957-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="50957-212">В этом разделе перечислены исключения папок, которые доставляются автоматически при установке роли Windows Server Update Services (WSUS).</span><span class="sxs-lookup"><span data-stu-id="50957-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="50957-213">Папка WSUS указана в ключе реестра `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="50957-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="50957-214">См. также</span><span class="sxs-lookup"><span data-stu-id="50957-214">See also</span></span>

- [<span data-ttu-id="50957-215">Настройка и проверка исключений для антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="50957-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-216">Настройка и проверка исключений на основе имени, расширения и расположения папки</span><span class="sxs-lookup"><span data-stu-id="50957-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-217">Настройка и проверка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="50957-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-218">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="50957-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-219">Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений</span><span class="sxs-lookup"><span data-stu-id="50957-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="50957-220">антивирусная программа в Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="50957-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)