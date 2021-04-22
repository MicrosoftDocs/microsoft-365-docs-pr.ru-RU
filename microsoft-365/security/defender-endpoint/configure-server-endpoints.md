---
title: Onboard Windows servers to the Microsoft Defender for Endpoint service
description: На борту серверов Windows, чтобы они могли отправлять данные датчиков в датчик Microsoft Defender для конечной точки.
keywords: бортовой сервер, сервер, 2012r2, 2016, 2019, бортовой сервер, управление устройствами, настройка Microsoft Defender для серверов конечных точек, на борту серверов Microsoft Defender для конечных точек, на борту серверов Microsoft Defender для серверов endpoint
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
ms.openlocfilehash: 4eea2931196c192620812c1609c506e1fb99093d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932957"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="b338a-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="b338a-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b338a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b338a-105">**Applies to:**</span></span>

- <span data-ttu-id="b338a-106">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b338a-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="b338a-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b338a-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="b338a-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b338a-108">Windows Server 2016</span></span>
- <span data-ttu-id="b338a-109">Windows Server (SAC) версии 1803 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="b338a-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="b338a-110">Windows Server 2019 и более поздний</span><span class="sxs-lookup"><span data-stu-id="b338a-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="b338a-111">Основной выпуск Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b338a-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="b338a-112">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b338a-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b338a-113">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b338a-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="b338a-114">Defender for Endpoint расширяет поддержку и включает операционную систему Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b338a-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="b338a-115">Эта поддержка обеспечивает расширенные возможности обнаружения и расследования атак с помощью консоли Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b338a-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="b338a-116">Практические рекомендации по вопросам лицензирования и инфраструктуры см. в статью Защита [Windows Servers с защитником для конечной точки.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="b338a-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="b338a-117">Инструкции по загрузке и использованию базовых показателей безопасности Windows для серверов Windows см. в этой [ссылке.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="b338a-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="b338a-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b338a-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="b338a-119">Вы можете использовать Windows Server 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016 в Defender для конечной точки с помощью любого из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b338a-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="b338a-120">**Вариант 1.** Установка и настройка [агента мониторинга Майкрософт (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) на борту</span><span class="sxs-lookup"><span data-stu-id="b338a-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="b338a-121">**Вариант 2.** [На борту через Центр безопасности Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="b338a-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="b338a-122">**Вариант 3.** [На борту через Microsoft Endpoint Manager версии 2002 и более поздней версии](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="b338a-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="b338a-123">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="b338a-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="b338a-124">Защитник для автономных серверов Конечной точки требуется для каждого узла для того, чтобы на борту сервера Windows через агента мониторинга Майкрософт (вариант 1) или через Microsoft Endpoint Manager (вариант 3).</span><span class="sxs-lookup"><span data-stu-id="b338a-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="b338a-125">Кроме того, требуется лицензия Azure Defender for Servers для каждого узла для того, чтобы на борту сервера Windows через Центр безопасности Azure (вариант 2) см. поддерживаемые функции, доступные в [Azure Defender.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="b338a-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="b338a-126">Вариант 1. На борту путем установки и настройки агента мониторинга Майкрософт (MMA)</span><span class="sxs-lookup"><span data-stu-id="b338a-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="b338a-127">Для передачи данных датчиков в Defender для конечной точки необходимо установить и настроить MMA для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="b338a-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="b338a-128">Дополнительные сведения см. в [журнале Collect data with Azure Log Analytics agent.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="b338a-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="b338a-129">Если вы уже используете system Center Operations Manager (SCOM) или Azure Monitor (ранее известный как Пакет управления операциями (OMS)), прикрепите агент мониторинга Майкрософт (MMA) для отчета в рабочее пространство Defender для конечной точки с помощью поддержки multihoming.</span><span class="sxs-lookup"><span data-stu-id="b338a-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="b338a-130">В общем, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b338a-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="b338a-131">Выполните требования к вмеяниям, описанным в **разделе Перед началом** работы.</span><span class="sxs-lookup"><span data-stu-id="b338a-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="b338a-132">Включим мониторинг сервера в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b338a-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="b338a-133">Установка и настройка ммА для сервера для передачи данных датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b338a-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="b338a-134">Настройка и обновление клиентов system Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="b338a-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="b338a-135">После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу.</span><span class="sxs-lookup"><span data-stu-id="b338a-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="b338a-136">Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="b338a-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="b338a-137">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="b338a-137">Before you begin</span></span>

<span data-ttu-id="b338a-138">Выполните следующие действия для выполнения требований к вмеяниям:</span><span class="sxs-lookup"><span data-stu-id="b338a-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="b338a-139">Для Windows Server 2008 R2 SP1 или Windows Server 2012 R2 убедитесь, что вы установите следующий hotfix:</span><span class="sxs-lookup"><span data-stu-id="b338a-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="b338a-140">Обновление для работы с клиентами и диагностики телеметрии</span><span class="sxs-lookup"><span data-stu-id="b338a-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="b338a-141">Для Windows Server 2008 R2 SP1 убедитесь, что вы выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="b338a-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="b338a-142">Установка [ежемесячного обновления в феврале](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="b338a-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="b338a-143">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="b338a-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="b338a-144">Если вы управляете Windows Server 2008 R2 sp1 с SCCM, клиентский агент SCCM устанавливает .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="b338a-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="b338a-145">Поэтому вам не нужно устанавливать фреймворк .NET 4.5 (или более поздний).</span><span class="sxs-lookup"><span data-stu-id="b338a-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="b338a-146">Для Windows Server 2008 R2 SP1 и Windows Server 2012 R2: Настройка и обновление клиентов system [Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="b338a-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="b338a-147">Этот шаг необходим только в том случае, если ваша организация использует защиту конечных точек System Center (SCEP) и вы Windows Server 2008 R2 SP1 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b338a-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="b338a-148">Установка и настройка агента мониторинга Microsoft (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b338a-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="b338a-149">Скачайте файл установки агента: [агент Windows 64-bit](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="b338a-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="b338a-150">Используя ID рабочего пространства и ключ Workspace, полученный в предыдущей процедуре, выберите любой из следующих методов установки для установки агента на сервере Windows:</span><span class="sxs-lookup"><span data-stu-id="b338a-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="b338a-151">[Установка агента вручную с помощью установки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="b338a-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="b338a-152">На странице **Параметры настройки агента** выберите Подключение агента **к Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="b338a-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="b338a-153">[Установите агента с помощью командной строки.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="b338a-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="b338a-154">[Настройка агента с помощью скрипта](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="b338a-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="b338a-155">Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.</span><span class="sxs-lookup"><span data-stu-id="b338a-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="b338a-156">Настройка параметров прокси-сервера Windows и подключения к Интернету при необходимости</span><span class="sxs-lookup"><span data-stu-id="b338a-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="b338a-157">Если серверы должны использовать прокси-сервер для связи с Defender для конечной точки, используйте один из следующих методов, чтобы настроить ммА для использования прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="b338a-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="b338a-158">Настройка ммА для использования прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b338a-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="b338a-159">Настройка Windows для использования прокси-сервера для всех подключений</span><span class="sxs-lookup"><span data-stu-id="b338a-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="b338a-160">Если используется прокси-сервер или брандмауэр, убедитесь, что серверы могут получать доступ ко всем URL-адресам службы Microsoft Defender для конечных точек напрямую и без перехвата SSL.</span><span class="sxs-lookup"><span data-stu-id="b338a-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="b338a-161">Дополнительные сведения см. в том, как включить доступ к URL-адресам [службы Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="b338a-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="b338a-162">Использование перехвата SSL не позволит системе общаться со службой Защитник для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b338a-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="b338a-163">После завершения работы в течение часа на портале должны быть открыты серверы Windows.</span><span class="sxs-lookup"><span data-stu-id="b338a-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="b338a-164">Вариант 2. На борту серверов Windows через Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="b338a-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="b338a-165">В области навигации Центра безопасности Microsoft Defender выберите **параметры** управления  >    >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="b338a-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="b338a-166">Выберите **Windows Server 2008 R2 2012 R2 и 2016** в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b338a-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="b338a-167">Нажмите **кнопку Onboard Servers в Центре безопасности Azure.**</span><span class="sxs-lookup"><span data-stu-id="b338a-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="b338a-168">Следуйте инструкциям по интеграции в [Microsoft Defender для](https://docs.microsoft.com/azure/security-center/security-center-wdatp) конечной точки с помощью Azure Defender и Если вы используете Azure ARC, выполните инструкции по включению интеграции Microsoft Defender для конечной [точки.](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)</span><span class="sxs-lookup"><span data-stu-id="b338a-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="b338a-169">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="b338a-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b338a-170">Для работы с помощью Azure Defender для серверов серверы должны иметь соответствующее рабочее пространство и ключ, настроенный в параметрах Агент мониторинга Майкрософт (MMA).</span><span class="sxs-lookup"><span data-stu-id="b338a-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="b338a-171">После настройки на компьютере развертывается соответствующий пакет управления облаками, а процесс сенсора (MsSenseS.exe) будет развернут и запущен.</span><span class="sxs-lookup"><span data-stu-id="b338a-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="b338a-172">Это также необходимо, если сервер настроен на использование сервера шлюза OMS в качестве прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b338a-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="b338a-173">Вариант 3. На борту серверов Windows с помощью Microsoft Endpoint Manager версии 2002 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="b338a-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="b338a-174">Вы можете использовать Windows Server 2012 R2 и Windows Server 2016 с помощью microsoft Endpoint Manager версии 2002 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b338a-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="b338a-175">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint в текущем](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)филиале Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b338a-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="b338a-176">После выполнения действий по настройке и обновлению клиенты [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)необходимо настроить и обновить.</span><span class="sxs-lookup"><span data-stu-id="b338a-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="b338a-177">Windows Server (SAC) версии 1803, Windows Server 2019 и Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="b338a-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="b338a-178">На борту Windows Server (SAC) версии 1803, Windows Server 2019 или Windows Server 2019 Core можно использовать следующие методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="b338a-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="b338a-179">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="b338a-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="b338a-180">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="b338a-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="b338a-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b338a-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="b338a-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="b338a-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="b338a-183">Скрипты на борту VDI для нестандартных устройств</span><span class="sxs-lookup"><span data-stu-id="b338a-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="b338a-184">Пакет onboarding для Windows Server 2019 через Microsoft Endpoint Manager в настоящее время разнонаправленный скрипт.</span><span class="sxs-lookup"><span data-stu-id="b338a-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="b338a-185">Дополнительные сведения о развертывании скриптов в Диспетчер конфигурации см. в тексте Пакеты и [программы в Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="b338a-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="b338a-186">Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства.</span><span class="sxs-lookup"><span data-stu-id="b338a-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="b338a-187">Для развертывания производства рекомендуется использовать групповую политику или Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b338a-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="b338a-188">Поддержка Windows Server обеспечивает более глубокое представление о действиях сервера, охвате обнаружения атак ядра и памяти, а также позволяет реагировать на действия.</span><span class="sxs-lookup"><span data-stu-id="b338a-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="b338a-189">Настройте параметры onboarding Defender для конечной точки на сервере Windows с помощью тех же инструментов и методов для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b338a-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="b338a-190">Дополнительные сведения см. [в таблице Onboard Windows 10 devices.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="b338a-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="b338a-191">Если вы работаете с сторонним решением по борьбе с вредоносными программами, вам потребуется применить следующие параметры пассивного режима AV Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b338a-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="b338a-192">Убедитесь, что она была настроена правильно:</span><span class="sxs-lookup"><span data-stu-id="b338a-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="b338a-193">Установите следующую запись реестра:</span><span class="sxs-lookup"><span data-stu-id="b338a-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="b338a-194">Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="b338a-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="b338a-195">Имя: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="b338a-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="b338a-196">Тип: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="b338a-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="b338a-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="b338a-197">Value: 1</span></span>

    1. <span data-ttu-id="b338a-198">Запустите следующую команду PowerShell, чтобы убедиться, что пассивный режим настроен:</span><span class="sxs-lookup"><span data-stu-id="b338a-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="b338a-199">Подтверди, что обнаружено недавнее событие, содержащее событие пассивного режима:</span><span class="sxs-lookup"><span data-stu-id="b338a-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Изображение результата проверки пассивного режима](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="b338a-201">Запустите следующую команду, чтобы проверить, установлен ли AV Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="b338a-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="b338a-202">Если в результате "указанная служба не существует в качестве установленной службы", вам потребуется установить av Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b338a-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="b338a-203">Дополнительные сведения см. в [антивирусе Microsoft Defender в Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="b338a-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="b338a-204">Сведения о том, как использовать групповую политику для настройки и управления антивирусом Microsoft Defender на серверах Windows, см. в см. в руб. Параметры групповой политики для настройки и управления антивирусом [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b338a-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="b338a-205">Интеграция с Защитником Azure</span><span class="sxs-lookup"><span data-stu-id="b338a-205">Integration with Azure Defender</span></span>

<span data-ttu-id="b338a-206">Defender for Endpoint может интегрироваться с Azure Defender, чтобы предоставить комплексное решение по защите серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="b338a-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="b338a-207">С помощью этой интеграции Azure Defender может использовать силу Defender для конечной точки, чтобы обеспечить улучшенное обнаружение угроз для Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="b338a-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="b338a-208">В эту интеграцию включены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="b338a-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="b338a-209">Автоматическая бортовая запись — датчик Defender для конечной точки автоматически включен на Серверах Windows, которые включены в Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="b338a-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="b338a-210">Дополнительные сведения о onboarding Azure Defender см. в таблице [Onboarding to Azure Defender Standard for enhanced security.](https://docs.microsoft.com/azure/security-center/security-center-onboarding)</span><span class="sxs-lookup"><span data-stu-id="b338a-210">For more information on Azure Defender onboarding, see [Onboarding to Azure Defender Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b338a-211">Интеграция Между Azure Defender для серверов и Microsoft Defender для конечной точки была расширена для поддержки [Windows Server 2019 и Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="b338a-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="b338a-212">Серверы Windows, под наблюдением Azure Defender, также будут доступны в Защитнике для конечной точки . Azure Defender без проблем подключается к клиенту Defender для конечных точек, обеспечивая единое представление между клиентами и серверами.</span><span class="sxs-lookup"><span data-stu-id="b338a-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="b338a-213">Кроме того, оповещения Defender для конечной точки будут доступны в консоли Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="b338a-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="b338a-214">Исследование сервера . Клиенты Azure Defender могут получить доступ к Центру безопасности Защитника Майкрософт, чтобы выполнить подробное исследование, чтобы выявить область потенциального нарушения.</span><span class="sxs-lookup"><span data-stu-id="b338a-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="b338a-215">При использовании Azure Defender для мониторинга серверов автоматически создается клиент Defender для конечных точек (в США для пользователей США, в ЕС для европейских и британских пользователей).</span><span class="sxs-lookup"><span data-stu-id="b338a-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="b338a-216">Данные, собранные Defender для конечной точки, хранятся в географическом расположении клиента, как определено во время предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="b338a-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="b338a-217">Если вы используете Defender для конечной точки перед использованием Azure Defender, ваши данные будут храниться в указанном вами расположении при создания клиента, даже если вы интегрируете с Azure Defender позднее.</span><span class="sxs-lookup"><span data-stu-id="b338a-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="b338a-218">После настройки невозможно изменить расположение, в котором хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="b338a-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="b338a-219">Если необходимо переместить данные в другое расположение, необходимо обратиться в службу поддержки Майкрософт для сброса клиента.</span><span class="sxs-lookup"><span data-stu-id="b338a-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="b338a-220">Мониторинг конечной точки сервера с использованием этой интеграции отключен для клиентов GCC Office 365.</span><span class="sxs-lookup"><span data-stu-id="b338a-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="b338a-221">Настройка и обновление клиентов system Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="b338a-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="b338a-222">Защитник для конечной точки интегрируется с системой Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="b338a-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="b338a-223">Интеграция обеспечивает видимость обнаружения вредоносных программ и остановку распространения атаки в организации, запрещая потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="b338a-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="b338a-224">Чтобы включить эту интеграцию, необходимы следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b338a-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="b338a-225">Установите обновление платформы защиты от вредоносных программ за январь [2017 г. для клиентов Endpoint Protection.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="b338a-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="b338a-226">[Настройка членства службы облачной защиты клиента SCEP в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) **параметре Advanced.**</span><span class="sxs-lookup"><span data-stu-id="b338a-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="b338a-227">Offboard Windows servers</span><span class="sxs-lookup"><span data-stu-id="b338a-227">Offboard Windows servers</span></span>

<span data-ttu-id="b338a-228">Вы можете отключить Windows Server (SAC), Windows Server 2019 и Windows Server 2019 Core в том же методе, который доступен для клиентских устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b338a-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="b338a-229">Для других версий windows server у вас есть два варианта отключения серверов Windows от службы:</span><span class="sxs-lookup"><span data-stu-id="b338a-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="b338a-230">Удалить агент MMA</span><span class="sxs-lookup"><span data-stu-id="b338a-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="b338a-231">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b338a-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="b338a-232">Отключение приводит к тому, что сервер Windows перестает отправлять данные датчиков на портал, но данные с сервера Windows, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="b338a-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="b338a-233">Удалить серверы Windows, отстранив агента MMA</span><span class="sxs-lookup"><span data-stu-id="b338a-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="b338a-234">Чтобы отключить сервер Windows, можно удалить агента ММА с сервера Windows или отсоедидить его от отчетности в рабочее пространство Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b338a-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="b338a-235">После отключения агента сервер Windows больше не будет отправлять данные датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b338a-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="b338a-236">Дополнительные сведения см. в [статью Отключение агента.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="b338a-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="b338a-237">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b338a-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="b338a-238">Чтобы отключить сервер Windows, можно использовать любой из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="b338a-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="b338a-239">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="b338a-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="b338a-240">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="b338a-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="b338a-241">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="b338a-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="b338a-242">В поле **Свойства агента мониторинга Майкрософт** выберите **вкладку Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="b338a-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="b338a-243">Выберите рабочее пространство Defender для конечной точки и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b338a-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Изображение свойств агентов мониторинга Майкрософт](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="b338a-245">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="b338a-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="b338a-246">Получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="b338a-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="b338a-247">В области навигации выберите **параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="b338a-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="b338a-248">Выберите **Windows Server 2008 R2 SP1, 2012 R2 и 2016** в качестве операционной системы и получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="b338a-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Изображение бортового сервера Windows](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="b338a-250&quot;>Откройте повышенную powerShell и запустите следующую команду.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b338a-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;b338a-251&quot;>Используйте полученный ИД рабочей области и `WorkspaceID` замените:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b338a-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="b338a-252">Onboarding Servers без решения управления</span><span class="sxs-lookup"><span data-stu-id="b338a-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="b338a-253">Использование групповой политики</span><span class="sxs-lookup"><span data-stu-id="b338a-253">Using Group Policy</span></span>

<span data-ttu-id="b338a-254">**Шаг-1. Создайте необходимые файлы для копирования на серверы.**</span><span class="sxs-lookup"><span data-stu-id="b338a-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="b338a-255">Перейдите к c:\windows\sysvol\domain\scripts (управление изменением может быть необходимо на одном из контроллеров домена.)</span><span class="sxs-lookup"><span data-stu-id="b338a-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="b338a-256">Создайте папку с именем MMA.</span><span class="sxs-lookup"><span data-stu-id="b338a-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="b338a-257">Скачайте следующее и поместите в папку ММА:</span><span class="sxs-lookup"><span data-stu-id="b338a-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="b338a-258">**Обновление для работы с клиентами и диагностической телеметрии (Windows Server 2008 R2 и Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="b338a-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="b338a-259">Для Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="b338a-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="b338a-260">Для Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="b338a-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="b338a-261">В этой статье предполагается, что вы используете серверы на основе x64 (MMA Agent .exe x64 [New SHA-2 compliant version)](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="b338a-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="b338a-262">**Шаг-2. Создание имени файла DeployMMA.cmd (с помощью блокнота)** Добавьте в файл cmd следующие строки.</span><span class="sxs-lookup"><span data-stu-id="b338a-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="b338a-263">Обратите внимание, что вам потребуется ваш WORKSPACE ID и KEY.</span><span class="sxs-lookup"><span data-stu-id="b338a-263">Note that you will need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="b338a-264">Конфигурация групповой политики</span><span class="sxs-lookup"><span data-stu-id="b338a-264">Group Policy Configuration</span></span>

<span data-ttu-id="b338a-265">Создайте новую групповую политику специально для бортовых устройств, таких как "Microsoft Defender for Endpoint Onboarding".</span><span class="sxs-lookup"><span data-stu-id="b338a-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="b338a-266">Создание папки групповой политики с именем "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="b338a-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="папки":::

    <span data-ttu-id="b338a-268">**Это добавит новую папку на каждом сервере, на который применяется GPO под названием MMA, и будет храниться в c:\windows. Это будет содержать файлы установки для ммА, необходимые условия и установить скрипт.**</span><span class="sxs-lookup"><span data-stu-id="b338a-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="b338a-269">Создайте предпочтение групповым файлам политик для каждого из файлов, хранимого в логотипе Net.</span><span class="sxs-lookup"><span data-stu-id="b338a-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="изображение групповой политики1":::

<span data-ttu-id="b338a-271">Он копирует файлы из DOMAIN\NETLOGON\MMA\filename в C:\windows\MMA\filename , поэтому файлы установки локализованы **на сервере:**</span><span class="sxs-lookup"><span data-stu-id="b338a-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="развертывание мма cmd":::

<span data-ttu-id="b338a-273">Для двух ЦБ (один для Windows Server 2008R2/Windows 7 и другой для Windows Server 2012 R2) повторите процесс, но создайте таргетинг уровня элементов на вкладке COMMON, поэтому файл будет скопирован только в соответствующую версию платформы и операционной системы в области:</span><span class="sxs-lookup"><span data-stu-id="b338a-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="целевой редактор":::

- <span data-ttu-id="b338a-275">Для Windows Server 2008 R2 необходимо (и он будет только скопировать вниз) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="b338a-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="b338a-276">Для Windows Server 2012 R2 требуется (и он будет только скопировать) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="b338a-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="b338a-277">После этого необходимо создать политику скриптов для запуска:</span><span class="sxs-lookup"><span data-stu-id="b338a-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="свойства запуска":::

<span data-ttu-id="b338a-279">Имя файла для запуска здесь c:\windows\MMA\DeployMMA.cmd После перезапуска сервера в процессе запуска он установит обновление для работы с клиентами и диагностическую телеметрию КБ, а затем установит MMAAgent, задав код рабочего пространства и ключ, и сервер будет на борту.</span><span class="sxs-lookup"><span data-stu-id="b338a-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMAAgent, while setting the workspace id and key, and the server will be onboarded.</span></span>

<span data-ttu-id="b338a-280">Вы также можете  использовать немедленную задачу для запуска deployMMA.cmd, если вы не хотите перезагрузки всех серверов.</span><span class="sxs-lookup"><span data-stu-id="b338a-280">You could also use an **immediate task** to run the deployMMA.cmd if you do not want to reboot all the servers.</span></span>
<span data-ttu-id="b338a-281">Это можно сделать в два этапа.</span><span class="sxs-lookup"><span data-stu-id="b338a-281">This could be done in two phases.</span></span> <span data-ttu-id="b338a-282">Сначала **создайте файлы** и папку в GPO — дайте системе время для обеспечения того, чтобы GPO была применена, и все серверы имеют файлы установки.</span><span class="sxs-lookup"><span data-stu-id="b338a-282">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="b338a-283">Затем добавьте немедленную задачу.</span><span class="sxs-lookup"><span data-stu-id="b338a-283">Then, add the immediate task.</span></span> <span data-ttu-id="b338a-284">Это приведет к такому же результату, не требуя перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="b338a-284">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="b338a-285">Так как сценарий имеет метод выхода и не будет повторно запускаться, если ммА установлен, вы также можете использовать ежедневную запланированную задачу для достижения того же результата.</span><span class="sxs-lookup"><span data-stu-id="b338a-285">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="b338a-286">Как и политика соответствия требованиям диспетчера конфигурации, она будет ежедневно проверять, чтобы убедиться, что ммА присутствует.</span><span class="sxs-lookup"><span data-stu-id="b338a-286">Similar to an Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="задача расписания":::

:::image type="content" source="images/newtaskprops.png" alt-text="новые свойства задач":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="развертывание реквизитов для скачивания мма":::

:::image type="content" source="images/tasksch.png" alt-text="планировщик задач":::

<span data-ttu-id="b338a-291">Как упоминалось в документации по onboarding для Server, конкретно вокруг Сервера 2008 R2, см. ниже:</span><span class="sxs-lookup"><span data-stu-id="b338a-291">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="b338a-292">Для Windows Server 2008 R2 PS1 убедитесь, что вы выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="b338a-292">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="b338a-293">Установка [ежемесячного обновления в феврале 2018 г.](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="b338a-293">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="b338a-294">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="b338a-294">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="b338a-295">Проверьте, присутствуют ли ЦБ перед Windows Server 2008 R2 этот процесс позволяет использовать все серверы, если у вас нет диспетчера конфигурации, управляющего серверами.</span><span class="sxs-lookup"><span data-stu-id="b338a-295">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b338a-296">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="b338a-296">Related topics</span></span>

- [<span data-ttu-id="b338a-297">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="b338a-297">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="b338a-298">Подключение устройствах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="b338a-298">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="b338a-299">Настройка параметров прокси-сервера и соединения с Интернетом</span><span class="sxs-lookup"><span data-stu-id="b338a-299">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="b338a-300">Запустите тест обнаружения на недавно висячем устройстве Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="b338a-300">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="b338a-301">Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b338a-301">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
