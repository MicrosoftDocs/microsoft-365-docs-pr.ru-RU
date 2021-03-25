---
title: Onboard previous versions of Windows on Microsoft Defender ATP
description: На борту поддерживали предыдущие версии устройств Windows, чтобы они могли отправлять данные датчиков в датчик ATP Защитника Майкрософт
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186393"
---
# <a name="onboard-previous-versions-of-windows"></a>На борту предыдущих версий Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Платформы**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Корпоративная


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint расширяет поддержку, включив в нее операционные системы на более высоком уровне, предоставляя расширенные возможности обнаружения атак и расследования в поддерживаемых версиях Windows.

Чтобы на борту конечных точек клиента Windows на уровне "Защитник для конечной точки", необходимо:
- Настройка и обновление клиентов system Center Endpoint Protection.
- Установите и настройте агент мониторинга Майкрософт (MMA), чтобы сообщить данные датчика в Defender для конечной точки, как поручено ниже.

> [!TIP]
> После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу. Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Настройка и обновление клиентов system Center Endpoint Protection
> [!IMPORTANT]
> Этот шаг необходим только в том случае, если ваша организация использует защиту конечных точек System Center (SCEP).

Defender for Endpoint интегрируется с системой Center Endpoint Protection, чтобы обеспечить видимость обнаружения вредоносных программ и остановить распространение атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы. 

Чтобы включить эту интеграцию, необходимы следующие действия: 
- Установка обновления платформы защиты от вредоносных программ за январь [2017 г. для клиентов endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Настройка членства клиентской службы облачной защиты SCEP в **расширенный** параметр
- Настройте сеть, чтобы разрешить подключение к облаку антивирусов Microsoft Defender. Дополнительные сведения см. в дополнительных сведениях о том, как разрешить [подключение к облаку антивирусных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud) программ Microsoft Defender

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Установка и настройка агента мониторинга Microsoft (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки

### <a name="before-you-begin"></a>Прежде чем начать
Просмотрите следующие сведения, чтобы проверить минимальные требования к системе:
- Установка [ежемесячного обновления в феврале 2018 г.](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Применимо только для Windows 7 SP1 Enterprise и Windows 7 SP1 Pro. 

- Установка обновления [для работы с клиентами и диагностики телеметрии](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Применимо только для Windows 7 SP1 Enterprise и Windows 7 SP1 Pro.
    > Не устанавливайте платформа .NET Framework 4.0.x, так как это отменит вышеуказанную установку.

- Соответствовать минимальным системным требованиям агента Azure Log Analytics. Дополнительные сведения см. в [журнале Collect data from computers in you environment with Log Analytics.](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Скачайте файл настройки агента: [агент Windows 64-bit или](https://go.microsoft.com/fwlink/?LinkId=828603) агент Windows [32-bit](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Получение ID рабочего пространства:
   - В области навигации Defender для конечной точки выберите параметры > **управления устройствами > onboarding**
   - Выберите **Windows 7 SP1 и 8.1** в качестве операционной системы
   - Копирование ID рабочего пространства и ключа рабочего пространства

3. С помощью ID рабочего пространства и клавиши Workspace выберите любой из следующих методов установки для установки агента:
    - [Установка агента вручную с помощью установки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) <br>
      На странице **Параметры настройки агента** выберите Подключение агента **к Azure Log Analytics (OMS)**
    - [Установите агента с помощью командной строки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [Настройка агента с помощью скрипта](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.

4. Если вы используете прокси для подключения к Интернету, см. раздел Настройка параметров прокси.

После завершения работы в течение часа на портале должны быть понастройки конечных точек.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Настройка параметров прокси и подключения к Интернету
 
- Каждая конечная точка Windows должна иметь возможность подключения к Интернету с помощью HTTPS. Это подключение может быть прямым, с помощью прокси или через [шлюз OMS.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)
- Если прокси-сервер или брандмауэр блокируют весь трафик по умолчанию и позволяют просматривать только определенные домены или проверку HTTPS (проверка SSL), убедитесь, что вы включаете доступ к URL-адресам службы [Defender для](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)конечных точек.

## <a name="offboard-client-endpoints"></a>Конечные точки клиента offboard
Для отключения можно удалить агента ММА из конечной точки или отсоединить его от отчетности в рабочее пространство Defender для конечной точки. После отключения агента конечная точка больше не будет отправлять данные датчика в Defender для конечной точки. 

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)

