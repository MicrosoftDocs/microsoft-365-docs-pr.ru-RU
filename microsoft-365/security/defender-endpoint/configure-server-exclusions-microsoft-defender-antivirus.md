---
title: Настройка исключений антивируса Microsoft Defender на Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Server включает автоматические исключения, основанные на роли сервера. Можно также добавить настраиваемые исключения.
keywords: исключения, сервер, автоматические исключения, автоматические, пользовательские, сканы, антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764345"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Настройка исключений антивируса Microsoft Defender на Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender на Windows Server 2016 и Windows Server 2019 автоматически регистрируется в определенных исключениях, определенных определенной ролью сервера. Эти исключения не отображаются в стандартных списках исключений, которые отображаются в [приложении Windows Security.](microsoft-defender-security-center-antivirus.md)

> [!NOTE]
> Автоматические исключения применяются только к проверке защиты в режиме реального времени (RTP). Автоматические исключения не будут соблюдаться во время проверки full/quick или on-demand.

Помимо автоматических исключений, определенных ролью сервера, можно добавить или удалить настраиваемые исключения. Для этого обратитесь к этим статьям:
- [Настройка и проверка исключений на основе имени, расширения и расположения папки](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений для файлов, открытых процессами](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Несколько моментов, которые необходимо иметь в виду

Имейте в виду следующие важные моменты:

- Пользовательские исключения имеют приоритет над автоматическими исключениями.
- Автоматические исключения применяются только к проверке защиты в режиме реального времени (RTP). Автоматические исключения не будут соблюдаться во время проверки full/quick или on-demand.
- Настраиваемые и дублирующиеся исключения не конфликтуют с автоматическими исключениями.
- Антивирус Microsoft Defender использует средства обслуживания и управления изображениями развертывания (DISM) для определения ролей, установленных на компьютере.

## <a name="opt-out-of-automatic-exclusions"></a>Отказ от автоматических исключений

В Windows Server 2016 и Windows Server 2019 заранее заданные исключения, доставленные обновлениями разведки безопасности, исключают только пути по умолчанию для роли или функции. Если вы установили роль или функцию на настраиваемом пути или хотите вручную управлять набором исключений, не забудьте отказаться от автоматических исключений, доставленных в обновлениях разведки безопасности. Но помните, что автоматически доставляемые исключения оптимизированы для ролей Windows Server 2016 и 2019. Рекомендации [по определению исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.

> [!WARNING]
> Отказ от автоматических исключений может отрицательно сказаться на производительности или привести к повреждениям данных. Автоматически доставляемые исключения оптимизированы для ролей Windows Server 2016 и Windows Server 2019.

Так как предопределение исключений исключает только пути по **умолчанию,** если переместить NTDS и SYSVOL на другой диск или путь, который отличается от исходного *пути,* необходимо добавить исключения вручную с помощью сведений [здесь](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .

Автоматические списки исключений можно отключить с помощью групп Политик, PowerShell и WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Использование групповой политики для отключения списка автоматических исключений на Windows Server 2016 и Windows Server 2019

1. На компьютере управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)) Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем нажмите **кнопку Изменить**.
2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и нажмите **административные шаблоны.**
3. Расширь дерево до **компонентов**  >  **Антивирусного исключения Microsoft Defender**  >  **Microsoft** Defender.
4. Дважды **щелкните Кнопку Отключение автоматических исключений** и установите параметр **Включено**. Нажмите кнопку **ОК**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Чтобы отключить список автоматических исключений на Windows Server 2016 и 2019, используйте cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- [Используйте cmdlets PowerShell для](use-powershell-cmdlets-microsoft-defender-antivirus.md)настройки и запуска антивируса Microsoft Defender.
- [Используйте PowerShell с антивирусом Microsoft Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Использование инструкции по управлению Windows (WMI) для отключения списка автоматических исключений на Windows Server 2016 и Windows Server 2019

Используйте метод **Set** класса [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) для следующих свойств:

```WMI
DisableAutoExclusions
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Список автоматических исключений

В следующих разделах содержатся исключения, доставляемые с автоматическими путями файлов исключений и типами файлов.

### <a name="default-exclusions-for-all-roles"></a>Исключения по умолчанию для всех ролей

В этом разделе перечислены исключения по умолчанию для всех ролей Windows Server 2016 и 2019.

> [!NOTE]
> Расположение по умолчанию может быть иным, чем то, что указано в этой статье.

#### <a name="windows-tempedb-files"></a>Файлы Windows "temp.edb"

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Файлы обновления Windows или файлы автоматического обновления

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Файлы безопасности Windows

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Файлы групповой политики

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS files

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Исключения службы репликации файлов (FRS)

- Файлы в рабочей папке службы репликации файлов (FRS). Рабочая папка FRS указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- Файлы журналов баз данных FRS. Папка файлов журнала данных FRS задана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- Папка постановок FRS. Папка постановки указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- Папка preinstall FRS. Эта папка указана в папке `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- База данных репликации распределенной файловой системы (DFSR) и рабочие папки. Эти папки указаны ключом реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Для настраиваемого расположения [см. пункт Отказ от автоматических исключений.](#opt-out-of-automatic-exclusions)

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

#### <a name="process-exclusions"></a>Исключения для процессов

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V исключений

В следующей таблице перечислены исключения типа файлов, исключения папок и исключения процессов, которые автоматически доставляются при установке Hyper-V роли.

|Исключения типа файлов |Исключения папок  | Process exclusions |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>Файлы SYSVOL

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Исключения Active Directory

В этом разделе перечислены исключения, которые доставляются автоматически при установке служб домена Active Directory.

#### <a name="ntds-database-files"></a>Файлы баз данных NTDS

Файлы базы данных указаны в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>Файлы журнала транзакций AD DS

Файлы журнала транзакций указаны в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>Рабочая папка NTDS

Эта папка указана в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Исключения процесса для файлов поддержки AD DS и AD DS

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>Исключения DHCP Server

В этом разделе перечислены исключения, которые доставляются автоматически при установке роли DHCP Server. Расположения файлов DHCP Server указаны параметрами *DatabasePath,* *DhcpLogFilePath* и *BackupDatabasePath* в ключе реестра `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>Исключения DNS Server

В этом разделе перечислены исключения файлов и папок, а также исключения процессов, которые доставляются автоматически при установке роли DNS Server.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Исключения файлов и папок для роли DNS Server

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Исключения процесса для роли DNS Server

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Исключения служб хранения и файлов

В этом разделе перечислены исключения файлов и папок, которые доставляются автоматически при установке роли Службы файлов и хранения. Перечисленные ниже исключения не содержат исключений для роли Кластеризация.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Исключения print Server

В этом разделе перечислены исключения типа файлов, исключения папок и исключения процессов, которые доставляются автоматически при установке роли Print Server.

#### <a name="file-type-exclusions"></a>Исключения типа файлов

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Исключения папок

Эта папка указана в ключе реестра `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Исключения для процессов

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Исключения веб-сервера

В этом разделе перечислены исключения папок и исключения процессов, которые доставляются автоматически при установке роли веб-сервера.

#### <a name="folder-exclusions"></a>Исключения папок

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Отключение сканирования файлов в папке Sysvol\Sysvol или папке SYSVOL_DFSR\Sysvol

Текущее расположение папки и всех подмостков — это цель репараса файловой системы корневого `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` набора реплики. В папках по умолчанию `Sysvol\Sysvol` используются следующие `SYSVOL_DFSR\Sysvol` расположения:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Путь к активному в настоящее время ссылается на долю NETLOGON и может быть определен именем `SYSVOL` значения SysVol в следующем подкайке: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Исключите следующие файлы из этой папки и всех ее подвещений:

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

### <a name="windows-server-update-services-exclusions"></a>cлужбы Windows Server Update Services исключений

В этом разделе перечислены исключения папок, которые доставляются автоматически при установке роли cлужбы Windows Server Update Services (WSUS). Папка WSUS указана в ключе реестра `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>См. также

- [Настройка и проверка исключений для проверки антивирусных программ Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений на основе имени, расширения и расположения папки](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений для файлов, открытых процессами](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Распространенные ошибки, которых следует избегать при определении исключений](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)