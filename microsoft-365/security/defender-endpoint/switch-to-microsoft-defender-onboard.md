---
title: Переключиться на Microsoft Defender для конечной точки — на борту
description: Это этап 3, на борту, для переноса из решения, не от Microsoft, в Microsoft Defender для конечной точки.
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
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 939fea5b815827f5afbe6cdf78fd9335da6337e8
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594065"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Переход на Microsoft Defender для конечной точки — этап 3. На борту

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Этап 1. Подготовка3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Этап 1. Подготовка](switch-to-microsoft-defender-prepare.md) | [![Этап 2. Настройка](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Этап 2. Настройка](switch-to-microsoft-defender-setup.md) | ![Этап 3. Подключение](images/phase-diagrams/onboard.png)<br/>Этап 3. Подключение |
|--|--|--|
|| |*Вы здесь!* |


**Добро пожаловать на этап 3 [перехода на Защитник для конечной точки](switch-to-microsoft-defender-migration.md#the-migration-process)**. Этот этап миграции включает следующие действия:

1. [Onboard devices to Defender for Endpoint.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [Запустите тест обнаружения](#run-a-detection-test).
3. [Подтвердите, антивирусная программа в Microsoft Defender находится в пассивном режиме на конечных точках.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)
4. [Получать обновления для антивирусная программа в Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
5. [Удалить решение, не в microsoft.](#uninstall-your-non-microsoft-solution) 
6. [Убедитесь, что Defender для конечной точки работает правильно.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Подключение устройств к Microsoft Defender для конечной точки

1. Перейдите в Центр безопасности в Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите.

2. Выберите **Параметры**  >  **управления**  >  **устройствами.** 

3. В **списке Выберите операционную систему для** запуска списка процессов бортового управления выберите операционную систему. 

4. В **методе Развертывания** выберите параметр. Следуйте ссылкам и подсказкам на устройствах организации. Нужна помощь? См. [методы onboarding](#onboarding-methods) (в этой статье).

### <a name="onboarding-methods"></a>Методы onboarding
 
Методы развертывания различаются в зависимости от операционной системы и предпочтительных методов. В следующей таблице перечислены ресурсы, которые помогут вам на борту в Defender для конечной точки:

|Операционные системы  |Методы  |
|---------|---------|
| Windows 10     | [Групповая политика](configure-endpoints-gp.md)<p>[Диспетчер конфигураций](configure-endpoints-sccm.md)<p>[Управление мобильными устройствами (Intune)](configure-endpoints-mdm.md)<p>[Локальный скрипт](configure-endpoints-script.md) <p>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.         |
| Windows 8.1 Корпоративная <p>Windows 8.1 Профессиональная <p>Windows 7 sp1 Enterprise <p>Windows 7 sp1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**ПРИМЕЧАНИЕ.** Microsoft Monitoring Agent агент Azure Log Analytics. Дополнительные сведения см. в обзоре агента [log Analytics.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 и более поздний <p>Windows Основное издание Server 2019 <p>Windows Сервер версии 1803 и более поздней версии | [Локальный скрипт](configure-endpoints-script.md) <p>[Групповая политика](configure-endpoints-gp.md) <p>[Диспетчер конфигураций](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[Скрипты на борту VDI для нестандартных устройств](configure-endpoints-vdi.md) <p>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 с пакетом обновления 1 (SP1)  | [Центр безопасности в Microsoft Defender](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Каталина)<p>10.14 (Mojave) | [Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)  |
| iOS | [Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)  |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS или более высокий LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | [Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Выполнить тест обнаружения

Чтобы убедиться, что бортовые устройства подключены должным образом к Защитнику для конечной точки, можно выполнить тест обнаружения.

|Операционная система  |Рекомендации  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows Сервер, версия 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | См. [тест run a detection](run-detection-test.md). <p>Посетите сайт демонстрационных сценариев Defender для конечной точки () и [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) попробуйте один или несколько сценариев. Например, попробуйте демонстрационный сценарий **облачной** защиты.    |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Каталина)<p>10.14 (Mojave)    | Скачайте и используйте приложение DIY по [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) ссылке . <p>Дополнительные сведения см. в [сайте Defender for Endpoint на macOS.](microsoft-defender-endpoint-mac.md)        |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS или более высокий LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | 1. Выполнить следующую команду и искать результат **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Откройте окно терминала и запустите следующую команду: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Запустите следующую команду, чтобы перечислить все обнаруженные угрозы: <br/>`mdatp threat list`. <p>Дополнительные сведения см. в [выпуске Defender for Endpoint on Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Подтвердите, антивирусная программа в Microsoft Defender находится в пассивном режиме на конечных точках

Теперь, когда конечные точки переназначили в Defender для конечной точки, следующим шагом будет убедиться, что антивирусная программа в Microsoft Defender работает в пассивном режиме. Для выполнения этой задачи можно использовать командную подсказку или PowerShell, как описано в следующей таблице:

| Метод  | Действия  |
|:-------|:-------|
|Командная строка     | 1. На Windows откройте командную подсказку в качестве администратора.<p>2. Введите `sc query windefend` и нажмите кнопку Ввод.<p>3. Просмотрите результаты, чтобы подтвердить, что антивирусная программа в Microsoft Defender работает в пассивном режиме.         |
| PowerShell     | 1. На Windows откройте Windows PowerShell в качестве администратора.<p>2. Запустите [комлет Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p>3. В списке результатов найди **amRunningMode: Пассивный режим** или **AMRunningMode: пассивный режим SxS.**    |

> [!NOTE]
> Вы можете *антивирусная программа* вместо *антивирусная программа в Microsoft Defender* в некоторых версиях Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Настройка антивирусная программа в Microsoft Defender на Windows Server в пассивный режим вручную

Чтобы установить антивирусная программа в Microsoft Defender пассивный режим на Windows Server, версии 1803 или более новой или Windows Server 2019, выполните следующие действия:

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

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Начните антивирусная программа в Microsoft Defender Windows Server 2016

Если вы используете Windows Server 2016, вам может потребоваться начать антивирусная программа в Microsoft Defender вручную. Это можно сделать с помощью cmdlet PowerShell `mpcmdrun.exe -wdenable` на устройстве.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Получать обновления для антивирусная программа в Microsoft Defender

Сохранение антивирусная программа в Microsoft Defender данных имеет решающее значение для обеспечения того, чтобы устройства были оснащены новейшими технологиями и функциями, необходимыми для защиты от новых вредоносных программ и методов атак, даже если антивирусная программа в Microsoft Defender работает в пассивном режиме. [(См. антивирусная программа в Microsoft Defender совместимость.)](microsoft-defender-antivirus-compatibility.md)

Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:

- Обновления аналитики безопасности
- Обновления продукта

Чтобы получить обновления, следуйте указаниям [в антивирусная программа в Microsoft Defender и применяйте базовые показатели.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-your-non-microsoft-solution"></a>Отостановка решения, не влияемого на Корпорацию Майкрософт

Если на данный момент у вас есть:

- На борту устройств организации в Defender для конечной точки и 
- антивирусная программа в Microsoft Defender установлена и включена, 

Далее необходимо удалить решение по защите конечных точек, не в microsoft. 

Чтобы получить помощь в решении этой задачи, вы можете связаться с командой технической поддержки поставщика решений.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Убедитесь, что Defender для конечной точки работает правильно

Теперь, когда вы перенаправили в Defender для конечной точки и вы отостановили свое прежнее решение, не в составе Microsoft, следующим шагом будет убедиться, что Defender для конечной точки работает правильно. Один из хороших способов сделать это, посетив сайт демо-сценариев Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Попробуйте один или несколько демонстрационных сценариев на этой странице, включая по крайней мере следующие:

- Облачная защита
- Потенциально нежелательные приложения (PUA)
- Защита сети (NP)

## <a name="next-steps"></a>Дальнейшие действия

**Поздравляем!** Вы завершили [миграцию в Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [Посетите панель мониторинга операций безопасности](security-operations-dashboard.md) в Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 
- [Управление защитником для конечной точки, после миграции](manage-atp-post-migration.md).
