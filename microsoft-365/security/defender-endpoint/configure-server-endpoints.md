---
title: Onboard Windows servers to the Microsoft Defender for Endpoint service
description: На борту серверов Windows, чтобы они могли отправлять данные датчиков в датчик Microsoft Defender для конечной точки.
keywords: сервер, сервер, 2012r2, 2016, 2019, бортовой сервер, управление устройствами, настройка серверов ATP Windows, сервер Microsoft Defender для серверов конечных точек, на борту серверов Microsoft Defender для серверов endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1757160b37500e97586fbb6dfb16d81303bc54e4
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476485"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Onboard Windows servers to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- Windows Server 2008 R2 с пакетом обновления 1 (SP1)
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) версии 1803 и более поздней версии
- Windows Server 2019 и более поздний
- Основной выпуск Windows Server 2019

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


Defender for Endpoint расширяет поддержку и включает операционную систему Windows Server. Эта поддержка обеспечивает расширенные возможности обнаружения и расследования атак с помощью консоли Центра безопасности Защитника Майкрософт.

Практические рекомендации по вопросам лицензирования и инфраструктуры см. в статью Защита [Windows Servers с защитником для конечной точки.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)

Инструкции по загрузке и использованию базовых показателей безопасности Windows для серверов Windows см. в этой [ссылке.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016

Вы можете использовать Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016 в Defender для конечной точки с помощью любого из следующих вариантов:

- **Вариант 1.** Установка и настройка [агента мониторинга Майкрософт (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) на борту
- **Вариант 2.** [На борту через Центр безопасности Azure](#option-2-onboard-windows-servers-through-azure-security-center)
- **Вариант 3.** [На борту через Microsoft Endpoint Manager версии 2002 и более поздней версии](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)


После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.


> [!NOTE]
> Защитник для автономных серверов Конечной точки требуется для каждого узла для того, чтобы на борту сервера Windows через агента мониторинга Майкрософт (вариант 1) или через Microsoft Endpoint Manager (вариант 3). Кроме того, требуется лицензия Azure Defender for Servers для каждого узла для того, чтобы на борту сервера Windows через Центр безопасности Azure (вариант 2) см. поддерживаемые функции, доступные в Центре безопасности [Azure.](https://docs.microsoft.com/azure/security-center/security-center-services)


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>Вариант 1. На борту путем установки и настройки агента мониторинга Майкрософт (MMA)
Для передачи данных датчиков в Defender для конечной точки необходимо установить и настроить MMA для серверов Windows. Дополнительные сведения см. в [журнале Collect data with Azure Log Analytics agent.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)

Если вы уже используете system Center Operations Manager (SCOM) или Azure Monitor (ранее известный как Пакет управления операциями (OMS)), прикрепите агент мониторинга Майкрософт (MMA) для отчета в рабочее пространство Defender для конечной точки с помощью поддержки multihoming.

В общем, необходимо предпринять следующие действия:
1. Выполните требования к вмеяниям, описанным в **разделе Перед началом** работы.
2. Включим мониторинг сервера в центре безопасности Microsoft Defender.
3. Установка и настройка ммА для сервера для передачи данных датчиков в Defender для конечной точки.
4. Настройка и обновление клиентов system Center Endpoint Protection.


> [!TIP]
> После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу. Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)


#### <a name="before-you-begin"></a>Прежде чем начать 
Выполните следующие действия для выполнения требований к вмеяниям:

 - Для Windows Server 2008 R2 SP1 или Windows Server 2012 R2 убедитесь, что вы установите следующий hotfix:
    - [Обновление для работы с клиентами и диагностики телеметрии](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - Кроме того, для Windows Server 2008 R2 SP1 убедитесь, что вы выполните следующие требования:
    - Установка [ежемесячного обновления в феврале](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
    - Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)
   
   > [!NOTE]
    > Если вы управляете Windows Server 2008 R2 sp1 с SCCM, клиентский агент SCCM устанавливает .Net Framework 4.5.2. Поэтому вам не нужно устанавливать фреймворк .NET 4.5 (или более поздний).
   
 - Для Windows Server 2008 R2 SP1 и Windows Server 2012 R2: Настройка и обновление клиентов system [Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)

    > [!NOTE]
    > Этот шаг необходим только в том случае, если ваша организация использует защиту конечных точек System Center (SCEP) и вы Windows Server 2008 R2 SP1 и Windows Server 2012 R2.


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Установка и настройка агента мониторинга Microsoft (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки

1. Скачайте файл установки агента: [агент Windows 64-bit](https://go.microsoft.com/fwlink/?LinkId=828603).

2. Используя ID рабочего пространства и ключ Workspace, полученный в предыдущей процедуре, выберите любой из следующих методов установки для установки агента на сервере Windows:
    - [Установка агента вручную с помощью установки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) <br>
    На странице **Параметры настройки агента** выберите Подключение агента **к Azure Log Analytics (OMS).**
    - [Установите агента с помощью командной строки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [Настройка агента с помощью скрипта](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

> [!NOTE]
> Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>Настройка параметров прокси-сервера Windows и подключения к Интернету при необходимости
Если серверы должны использовать прокси-сервер для связи с Defender для конечной точки, используйте один из следующих методов, чтобы настроить ммА для использования прокси-сервера:


- [Настройка ммА для использования прокси-сервера](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Настройка Windows для использования прокси-сервера для всех подключений](configure-proxy-internet.md)

Если используется прокси-сервер или брандмауэр, убедитесь, что серверы могут получать доступ ко всем URL-адресам службы Microsoft Defender для конечных точек напрямую и без перехвата SSL. Дополнительные сведения см. в том, как включить доступ к URL-адресам [службы Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) Использование перехвата SSL не позволит системе общаться со службой Защитник для конечных точек. 

После завершения работы в течение часа на портале должны быть открыты серверы Windows.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>Вариант 2. На борту серверов Windows через Центр безопасности Azure
1. В области навигации Центра безопасности Microsoft Defender выберите **параметры** управления  >    >  **устройствами.**

2. Выберите **Windows Server 2008 R2 2012 R2 и 2016** в качестве операционной системы.

3. Нажмите **кнопку Onboard Servers в Центре безопасности Azure.**

4. Следуйте инструкциям по взимаемой основе в [Microsoft Defender для конечной точки с Помощью Центра безопасности Azure.](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.

> [!NOTE]
> - Для работы с помощью Azure Defender for Servers (ранее Стандартная версия Центра безопасности Azure) сервер должен иметь соответствующее рабочее пространство и ключ, настроенный в параметрах Агента мониторинга Майкрософт (MMA).
> - После настройки на компьютере развертывается соответствующий пакет управления облаками, а процесс сенсора (MsSenseS.exe) будет развернут и запущен. 
> - Это также необходимо, если сервер настроен на использование сервера шлюза OMS в качестве прокси-сервера.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>Вариант 3. На борту серверов Windows с помощью Microsoft Endpoint Manager версии 2002 и более поздней версии
Вы можете использовать Windows Server 2012 R2 и Windows Server 2016 с помощью microsoft Endpoint Manager версии 2002 и более поздней версии. Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint в текущем](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)филиале Microsoft Endpoint Manager.

После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) версии 1803, Windows Server 2019 и Windows Server 2019 Core edition
На борту Windows Server (SAC) версии 1803, Windows Server 2019 или Windows Server 2019 Core можно использовать следующие методы развертывания:

- [Локальный скрипт](configure-endpoints-script.md) 
- [Групповая политика](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [Скрипты на борту VDI для нестандартных устройств](configure-endpoints-vdi.md)

> [!NOTE]
> - Пакет onboarding для Windows Server 2019 через Microsoft Endpoint Manager в настоящее время разнонаправленный скрипт. Дополнительные сведения о развертывании скриптов в Диспетчер конфигурации см. в тексте Пакеты и [программы в Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)
> - Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства. Для развертывания производства рекомендуется использовать групповую политику или Microsoft Endpoint Configuration Manager.

Поддержка Windows Server обеспечивает более глубокое представление о действиях сервера, охвате обнаружения атак ядра и памяти, а также позволяет реагировать на действия.

1. Настройте параметры onboarding Defender для конечной точки на сервере Windows с помощью тех же инструментов и методов для устройств Windows 10. Дополнительные сведения см. [в таблице Onboard Windows 10 devices.](configure-endpoints.md)

2. Если вы работаете с сторонним решением противомалярийных программ, необходимо применить следующие параметры пассивного режима Microsoft Defender AV. Убедитесь, что она была настроена правильно:

    1. Установите следующую запись реестра:
       - Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - Имя: ForceDefenderPassiveMode
       - Тип: REG_DWORD
       - Value: 1

    1. Запустите следующую команду PowerShell, чтобы убедиться, что пассивный режим настроен:

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. Подтверди, что обнаружено недавнее событие, содержащее событие пассивного режима:

       ![Изображение результата проверки пассивного режима](images/atp-verify-passive-mode.png)

3. Запустите следующую команду, чтобы проверить, установлен ли AV Microsoft Defender:

   ```sc.exe query Windefend```

    Если в результате "указанная служба не существует в качестве установленной службы", вам потребуется установить av Microsoft Defender. Дополнительные сведения см. в [антивирусе Microsoft Defender в Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
    
    Сведения о том, как использовать групповую политику для настройки и управления антивирусом Microsoft Defender на серверах Windows, см. в см. в руб. Параметры групповой политики для настройки и управления антивирусом [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)

<br>

## <a name="integration-with-azure-security-center"></a>Интеграция с Центром безопасности Azure
Defender for Endpoint может интегрироваться с Центром безопасности Azure, чтобы предоставить комплексное решение по защите серверов Windows. С помощью этой интеграции Центр безопасности Azure может использовать силу Defender для конечной точки для улучшения обнаружения угроз для Windows Servers.

В эту интеграцию включены следующие возможности:
- Автоматическая бортовая запись — датчик Defender для конечной точки автоматически включен на серверах Windows, которые находятся на борту в Центр безопасности Azure. Дополнительные сведения о в центре безопасности Azure см. в таблице [Onboarding to Azure Security Center Standard for enhanced security.](https://docs.microsoft.com/azure/security-center/security-center-onboarding)

    > [!NOTE]
    > Интеграция Между Azure Defender для серверов и Microsoft Defender для конечной точки была расширена для поддержки [Windows Server 2019 и Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across customers and servers.  Кроме того, оповещения Defender для конечной точки будут доступны на консоли Azure Security Center.
- Исследование сервера . Клиенты Центра безопасности Azure могут получить доступ к Центру безопасности Защитника Майкрософт, чтобы выполнить подробное исследование, чтобы выявить область потенциального нарушения.

> [!IMPORTANT]
> - При использовании Центра безопасности Azure для мониторинга серверов автоматически создается клиент Defender for Endpoint (в США для пользователей США, в ЕС для европейских и британских пользователей).<br>
Данные, собранные Defender для конечной точки, хранятся в географическом расположении клиента, как определено во время предварительной обработки.
> - Если вы используете Defender для конечной точки перед использованием Центра безопасности Azure, ваши данные будут храниться в указанном вами месте при создания клиента, даже если вы интегрируете его в Центр безопасности Azure в более позднее время.
> - После настройки невозможно изменить расположение, в котором хранятся данные. Если необходимо переместить данные в другое расположение, необходимо обратиться в службу поддержки Майкрософт для сброса клиента. <br>
Мониторинг конечной точки сервера с использованием этой интеграции отключен для клиентов GCC Office 365.

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Настройка и обновление клиентов system Center Endpoint Protection

Защитник для конечной точки интегрируется с системой Center Endpoint Protection. Интеграция обеспечивает видимость обнаружения вредоносных программ и остановку распространения атаки в организации, запрещая потенциально вредоносные файлы или подозрительные вредоносные программы.

Чтобы включить эту интеграцию, необходимы следующие действия:
- Установите обновление платформы защиты от вредоносных программ за январь [2017 г. для клиентов Endpoint Protection.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)

- [Настройка членства службы облачной защиты клиента SCEP в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) **параметре Advanced.**

<br>

## <a name="offboard-windows-servers"></a>Offboard Windows servers
Вы можете отключить Windows Server (SAC), Windows Server 2019 и Windows Server 2019 Core в том же методе, который доступен для клиентских устройств Windows 10.

Для других версий windows server у вас есть два варианта отключения серверов Windows от службы:
- Удалить агент MMA
- Удаление конфигурации рабочего пространства Defender для конечной точки

> [!NOTE]
> Отключение приводит к тому, что сервер Windows перестает отправлять данные датчиков на портал, но данные с сервера Windows, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>Удалить серверы Windows, отстранив агента MMA
Чтобы отключить сервер Windows, можно удалить агента ММА с сервера Windows или отсоедидить его от отчетности в рабочее пространство Defender для конечной точки. После отключения агента сервер Windows больше не будет отправлять данные датчиков в Defender для конечной точки.
Дополнительные сведения см. в [статью Отключение агента.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Удаление конфигурации рабочего пространства Defender для конечной точки
Чтобы отключить сервер Windows, можно использовать любой из следующих методов:

- Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA
- Запустите команду PowerShell, чтобы удалить конфигурацию

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA

1. В поле **Свойства агента мониторинга Майкрософт** выберите **вкладку Azure Log Analytics (OMS).**

2. Выберите рабочее пространство Defender для конечной точки и нажмите кнопку **Удалить**.

    ![Изображение свойств агентов мониторинга Майкрософт](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Запустите команду PowerShell, чтобы удалить конфигурацию

1. Получите свой ID рабочего пространства:

   1. В области навигации выберите **параметры**  >  **onboarding**.

   1. Выберите **Windows Server 2008 R2 SP1, 2012 R2 и 2016** в качестве операционной системы и получите свой ID рабочего пространства:

      ![Изображение бортового сервера Windows](images/atp-server-offboarding-workspaceid.png)

2. Откройте повышенную powerShell и запустите следующую команду. Используйте полученный ИД рабочей области и `WorkspaceID` замените:

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a>Статьи по теме
- [Подключение устройств Windows 10](configure-endpoints.md)
- [Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md)
- [Настройка параметров прокси-сервера и соединения с Интернетом](configure-proxy-internet.md)
- [Запустите тест обнаружения на недавно висячем устройстве Defender для конечных точек](run-detection-test.md)
- [Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки](troubleshoot-onboarding.md)
