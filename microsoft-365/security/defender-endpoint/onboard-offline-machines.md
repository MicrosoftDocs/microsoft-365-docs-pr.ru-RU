---
title: На борту устройств без доступа к Интернету в Microsoft Defender для конечной точки
ms.reviewer: ''
description: Бортовые устройства без доступа в Интернет, чтобы они могли отправлять данные датчиков в датчик Microsoft Defender для конечной точки
keywords: onboard, servers, vm, on-premise, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: ee06f927579445825a2b2813e483c24357d2ed78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934925"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>На борту устройств без доступа к Интернету в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Для бортовых устройств без доступа к Интернету необходимо предпринять следующие общие действия:

> [!IMPORTANT] 
> Ниже приведены действия, применимые только к устройствам, работающим в предыдущих версиях Windows, например: Windows Server 2016 и более ранних Windows 8.1 и ранее.

> [!NOTE]
> - Сервер шлюза OMS не может использоваться в качестве прокси-сервера для отключенных устройств Windows 10 или Windows Server 2019 при настройке через реестр "TelemetryProxyServer" или GPO.
> - Для Windows 10 или Windows Server 2019 , хотя вы можете использовать TelemetryProxyServer, он должен указать на стандартное прокси-устройство или устройство.
> - Кроме того, Windows 10 или Windows Server 2019 в отключенных средах должна иметь возможность обновлять списки доверия сертификатов в автономном режиме с помощью внутреннего файла или веб-сервера.
> - Дополнительные сведения об обновлении CTLs в автономном режиме см. в странице Настройка файла или веб-сервера для загрузки [CTL-файлов.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

Дополнительные сведения о методах бортового управления см. в следующих статьях:
- [Подключение предыдущих версий Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Бортовые серверы службы Microsoft Defender для конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Настройка параметров прокси-сервера устройства и подключения к Интернету](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Локальное устройство

- Настройка Azure Log Analytics (ранее известный как ШЛЮЗ OMS) для действий в качестве прокси-сервера или концентратора:
  - [Агент аналитики журналов Azure](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Установка и настройка агента мониторинга Майкрософт (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) указывают на ключ Defender для рабочей области конечной точки & ID

- Автономные устройства в одной сети Azure Log Analytics
  -  Настройте ММА, чтобы указать на:
     - IP-адрес Azure Log Analytics в качестве прокси-сервера
     - Ключ защитника для рабочей области конечной точки & ID

## <a name="azure-virtual-machines"></a>Виртуальные машины Azure
- Настройка и включить [рабочее пространство Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Настройка шлюза аналитики журналов Azure (ранее известного как ШЛЮЗ OMS) для действий в качестве прокси-сервера или концентратора:
      - [Шлюз аналитики журналов Azure](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Установка и настройка агента мониторинга Майкрософт (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) указывают на ключ Defender для рабочей области конечной точки & ID
    - Автономные VMs Azure в одной сети шлюза OMS
      - Настройка IP-адреса Azure Log Analytics в качестве прокси-сервера
      - Ключ рабочего пространства azure Log Analytics & ID

    - Azure Defender
      - [Рабочее пространство \> журнала журналов политики безопасности](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Обнаружение угроз \> позволяет защитнику конечной точки получать доступ к моим данным](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Дополнительные сведения см. [в ссылке Работа с политиками безопасности.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)
