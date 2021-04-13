---
title: Symantec в Microsoft Defender для конечной точки — этап 3, onboarding
description: Это этап 3, онбординг, миграции из Symantec в Microsoft Defender для конечной точки
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 1d332f6b0d6338d18c5a85dcf737f968f00f275f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689525"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Миграция из Symantec — этап 3: на борту в Microsoft Defender для конечной точки

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Этап 1. Подготовка](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Этап 1. Подготовка](symantec-to-microsoft-defender-atp-prepare.md) |[![Этап 2. Настройка](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Этап 2. Настройка](symantec-to-microsoft-defender-atp-setup.md) |![Этап 3. Подключение](images/phase-diagrams/onboard.png)<br/>Этап 3. Подключение |
|--|--|--|
|| |*Вы здесь!* |


**Добро пожаловать на этап 3 [миграции из Symantec в Microsoft Defender для конечной точки.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Этот этап миграции включает следующие действия:

1. [Onboard devices to Microsoft Defender for Endpoint.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [Запустите тест обнаружения](#run-a-detection-test).
3. [Удалить Symantec](#uninstall-symantec).
4. [Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Подключение устройств к Microsoft Defender для конечной точки

1. Перейдите в Центр безопасности защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.
2. Выбор   >  onboarding **управления**  >  **устройствами параметров.** 
3. В **списке Выберите операционную систему для** запуска списка процессов бортового управления выберите операционную систему. 
4. В **методе Развертывания** выберите параметр. Следуйте ссылкам и подсказкам на устройствах организации. Нужна помощь? См. [методы onboarding](#onboarding-methods) (в этой статье).

### <a name="onboarding-methods"></a>Методы onboarding
 
Методы развертывания различаются в зависимости от выбранной операционной системы. Обратитесь к ресурсам, перечисленным в таблице ниже, чтобы получить помощь в включении.

|Операционная система  |Method  |
|---------|---------|
|Windows 10     |- [Групповой политики](configure-endpoints-gp.md)<br/>- [Диспетчер конфигурации](configure-endpoints-sccm.md)<br/>- [Управление мобильными устройствами (Intune)](configure-endpoints-mdm.md)<br/>- [Локальный скрипт](configure-endpoints-script.md) <br/><br/>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.         |
|- Windows 8.1 Корпоративная <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Агент мониторинга Майкрософт](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**ПРИМЕЧАНИЕ.** Агент мониторинга Майкрософт теперь является агентом Аналитики журналов Azure. Дополнительные сведения см. в обзоре агента [log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 и более поздний <br/>- Основное издание Windows Server 2019 <br/>- Windows Server версии 1803 и более поздней версии |- [Локальный скрипт](configure-endpoints-script.md) <br/>- [Групповой политики](configure-endpoints-gp.md) <br/>- [Диспетчер конфигурации](/configure-endpoints-sccm.md) <br/>- [Диспетчер конфигурации центра системы](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [Скрипты на борту VDI для нестандартных устройств](configure-endpoints-vdi.md) <br/><br/>**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Центр безопасности Защитника Майкрософт](configure-server-endpoints.md)<br/>- [Центр безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)<br/>- 10.13 (Высокая сьерра)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Выполнить тест обнаружения

Чтобы убедиться, что бортовые устройства подключены должным образом к Microsoft Defender для конечной точки, можно выполнить тест обнаружения.

|Операционная система  |Рекомендации  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, версия 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |См. [тест run a detection](run-detection-test.md). <br/><br/>Посетите сайт демонстрационных сценариев Microsoft Defender for Endpoint () и попробуйте один или [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) несколько сценариев. Например, попробуйте демонстрационный сценарий **облачной** защиты.         |
|macOS<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)<br/>- 10.13 (Высокая сьерра)     |Скачайте и используйте приложение DIY по [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) ссылке . <br/><br/>Дополнительные сведения см. [в сайте Microsoft Defender для конечной точки на macOS.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Выполнить следующую команду и искать результат **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Откройте окно терминала и запустите следующую команду: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Запустите следующую команду, чтобы перечислить все обнаруженные угрозы: <br/>`mdatp threat list`. <br/><br/>Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки в Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-symantec"></a>Удалить Symantec

Теперь, когда устройства вашей организации были перенастроены в Microsoft Defender для конечной точки, следующим шагом будет удалить Symantec.

1. [Отключение защиты от взлома](https://knowledge.broadcom.com/external/article?legacyId=tech192023) в Symantec.
2. Удалите пароль для Symantec:<br/>
   1. На устройствах Windows откройте редактор реестра в качестве администратора.
   2. Перейдите на сайт `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.
   3. Найди запись с именем **SmcInstData.** 
   4. Щелкните правой кнопкой мыши элемент, а затем выберите **Удалить**. 
3. Удалите Symantec с устройств. Если вам нужна помощь в этом, см. в документации Broadcom. Вот несколько ресурсов Broadcom: 
   - [Uninstall Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Устройства Windows: вручную удалить клиенты [endpoint Protection 14 в Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   - macOS-компьютеры: [удаление программного обеспечения Symantec для Mac с помощью RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Устройства Linux: [часто задающие вопросы для защиты конечных точек для Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме

Теперь, когда у вас есть uninstalled Symantec, следующим шагом будет убедиться, что антивирус Microsoft Defender и Microsoft Defender для конечной точки включены и в активном режиме.

Для этого посетите веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Попробуйте один или несколько демонстрационных сценариев на этой странице, включая по крайней мере следующие:
- Защита с облачным доставкой
- Потенциально нежелательные приложения (PUA)
- Защита сети (NP)

> [!IMPORTANT]
> Если вы используете Windows Server 2016, вам может потребоваться запустить антивирус Microsoft Defender вручную. Это можно сделать с помощью cmdlet PowerShell `mpcmdrun.exe -wdenable` на устройстве.

## <a name="next-steps"></a>Дальнейшие действия

**Поздравляем!** Вы завершили [миграцию из Symantec в Microsoft Defender для конечной точки!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process) 
- [Посетите панель мониторинга операций безопасности](security-operations-dashboard.md) в Центре безопасности Защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) (). 
- [Управление Microsoft Defender для конечной точки, после миграции.](manage-atp-post-migration.md)
