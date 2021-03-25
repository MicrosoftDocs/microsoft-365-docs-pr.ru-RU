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
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069741"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="e41a0-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="e41a0-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e41a0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e41a0-105">**Applies to:**</span></span>

- <span data-ttu-id="e41a0-106">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="e41a0-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="e41a0-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e41a0-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="e41a0-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e41a0-108">Windows Server 2016</span></span>
- <span data-ttu-id="e41a0-109">Windows Server (SAC) версии 1803 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e41a0-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="e41a0-110">Windows Server 2019 и более поздний</span><span class="sxs-lookup"><span data-stu-id="e41a0-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="e41a0-111">Основной выпуск Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e41a0-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="e41a0-112">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e41a0-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e41a0-113">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e41a0-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="e41a0-114">Defender for Endpoint расширяет поддержку и включает операционную систему Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e41a0-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="e41a0-115">Эта поддержка обеспечивает расширенные возможности обнаружения и расследования атак с помощью консоли Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e41a0-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="e41a0-116">Практические рекомендации по вопросам лицензирования и инфраструктуры см. в статью Защита [Windows Servers с защитником для конечной точки.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="e41a0-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="e41a0-117">Инструкции по загрузке и использованию базовых показателей безопасности Windows для серверов Windows см. в этой [ссылке.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="e41a0-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="e41a0-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e41a0-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="e41a0-119">Вы можете использовать Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016 в Defender для конечной точки с помощью любого из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e41a0-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="e41a0-120">**Вариант 1.** Установка и настройка [агента мониторинга Майкрософт (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) на борту</span><span class="sxs-lookup"><span data-stu-id="e41a0-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="e41a0-121">**Вариант 2.** [На борту через Центр безопасности Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="e41a0-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="e41a0-122">**Вариант 3.** [На борту через Microsoft Endpoint Manager версии 2002 и более поздней версии](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="e41a0-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="e41a0-123">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="e41a0-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="e41a0-124">Защитник для автономных серверов Конечной точки требуется для каждого узла для того, чтобы на борту сервера Windows через агента мониторинга Майкрософт (вариант 1) или через Microsoft Endpoint Manager (вариант 3).</span><span class="sxs-lookup"><span data-stu-id="e41a0-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="e41a0-125">Кроме того, требуется лицензия Azure Defender for Servers для каждого узла для того, чтобы на борту сервера Windows через Центр безопасности Azure (вариант 2) см. поддерживаемые функции, доступные в Центре безопасности [Azure.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="e41a0-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="e41a0-126">Вариант 1. На борту путем установки и настройки агента мониторинга Майкрософт (MMA)</span><span class="sxs-lookup"><span data-stu-id="e41a0-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="e41a0-127">Для передачи данных датчиков в Defender для конечной точки необходимо установить и настроить MMA для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="e41a0-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="e41a0-128">Дополнительные сведения см. в [журнале Collect data with Azure Log Analytics agent.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="e41a0-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="e41a0-129">Если вы уже используете system Center Operations Manager (SCOM) или Azure Monitor (ранее известный как Пакет управления операциями (OMS)), прикрепите агент мониторинга Майкрософт (MMA) для отчета в рабочее пространство Defender для конечной точки с помощью поддержки multihoming.</span><span class="sxs-lookup"><span data-stu-id="e41a0-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="e41a0-130">В общем, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e41a0-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="e41a0-131">Выполните требования к вмеяниям, описанным в **разделе Перед началом** работы.</span><span class="sxs-lookup"><span data-stu-id="e41a0-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="e41a0-132">Включим мониторинг сервера в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e41a0-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="e41a0-133">Установка и настройка ммА для сервера для передачи данных датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e41a0-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="e41a0-134">Настройка и обновление клиентов system Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="e41a0-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="e41a0-135">После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу.</span><span class="sxs-lookup"><span data-stu-id="e41a0-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="e41a0-136">Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="e41a0-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="e41a0-137">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e41a0-137">Before you begin</span></span> 
<span data-ttu-id="e41a0-138">Выполните следующие действия для выполнения требований к вмеяниям:</span><span class="sxs-lookup"><span data-stu-id="e41a0-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="e41a0-139">Для Windows Server 2008 R2 SP1 или Windows Server 2012 R2 убедитесь, что вы установите следующий hotfix:</span><span class="sxs-lookup"><span data-stu-id="e41a0-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="e41a0-140">Обновление для работы с клиентами и диагностики телеметрии</span><span class="sxs-lookup"><span data-stu-id="e41a0-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="e41a0-141">Кроме того, для Windows Server 2008 R2 SP1 убедитесь, что вы выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="e41a0-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="e41a0-142">Установка [ежемесячного обновления в феврале](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="e41a0-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="e41a0-143">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="e41a0-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

 - <span data-ttu-id="e41a0-144">Для Windows Server 2008 R2 SP1 и Windows Server 2012 R2: Настройка и обновление клиентов system [Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="e41a0-144">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e41a0-145">Этот шаг необходим только в том случае, если ваша организация использует защиту конечных точек System Center (SCEP) и вы Windows Server 2008 R2 SP1 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="e41a0-145">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e41a0-146">Установка и настройка агента мониторинга Microsoft (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e41a0-146">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="e41a0-147">Скачайте файл установки агента: [агент Windows 64-bit](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="e41a0-147">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="e41a0-148">Используя ID рабочего пространства и ключ Workspace, полученный в предыдущей процедуре, выберите любой из следующих методов установки для установки агента на сервере Windows:</span><span class="sxs-lookup"><span data-stu-id="e41a0-148">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="e41a0-149">[Установка агента вручную с помощью установки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="e41a0-149">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="e41a0-150">На странице **Параметры настройки агента** выберите Подключение агента **к Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="e41a0-150">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="e41a0-151">[Установите агента с помощью командной строки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="e41a0-151">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="e41a0-152">[Настройка агента с помощью скрипта](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="e41a0-152">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="e41a0-153">Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.</span><span class="sxs-lookup"><span data-stu-id="e41a0-153">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="e41a0-154">Настройка параметров прокси-сервера Windows и подключения к Интернету при необходимости</span><span class="sxs-lookup"><span data-stu-id="e41a0-154">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="e41a0-155">Если серверы должны использовать прокси-сервер для связи с Defender для конечной точки, используйте один из следующих методов, чтобы настроить ммА для использования прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="e41a0-155">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="e41a0-156">Настройка ммА для использования прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="e41a0-156">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="e41a0-157">Настройка Windows для использования прокси-сервера для всех подключений</span><span class="sxs-lookup"><span data-stu-id="e41a0-157">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="e41a0-158">Если используется прокси-сервер или брандмауэр, убедитесь, что серверы могут получать доступ ко всем URL-адресам службы Microsoft Defender для конечных точек напрямую и без перехвата SSL.</span><span class="sxs-lookup"><span data-stu-id="e41a0-158">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="e41a0-159">Дополнительные сведения см. в том, как включить доступ к URL-адресам [службы Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="e41a0-159">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="e41a0-160">Использование перехвата SSL не позволит системе общаться со службой Защитник для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e41a0-160">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="e41a0-161">После завершения работы в течение часа на портале должны быть открыты серверы Windows.</span><span class="sxs-lookup"><span data-stu-id="e41a0-161">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="e41a0-162">Вариант 2. На борту серверов Windows через Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="e41a0-162">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="e41a0-163">В области навигации Центра безопасности Microsoft Defender выберите **параметры** управления  >    >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="e41a0-163">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="e41a0-164">Выберите **Windows Server 2008 R2 2012 R2 и 2016** в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e41a0-164">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="e41a0-165">Нажмите **кнопку Onboard Servers в Центре безопасности Azure.**</span><span class="sxs-lookup"><span data-stu-id="e41a0-165">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="e41a0-166">Следуйте инструкциям по взимаемой основе в [Microsoft Defender для конечной точки с Помощью Центра безопасности Azure.](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="e41a0-166">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="e41a0-167">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="e41a0-167">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="e41a0-168">Для работы с помощью Azure Defender for Servers (ранее Стандартная версия Центра безопасности Azure) сервер должен иметь соответствующее рабочее пространство и ключ, настроенный в параметрах Агента мониторинга Майкрософт (MMA).</span><span class="sxs-lookup"><span data-stu-id="e41a0-168">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="e41a0-169">После настройки на компьютере развертывается соответствующий пакет управления облаками, а процесс сенсора (MsSenseS.exe) будет развернут и запущен.</span><span class="sxs-lookup"><span data-stu-id="e41a0-169">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="e41a0-170">Это также необходимо, если сервер настроен на использование сервера шлюза OMS в качестве прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e41a0-170">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="e41a0-171">Вариант 3. На борту серверов Windows с помощью Microsoft Endpoint Manager версии 2002 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e41a0-171">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="e41a0-172">Вы можете использовать Windows Server 2012 R2 и Windows Server 2016 с помощью microsoft Endpoint Manager версии 2002 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e41a0-172">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="e41a0-173">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint в текущем](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)филиале Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e41a0-173">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="e41a0-174">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="e41a0-174">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="e41a0-175">Windows Server (SAC) версии 1803, Windows Server 2019 и Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="e41a0-175">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="e41a0-176">На борту Windows Server (SAC) версии 1803, Windows Server 2019 или Windows Server 2019 Core можно использовать следующие методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="e41a0-176">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="e41a0-177">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="e41a0-177">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="e41a0-178">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="e41a0-178">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="e41a0-179">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e41a0-179">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="e41a0-180">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="e41a0-180">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="e41a0-181">Скрипты на борту VDI для нестандартных устройств</span><span class="sxs-lookup"><span data-stu-id="e41a0-181">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="e41a0-182">Пакет onboarding для Windows Server 2019 через Microsoft Endpoint Manager в настоящее время разнонаправленный скрипт.</span><span class="sxs-lookup"><span data-stu-id="e41a0-182">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="e41a0-183">Дополнительные сведения о развертывании скриптов в Диспетчер конфигурации см. в тексте Пакеты и [программы в Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="e41a0-183">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="e41a0-184">Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства.</span><span class="sxs-lookup"><span data-stu-id="e41a0-184">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="e41a0-185">Для развертывания производства рекомендуется использовать групповую политику или Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e41a0-185">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="e41a0-186">Поддержка Windows Server обеспечивает более глубокое представление о действиях сервера, охвате обнаружения атак ядра и памяти, а также позволяет реагировать на действия.</span><span class="sxs-lookup"><span data-stu-id="e41a0-186">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="e41a0-187">Настройте параметры onboarding Defender для конечной точки на сервере Windows с помощью тех же инструментов и методов для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e41a0-187">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="e41a0-188">Дополнительные сведения см. [в таблице Onboard Windows 10 devices.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="e41a0-188">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="e41a0-189">Если вы работаете с сторонним решением противомалярийных программ, необходимо применить следующие параметры пассивного режима Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="e41a0-189">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="e41a0-190">Убедитесь, что она была настроена правильно:</span><span class="sxs-lookup"><span data-stu-id="e41a0-190">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="e41a0-191">Установите следующую запись реестра:</span><span class="sxs-lookup"><span data-stu-id="e41a0-191">Set the following registry entry:</span></span>
       - <span data-ttu-id="e41a0-192">Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="e41a0-192">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="e41a0-193">Имя: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="e41a0-193">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="e41a0-194">Тип: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e41a0-194">Type: REG_DWORD</span></span>
       - <span data-ttu-id="e41a0-195">Value: 1</span><span class="sxs-lookup"><span data-stu-id="e41a0-195">Value: 1</span></span>

    1. <span data-ttu-id="e41a0-196">Запустите следующую команду PowerShell, чтобы убедиться, что пассивный режим настроен:</span><span class="sxs-lookup"><span data-stu-id="e41a0-196">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="e41a0-197">Подтверди, что обнаружено недавнее событие, содержащее событие пассивного режима:</span><span class="sxs-lookup"><span data-stu-id="e41a0-197">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Изображение результата проверки пассивного режима](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="e41a0-199">Запустите следующую команду, чтобы проверить, установлен ли AV Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="e41a0-199">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="e41a0-200">Если в результате "указанная служба не существует в качестве установленной службы", вам потребуется установить av Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e41a0-200">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="e41a0-201">Дополнительные сведения см. в [антивирусе Microsoft Defender в Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="e41a0-201">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="e41a0-202">Сведения о том, как использовать групповую политику для настройки и управления антивирусом Microsoft Defender на серверах Windows, см. в см. в руб. Параметры групповой политики для настройки и управления антивирусом [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="e41a0-202">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="e41a0-203">Интеграция с Центром безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="e41a0-203">Integration with Azure Security Center</span></span>
<span data-ttu-id="e41a0-204">Defender for Endpoint может интегрироваться с Центром безопасности Azure, чтобы предоставить комплексное решение по защите серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="e41a0-204">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="e41a0-205">С помощью этой интеграции Центр безопасности Azure может использовать силу Defender для конечной точки для улучшения обнаружения угроз для Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="e41a0-205">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="e41a0-206">В эту интеграцию включены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="e41a0-206">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="e41a0-207">Автоматическая бортовая запись — датчик Defender для конечной точки автоматически включен на серверах Windows, которые находятся на борту в Центр безопасности Azure.</span><span class="sxs-lookup"><span data-stu-id="e41a0-207">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="e41a0-208">Дополнительные сведения о в центре безопасности Azure см. в таблице [Onboarding to Azure Security Center Standard for enhanced security.](https://docs.microsoft.com/azure/security-center/security-center-onboarding)</span><span class="sxs-lookup"><span data-stu-id="e41a0-208">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e41a0-209">Автоматическая бортовая система применяется только для Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="e41a0-209">Automated onboarding is only applicable for Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016.</span></span>

- <span data-ttu-id="e41a0-210">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across customers and servers.</span><span class="sxs-lookup"><span data-stu-id="e41a0-210">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="e41a0-211">Кроме того, оповещения Defender для конечной точки будут доступны на консоли Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="e41a0-211">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="e41a0-212">Исследование сервера . Клиенты Центра безопасности Azure могут получить доступ к Центру безопасности Защитника Майкрософт, чтобы выполнить подробное исследование, чтобы выявить область потенциального нарушения.</span><span class="sxs-lookup"><span data-stu-id="e41a0-212">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="e41a0-213">При использовании Центра безопасности Azure для мониторинга серверов автоматически создается клиент Defender for Endpoint (в США для пользователей США, в ЕС для европейских и британских пользователей).</span><span class="sxs-lookup"><span data-stu-id="e41a0-213">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="e41a0-214">Данные, собранные Defender для конечной точки, хранятся в географическом расположении клиента, как определено во время предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="e41a0-214">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="e41a0-215">Если вы используете Defender для конечной точки перед использованием Центра безопасности Azure, ваши данные будут храниться в указанном вами месте при создания клиента, даже если вы интегрируете его в Центр безопасности Azure в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="e41a0-215">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="e41a0-216">После настройки невозможно изменить расположение, в котором хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="e41a0-216">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="e41a0-217">Если необходимо переместить данные в другое расположение, необходимо обратиться в службу поддержки Майкрософт для сброса клиента.</span><span class="sxs-lookup"><span data-stu-id="e41a0-217">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="e41a0-218">Мониторинг конечной точки сервера с использованием этой интеграции отключен для клиентов GCC Office 365.</span><span class="sxs-lookup"><span data-stu-id="e41a0-218">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="e41a0-219">Настройка и обновление клиентов system Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="e41a0-219">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="e41a0-220">Защитник для конечной точки интегрируется с системой Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="e41a0-220">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="e41a0-221">Интеграция обеспечивает видимость обнаружения вредоносных программ и остановку распространения атаки в организации, запрещая потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="e41a0-221">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="e41a0-222">Чтобы включить эту интеграцию, необходимы следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e41a0-222">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="e41a0-223">Установите обновление платформы защиты от вредоносных программ за январь [2017 г. для клиентов Endpoint Protection.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="e41a0-223">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="e41a0-224">[Настройка членства службы облачной защиты клиента SCEP в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) **параметре Advanced.**</span><span class="sxs-lookup"><span data-stu-id="e41a0-224">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="e41a0-225">Offboard Windows servers</span><span class="sxs-lookup"><span data-stu-id="e41a0-225">Offboard Windows servers</span></span>
<span data-ttu-id="e41a0-226">Вы можете отключить Windows Server (SAC), Windows Server 2019 и Windows Server 2019 Core в том же методе, который доступен для клиентских устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e41a0-226">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="e41a0-227">Для других версий windows server у вас есть два варианта отключения серверов Windows от службы:</span><span class="sxs-lookup"><span data-stu-id="e41a0-227">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="e41a0-228">Удалить агент MMA</span><span class="sxs-lookup"><span data-stu-id="e41a0-228">Uninstall the MMA agent</span></span>
- <span data-ttu-id="e41a0-229">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e41a0-229">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="e41a0-230">Отключение приводит к тому, что сервер Windows перестает отправлять данные датчиков на портал, но данные с сервера Windows, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="e41a0-230">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="e41a0-231">Удалить серверы Windows, отстранив агента MMA</span><span class="sxs-lookup"><span data-stu-id="e41a0-231">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="e41a0-232">Чтобы отключить сервер Windows, можно удалить агента ММА с сервера Windows или отсоедидить его от отчетности в рабочее пространство Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e41a0-232">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="e41a0-233">После отключения агента сервер Windows больше не будет отправлять данные датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e41a0-233">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="e41a0-234">Дополнительные сведения см. в [статью Отключение агента.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="e41a0-234">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="e41a0-235">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e41a0-235">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="e41a0-236">Чтобы отключить сервер Windows, можно использовать любой из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="e41a0-236">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="e41a0-237">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="e41a0-237">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="e41a0-238">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="e41a0-238">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="e41a0-239">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="e41a0-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="e41a0-240">В поле **Свойства агента мониторинга Майкрософт** выберите **вкладку Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="e41a0-240">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="e41a0-241">Выберите рабочее пространство Defender для конечной точки и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e41a0-241">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Изображение свойств агентов мониторинга Майкрософт](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="e41a0-243">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="e41a0-243">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="e41a0-244">Получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="e41a0-244">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="e41a0-245">В области навигации выберите **параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="e41a0-245">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="e41a0-246">Выберите **Windows Server 2008 R2 SP1, 2012 R2 и 2016** в качестве операционной системы и получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="e41a0-246">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Изображение бортового сервера Windows](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="e41a0-248">Откройте повышенную powerShell и запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e41a0-248">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="e41a0-249">Используйте полученный ИД рабочей области и `WorkspaceID` замените:</span><span class="sxs-lookup"><span data-stu-id="e41a0-249">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="e41a0-250">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e41a0-250">Related topics</span></span>
- [<span data-ttu-id="e41a0-251">На борту устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="e41a0-251">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="e41a0-252">Onboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="e41a0-252">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="e41a0-253">Настройка параметров прокси и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="e41a0-253">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="e41a0-254">Запустите тест обнаружения на недавно висячем устройстве Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="e41a0-254">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="e41a0-255">Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e41a0-255">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)