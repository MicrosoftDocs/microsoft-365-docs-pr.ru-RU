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
ms.date: 05/10/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: aff6439c08a4f8540a10589a436893c62e48d756
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327406"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Миграция из Symantec — этап 2. Настройка Microsoft Defender для конечной точки

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Этап 1. Подготовка](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Этап 1. Подготовка](symantec-to-microsoft-defender-atp-prepare.md) |![Этап 2. Настройка](images/phase-diagrams/setup.png)<br/>Этап 2. Настройка |[![Этап 3. Подключение](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Этап 3. Подключение](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Вы здесь!* | |


Добро пожаловать на этап установки перехода из **[Symantec в Microsoft Defender для конечной точки.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Этот этап включает в себя следующие действия:
1. [Включить или переустановить антивирус Microsoft Defender (для определенных версий Windows).](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Включить антивирус Microsoft Defender.](#enable-microsoft-defender-antivirus)
3. [Получите обновления антивируса Microsoft Defender.](#get-updates-for-microsoft-defender-antivirus)
4. [Добавьте Microsoft Defender для конечной точки в список исключений для Symantec.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Добавьте Symantec в список исключений для антивируса Microsoft Defender.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [Настройка групп устройств, коллекций устройств и подразделений организации.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Настройка политик антивирусного обеспечения и защиты в режиме реального времени.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Включить или переустановить антивирус Microsoft Defender (для определенных версий Windows)

> [!TIP]
> Если вы работаете с Windows 10, вам не нужно выполнять эту задачу. Приступить к **[включить антивирус Microsoft Defender](#enable-microsoft-defender-antivirus)**.

В некоторых версиях Windows антивирус Microsoft Defender мог быть отключен или отключен. Это происходит из-за того, что антивирус Microsoft Defender не входит в пассивный или отключенный режим при установке сторонного антивирусного продукта, например Symantec. Дополнительные дополнительные возможности см. в [веб-сайте Совместимость антивирусных программ Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

Теперь, когда вы переходите из Symantec в Microsoft Defender для конечной точки, необходимо включить или переустановить антивирус Microsoft Defender и настроить его на пассивный режим. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Переустановка антивируса Microsoft Defender на Windows Server

> [!NOTE]
> Следующая процедура применяется только к конечным точкам или устройствам, работающим в следующих версиях Windows:
> - Windows Server 2019
> - Windows Server, версия 1803 (режим только для ядра)
> - Windows Server 2016
> 
> Антивирус Microsoft Defender встроен в Windows 10, но может быть отключен. В этом случае приступить к [включить антивирус Microsoft Defender](#enable-microsoft-defender-antivirus).

1. Как локальный администратор на конечной точке или устройстве откройте Windows PowerShell.

1. Запустите следующие cmdlets PowerShell:<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > При использовании команды DISM в последовательности задач под управлением PS требуется следующий путь к cmd.exe.
    > Пример:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Чтобы убедиться, что антивирус Microsoft Defender запущен, используйте следующий cmdlet PowerShell: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Используете ли вы Windows Server 2016?

Если вы используете Windows Server 2016 и у вас возникли проблемы с включением антивируса Microsoft Defender, используйте следующий cmdlet PowerShell:

`mpcmdrun -wdenable`

> [!TIP]
> Остались вопросы? См. [антивирус Microsoft Defender на Windows Server 2016 и 2019](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Установите антивирус Microsoft Defender в пассивный режим на Windows Server

Так как ваша организация по-прежнему использует Symantec, необходимо настроить антивирус Microsoft Defender в пассивный режим. Таким образом, антивирус Symantec и Microsoft Defender может работать бок о бок, пока не закончится запись в Microsoft Defender для конечной точки.

1. Откройте редактор реестра и перейдите к <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Изменить (или создать) запись DWORD под названием **ForcePassiveMode** и указать следующие параметры:
   - Установите значение DWORD в **1**.
   - В **базовой** статье выберите **Hexadecimal**.

> [!NOTE]
> Для набора ключа реестра можно использовать другие методы, например следующие:
>- [Предпочтения групповой политики](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Локальный объект групповой политики](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Пакет в диспетчере конфигурации](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Включить антивирус Microsoft Defender

Так как ваша организация использует Symantec в качестве основного антивирусного решения, антивирус Microsoft Defender, скорее всего, отключен на устройствах Windows организации. Этот этап процесса миграции включает включение антивируса Microsoft Defender. 

Чтобы включить антивирус Microsoft Defender, рекомендуется использовать Intune. Однако вы можете использовать любые методы, перечисленные в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь является Microsoft Endpoint Manager. |1. Перейдите в центр администрирования [конечной](https://go.microsoft.com/fwlink/?linkid=2109431) точки Microsoft Manager и войдите.<p>2. **Выберите профили конфигурации** устройств и выберите тип профиля, который  >  необходимо настроить. Если вы еще не  создали тип профиля ограничения устройств или хотите создать новый, см. в странице Настройка параметров ограничения устройств в [Microsoft Intune.](/intune/device-restrictions-configure)<p>3. Выберите **свойства,** а затем выберите **параметры конфигурации: Изменить**.<p>4. Расширение **антивируса Microsoft Defender**. <p>5. Включить **облачную защиту.**<p>6. В **запросных пользователях перед** отсевом образца отправки выберите отправку всех **образцов автоматически.**<p>7. При **обнаружении потенциально нежелательных** приложений при отсеве выберите **Включить** или **Аудит.**<p>8. **Выберите обзор + сохранить,** а затем выберите **Сохранить**.<br/>Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в странице [What are Microsoft Intune device profiles?.](/intune/device-profiles)|
|Панель управления в Windows     |Следуйте указаниям здесь: [Включи антивирус Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*        |
|[Расширенное управление групповыми политиками](/microsoft-desktop-optimization-pack/agpm/) <br/>или<br/>[Консоль управления групповой политикой](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Перейдите к `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <p>2. Найди политику, называемую **отключением антивируса Microsoft Defender.**<p>3. **Выберите параметр политики редактирования** и убедитесь, что политика отключена. Это позволяет антивирус Microsoft Defender. <p>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.* |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Убедитесь, что антивирус Microsoft Defender находится в пассивном режиме

Антивирус Microsoft Defender может работать вместе с Symantec, если настроить антивирус Microsoft Defender в пассивный режим. Для выполнения этой задачи можно использовать командную подсказку или PowerShell, как описано в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|Командная строка     |1. На устройстве Windows откройте командную подсказку в качестве администратора. <p>2. Введите `sc query windefend` и нажмите кнопку Ввод.<p>3. Просмотрите результаты, чтобы подтвердить, что антивирус Microsoft Defender работает в пассивном режиме.         |
|PowerShell     |1. На устройстве Windows откройте Windows PowerShell в качестве администратора.<p>2. Запустите [комлет Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus)<p>3. В списке результатов найди **amRunningMode: Пассивный режим** или **AMRunningMode: пассивный режим SxS.**|

> [!NOTE]
> В некоторых версиях *Windows Защитник Windows* *антивирус,* а не антивирус Microsoft Defender.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Получать обновления антивируса Microsoft Defender

Обновление антивируса Microsoft Defender имеет решающее значение для обеспечения того, чтобы устройства были оснащены новейшими технологиями и функциями, необходимыми для защиты от новых вредоносных программ и методов атак, даже если антивирус Microsoft Defender работает в пассивном [режиме.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Существует два типа обновлений, связанных с обновлением антивируса Microsoft Defender:
- Обновления аналитики безопасности
- Обновления продукта

Чтобы получить обновления, следуйте указаниям в управлении обновлениями антивирусного антивируса Microsoft Defender и [применяйте базовые показатели.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Добавление Защитника Майкрософт для конечной точки в список исключений для Symantec

Этот этап процесса настройки включает добавление Microsoft Defender для конечной точки в список исключений для Symantec и любых других продуктов безопасности, которые использует ваша организация. Конкретные исключения, которые необходимо настроить, зависят от того, какая версия Windows работает с конечными точками или устройствами, и указаны в следующей таблице:

|OS |Исключения |
|--|--|
|- Windows 10, [версия 1803 или](/windows/release-health/status-windows-10-1803) более поздней версии (см. сведения о выпуске [Windows 10)](/windows/release-health/release-information)<br/>- Windows 10, версия 1703 или 1709 с [установленным KB4493441](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, версия 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**ПРИМЕЧАНИЕ.** В тех случаях, когда мониторинг временных файлов 6\45 может быть различным про номерами подмостки.<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Добавление Symantec в список исключений для антивируса Microsoft Defender

На этом этапе процесса настройки вы добавляете Symantec и другие решения безопасности в список исключений антивируса Microsoft Defender. 

> [!NOTE]
> Чтобы получить представление о том, какие процессы и службы исключить, см. в примере Broadcom's [Processes and services used by Endpoint Protection 14.](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)

При [добавлении исключений в антивирусные](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)проверки Microsoft Defender необходимо добавить исключения пути и процесса. Имейте в виду следующие моменты:
- Исключения пути исключают определенные файлы и все, к каким именно файлам можно получить доступ.
- Исключения процесса исключают все, что касается процесса, но не исключают самого процесса.
- Если каждый исполняемый (.exe) как исключение пути, так и исключение процесса, процесс и все, к чем он прикасается, исключаются.
- Список исключений процесса с использованием полного пути, а не только их имени. (Метод только для имен менее безопасен.)

Вы можете выбрать один из нескольких способов добавления исключений в антивирус Microsoft Defender, как указано в следующей таблице:

|Метод | Действия|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь является Microsoft Endpoint Manager. |1. Перейдите в центр администрирования [конечной](https://go.microsoft.com/fwlink/?linkid=2109431) точки Microsoft Manager и войдите.<p>2. **Выберите профили**  >  **конфигурации устройств,** а затем выберите профиль, который необходимо настроить.<p>3. В **соответствии с управлением** выберите **свойства**. <p>4. Выберите **параметры конфигурации: Изменить**.<p>5. Расширение **антивируса Microsoft Defender,** а затем расширение **исключений антивируса Microsoft Defender.**<p>6. Укажите файлы и папки, расширения и процессы, чтобы исключить из антивирусного сканирования Microsoft Defender. Для справки см. [исключения антивируса Microsoft Defender.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p>7. **Выберите обзор + сохранить**, а затем выбрать **сохранить**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. С помощью консоли Configuration  [Manager](/mem/configmgr/core/servers/manage/admin-console)перейдите к политикам защиты от конечной точки и активов и защите соответствия требованиям, а затем выберите политику, которую необходимо  >    >  изменить. <p>2. Укажите параметры исключения для файлов и папок, расширений и процессов, чтобы исключить из антивирусного сканирования Microsoft Defender. |
|[Объект групповой политики](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.<p>2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны.**<p>3. Расширь дерево до компонентов Windows > **антивируса Microsoft Defender > исключений.**<br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*<p>4. Дважды щелкните параметр **"Исключения** пути" и добавьте исключения.<p>- Установите параметр **Включено**.<p>- В разделе **Параметры** щелкните **Показать...**.<p>- Укажите каждую папку по своей строке в столбце **Имя значения.**<p>- Если вы указываете файл, убедитесь, что введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение. Введите **0** в **столбце Значение.**<p>5. Нажмите **кнопку ОК**.<p>6. Дважды щелкните параметр **Исключения расширения** и добавьте исключения.<p>- Установите параметр **Включено**.<p>- В разделе **Параметры** щелкните **Показать...**.<p>- Введите каждое расширение файла по своей строке в столбце **Имя значения.**  Введите **0** в **столбце Значение.**<br/>7. Нажмите **кнопку ОК**. |
|Объект локальной групповой политики |1. На конечной точке или устройстве откройте редактор локальной групповой политики. <p>2. Перейдите к **административным** шаблонам конфигурации  >    >  **компьютеров Windows Components**  >  **Антивирусные**  >  **исключения** Microsoft Defender . <br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*<p>3. Укажите пути и исключения процесса. |
|Раздел реестра |1. Экспорт следующего ключа реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Импорт ключа реестра. Далее приведено два примера.<br/>- Локальный путь: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Доля сети: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Настройка групп устройств, коллекций устройств и подразделений организации

| Тип коллекции | Действия |
|--|--|
|[Группы устройств](/microsoft-365/security/defender-endpoint/machine-groups) (ранее называемые группами машин) позволяют группе операций безопасности настраивать возможности безопасности, такие как автоматическое расследование и исправление.<br/> Группы устройств также полезны для назначения доступа к этим устройствам, чтобы ваша группа операций безопасности при необходимости может принимать меры по исправлению. <br/>Группы устройств создаются в Центре безопасности Защитника Майкрософт. |1. Перейдите в Центр безопасности защитника Майкрософт ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. В области навигации слева выберите **группы устройств**  >  **Settings Permissions.**  >    <p>3. Выберите **+ Добавить группу устройств**.<p>4. Укажите имя и описание группы устройств.<p>5. В **списке уровня автоматизации** выберите параметр. (Мы рекомендуем автоматически устранять угрозы full **- исправление.)** Дополнительные статьи о различных уровнях автоматизации см. в статьи Как устраняются [угрозы.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Укажите условия для правила совпадения, чтобы определить, какие устройства относятся к группе устройств. Например, можно выбрать домен, версии ОС или даже использовать [теги устройств.](/microsoft-365/security/defender-endpoint/machine-tags)<br/> <br/>7. На **вкладке Доступ пользователя** укажите роли, которые должны иметь доступ к устройствам, включенным в группу устройств. <p>8. Выберите **Готово**. |
|[Коллекции устройств позволяют](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) группе операций безопасности управлять приложениями, развертывать параметры соответствия требованиям или устанавливать обновления программного обеспечения на устройствах в организации. <br/>Коллекции устройств создаются с помощью [диспетчера конфигурации.](/mem/configmgr/) |Выполните действия в [Create a collection](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Организационные подразделения](/azure/active-directory-domain-services/create-ou) позволяют логически группить объекты, такие как учетные записи пользователей, учетные записи служб или учетные записи компьютера. Затем можно назначить администраторов определенным организационным подразделениям и применить групповую политику для применения целевых параметров конфигурации.<br/> Организационные единицы определяются в [службах домена Azure Active Directory.](/azure/active-directory-domain-services) | Выполните действия в ["Создание организационного подразделения" в управляемом домене Azure Active Directory Domain Services.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Настройка политик антивирусного обеспечения и защиты в режиме реального времени

С помощью диспетчера конфигурации и коллекции устройств настройте политики антивирусного обеспечения.

- См. [в рублях Create and deploy antimalware policies for Endpoint Protection in Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- При создании и настройке политик антивирусного программного обеспечения [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) убедитесь, что необходимо просмотреть параметры защиты в режиме реального времени и включить блокировку [на первый взгляд.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Вы можете развернуть политики перед устройствами организации на борту.

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап установки перехода из [Symantec в Microsoft Defender для конечной точки!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Переходите к этапу 3. На борту в Microsoft Defender для конечной точки](symantec-to-microsoft-defender-atp-onboard.md)
