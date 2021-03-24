---
title: McAfee в Microsoft Defender для конечной точки — настройка
description: Это этап 2, Установка, для переноса из McAfee в Microsoft Defender для конечной точки.
keywords: миграция, защита от угроз защитника Windows, atp, edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 50e87eb188b64c99372d1a141f6a70e6748ecd2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073006"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>Миграция из McAfee — этап 2. Настройка Microsoft Defender для конечной точки

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Этап 1. Подготовка](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Этап 1. Подготовка](mcafee-to-microsoft-defender-prepare.md) |![Этап 2. Настройка](images/phase-diagrams/setup.png)<br/>Этап 2. Настройка |[![Этап 3. На борту](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Этап 3. На борту](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Вы здесь!* | |

Добро пожаловать на этап установки перехода из **[McAfee Endpoint Security (McAfee) в Microsoft Defender для конечной точки.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** Этот этап включает в себя следующие действия:
1. [Включить антивирус Microsoft Defender и подтвердить, что он в пассивном режиме.](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)
2. [Получите обновления антивируса Microsoft Defender.](#get-updates-for-microsoft-defender-antivirus)
3. [Добавьте Microsoft Defender для конечной точки в список исключений для McAfee](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee).
4. [Добавьте McAfee в список исключений для антивируса Microsoft Defender.](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus)
5. [Добавьте McAfee в список исключений для Microsoft Defender для конечной точки.](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
6. [Настройка групп устройств, коллекций устройств и подразделений организации.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Настройка политик антивирусного обеспечения и защиты в режиме реального времени.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Включить антивирус Microsoft Defender и подтвердить, что он в пассивном режиме

В некоторых версиях Windows, таких как Windows Server, антивирус Microsoft Defender мог быть отключен или отключен при установке решения McAfee. Это происходит из-за того, что антивирус Microsoft Defender не входит в пассивный или отключенный режим при установке сторонного антивирусного продукта, например McAfee. Подробнее об этом см. в сайте [Microsoft Defender Antivirus compatibility.)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Этот этап процесса миграции включает в себя следующие задачи:
- [Настройка параметра DisableAntiSpyware для ложного на Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Переустановка антивируса Microsoft Defender на Windows Server;](#reinstall-microsoft-defender-antivirus-on-windows-server)
- [Настройка антивируса Microsoft Defender в пассивном режиме на Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Включение антивируса Microsoft Defender на клиентских устройствах Windows;](#enable-microsoft-defender-antivirus-on-your-windows-client-devices) и
- [Подтверждение того, что антивирус Microsoft Defender настроен на пассивный режим.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Установите отключениеAntiSpyware на ложный сервер Windows Server

В прошлом ключ реестра [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) использовался для отключения антивируса Microsoft Defender и развертывания другого антивирусного продукта, например McAfee. Как правило, этот ключ реестра не должен быть на устройствах и конечных точках Windows; Однако, если у вас есть настройка, вот как установить `DisableAntiSpyware` его значение false:

1. На устройстве Windows Server откройте редактор реестра.

2. Перейдите по адресу `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. В этой папке найди запись DWORD под названием **DisableAntiSpyware.**

   - Если вы не видите эту запись, вы все настроены.

   - Если вы видите **DisableAntiSpyware,** переходите к шагу 4.

4. Щелкните правой кнопкой мыши DWORD DisableAntiSpyware и выберите **Изменение**.

5. Установите значение `0` . (Это задает значение ключа реестра *ложным.)*

> [!TIP]
> Дополнительные информацию об этом ключе реестра см. в [см. в записи DisableAntiSpyware.](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Переустановка антивируса Microsoft Defender на Windows Server

> [!NOTE]
> Следующая процедура применяется только к конечным точкам или устройствам, работающим в следующих версиях Windows:
> - Windows Server 2019
> - Windows Server, версия 1803 (режим только для ядра)
> - Windows Server 2016

1. Как локальный администратор на конечной точке или устройстве откройте Windows PowerShell.

2. Запустите следующие cmdlets PowerShell: <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

> [!NOTE]
> При использовании команды DISM в последовательности задач под управлением PS требуется следующий путь к cmd.exe.
> Пример.<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Чтобы убедиться, что антивирус Microsoft Defender запущен, используйте следующий cmdlet PowerShell: <br/>
   
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Используете ли вы Windows Server 2016?

Если вы используете Windows Server 2016 и у вас возникли проблемы с включением антивируса Microsoft Defender, используйте следующий cmdlet PowerShell:

`mpcmdrun -wdenable`

> [!TIP]
> Остались вопросы? См. [антивирус Microsoft Defender на Windows Server 2016 и 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Установите антивирус Microsoft Defender в пассивный режим на Windows Server

Так как ваша организация по-прежнему использует McAfee, необходимо настроить антивирус Microsoft Defender в пассивный режим. Таким образом, антивирус McAfee и Microsoft Defender может работать бок о бок, пока не закончится запись в Microsoft Defender для конечной точки.

1. Откройте редактор реестра и перейдите к <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Изменить (или создать) запись DWORD под названием **ForceDefenderPassiveMode** и указать следующие параметры:
   
   - Установите значение DWORD в **1**.
   
   - В **базовой** статье выберите **Hexadecimal**.

> [!NOTE]
> Для набора ключа реестра можно использовать другие методы, например следующие:
>- [Предпочтения групповой политики](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Локальный объект групповой политики](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Пакет в диспетчере конфигурации](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Включить антивирус Microsoft Defender на клиентских устройствах Windows

Так как ваша организация использует McAfee в качестве основного антивирусного решения, антивирус Microsoft Defender, скорее всего, отключен на устройствах Windows организации. Этот этап процесса миграции включает включение антивируса Microsoft Defender. 

Чтобы включить антивирус Microsoft Defender, рекомендуется использовать Intune. Однако вы можете использовать любые методы, перечисленные в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**ПРИМЕЧАНИЕ.** Intune теперь является Microsoft Endpoint Manager. |1. Перейдите в центр администрирования [конечной](https://go.microsoft.com/fwlink/?linkid=2109431) точки Microsoft Manager и войдите.<br/><br/>2. **Выберите профили конфигурации** устройств и выберите тип профиля, который  >  необходимо настроить. <br/>Если вы еще не  создали тип профиля ограничения устройств или хотите создать новый, см. в странице Настройка параметров ограничения устройств в [Microsoft Intune.](https://docs.microsoft.com/intune/device-restrictions-configure)<br/><br/>3. Выберите **свойства,** а затем выберите **параметры конфигурации: Изменить**.<br/><br/>4. Расширение **антивируса Microsoft Defender**. <br/><br/>5. Включить **облачную защиту.**<br/><br/>6. В **запросных пользователях перед** отсевом образца отправки выберите отправку всех **образцов автоматически.**<br/><br/>7. При **обнаружении потенциально нежелательных** приложений при отсеве выберите **Включить** или **Аудит.**<br/><br/>8. **Выберите обзор + сохранить,** а затем выберите **Сохранить**.<br/><br/>Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в странице [What are Microsoft Intune device profiles?.](https://docs.microsoft.com/intune/device-profiles)|
|Панель управления в Windows     |Следуйте указаниям здесь: [Включи антивирус Microsoft Defender](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows). <br/><br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*        |
|[Расширенное управление групповыми политиками](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>или<br/>[Консоль управления групповой политикой](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Перейдите к `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. Найди политику, называемую **отключением антивируса Microsoft Defender.**<br/> <br/>3. **Выберите параметр политики редактирования** и убедитесь, что политика отключена. Это позволяет антивирус Microsoft Defender. <br/><br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.* |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Подтверждение того, что антивирус Microsoft Defender находится в пассивном режиме

Антивирус Microsoft Defender может работать вместе с McAfee, если вы установите антивирус Microsoft Defender в пассивный режим. Для выполнения этой задачи можно использовать командную подсказку или PowerShell, как описано в следующей таблице:

|Метод  |Действия  |
|---------|---------|
|Командная строка     |1. На устройстве Windows откройте командную подсказку в качестве администратора. <br/><br/>2. Введите `sc query windefend` и нажмите кнопку Ввод.<br/><br/>3. Просмотрите результаты, чтобы подтвердить, что антивирус Microsoft Defender работает в пассивном режиме.         |
|PowerShell     |1. На устройстве Windows откройте Windows PowerShell в качестве администратора.<br/><br/>2. Запустите [комлет Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) <br/><br/>3. В списке результатов найди **amRunningMode: Пассивный режим** или **AMRunningMode: пассивный режим SxS.**|

> [!NOTE]
> В некоторых версиях *Windows Защитник Windows* *антивирус,* а не антивирус Microsoft Defender.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Получать обновления антивируса Microsoft Defender

Обновление антивируса Microsoft Defender имеет решающее значение для обеспечения того, чтобы устройства были оснащены новейшими технологиями и функциями, необходимыми для защиты от новых вредоносных программ и методов атак, даже если антивирус Microsoft Defender работает в пассивном [режиме.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Существует два типа обновлений, связанных с обновлением антивируса Microsoft Defender:
- Обновления аналитики безопасности
- Обновления продукта

Чтобы получить обновления, следуйте указаниям в управлении обновлениями антивирусного антивируса Microsoft Defender и [применяйте базовые показатели.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>Добавление Защитника Майкрософт для конечной точки в список исключений для McAfee

Этот этап процесса настройки включает добавление Microsoft Defender для конечной точки в список исключений для McAfee и любых других продуктов безопасности, которые использует ваша организация. 

> [!TIP]
> Чтобы получить справку по настройке исключений, обратитесь к документации McAfee, например к следующей статье: [McAfee Endpoint Security 10.5.0 - Руководство](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html)по продуктам модуля предотвращения угроз (McAfee ePolicy Orchestrator) - Windows: Настройка исключений .

Конкретные исключения, которые необходимо настроить, зависят от того, какая версия Windows работает с конечными точками или устройствами, и указаны в следующей таблице:

|OS |Исключения |
|--|--|
|- Windows 10, [версия 1803 или](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) более поздней версии (см. сведения о выпуске [Windows 10)](https://docs.microsoft.com/windows/release-health/release-information)<br/>- Windows 10, версия 1703 или [1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) с [установленным KB4493441](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, версия 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**ПРИМЕЧАНИЕ.** В тех случаях, когда мониторинг временных файлов 6\45 может быть различным про номерами подмостки.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Добавление McAfee в список исключений для антивируса Microsoft Defender

На этом этапе процесса настройки вы добавляете McAfee и другие решения безопасности в список исключений антивируса Microsoft Defender. 

При [добавлении исключений в антивирусные](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)проверки Microsoft Defender необходимо добавить исключения пути и процесса. Имейте в виду следующие моменты:
- Исключения пути исключают определенные файлы и все, к каким именно файлам можно получить доступ.
- Исключения процесса исключают все, что касается процесса, но не исключают самого процесса.
- Если вы перечислите каждый исполняемый (.exe) как исключение пути, так и исключение процесса, процесс и все, к чем он прикасается, исключаются.
- Список исключений процесса с использованием полного пути, а не только их имени. (Метод только для имен менее безопасен.)

Вы можете выбрать один из нескольких способов добавления исключений в антивирус Microsoft Defender, как указано в следующей таблице:

|Метод | Действия|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**ПРИМЕЧАНИЕ.** Intune теперь является Microsoft Endpoint Manager. |1. Перейдите в центр администрирования [конечной](https://go.microsoft.com/fwlink/?linkid=2109431) точки Microsoft Manager и войдите.<br/><br/>2. **Выберите профили**  >  **конфигурации устройств,** а затем выберите профиль, который необходимо настроить.<br/><br/>3. В **соответствии с управлением** выберите **свойства**. <br/><br/>4. Выберите **параметры конфигурации: Изменить**.<br/><br/>5. Расширение **антивируса Microsoft Defender,** а затем расширение **исключений антивируса Microsoft Defender.**<br/><br/>6. Укажите файлы и папки, расширения и процессы, чтобы исключить из антивирусного сканирования Microsoft Defender. Для справки см. [исключения антивируса Microsoft Defender.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. **Выберите обзор + сохранить**, а затем выбрать **сохранить**.  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. С помощью консоли Configuration  [Manager](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)перейдите к политикам защиты от конечной точки и активов и защите соответствия требованиям, а затем выберите политику, которую необходимо  >    >  изменить. <br/><br/>2. Укажите параметры исключения для файлов и папок, расширений и процессов, чтобы исключить из антивирусного сканирования Microsoft Defender. |
|[Объект групповой политики](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.<br/><br/>2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны.**<br/><br/>3. Расширь дерево до компонентов Windows > **антивируса Microsoft Defender > исключений.**<br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*<br/><br/>4. Дважды щелкните параметр **"Исключения** пути" и добавьте исключения.<br/>- Установите параметр **Включено**.<br/>- В разделе **Параметры** щелкните **Показать...**.<br/>- Укажите каждую папку по своей строке в столбце **Имя значения.**<br/>- Если вы указываете файл, убедитесь, что введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение. Введите **0** в **столбце Значение.**<br/><br/>5. Нажмите **кнопку ОК**.<br/><br/>6. Дважды щелкните параметр **Исключения расширения** и добавьте исключения.<br/>- Установите параметр **Включено**.<br/>- В разделе **Параметры** щелкните **Показать...**.<br/>- Введите каждое расширение файла по своей строке в столбце **Имя значения.**  Введите **0** в **столбце Значение.**<br/><br/>7. Нажмите **кнопку ОК**. |
|Объект локальной групповой политики |1. На конечной точке или устройстве откройте редактор локальной групповой политики. <br/><br/>2. Перейдите к **административным** шаблонам конфигурации  >    >  **компьютеров Windows Components**  >  **Антивирусные**  >  **исключения** Microsoft Defender . <br/>**ПРИМЕЧАНИЕ.** В некоторых версиях *Windows Защитник Windows* антивирус, а не антивирус *Microsoft Defender.*<br/><br/>3. Укажите пути и исключения процесса. |
|Раздел реестра |1. Экспорт следующего ключа реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Импорт ключа реестра. Далее приведено два примера.<br/>- Локальный путь: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Доля сети: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Добавление McAfee в список исключений для Microsoft Defender для конечной точки

Чтобы добавить исключения в Microsoft Defender для конечной точки, создайте [индикаторы.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)

1. Перейдите в Центр безопасности защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.

2. В области навигации выберите **индикаторы правил**  >    >  **параметров.**

3.  На **вкладке "Хеши файла"** выберите **индикатор Добавить**.

3. На **вкладке Индикатор** укажите следующие параметры:
   - Hash file (Need help? См. [в статье Найти hash файла с помощью CMPivot.)](#find-a-file-hash-using-cmpivot)
   - В **соответствии с истекает на (UTC)**, выберите **Никогда**.

4. На **вкладке Действие** укажите следующие параметры:
   - **Действие отклика:** **Разрешить**
   - Название и описание

5. На **вкладке Область** в **группах Устройств** выберите все устройства в **моей** области или Выберите **из списка**.

6. На **вкладке Сводка** просмотрите параметры и нажмите кнопку **Сохранить**.

### <a name="find-a-file-hash-using-cmpivot"></a>Поиск hash файла с помощью CMPivot

CMPivot — это утилита для диспетчера конфигурации в консоли. CMPivot предоставляет доступ к устройству в режиме реального времени в вашей среде. Он немедленно запускает запрос на все подключенные к настоящему моменту устройства в целевой коллекции и возвращает результаты. Дополнительные сведения см. [в обзоре CMPivot.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)

Чтобы использовать CMPivot для получения хаша файла, выполните следующие действия:

1. Просмотрите [необходимые условия.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)

2. [Запуск CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 

3. Подключение к диспетчеру конфигурации `SCCM_ServerName.DomainName.com` ( ).

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
|[Группы устройств](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (ранее называемые группами машин) позволяют группе операций безопасности настраивать возможности безопасности, такие как автоматическое расследование и исправление.<br/><br/> Группы устройств также полезны для назначения доступа к этим устройствам, чтобы ваша группа операций безопасности при необходимости может принимать меры по исправлению. <br/><br/>Группы устройств создаются в Центре безопасности Защитника Майкрософт. |1. Перейдите в Центр безопасности защитника Майкрософт ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. В области навигации слева выберите **группы устройств**  >  **Settings Permissions.**  >    <br/><br/>3. Выберите **+ Добавить группу устройств**.<br/><br/>4. Укажите имя и описание группы устройств.<br/><br/>5. В **списке уровня автоматизации** выберите параметр. (Мы рекомендуем автоматически устранять угрозы full **- исправление.)** Дополнительные статьи о различных уровнях автоматизации см. в статьи Как устраняются [угрозы.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. Укажите условия для правила совпадения, чтобы определить, какие устройства относятся к группе устройств. Например, можно выбрать домен, версии ОС или даже использовать [теги устройств.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/><br/>7. На **вкладке Доступ пользователя** укажите роли, которые должны иметь доступ к устройствам, включенным в группу устройств. <br/><br/>8. Выберите **Готово**. |
|[Коллекции устройств позволяют](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) группе операций безопасности управлять приложениями, развертывать параметры соответствия требованиям или устанавливать обновления программного обеспечения на устройствах в организации. <br/><br/>Коллекции устройств создаются с помощью [диспетчера конфигурации.](https://docs.microsoft.com/mem/configmgr/) |Выполните действия в [Create a collection](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Организационные подразделения](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) позволяют логически группить объекты, такие как учетные записи пользователей, учетные записи служб или учетные записи компьютера. Затем можно назначить администраторов определенным организационным подразделениям и применить групповую политику для применения целевых параметров конфигурации.<br/><br/> Организационные единицы определяются в [службах домена Azure Active Directory.](https://docs.microsoft.com/azure/active-directory-domain-services) | Выполните действия в ["Создание организационного подразделения" в управляемом домене Azure Active Directory Domain Services.](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Настройка политик антивирусного обеспечения и защиты в режиме реального времени

С помощью диспетчера конфигурации и коллекции устройств настройте политики антивирусного обеспечения.

- См. [в рублях Create and deploy antimalware policies for Endpoint Protection in Configuration Manager.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- При создании и настройке политик антивирусного программного обеспечения [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) убедитесь, что необходимо просмотреть параметры защиты в режиме реального времени и включить блокировку [на первый взгляд.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Вы можете развернуть политики перед устройствами организации на борту.

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап установки перехода из [McAfee в Microsoft Defender для конечной точки!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Переходите к этапу 3. На борту в Microsoft Defender для конечной точки](mcafee-to-microsoft-defender-onboard.md)
