---
title: Переключиться на Microsoft Defender для конечной точки — настройка
description: Этап 2, процесс настройки при переходе на Microsoft Defender для конечной точки.
keywords: миграция, Microsoft Defender для конечной точки, edr, Защитник Windows
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
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 07/02/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: a08b84d69a3ef92a5aa23a37f62208c296b3e785
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289623"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Переключиться на Microsoft Defender для конечной точки — этап 2: настройка

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Этап 1. Подготовка](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Этап 1. Подготовка](switch-to-microsoft-defender-prepare.md) |![Этап 2. Настройка](images/phase-diagrams/setup.png)<br/>Этап 2. Настройка |[![Этап 3. Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Этап 3. Подключение](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Вы здесь!* | |

**Добро пожаловать на этап установки перехода [на Защитник для конечной точки](switch-to-microsoft-defender-migration.md#the-migration-process)**. Этот этап включает в себя следующие действия:

1. [Переустановка/включить антивирусная программа в Microsoft Defender конечных точек](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).
2. [Настройка Защитника для конечной точки](#configure-defender-for-endpoint).
3. [Добавьте Defender для конечной точки в список исключений для существующего решения.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [Добавьте существующее решение в список исключений для антивирусная программа в Microsoft Defender.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)
5. [Настройка групп устройств, коллекций устройств и подразделений организации.](#set-up-your-device-groups-device-collections-and-organizational-units)
6. [Настройка политик антивирусного обеспечения и защиты в режиме реального времени.](#configure-antimalware-policies-and-real-time-protection)


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstall/enable антивирусная программа в Microsoft Defender конечных точках

В некоторых версиях Windows, антивирусная программа в Microsoft Defender при установке антивирусного и антивирусного решения антивирусная программа в Microsoft Defender отключены или отключены. До тех пор, пока устройства не будут перенагрузки в Defender for Endpoint, антивирусная программа в Microsoft Defender не будет работать в активном режиме наряду с антивирусным решением, не относяжимым к Майкрософт. Дополнительные возможности см. [в антивирусная программа в Microsoft Defender совместимости.](microsoft-defender-antivirus-compatibility.md)

Теперь, когда вы планируете перейти на Defender для конечной точки, может потребоваться предпринять определенные действия, чтобы переустановить или включить антивирусная программа в Microsoft Defender. 


| Тип конечной точки  | Действия  |
|---------|---------|
| Windows (например, конечные точки, работающие Windows 10)     | Как правило, вам не нужно принимать какие-либо меры для Windows клиентов (если антивирусная программа в Microsoft Defender не было uninstalled). Вот почему: <p>антивирусная программа в Microsoft Defender по-прежнему следует установить, но, скорее всего, отключен на данном этапе процесса миграции.<p> При установке решения антивируса и антивирусного программного обеспечения, не включаемого в Защитник для конечной точки, антивирусная программа в Microsoft Defender автоматически отключается. <p>Позже, когда конечные точки клиента находятся на борту в Defender для конечной точки, если эти конечные точки работают с антивирусным решением, которое не относится к Майкрософт, антивирусная программа в Microsoft Defender переходит в пассивный режим. <p>Если антивирусное решение, не включаемого в Корпорацию Майкрософт, будет отключлено, антивирусная программа в Microsoft Defender автоматически переходит в активный режим.  |
|Windows серверов     | На Windows Server необходимо переустановить антивирусная программа в Microsoft Defender и настроить его в пассивный режим вручную. Вот почему: <p>На Windows серверах при установке антивируса и антивируса, не в microsoft, антивирусная программа в Microsoft Defender не может работать вместе с антивирусным решением, не относяжимся к Майкрософт. В этих случаях антивирусная программа в Microsoft Defender отключена или неустановлена вручную. <p>Чтобы переустановить или включить антивирусная программа в Microsoft Defender на Windows Server, выполните следующие taks: <p>- [Установите отключениеAntiSpyware](#set-disableantispyware-to-false-on-windows-server) на ложный Windows Server (только при необходимости)<br/>- [Переустановка антивирусная программа в Microsoft Defender на Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [Настройка антивирусная программа в Microsoft Defender пассивного режима на Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)       |


> [!TIP]
> Дополнительные информацию о антивирусная программа в Microsoft Defender состояниях с антивирусной защитой, не в microsoft, см. в антивирусная программа в Microsoft Defender [совместимости.](microsoft-defender-antivirus-compatibility.md)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Установите отключениеAntiSpyware на ложный Windows Server

Ключ [реестра DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) использовался в прошлом для отключения антивирусная программа в Microsoft Defender и развертывания другого антивирусного продукта, например McAfee, Symantec или других. Как правило, этот ключ реестра не должен быть на Windows **устройствах и конечных точках;** Однако, если *у вас* есть настройка, вот как установить его значение `DisableAntiSpyware` false:

1. На устройстве Windows Server откройте редактор реестра.

2. Перейдите на сайт `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. В этой папке найди запись DWORD под названием **DisableAntiSpyware.**
   - Если вы не видите эту запись, вы все настроены.
   - Если вы видите **DisableAntiSpyware,** переходите к шагу 4.

4. Щелкните правой кнопкой мыши DWORD DisableAntiSpyware и выберите **Изменение**.

5. Установите значение `0` . (Это действие задает значение ключа реестра *ложным.)*

> [!TIP]
> Дополнительные информацию об этом ключе реестра см. в [см. в записи DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Переустановка антивирусная программа в Microsoft Defender на Windows Server

> [!IMPORTANT]
> Следующая процедура применяется только к конечным точкам или устройствам, которые запускают следующие версии Windows:
> - Windows Server 2019
> - Windows Сервер, версия 1803 (режим только для ядра)
> - Windows Server 2016 (см. следующий раздел, [используете ли вы Windows Server 2016?)](#are-you-using-windows-server-2016)

1. Как локальный администратор на конечной точке или устройстве откройте Windows PowerShell.

2. Запустите следующие cmdlets PowerShell: <br/>   

   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
   При использовании команды DISM в последовательности задач под управлением PS требуется следующий путь к cmd.exe.
   Пример.<br/>
   
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Чтобы проверить антивирусная программа в Microsoft Defender запущен, используйте следующий комдлет PowerShell: <br/>
   `Get-Service -Name windefend`

   И посмотрите на состояние *Running*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Настройка антивирусная программа в Microsoft Defender пассивного режима на Windows Server

1. Откройте редактор реестра и перейдите к <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Изменить (или создать) запись DWORD под названием **ForceDefenderPassiveMode** и указать следующие параметры:

   - Установите значение DWORD в **1**.
   - В **базовой** статье выберите **Hexadecimal**.

> [!NOTE]
> После встройки в Defender для конечной точки может потребоваться антивирусная программа в Microsoft Defender пассивный режим на Windows Server. Для проверки того, что пассивный режим был задан как ожидалось, поиск события *5007* в журнале **microsoft-Windows-Защитник Windows** Operational (расположен в ) и подтверждение клавиш реестра `C:\Windows\System32\winevt\Logs` **ForcePassiveMode** или **PassiveMode** были заданы 0x1 . 

### <a name="are-you-using-windows-server-2016"></a>Вы используете Windows Server 2016?

Если у вас есть конечные точки Windows Server 2016, вы не антивирусная программа в Microsoft Defender запустить антивирусная программа в Microsoft Defender наряду с антивирусным и антивирусным решением, не относя к Майкрософт. антивирусная программа в Microsoft Defender не может работать в пассивном режиме на Windows Server 2016. В этом случае необходимо удалить решение, не влияемого на антивирусы и антивирусные программы Майкрософт, и установить или включить антивирусная программа в Microsoft Defender. Дополнительные дополнительные возможности см. в этой ссылке в списке совместимость антивирусных [решений с Защитником для конечной точки.](microsoft-defender-antivirus-compatibility.md)

Если вы используете Windows Server 2016 и у вас возникли проблемы с включением антивирусная программа в Microsoft Defender, выполните следующие действия:

1. На устройстве откройте PowerShell в качестве администратора.

2. Введите следующий cmdlet PowerShell: `mpcmdrun -wdenable`

> [!TIP]
> Дополнительные сведения см. [в антивирусная программа в Microsoft Defender на Windows Server.](microsoft-defender-antivirus-on-windows-server.md)

## <a name="configure-defender-for-endpoint"></a>Настройка Защитника для конечной точки

Этот этап процесса миграции включает настройку антивирусная программа в Microsoft Defender конечных точек. Рекомендуется использовать Intune; Однако вы можете использовать любой из методов, перечисленных в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь является частью Microsoft Endpoint Manager. | 1. Перейдите в [центр администрирования Microsoft Endpoint Manager и](https://go.microsoft.com/fwlink/?linkid=2109431) войдите.<p> 2. **Выберите профили конфигурации** устройств и выберите тип профиля, который  >  необходимо настроить. Если вы еще не  создали тип профиля ограничений устройства или хотите создать новый, см. в этой странице Настройка параметров ограничения устройств в [Microsoft Intune.](/intune/device-restrictions-configure)<p> 3. Выберите **свойства,** а затем выберите **параметры конфигурации: Изменить**.<p> 4. Расширение **антивирусная программа в Microsoft Defender**. <p> 5. Включить **облачную защиту.**<p> 6. В **запросных пользователях перед** отсевом образца отправки выберите отправку всех **образцов автоматически.**<p> 7. При **обнаружении потенциально нежелательных** приложений при отсеве выберите **Включить** или **Аудит.**<p> 8. **Выберите обзор + сохранить,** а затем выберите **Сохранить**.<p>**Совет.** Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в Microsoft Intune [профилей устройств?](/intune/device-profiles).|
|Панель управления в Windows     |Следуйте указаниям здесь: [включи антивирусная программа в Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <p>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.        |
|[Расширенное управление групповыми политиками](/microsoft-desktop-optimization-pack/agpm/) <br/>или<br/>[Консоль управления групповой политикой](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Перейдите к **конфигурации** компьютера  >  **Административные**  >  **шаблоны** Windows компонентов  >  **антивирусная программа в Microsoft Defender**. <p> 2. И посмотрите на политику, называемую **отключением антивирусная программа в Microsoft Defender**.<p> 3. **Выберите параметр политики редактирования** и убедитесь, что политика отключена. Это действие позволяет антивирусная программа в Microsoft Defender. <p>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Добавление Microsoft Defender для конечной точки в список исключений для существующего решения

Этот этап процесса настройки включает добавление Защитника для конечной точки в список исключений для существующего решения по защите конечной точки и любых других продуктов безопасности, которые использует ваша организация. 

> [!TIP]
> Чтобы получить справку по настройке исключений, обратитесь к документации поставщика решений.

Конкретные исключения для настройки зависят от версии Windows конечных точек или устройств и указаны в следующей таблице:

|OS |Исключения |
|--|--|
|Windows 10 версии [1803](/windows/release-health/status-windows-10-1803) или более поздней версии [(см. Windows 10 сведения о выпуске)](/windows/release-health/release-information)<p>Windows 10 версии 1703 или 1709 с [установленным KB4493441](https://support.microsoft.com/help/4493441) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Сервер, версия 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 с пакетом обновления 1 (SP1)](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**ПРИМЕЧАНИЕ.** Мониторинг временного размещения файлов 6\45 может быть различными про номерными подмостки. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Добавьте существующее решение в список исключений для антивирусная программа в Microsoft Defender

На этом этапе процесса настройки в список исключений антивирусная программа в Microsoft Defender существующее решение. Вы можете выбрать один из нескольких способов добавления исключений в антивирусная программа в Microsoft Defender, как указано в следующей таблице:

|Метод | Действия|
|:---|:---|
| [Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**ПРИМЕЧАНИЕ.** Intune теперь является частью Microsoft Endpoint Manager. | 1. Перейдите в [центр администрирования Microsoft Endpoint Manager и](https://go.microsoft.com/fwlink/?linkid=2109431) войдите.<p> 2. **Выберите профили**  >  **конфигурации устройств,** а затем выберите профиль, который необходимо настроить.<p> 3. В **соответствии с управлением** выберите **свойства**.<p> 4. Выберите **параметры конфигурации: Изменить**.<p> 5. **Расширь антивирусная программа в Microsoft Defender,** а затем **антивирусная программа в Microsoft Defender исключений.**<p> 6. Укажите файлы и папки, расширения и процессы, чтобы исключить антивирусная программа в Microsoft Defender сканирования. Для справки [см. антивирусная программа в Microsoft Defender исключения.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. **Выберите обзор + сохранить**, а затем выбрать **сохранить**.  |
| [Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. С помощью консоли [Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)перейдите к политике Endpoint Protection ресурсов и соответствия требованиям, а затем выберите политику, которую   >    >  необходимо изменить. <p> 2. Укажите параметры исключения для файлов и папок, расширений и процессов, чтобы исключить антивирусная программа в Microsoft Defender проверки. |
| [Объект групповой политики](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.<p> 2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**<p> 3. Расширь дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > исключений.**<br/>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.<p> 4. Дважды щелкните параметр **"Исключения** пути" и добавьте исключения.<br/>- Установите параметр **Включено**.<br/>- В разделе **Параметры** выберите **Показать...**.<br/>- Укажите каждую папку по своей строке в столбце **Имя значения.**<br/>- Если вы указываете файл, убедитесь, что введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение. Введите **0** в **столбце Значение.**<p> 5. Выберите **ОК**.<p> 6. Дважды щелкните параметр **Исключения расширения** и добавьте исключения.<br/>- Установите параметр **Включено**.<br/>- В разделе **Параметры** выберите **Показать...**.<br/>- Введите каждое расширение файла по своей строке в столбце **Имя значения.**  Введите **0** в **столбце Значение.**<p> 7. Выберите **ОК**. |
| Объект локальной групповой политики |1. На конечной точке или устройстве откройте редактор локальной групповой политики. <p>2. Перейдите к **административным** шаблонам конфигурации  >    >  **компьютера Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **исключений**.<p>**ПРИМЕЧАНИЕ.** Вы можете *антивирусная программа* вместо антивирусная программа в Microsoft Defender *в* некоторых версиях Windows.<p>3. Укажите пути и исключения процесса. |
| Раздел реестра |1. Экспорт следующего ключа реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Импорт ключа реестра. Далее приведено два примера.<br/>- Локальный путь: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Доля сети: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Имейте в виду следующие пункты об исключениях

При [добавлении исключений в антивирусная программа в Microsoft Defender проверки](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)следует добавить исключения пути и процесса. 

Имейте в виду следующие моменты:

- *Исключения пути исключают* определенные файлы и все, к каким именно файлам можно получить доступ.
- *Исключения процесса исключают* все, что касается процесса, но не исключают самого процесса.
- Список исключений процесса с использованием полного пути, а не только их имени. (Метод только для имен менее безопасен.)
- Если каждый исполняемый (.exe) как исключение пути, так и исключение процесса, процесс и все, к чем он прикасается, исключаются.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Настройка групп устройств, коллекций устройств и подразделений организации

Группы устройств, коллекции устройств и организационные подразделения позволяют группе безопасности эффективно и эффективно управлять политиками безопасности и назначать их. В следующей таблице описаны все эти группы и их настройка. Организация может не использовать все три типа коллекции.

| Тип коллекции | Действия |
|:---|:---|
| [Группы устройств](/microsoft-365/security/defender-endpoint/machine-groups) (ранее называемые машинными группами) позволяют группе операций безопасности настраивать возможности безопасности, такие как автоматическое расследование и исправление.<p>Группы устройств также полезны для назначения доступа к этим устройствам, чтобы ваша группа операций безопасности при необходимости может принимать меры по исправлению. <p>Группы устройств создаются в [Центр безопасности в Microsoft Defender.](microsoft-defender-security-center.md) | 1. Перейдите к Центр безопасности в Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. В области навигации слева выберите группы устройств **Параметры**  >    >  **разрешений.**  <p>3. Выберите **+ Добавить группу устройств**.<p>4. Укажите имя и описание группы устройств.<p>5. В **списке уровня автоматизации** выберите параметр. (Мы рекомендуем автоматически устранять угрозы full **- исправление.)** Дополнительные статьи о различных уровнях автоматизации см. в статьи Как устраняются [угрозы.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Укажите условия для правила совпадения, чтобы определить, какие устройства относятся к группе устройств. Например, можно выбрать домен, версии ОС или даже использовать [теги устройств.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. На **вкладке Доступ пользователя** укажите роли, которые должны иметь доступ к устройствам, включенным в группу устройств. <p>8. Выберите **Готово**. |
| [Коллекции устройств позволяют](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) группе операций безопасности управлять приложениями, развертывать параметры соответствия требованиям или устанавливать обновления программного обеспечения на устройствах в организации.<p>Коллекции устройств создаются с помощью [диспетчера конфигурации.](/mem/configmgr/) | Выполните действия в [Create a collection](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
| [Организационные подразделения](/azure/active-directory-domain-services/create-ou) позволяют логически группить объекты, такие как учетные записи пользователей, учетные записи служб или учетные записи компьютера. Затем можно назначить администраторов определенным организационным подразделениям и применить групповую политику для применения целевых параметров конфигурации.<p> Организационные подразделения определяются в [Azure Active Directory domain Services.](/azure/active-directory-domain-services) | Выполните действия в [создании организационного подразделения в управляемом домене Azure Active Directory служб домена.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Настройка политик антивирусного обеспечения и защиты в режиме реального времени

С помощью диспетчера конфигурации и коллекции устройств настройте политики антивирусного обеспечения.

- См. [в рублях Create and deploy antimalware policies for Endpoint Protection в Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- При создании и настройке политик антивирусного программного обеспечения [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) убедитесь, что необходимо просмотреть параметры защиты в режиме реального времени и включить блокировку [на первый взгляд.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Вы можете развернуть политики перед устройствами организации на борту.

## <a name="next-step"></a>Следующий этап

**Поздравляем!** Вы завершили этап установки перехода [на Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Переходите к этапу 3. На борту в Defender для конечной точки](switch-to-microsoft-defender-onboard.md)
