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
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861351"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="10312-104">На борту устройств без доступа к Интернету в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="10312-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="10312-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="10312-105">**Applies to:**</span></span>
- [<span data-ttu-id="10312-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="10312-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10312-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10312-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="10312-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="10312-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="10312-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="10312-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="10312-110">Для бортовых устройств без доступа к Интернету необходимо предпринять следующие общие действия:</span><span class="sxs-lookup"><span data-stu-id="10312-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="10312-111">Ниже приведены действия, применимые только к устройствам, работающим в предыдущих версиях Windows, например: Windows Server 2016 и более ранних Windows 8.1 и ранее.</span><span class="sxs-lookup"><span data-stu-id="10312-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="10312-112">Сервер шлюза OMS не может использоваться в качестве прокси-сервера для отключенных устройств Windows 10 или Windows Server 2019 при настройке через реестр "TelemetryProxyServer" или GPO.</span><span class="sxs-lookup"><span data-stu-id="10312-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="10312-113">Для Windows 10 или Windows Server 2019 , хотя вы можете использовать TelemetryProxyServer, он должен указать на стандартное прокси-устройство или устройство.</span><span class="sxs-lookup"><span data-stu-id="10312-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="10312-114">Кроме того, Windows 10 или Windows Server 2019 в отключенных средах должна иметь возможность обновлять списки доверия сертификатов в автономном режиме с помощью внутреннего файла или веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="10312-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="10312-115">Дополнительные сведения об обновлении CTLs в автономном режиме см. в странице Настройка файла или веб-сервера для загрузки [CTL-файлов.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)</span><span class="sxs-lookup"><span data-stu-id="10312-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="10312-116">Дополнительные сведения о методах бортового управления см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="10312-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="10312-117">Подключение предыдущих версий Windows</span><span class="sxs-lookup"><span data-stu-id="10312-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="10312-118">Бортовые серверы службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="10312-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="10312-119">Настройка параметров прокси-сервера устройства и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="10312-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="10312-120">Локальное устройство</span><span class="sxs-lookup"><span data-stu-id="10312-120">On-premise devices</span></span>

- <span data-ttu-id="10312-121">Настройка Azure Log Analytics (ранее известный как ШЛЮЗ OMS) для действий в качестве прокси-сервера или концентратора:</span><span class="sxs-lookup"><span data-stu-id="10312-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="10312-122">Агент аналитики журналов Azure</span><span class="sxs-lookup"><span data-stu-id="10312-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="10312-123">[Установка и настройка агента мониторинга Майкрософт (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) указывают на ключ Defender для рабочей области конечной точки & ID</span><span class="sxs-lookup"><span data-stu-id="10312-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="10312-124">Автономные устройства в одной сети Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="10312-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="10312-125">Настройте ММА, чтобы указать на:</span><span class="sxs-lookup"><span data-stu-id="10312-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="10312-126">IP-адрес Azure Log Analytics в качестве прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="10312-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="10312-127">Ключ защитника для рабочей области конечной точки & ID</span><span class="sxs-lookup"><span data-stu-id="10312-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="10312-128">Виртуальные машины Azure</span><span class="sxs-lookup"><span data-stu-id="10312-128">Azure virtual machines</span></span>
- <span data-ttu-id="10312-129">Настройка и включить [рабочее пространство Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="10312-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="10312-130">Настройка шлюза аналитики журналов Azure (ранее известного как ШЛЮЗ OMS) для действий в качестве прокси-сервера или концентратора:</span><span class="sxs-lookup"><span data-stu-id="10312-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="10312-131">Шлюз аналитики журналов Azure</span><span class="sxs-lookup"><span data-stu-id="10312-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="10312-132">[Установка и настройка агента мониторинга Майкрософт (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) указывают на ключ Defender для рабочей области конечной точки & ID</span><span class="sxs-lookup"><span data-stu-id="10312-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="10312-133">Автономные VMs Azure в одной сети шлюза OMS</span><span class="sxs-lookup"><span data-stu-id="10312-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="10312-134">Настройка IP-адреса Azure Log Analytics в качестве прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="10312-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="10312-135">Ключ рабочего пространства azure Log Analytics & ID</span><span class="sxs-lookup"><span data-stu-id="10312-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="10312-136">Центр безопасности Azure (ASC)</span><span class="sxs-lookup"><span data-stu-id="10312-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="10312-137">Рабочее пространство \> журнала журналов политики безопасности</span><span class="sxs-lookup"><span data-stu-id="10312-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="10312-138">Обнаружение угроз \> позволяет защитнику конечной точки получать доступ к моим данным</span><span class="sxs-lookup"><span data-stu-id="10312-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="10312-139">Дополнительные сведения см. [в ссылке Работа с политиками безопасности.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="10312-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
