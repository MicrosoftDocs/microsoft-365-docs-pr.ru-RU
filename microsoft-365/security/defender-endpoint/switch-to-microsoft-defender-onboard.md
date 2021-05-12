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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6b3b9fda0060108bd6a3c48188ff6e89261be096
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327250"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Переход на Microsoft Defender для конечной точки — этап 3. На борту

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Этап 1. Подготовка3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Этап 1. Подготовка](switch-to-microsoft-defender-prepare.md) | [![Этап 2. Настройка](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Этап 2. Настройка](switch-to-microsoft-defender-setup.md) | ![Этап 3. Подключение](images/phase-diagrams/onboard.png)<br/>Этап 3. Подключение |
|--|--|--|
|| |*Вы здесь!* |


**Добро пожаловать в фазу 3 перехода на [Microsoft Defender для конечной точки.](switch-to-microsoft-defender-migration.md#the-migration-process)** Этот этап миграции включает следующие действия:

1. [Onboard devices to Microsoft Defender for Endpoint.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [Запустите тест обнаружения](#run-a-detection-test).
3. [Удалить решение, не в microsoft.](#uninstall-your-non-microsoft-solution)
4. [Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Подключение устройств к Microsoft Defender для конечной точки

1. Перейдите в Центр безопасности в Microsoft Defender [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.
2. Выберите **Параметры**  >  **управления**  >  **устройствами.** 
3. В **списке Выберите операционную систему для** запуска списка процессов бортового управления выберите операционную систему. 
4. В **методе Развертывания** выберите параметр. Следуйте ссылкам и подсказкам на устройствах организации. Нужна помощь? См. [методы onboarding](#onboarding-methods) (в этой статье).

### <a name="onboarding-methods"></a>Методы onboarding
 
Методы развертывания различаются в зависимости от выбранной операционной системы. Обратитесь к ресурсам, перечисленным в таблице ниже, чтобы получить помощь в включении.

|Операционная система  |Метод  |
|---------|---------|
|Windows 10     |- [Групповой политики](configure-endpoints-gp.md)<br/>- [Диспетчер конфигурации](configure-endpoints-sccm.md)<br/>- [Управление мобильными устройствами (Intune)](configure-endpoints-mdm.md)<br/>- [Локальный скрипт](configure-endpoints-script.md) <p>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.         |
|- Windows 8.1 Корпоративная <br/>- Windows 8.1 Профессиональная <br/>- Windows 7 sp1 Enterprise <br/>- Windows 7 sp1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**ПРИМЕЧАНИЕ.** Microsoft Monitoring Agent агент Azure Log Analytics. Дополнительные сведения см. в обзоре агента [log Analytics.](/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 и более поздней <br/>- Windows Server 2019 основного выпуска <br/>- Windows Версии 1803 и более поздней версии |- [Локальный скрипт](configure-endpoints-script.md) <br/>- [Групповой политики](configure-endpoints-gp.md) <br/>- [Диспетчер конфигурации](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [Скрипты на борту VDI для нестандартных устройств](configure-endpoints-vdi.md) <p>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows 2008 R2 SP1  |- [Центр безопасности в Microsoft Defender](configure-server-endpoints.md)<br/>- [Защитник Azure](/azure/security-center/security-center-wdatp) |
|macOS<br/>- 11.3.1 (Big Sur) <br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)<p>iOS<p>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Выполнить тест обнаружения

Чтобы убедиться, что бортовые устройства подключены должным образом к Microsoft Defender для конечной точки, можно выполнить тест обнаружения.

|Операционная система  |Рекомендации  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, версия 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |См. [тест run a detection](run-detection-test.md). <p>Посетите сайт демонстрационных сценариев Microsoft Defender for Endpoint () и попробуйте один или [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) несколько сценариев. Например, попробуйте демонстрационный сценарий **облачной** защиты.         |
|macOS<br/>- 11.3.1 (Big Sur) <br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)    |Скачайте и используйте приложение DIY по [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) ссылке . <p>Дополнительные сведения см. [в сайте Microsoft Defender для конечной точки на macOS.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Выполнить следующую команду и искать результат **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Откройте окно терминала и запустите следующую команду: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Запустите следующую команду, чтобы перечислить все обнаруженные угрозы: <br/>`mdatp threat list`. <p>Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки в Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-your-non-microsoft-solution"></a>Отостановка решения, не влияемого на Корпорацию Майкрософт

Теперь, когда вы перенастроили устройства организации в Microsoft Defender для конечной точки, следующим шагом будет удалить решение по защите конечных точек, не в microsoft.

Чтобы получить помощь на этом шаге, протянуть службу технической поддержки поставщика решений.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме

Теперь, когда вы отключили решение по защите конечной точки, не от Microsoft, следующим шагом будет убедиться, что антивирусная программа в Microsoft Defender и Microsoft Defender для конечной точки включены и находятся в активном режиме.

Для этого посетите веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Попробуйте один или несколько демонстрационных сценариев на этой странице, включая по крайней мере следующие:
- Облачная защита
- Потенциально нежелательные приложения (PUA)
- Защита сети (NP)

> [!IMPORTANT]
> Если вы используете Windows Server 2016, вам может потребоваться начать антивирусная программа в Microsoft Defender вручную. Это можно сделать с помощью cmdlet PowerShell `mpcmdrun.exe -wdenable` на устройстве.

## <a name="next-steps"></a>Дальнейшие действия

**Поздравляем!** Вы завершили [миграцию в Microsoft Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [Посетите панель мониторинга операций безопасности](security-operations-dashboard.md) в Центр безопасности в Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Управление Microsoft Defender для конечной точки, после миграции.](manage-atp-post-migration.md)
