---
title: Переключиться на Microsoft Defender для конечной точки — на борту
description: Это этап 3, на борту, для переноса из решения, не от Microsoft, в Microsoft Defender для конечной точки.
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
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 2916f113f3c26a9c33c6da1f235a9b143667b9cf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076510"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Переход на Microsoft Defender для конечной точки — этап 3. На борту

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Этап 1. Подготовка3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Этап 1. Подготовка](switch-to-microsoft-defender-prepare.md) | [![Этап 2. Настройка](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Этап 2. Настройка](switch-to-microsoft-defender-setup.md) | ![Этап 3. На борту](images/phase-diagrams/onboard.png)<br/>Этап 3. На борту |
|--|--|--|
|| |*Вы здесь!* |


**Добро пожаловать в фазу 3 перехода на [Microsoft Defender для конечной точки.](switch-to-microsoft-defender-migration.md#the-migration-process)** Этот этап миграции включает следующие действия:

1. [Onboard devices to Microsoft Defender for Endpoint.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [Запустите тест обнаружения](#run-a-detection-test).
3. [Удалить решение, не в microsoft.](#uninstall-your-non-microsoft-solution)
4. [Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboard devices to Microsoft Defender for Endpoint

1. Перейдите в Центр безопасности защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.
2. Выбор   >  onboarding **управления**  >  **устройствами параметров.** 
3. В **списке Выберите операционную систему для** запуска списка процессов бортового управления выберите операционную систему. 
4. В **методе Развертывания** выберите параметр. Следуйте ссылкам и подсказкам на устройствах организации. Нужна помощь? См. [методы onboarding](#onboarding-methods) (в этой статье).

### <a name="onboarding-methods"></a>Методы onboarding
 
Методы развертывания различаются в зависимости от выбранной операционной системы. Обратитесь к ресурсам, перечисленным в таблице ниже, чтобы получить помощь в включении.

|Операционная система  |Метод  |
|---------|---------|
|Windows 10     |- [Групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Диспетчер конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Управление мобильными устройствами (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Локальный скрипт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.         |
|- Windows 8.1 Корпоративная <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Агент мониторинга Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**ПРИМЕЧАНИЕ.** Агент мониторинга Майкрософт теперь является агентом Аналитики журналов Azure. Дополнительные сведения см. в обзоре агента [log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 и более поздний <br/>- Основное издание Windows Server 2019 <br/>- Windows Server версии 1803 и более поздней версии |- [Локальный скрипт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Диспетчер конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [Диспетчер конфигурации центра системы](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [Скрипты на борту VDI для нестандартных устройств](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Центр безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)<br/>- 10.13 (Высокая сьерра)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Onboard non-Windows devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Выполнить тест обнаружения

Чтобы убедиться, что бортовые устройства подключены должным образом к Microsoft Defender для конечной точки, можно выполнить тест обнаружения.

|Операционная система  |Рекомендации  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, версия 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |См. [тест run a detection](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test). <br/><br/>Посетите сайт демонстрационных сценариев Microsoft Defender for Endpoint () и попробуйте один или [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) несколько сценариев. Например, попробуйте демонстрационный сценарий **облачной** защиты.         |
|macOS<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)<br/>- 10.13 (Высокая сьерра)     |Скачайте и используйте приложение DIY по [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) ссылке . <br/><br/>Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки для Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Выполнить следующую команду и искать результат **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Откройте окно терминала и запустите следующую команду: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Запустите следующую команду, чтобы перечислить все обнаруженные угрозы: <br/>`mdatp threat list`. <br/><br/>Дополнительные сведения см. в [веб-сайте ATP Microsoft Defender для Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux) |

## <a name="uninstall-your-non-microsoft-solution"></a>Отостановка решения, не влияемого на Корпорацию Майкрософт

Теперь, когда вы перенастроили устройства организации в Microsoft Defender для конечной точки, следующим шагом будет удалить решение по защите конечных точек, не в microsoft.

Чтобы получить помощь на этом шаге, протянуть службу технической поддержки поставщика решений.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме

Теперь, когда вы отключили решение по защите конечной точки, не от Microsoft, следующим шагом будет обеспечение включения антивируса Microsoft Defender и Microsoft Defender для конечной точки в активном режиме.

Для этого посетите веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Попробуйте один или несколько демонстрационных сценариев на этой странице, включая по крайней мере следующие:
- Защита с облачным доставкой
- Потенциально нежелательные приложения (PUA)
- Защита сети (NP)

> [!IMPORTANT]
> Если вы используете Windows Server 2016, вам может потребоваться запустить антивирус Microsoft Defender вручную. Это можно сделать с помощью cmdlet PowerShell `mpcmdrun.exe -wdenable` на устройстве.

## <a name="next-steps"></a>Дальнейшие действия

**Поздравляем!** Вы завершили [миграцию в Microsoft Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [Посетите панель мониторинга операций безопасности](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) в Центре безопасности Защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) (). 
- [Управление Microsoft Defender для конечной точки, после миграции.](manage-atp-post-migration.md)
