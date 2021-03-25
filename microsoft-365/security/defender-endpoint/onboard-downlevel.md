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
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="e5967-104">На борту предыдущих версий Windows</span><span class="sxs-lookup"><span data-stu-id="e5967-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5967-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e5967-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5967-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e5967-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5967-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5967-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e5967-108">**Платформы**</span><span class="sxs-lookup"><span data-stu-id="e5967-108">**Platforms**</span></span>
- <span data-ttu-id="e5967-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5967-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="e5967-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="e5967-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="e5967-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="e5967-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="e5967-112">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="e5967-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="e5967-113">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e5967-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="e5967-114">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="e5967-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="e5967-115">Defender for Endpoint расширяет поддержку, включив в нее операционные системы на более высоком уровне, предоставляя расширенные возможности обнаружения атак и расследования в поддерживаемых версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="e5967-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="e5967-116">Чтобы на борту конечных точек клиента Windows на уровне "Защитник для конечной точки", необходимо:</span><span class="sxs-lookup"><span data-stu-id="e5967-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="e5967-117">Настройка и обновление клиентов system Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="e5967-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="e5967-118">Установите и настройте агент мониторинга Майкрософт (MMA), чтобы сообщить данные датчика в Defender для конечной точки, как поручено ниже.</span><span class="sxs-lookup"><span data-stu-id="e5967-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="e5967-119">После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу.</span><span class="sxs-lookup"><span data-stu-id="e5967-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="e5967-120">Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="e5967-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="e5967-121">Настройка и обновление клиентов system Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="e5967-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e5967-122">Этот шаг необходим только в том случае, если ваша организация использует защиту конечных точек System Center (SCEP).</span><span class="sxs-lookup"><span data-stu-id="e5967-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="e5967-123">Defender for Endpoint интегрируется с системой Center Endpoint Protection, чтобы обеспечить видимость обнаружения вредоносных программ и остановить распространение атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="e5967-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="e5967-124">Чтобы включить эту интеграцию, необходимы следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5967-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="e5967-125">Установка обновления платформы защиты от вредоносных программ за январь [2017 г. для клиентов endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="e5967-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="e5967-126">Настройка членства клиентской службы облачной защиты SCEP в **расширенный** параметр</span><span class="sxs-lookup"><span data-stu-id="e5967-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="e5967-127">Настройте сеть, чтобы разрешить подключение к облаку антивирусов Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e5967-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="e5967-128">Дополнительные сведения см. в дополнительных сведениях о том, как разрешить [подключение к облаку антивирусных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud) программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e5967-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e5967-129">Установка и настройка агента мониторинга Microsoft (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e5967-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="e5967-130">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="e5967-130">Before you begin</span></span>
<span data-ttu-id="e5967-131">Просмотрите следующие сведения, чтобы проверить минимальные требования к системе:</span><span class="sxs-lookup"><span data-stu-id="e5967-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="e5967-132">Установка [ежемесячного обновления в феврале 2018 г.](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="e5967-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="e5967-133">Применимо только для Windows 7 SP1 Enterprise и Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="e5967-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="e5967-134">Установка обновления [для работы с клиентами и диагностики телеметрии](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="e5967-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="e5967-135">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="e5967-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5967-136">Применимо только для Windows 7 SP1 Enterprise и Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="e5967-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="e5967-137">Не устанавливайте платформа .NET Framework 4.0.x, так как это отменит вышеуказанную установку.</span><span class="sxs-lookup"><span data-stu-id="e5967-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="e5967-138">Соответствовать минимальным системным требованиям агента Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="e5967-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="e5967-139">Дополнительные сведения см. в [журнале Collect data from computers in you environment with Log Analytics.](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="e5967-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="e5967-140">Скачайте файл настройки агента: [агент Windows 64-bit или](https://go.microsoft.com/fwlink/?LinkId=828603) агент Windows [32-bit](https://go.microsoft.com/fwlink/?LinkId=828604).</span><span class="sxs-lookup"><span data-stu-id="e5967-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="e5967-141">Получение ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="e5967-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="e5967-142">В области навигации Defender для конечной точки выберите параметры > **управления устройствами > onboarding**</span><span class="sxs-lookup"><span data-stu-id="e5967-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="e5967-143">Выберите **Windows 7 SP1 и 8.1** в качестве операционной системы</span><span class="sxs-lookup"><span data-stu-id="e5967-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="e5967-144">Копирование ID рабочего пространства и ключа рабочего пространства</span><span class="sxs-lookup"><span data-stu-id="e5967-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="e5967-145">С помощью ID рабочего пространства и клавиши Workspace выберите любой из следующих методов установки для установки агента:</span><span class="sxs-lookup"><span data-stu-id="e5967-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="e5967-146">[Установка агента вручную с помощью установки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="e5967-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="e5967-147">На странице **Параметры настройки агента** выберите Подключение агента **к Azure Log Analytics (OMS)**</span><span class="sxs-lookup"><span data-stu-id="e5967-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="e5967-148">[Установите агента с помощью командной строки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="e5967-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="e5967-149">[Настройка агента с помощью скрипта](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="e5967-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5967-150">Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.</span><span class="sxs-lookup"><span data-stu-id="e5967-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="e5967-151">Если вы используете прокси для подключения к Интернету, см. раздел Настройка параметров прокси.</span><span class="sxs-lookup"><span data-stu-id="e5967-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="e5967-152">После завершения работы в течение часа на портале должны быть понастройки конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e5967-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="e5967-153">Настройка параметров прокси и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="e5967-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="e5967-154">Каждая конечная точка Windows должна иметь возможность подключения к Интернету с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e5967-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="e5967-155">Это подключение может быть прямым, с помощью прокси или через [шлюз OMS.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="e5967-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="e5967-156">Если прокси-сервер или брандмауэр блокируют весь трафик по умолчанию и позволяют просматривать только определенные домены или проверку HTTPS (проверка SSL), убедитесь, что вы включаете доступ к URL-адресам службы [Defender для](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e5967-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="e5967-157">Конечные точки клиента offboard</span><span class="sxs-lookup"><span data-stu-id="e5967-157">Offboard client endpoints</span></span>
<span data-ttu-id="e5967-158">Для отключения можно удалить агента ММА из конечной точки или отсоединить его от отчетности в рабочее пространство Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5967-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="e5967-159">После отключения агента конечная точка больше не будет отправлять данные датчика в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5967-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="e5967-160">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e5967-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="e5967-161">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)</span><span class="sxs-lookup"><span data-stu-id="e5967-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

