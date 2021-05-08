---
title: Symantec в Microsoft Defender для конечной точки — этап 2, настройка
description: Это этап 2, установка, переноса из Symantec в Microsoft Defender для конечной точки
keywords: миграция, Microsoft Defender для конечной точки, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 32ed277c87f5cca1a286cc24549dc331774cf03b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245736"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Миграция из Symantec — этап 2. Настройка Microsoft Defender для конечной точки

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Этап 1. Подготовка](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Этап 1. Подготовка](symantec-to-microsoft-defender-atp-prepare.md) |![Этап 2. Настройка](images/phase-diagrams/setup.png)<br/>Этап 2. Настройка |[![Этап 3. Подключение](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Этап 3. Подключение](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Вы здесь!* | |


Добро пожаловать на этап установки перехода из **[Symantec в Microsoft Defender для конечной точки.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Этот этап включает в себя следующие действия:
1. [Включить или переустановить антивирусная программа в Microsoft Defender (для определенных версий Windows).](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Включить антивирусная программа в Microsoft Defender](#enable-microsoft-defender-antivirus).
3. [Получать обновления для антивирусная программа в Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
4. [Добавьте Microsoft Defender для конечной точки в список исключений для Symantec.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Добавьте Symantec в список исключений для антивирусная программа в Microsoft Defender.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [Добавьте Symantec в список исключений для Microsoft Defender для конечной точки.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
7. [Настройка групп устройств, коллекций устройств и подразделений организации.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Настройка политик антивирусного обеспечения и защиты в режиме реального времени.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Включить или переустановить антивирусная программа в Microsoft Defender (для определенных версий Windows)

> [!TIP]
> Если вы выполняете Windows 10, вам не нужно выполнять эту задачу. Продолжить, **[чтобы включить антивирусная программа в Microsoft Defender](#enable-microsoft-defender-antivirus)**.

В некоторых версиях Windows, антивирусная программа в Microsoft Defender, возможно, были отключены или отключены. Это происходит потому, антивирусная программа в Microsoft Defender не вступает в пассивный или отключенный режим при установке сторонного антивирусного продукта, например Symantec. Дополнительные возможности см. [в антивирусная программа в Microsoft Defender совместимости.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

Теперь, когда вы переходите из Symantec в Microsoft Defender для конечной точки, необходимо включить или переустановить антивирусная программа в Microsoft Defender и настроить его на пассивный режим. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Переустановка антивирусная программа в Microsoft Defender на Windows Server

> [!NOTE]
> Следующая процедура применяется только к конечным точкам или устройствам, которые запускают следующие версии Windows:
> - Windows Server 2019
> - Windows Сервер, версия 1803 (режим только для ядра)
> - Windows Server 2016
> 
> антивирусная программа в Microsoft Defender встроена в Windows 10, но может быть отключена. В этом случае приступить к [включить антивирусная программа в Microsoft Defender](#enable-microsoft-defender-antivirus).

1. Как локальный администратор на конечной точке или устройстве откройте Windows PowerShell.

1. Запустите следующие cmdlets PowerShell:<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > При использовании команды DISM в последовательности задач под управлением PS требуется следующий путь к cmd.exe.
    > Пример:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Чтобы проверить антивирусная программа в Microsoft Defender запущен, используйте следующий комдлет PowerShell: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Вы используете Windows Server 2016?

Если вы используете Windows Server 2016 и у вас возникли проблемы с включением антивирусная программа в Microsoft Defender, используйте следующий cmdlet PowerShell:

`mpcmdrun -wdenable`

> [!TIP]
> Требуется дополнительная помощь? См. [антивирусная программа в Microsoft Defender на Windows Server 2016 и 2019](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Настройка антивирусная программа в Microsoft Defender пассивного режима на Windows Server

Так как организация по-прежнему использует Symantec, необходимо антивирусная программа в Microsoft Defender пассивный режим. Таким образом, Symantec и антивирусная программа в Microsoft Defender могут работать бок о бок, пока вы не закончите запись в Microsoft Defender для конечной точки.

1. Откройте редактор реестра и перейдите к <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Изменить (или создать) запись DWORD под названием **ForceDefenderPassiveMode** и указать следующие параметры:
   - Установите значение DWORD в **1**.
   - В **базовой** статье выберите **Hexadecimal**.

> [!NOTE]
> Для набора ключа реестра можно использовать другие методы, например следующие:
>- [Предпочтения групповой политики](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Локальный объект групповой политики](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Пакет в диспетчере конфигурации](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Включить антивирусная программа в Microsoft Defender

Так как ваша организация использует Symantec в качестве основного антивирусного решения, антивирусная программа в Microsoft Defender, скорее всего, отключено на устройствах Windows организации. Этот шаг процесса миграции включает включение антивирусная программа в Microsoft Defender. 

Чтобы включить антивирусная программа в Microsoft Defender, рекомендуется использовать Intune. Однако вы можете использовать любые методы, перечисленные в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь Microsoft Endpoint Manager. |1. Перейдите в [центр администрирования Microsoft Endpoint Manager и](https://go.microsoft.com/fwlink/?linkid=2109431) войдите.<br/><br/>2. **Выберите профили конфигурации** устройств и выберите тип профиля, который  >  необходимо настроить. Если вы еще не  создали тип профиля ограничений устройства или хотите создать новый, см. в этой странице Настройка параметров ограничения устройств в [Microsoft Intune.](/intune/device-restrictions-configure)<br/><br/>3. Выберите **свойства,** а затем выберите **параметры конфигурации: Изменить**.<br/><br/>4. Расширение **антивирусная программа в Microsoft Defender**. <br/><br/>5. Включить **облачную защиту.**<br/><br/>6. В **запросных пользователях перед** отсевом образца отправки выберите отправку всех **образцов автоматически.**<br/><br/>7. При **обнаружении потенциально нежелательных** приложений при отсеве выберите **Включить** или **Аудит.**<br/><br/>8. **Выберите обзор + сохранить,** а затем выберите **Сохранить**.<br/>Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в Microsoft Intune [профилей устройств?](/intune/device-profiles).|
|Панель управления в Windows     |Следуйте указаниям здесь: [включи антивирусная программа в Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <br/>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.        |
|[Расширенное управление групповыми политиками](/microsoft-desktop-optimization-pack/agpm/) <br/>или<br/>[Консоль управления групповой политикой](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Перейдите к `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. И посмотрите на политику, называемую **отключением антивирусная программа в Microsoft Defender**.<br/><br/>3. **Выберите параметр политики редактирования** и убедитесь, что политика отключена. Это позволяет антивирусная программа в Microsoft Defender. <br/><br/>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows. |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Убедитесь, антивирусная программа в Microsoft Defender находится в пассивном режиме

антивирусная программа в Microsoft Defender может работать вместе с Symantec, если антивирусная программа в Microsoft Defender пассивный режим. Для выполнения этой задачи можно использовать командную подсказку или PowerShell, как описано в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|Командная строка     |1. На Windows откройте командную подсказку в качестве администратора. <br/><br/>2. Введите `sc query windefend` и нажмите кнопку Ввод.<br/><br/>3. Просмотрите результаты, чтобы подтвердить, что антивирусная программа в Microsoft Defender работает в пассивном режиме.         |
|PowerShell     |1. На Windows откройте Windows PowerShell в качестве администратора.<br/><br/>2. Запустите [комлет Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus)<br/> <br/>3. В списке результатов найди **amRunningMode: Пассивный режим** или **AMRunningMode: пассивный режим SxS.**|

> [!NOTE]
> Вы можете *антивирусная программа* вместо *антивирусная программа в Microsoft Defender* в некоторых версиях Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Получать обновления для антивирусная программа в Microsoft Defender

Сохранение антивирусная программа в Microsoft Defender очень важно для обеспечения того, чтобы устройства были оснащены новейшими технологиями и функциями, необходимыми для защиты от новых вредоносных программ и методов атак, даже если антивирусная программа в Microsoft Defender работает в пассивном [режиме.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:
- Обновления аналитики безопасности
- Обновления продукта

Чтобы получить обновления, следуйте указаниям [в антивирусная программа в Microsoft Defender и применяйте базовые показатели.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Добавление Защитника Майкрософт для конечной точки в список исключений для Symantec

Этот этап процесса настройки включает добавление Microsoft Defender для конечной точки в список исключений для Symantec и любых других продуктов безопасности, которые использует ваша организация. Конкретные исключения для настройки зависят от версии Windows конечных точек или устройств и указаны в следующей таблице:

|OS |Исключения |
|--|--|
|- Windows 10 версии [1803](/windows/release-health/status-windows-10-1803) или более поздней версии [(см. Windows 10 сведения о выпуске)](/windows/release-health/release-information)<br/>- Windows 10 версии 1703 или 1709 с [установленным KB4493441](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Сервер, версия 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>- [Windows Сервер 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**ПРИМЕЧАНИЕ.** В тех случаях, когда мониторинг временных файлов 6\45 может быть различным про номерами подмостки.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Добавьте Symantec в список исключений для антивирусная программа в Microsoft Defender

На этом этапе процесса настройки вы добавляете Symantec и другие решения безопасности в список антивирусная программа в Microsoft Defender исключений. 

> [!NOTE]
> Чтобы получить представление о том, какие процессы и службы исключить, см. в примере Broadcom's [Processes and services used by Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html).

При [добавлении исключений в антивирусная программа в Microsoft Defender проверки](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)следует добавить исключения пути и процесса. Имейте в виду следующие моменты:
- Исключения пути исключают определенные файлы и все, к каким именно файлам можно получить доступ.
- Исключения процесса исключают все, что касается процесса, но не исключают самого процесса.
- Если каждый исполняемый (.exe) как исключение пути, так и исключение процесса, процесс и все, к чем он прикасается, исключаются.
- Список исключений процесса с использованием полного пути, а не только их имени. (Метод только для имен менее безопасен.)

Вы можете выбрать один из нескольких способов добавления исключений в антивирусная программа в Microsoft Defender, как указано в следующей таблице:

|Метод | Действия|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь Microsoft Endpoint Manager. |1. Перейдите в [центр администрирования Microsoft Endpoint Manager и](https://go.microsoft.com/fwlink/?linkid=2109431) войдите.<br/><br/>2. **Выберите профили**  >  **конфигурации устройств,** а затем выберите профиль, который необходимо настроить.<br/><br/>3. В **соответствии с управлением** выберите **свойства**. <br/><br/>4. Выберите **параметры конфигурации: Изменить**.<br/><br/>5. **Расширь антивирусная программа в Microsoft Defender,** а затем **антивирусная программа в Microsoft Defender исключений.**<br/><br/>6. Укажите файлы и папки, расширения и процессы, чтобы исключить антивирусная программа в Microsoft Defender сканирования. Для справки [см. антивирусная программа в Microsoft Defender исключения.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. **Выберите обзор + сохранить**, а затем выбрать **сохранить**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. С помощью консоли [Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)перейдите к политике Endpoint Protection ресурсов и соответствия требованиям, а затем выберите политику, которую   >    >  необходимо изменить. <br/><br/>2. Укажите параметры исключения для файлов и папок, расширений и процессов, чтобы исключить антивирусная программа в Microsoft Defender проверки. |
|[Объект групповой политики](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.<br/><br/>2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны.**<br/><br/>3. Расширь дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > исключений.**<br/>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.<br/><br/>4. Дважды щелкните параметр **"Исключения** пути" и добавьте исключения.<br/><br/>- Установите параметр **Включено**.<br/><br/>- В разделе **Параметры** щелкните **Показать...**.<br/><br/>- Укажите каждую папку по своей строке в столбце **Имя значения.**<br/><br/>- Если вы указываете файл, убедитесь, что введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение. Введите **0** в **столбце Значение.**<br/><br/>5. Нажмите **кнопку ОК**.<br/><br/>6. Дважды щелкните параметр **Исключения расширения** и добавьте исключения.<br/><br/>- Установите параметр **Включено**.<br/><br/>- В разделе **Параметры** щелкните **Показать...**.<br/><br/>- Введите каждое расширение файла по своей строке в столбце **Имя значения.**  Введите **0** в **столбце Значение.**<br/>7. Нажмите **кнопку ОК**. |
|Объект локальной групповой политики |1. На конечной точке или устройстве откройте редактор локальной групповой политики. <br/><br/>2. Перейдите к **административным** шаблонам конфигурации  >    >  **компьютера Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **исключений**. <br/>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.<br/><br/>3. Укажите пути и исключения процесса. |
|Раздел реестра |1. Экспорт следующего ключа реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Импорт ключа реестра. Далее приведено два примера.<br/>- Локальный путь: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Доля сети: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Добавление Symantec в список исключений для Microsoft Defender для конечной точки

Чтобы добавить исключения в Microsoft Defender для конечной точки, создайте [индикаторы.](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)

1. Перейдите в Центр безопасности в Microsoft Defender [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.

1. В области навигации выберите **индикаторы Параметры**  >    >  **правил**.

1.  На **вкладке "Хеши файла"** выберите **индикатор Добавить**.

1. На **вкладке Индикатор** укажите следующие параметры:
   - Hash file (Need help? См. [в статье Найти hash файла с помощью CMPivot.)](#find-a-file-hash-using-cmpivot)
   - В **соответствии с истекает на (UTC)**, выберите **Никогда**.
   
1. На **вкладке Действие** укажите следующие параметры:
   - **Действие отклика:** **Разрешить**
   - Название и описание

1. На **вкладке Область** в **группах Устройств** выберите все устройства в **моей** области или Выберите **из списка**.

1. На **вкладке Сводка** просмотрите параметры и нажмите кнопку **Сохранить**.

### <a name="find-a-file-hash-using-cmpivot"></a>Поиск hash файла с помощью CMPivot

CMPivot — это утилита для диспетчера конфигурации в консоли. CMPivot предоставляет доступ к устройству в режиме реального времени в вашей среде. Он немедленно запускает запрос на все подключенные к настоящему моменту устройства в целевой коллекции и возвращает результаты. Дополнительные сведения см. [в обзоре CMPivot.](/mem/configmgr/core/servers/manage/cmpivot-overview)

Чтобы использовать CMPivot для получения хаша файла, выполните следующие действия:

1. Просмотрите [необходимые условия.](/mem/configmgr/core/servers/manage/cmpivot#prerequisites)<br/>

2. [Запуск CMPivot](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 

3. Подключение диспетчеру конфигурации `SCCM_ServerName.DomainName.com` ( ).

4. Выберите **вкладку Запрос.**

5. В **списке коллекция устройств** выберите **Все системы (по умолчанию).**

6. В поле запроса введите следующий запрос:<br/>
   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > В запросе выше замените *notepad.exe* на имя сторонних продуктов безопасности. 
   

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Настройка групп устройств, коллекций устройств и подразделений организации

| Тип коллекции | Действия |
|--|--|
|[Группы устройств](/microsoft-365/security/defender-endpoint/machine-groups) (ранее называемые группами машин) позволяют группе операций безопасности настраивать возможности безопасности, такие как автоматическое расследование и исправление.<br/> Группы устройств также полезны для назначения доступа к этим устройствам, чтобы ваша группа операций безопасности при необходимости может принимать меры по исправлению. <br/>Группы устройств создаются в Центр безопасности в Microsoft Defender. |1. Перейдите к Центр безопасности в Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. В области навигации слева выберите группы устройств **Параметры**  >    >  **разрешений.**  <br/><br/>3. Выберите **+ Добавить группу устройств**.<br/><br/>4. Укажите имя и описание группы устройств.<br/><br/>5. В **списке уровня автоматизации** выберите параметр. (Мы рекомендуем автоматически устранять угрозы full **- исправление.)** Дополнительные статьи о различных уровнях автоматизации см. в статьи Как устраняются [угрозы.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. Укажите условия для правила совпадения, чтобы определить, какие устройства относятся к группе устройств. Например, можно выбрать домен, версии ОС или даже использовать [теги устройств.](/microsoft-365/security/defender-endpoint/machine-tags)<br/> <br/>7. На **вкладке Доступ пользователя** укажите роли, которые должны иметь доступ к устройствам, включенным в группу устройств. <br/><br/>8. Выберите **Готово**. |
|[Коллекции устройств позволяют](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) группе операций безопасности управлять приложениями, развертывать параметры соответствия требованиям или устанавливать обновления программного обеспечения на устройствах в организации. <br/>Коллекции устройств создаются с помощью [диспетчера конфигурации.](/mem/configmgr/) |Выполните действия в [Create a collection](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Организационные подразделения](/azure/active-directory-domain-services/create-ou) позволяют логически группить объекты, такие как учетные записи пользователей, учетные записи служб или учетные записи компьютера. Затем можно назначить администраторов определенным организационным подразделениям и применить групповую политику для применения целевых параметров конфигурации.<br/> Организационные подразделения определяются в [Azure Active Directory domain Services.](/azure/active-directory-domain-services) | Выполните действия в [создании организационного подразделения в управляемом домене Azure Active Directory служб домена.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Настройка политик антивирусного обеспечения и защиты в режиме реального времени

С помощью диспетчера конфигурации и коллекции устройств настройте политики антивирусного обеспечения.

- См. [в рублях Create and deploy antimalware policies for Endpoint Protection в Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- При создании и настройке политик антивирусного программного обеспечения [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) убедитесь, что необходимо просмотреть параметры защиты в режиме реального времени и включить блокировку [на первый взгляд.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Вы можете развернуть политики перед устройствами организации на борту.

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап установки перехода из [Symantec в Microsoft Defender для конечной точки!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Переходите к этапу 3. На борту в Microsoft Defender для конечной точки](symantec-to-microsoft-defender-atp-onboard.md)
