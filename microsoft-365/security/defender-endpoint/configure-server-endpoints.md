---
title: На Windows серверов службы Microsoft Defender для конечных точек
description: На Windows серверов, чтобы они могли отправлять данные датчиков в датчик Microsoft Defender для конечной точки.
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
ms.openlocfilehash: 47d57e51eca4950f7a8f4284fbc916e9d030b2c7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844338"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="9ca4c-104">На Windows серверов службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="9ca4c-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ca4c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-105">**Applies to:**</span></span>

- <span data-ttu-id="9ca4c-106">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="9ca4c-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9ca4c-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="9ca4c-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9ca4c-108">Windows Server 2016</span></span>
- <span data-ttu-id="9ca4c-109">Windows Версия 1803 Server (SAC) и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="9ca4c-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="9ca4c-110">Windows Server 2019 и более поздний</span><span class="sxs-lookup"><span data-stu-id="9ca4c-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="9ca4c-111">Windows Основное издание Server 2019</span><span class="sxs-lookup"><span data-stu-id="9ca4c-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="9ca4c-112">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9ca4c-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9ca4c-113">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="9ca4c-114">Defender for Endpoint расширяет поддержку и включает операционную Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="9ca4c-115">Эта поддержка обеспечивает расширенные возможности обнаружения и расследования атак с помощью консоли Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="9ca4c-116">Практические рекомендации по вопросам лицензирования и инфраструктуры см. в Windows [Servers with Defender for Endpoint.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="9ca4c-117">Руководство по загрузке и использованию Безопасность Windows базовых данных для Windows серверов см. в Безопасность Windows [Baselines.](/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="9ca4c-118">Windows Сервер 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9ca4c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="9ca4c-119">Вы можете использовать Windows 2008 R2 SP1, Windows Server 2012 R2 и Windows Server 2016 Defender для конечной точки с помощью любого из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="9ca4c-120">**Вариант 1.** На борту путем установки и настройки Microsoft Monitoring Agent [(MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="9ca4c-121">**Вариант 2.** [На борту через Центр безопасности Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="9ca4c-122">**Вариант 3.** [На борту Microsoft Endpoint Manager версии 2002 и более поздней версии](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="9ca4c-123">После выполнения действий по вмеяниям с помощью любого из предоставленных параметров необходимо настроить и обновить System Center Endpoint Protection [клиентов.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="9ca4c-124">Для каждого узла требуется лицензия defender для автономных серверов endpoint для Windows сервера через Microsoft Monitoring Agent (вариант 1) или Microsoft Endpoint Manager (вариант 3).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="9ca4c-125">Кроме того, требуется лицензия Azure Defender for Servers для каждого узла для того, чтобы на борту сервера Windows через Центр безопасности Azure (вариант 2), см. поддерживаемые функции, доступные в [Azure Defender.](/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="9ca4c-126">Вариант 1. На борту путем установки и настройки Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="9ca4c-127">Вам потребуется установить и настроить MMA для Windows серверов для передачи данных датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="9ca4c-128">Дополнительные сведения см. в [журнале Collect data with Azure Log Analytics agent.](/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-128">For more information, see [Collect log data with Azure Log Analytics agent](/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="9ca4c-129">Если вы уже используете System Center диспетчера операций (SCOM) или Azure Monitor (ранее известный как Пакет управления операциями (OMS)), прикрепите Microsoft Monitoring Agent (MMA) для отчета в рабочее пространство Defender for Endpoint с помощью поддержки multihoming.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="9ca4c-130">В общем, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="9ca4c-131">Выполните требования к вмеяниям, описанным в **разделе Перед началом** работы.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="9ca4c-132">Включим мониторинг сервера в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="9ca4c-133">Установка и настройка ммА для сервера для передачи данных датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="9ca4c-134">Настройка и обновление System Center Endpoint Protection клиентов.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="9ca4c-135">После работы с устройством можно выполнить тест обнаружения, чтобы убедиться, что оно правильно вложено в службу.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="9ca4c-136">Дополнительные сведения см. в сайте [Run a detection test on a newly onboarded Defender for Endpoint endpoint.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="9ca4c-137">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="9ca4c-137">Before you begin</span></span>

<span data-ttu-id="9ca4c-138">Выполните следующие действия для выполнения требований к вмеяниям:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="9ca4c-139">Для Windows Server 2008 R2 SP1 или Windows Server 2012 R2 убедитесь, что вы установите следующий hotfix:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="9ca4c-140">Обновление для работы с клиентами и диагностики телеметрии</span><span class="sxs-lookup"><span data-stu-id="9ca4c-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="9ca4c-141">Для Windows Server 2008 R2 SP1 убедитесь, что вы выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="9ca4c-142">Установка [ежемесячного обновления в феврале](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="9ca4c-143">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ca4c-144">Если вы управляете сервером Windows 2008 R2 SP1 с SCCM, клиентский агент SCCM устанавливает .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="9ca4c-145">Поэтому вам не нужно устанавливать фреймворк .NET 4.5 (или более поздний).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="9ca4c-146">Для Windows 2008 R2 SP1 и Windows Server 2012 R2: Настройка и обновление System Center Endpoint Protection [клиентов](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="9ca4c-147">Этот шаг необходим только в том случае, если ваша организация использует System Center Endpoint Protection (SCEP) и вы Windows Сервер 2008 R2 SP1 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="9ca4c-148">Установка и настройка Microsoft Monitoring Agent (MMA) для передачи данных датчиков в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9ca4c-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="9ca4c-149">Скачайте файл установки агента: [Windows 64-битного агента](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="9ca4c-150">Используя ключ Workspace ID и workspace, полученный в предыдущей процедуре, выберите любой из следующих методов установки для установки агента на Windows сервере:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="9ca4c-151">[Установка агента вручную с помощью установки.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-151">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="9ca4c-152">На странице **Параметры настройки** агентов **выберите Подключение агента в Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="9ca4c-153">[Установите агента с помощью командной строки.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-153">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="9ca4c-154">[Настройка агента с помощью скрипта](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-154">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="9ca4c-155">Если вы клиент правительства [США,](gov.md)в статье "Azure Cloud" необходимо выбрать параметр "Azure US Government", если используется мастер установки, или если используется командная строка или сценарий, задан параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="9ca4c-156">Настройка параметров прокси Windows сервера и подключения к Интернету при необходимости</span><span class="sxs-lookup"><span data-stu-id="9ca4c-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="9ca4c-157">Если серверы должны использовать прокси-сервер для связи с Defender для конечной точки, используйте один из следующих методов, чтобы настроить ммА для использования прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="9ca4c-158">Настройка ммА для использования прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="9ca4c-158">Configure the MMA to use a proxy server</span></span>](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="9ca4c-159">Настройка Windows для использования прокси-сервера для всех подключений</span><span class="sxs-lookup"><span data-stu-id="9ca4c-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="9ca4c-160">Если используется прокси-сервер или брандмауэр, убедитесь, что серверы могут получать доступ ко всем URL-адресам службы Microsoft Defender для конечных точек напрямую и без перехвата SSL.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="9ca4c-161">Дополнительные сведения см. в том, как включить доступ к URL-адресам [службы Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="9ca4c-162">Использование перехвата SSL не позволит системе общаться со службой Защитник для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="9ca4c-163">После завершения работы в течение часа Windows серверы на портале.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="9ca4c-164">Вариант 2. Серверы Windows через Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="9ca4c-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="9ca4c-165">В области Центр безопасности в Microsoft Defender навигации выберите **Параметры**  >  **управления**  >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="9ca4c-166">Выберите **Windows 2008 R2 SP1, 2012 R2 и 2016** в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="9ca4c-167">Нажмите **кнопку Onboard Servers в Центре безопасности Azure.**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="9ca4c-168">Следуйте инструкциям по интеграции в [Microsoft Defender для](/azure/security-center/security-center-wdatp) конечной точки с помощью Azure Defender и Если вы используете Azure ARC, выполните инструкции по включению интеграции Microsoft Defender для конечной [точки.](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="9ca4c-169">После выполнения действий по вмеяниям необходимо настроить и обновить System Center Endpoint Protection [клиентов.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9ca4c-170">Чтобы работать с помощью Azure Defender для серверов, сервер должен иметь соответствующее рабочее пространство и ключ, настроенный в Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="9ca4c-171">После настройки на компьютере развертывается соответствующий пакет управления облаками, а процесс сенсора (MsSenseS.exe) будет развернут и запущен.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="9ca4c-172">Это также необходимо, если сервер настроен на использование сервера шлюза OMS в качестве прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="9ca4c-173">Вариант 3. Windows серверы через Microsoft Endpoint Manager версии 2002 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="9ca4c-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="9ca4c-174">Вы можете использовать Windows Server 2012 R2 и Windows Server 2016 с помощью Microsoft Endpoint Manager версии 2002 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="9ca4c-175">Дополнительные сведения см. [в веб-сайте Microsoft Defender for Endpoint в Microsoft Endpoint Manager текущей ветви.](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="9ca4c-176">После выполнения действий по вмеяниям необходимо настроить и обновить System Center Endpoint Protection [клиентов.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="9ca4c-177">Windows Версия 1803 server (SAC), Windows Server 2019 и Windows Server 2019 Core</span><span class="sxs-lookup"><span data-stu-id="9ca4c-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="9ca4c-178">Вы можете использовать Windows Server (SAC) версии 1803, Windows Server 2019 или Windows Server 2019 Core с помощью следующих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="9ca4c-179">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="9ca4c-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="9ca4c-180">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="9ca4c-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="9ca4c-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9ca4c-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="9ca4c-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="9ca4c-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="9ca4c-183">Скрипты на борту VDI для нестандартных устройств</span><span class="sxs-lookup"><span data-stu-id="9ca4c-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="9ca4c-184">Пакет onboarding для Windows Server 2019 через Microsoft Endpoint Manager в настоящее время отсыт скрипт.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="9ca4c-185">Дополнительные сведения о развертывании скриптов в Диспетчер конфигурации см. в тексте Пакеты и [программы в Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="9ca4c-186">Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="9ca4c-187">Для развертывания производства рекомендуется использовать групповую политику или Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="9ca4c-188">Поддержка Windows Server обеспечивает более глубокое представление о действиях сервера, освещении обнаружения атак ядра и памяти, а также позволяет реагировать на действия.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="9ca4c-189">Настройте параметры onboarding Defender для конечной точки на Windows с помощью тех же средств и методов для Windows 10 устройств.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="9ca4c-190">Дополнительные сведения см. в [Windows 10 устройствах.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="9ca4c-191">Если вы работаете с сторонним решением по борьбе с вредоносными программами, вам потребуется применить следующие параметры пассивного режима AV Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="9ca4c-192">Убедитесь, что она была настроена правильно:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="9ca4c-193">Установите следующую запись реестра:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="9ca4c-194">Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="9ca4c-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="9ca4c-195">Имя: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="9ca4c-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="9ca4c-196">Тип: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9ca4c-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="9ca4c-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="9ca4c-197">Value: 1</span></span>

    1. <span data-ttu-id="9ca4c-198">Запустите следующую команду PowerShell, чтобы убедиться, что пассивный режим настроен:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="9ca4c-199">Подтверди, что обнаружено недавнее событие, содержащее событие пассивного режима:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Изображение результата проверки пассивного режима](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="9ca4c-201">Запустите следующую команду, чтобы проверить, установлен ли AV Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="9ca4c-202">Если в результате "указанная служба не существует в качестве установленной службы", вам потребуется установить av Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="9ca4c-203">Дополнительные сведения см. [в антивирусная программа в Microsoft Defender в Windows 10.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-203">For more information, see [Microsoft Defender Antivirus in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="9ca4c-204">Сведения об использовании групповой политики для настройки и управления антивирусная программа в Microsoft Defender на Windows серверах см. в этой Windows параметры [групповой политики](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)для настройки и управления антивирусная программа в Microsoft Defender .</span><span class="sxs-lookup"><span data-stu-id="9ca4c-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="9ca4c-205">Интеграция с Защитником Azure</span><span class="sxs-lookup"><span data-stu-id="9ca4c-205">Integration with Azure Defender</span></span>

<span data-ttu-id="9ca4c-206">Защитник для конечной точки может интегрироваться с Azure Defender, чтобы предоставить комплексное решение Windows защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="9ca4c-207">С помощью этой интеграции Azure Defender может использовать силу Defender для конечной точки, чтобы обеспечить улучшенное обнаружение угрозы для Windows серверов.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="9ca4c-208">В эту интеграцию включены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="9ca4c-209">Автоматическая бортовая система — датчик Defender для конечной точки автоматически включен на Windows серверах, которые находятся на борту в Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="9ca4c-210">Дополнительные сведения о встроенной платформе Azure Defender см. в таблице Использование интегрированной лицензии [Microsoft Defender для конечных точек.](/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ca4c-211">Интеграция между Azure Defender для серверов и Microsoft Defender для конечной точки была расширена для поддержки [Windows Server 2019](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)и Windows Виртуальный рабочий стол (WVD).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="9ca4c-212">Windows серверы, отслеживаемые Защитником Azure, также будут доступны в Defender for Endpoint — Azure Defender легко подключается к клиенту Defender для конечной точки, обеспечивая единое представление между клиентами и серверами.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="9ca4c-213">Кроме того, оповещения Defender для конечной точки будут доступны в консоли Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="9ca4c-214">Исследование сервера . Клиенты Azure Defender могут Центр безопасности в Microsoft Defender для выполнения подробного расследования, чтобы выявить область потенциального нарушения.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="9ca4c-215">При использовании Azure Defender для мониторинга серверов автоматически создается клиент Defender для конечных точек (в США для пользователей США, в ЕС для европейских и британских пользователей).</span><span class="sxs-lookup"><span data-stu-id="9ca4c-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="9ca4c-216">Данные, собранные Defender для конечной точки, хранятся в географическом расположении клиента, как определено во время предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="9ca4c-217">Если вы используете Defender для конечной точки перед использованием Azure Defender, ваши данные будут храниться в указанном вами расположении при создания клиента, даже если вы интегрируете с Azure Defender позднее.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="9ca4c-218">После настройки невозможно изменить расположение, в котором хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="9ca4c-219">Если необходимо переместить данные в другое расположение, необходимо обратиться в службу поддержки Майкрософт для сброса клиента.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="9ca4c-220">Мониторинг конечной точки сервера с использованием этой интеграции отключен для Office 365 GCC клиентов.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="9ca4c-221">Настройка и обновление System Center Endpoint Protection клиентов</span><span class="sxs-lookup"><span data-stu-id="9ca4c-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="9ca4c-222">Defender for Endpoint интегрируется с System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="9ca4c-223">Интеграция обеспечивает видимость обнаружения вредоносных программ и остановку распространения атаки в организации, запрещая потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="9ca4c-224">Чтобы включить эту интеграцию, необходимы следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="9ca4c-225">Установите обновление платформы для антивирусных программ за январь [2017 г. для](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)Endpoint Protection клиентов.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="9ca4c-226">[Настройка членства службы облачной защиты клиента SCEP в](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) **параметре Advanced.**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-226">[Configure the SCEP client Cloud Protection Service membership](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="9ca4c-227">Offboard Windows серверов</span><span class="sxs-lookup"><span data-stu-id="9ca4c-227">Offboard Windows servers</span></span>

<span data-ttu-id="9ca4c-228">Вы можете использовать Windows Server (SAC), Windows Server 2019 и Windows Server 2019 Core в том же методе, что и для Windows 10 клиентских устройств.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="9ca4c-229">Для других Windows серверных версий у вас есть два варианта отключения Windows серверов из службы:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="9ca4c-230">Удалить агент MMA</span><span class="sxs-lookup"><span data-stu-id="9ca4c-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="9ca4c-231">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9ca4c-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="9ca4c-232">Offboarding заставляет сервер Windows перестать отправлять данные датчиков на портал, но данные с Windows сервера, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="9ca4c-233">Удалить Windows серверов, отстранив агента MMA</span><span class="sxs-lookup"><span data-stu-id="9ca4c-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="9ca4c-234">Чтобы отключить сервер Windows, вы можете удалить агента ММА с сервера Windows или отсоединить его от отчетности в рабочее пространство Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="9ca4c-235">После отключения агента сервер Windows больше не будет отправлять данные датчиков в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="9ca4c-236">Дополнительные сведения см. в [статью Отключение агента.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-236">For more information, see [To disable an agent](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="9ca4c-237">Удаление конфигурации рабочего пространства Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9ca4c-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="9ca4c-238">Чтобы отключить сервер Windows, можно использовать любой из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="9ca4c-239">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="9ca4c-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="9ca4c-240">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="9ca4c-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="9ca4c-241">Удаление конфигурации рабочего пространства Defender для конечной точки из агента MMA</span><span class="sxs-lookup"><span data-stu-id="9ca4c-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="9ca4c-242">В Microsoft Monitoring Agent **свойства** выберите вкладку **Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="9ca4c-243">Выберите рабочее пространство Defender для конечной точки и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Изображение Microsoft Monitoring Agent свойств](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="9ca4c-245">Запустите команду PowerShell, чтобы удалить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="9ca4c-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="9ca4c-246">Получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="9ca4c-247">В области навигации выберите **Параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="9ca4c-248">Выберите **Windows Server 2008 R2 SP1, 2012 R2 и 2016** в качестве операционной системы и получите свой ID рабочего пространства:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Изображение Windows сервера](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="9ca4c-250&quot;>Откройте повышенную powerShell и запустите следующую команду.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9ca4c-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;9ca4c-251&quot;>Используйте полученный ИД рабочей области и `WorkspaceID` замените:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9ca4c-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="9ca4c-252">Onboarding Servers без решения управления</span><span class="sxs-lookup"><span data-stu-id="9ca4c-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="9ca4c-253">Использование групповой политики</span><span class="sxs-lookup"><span data-stu-id="9ca4c-253">Using Group Policy</span></span>

<span data-ttu-id="9ca4c-254">**Шаг-1. Создайте необходимые файлы для копирования на серверы.**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="9ca4c-255">Перейдите к c:\windows\sysvol\domain\scripts (управление изменением может быть необходимо на одном из контроллеров домена.)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="9ca4c-256">Создайте папку с именем MMA.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="9ca4c-257">Скачайте следующее и поместите в папку ММА:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="9ca4c-258">**Обновление для работы с клиентами и диагностической телеметрии (Windows 2008 R2 и Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="9ca4c-259">Для Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="9ca4c-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="9ca4c-260">Для Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="9ca4c-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="9ca4c-261">В этой статье предполагается, что вы используете серверы на основе x64 (MMA Agent .exe x64 [New SHA-2 compliant version)](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="9ca4c-262">**Шаг-2. Создание имени файла DeployMMA.cmd (с помощью блокнота)** Добавьте в файл cmd следующие строки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="9ca4c-263">Обратите внимание, что вам потребуется свой ID и KEY WORKSPACE.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

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

## <a name="group-policy-configuration"></a><span data-ttu-id="9ca4c-264">Конфигурация групповой политики</span><span class="sxs-lookup"><span data-stu-id="9ca4c-264">Group Policy Configuration</span></span>

<span data-ttu-id="9ca4c-265">Создайте новую групповую политику специально для бортовых устройств, таких как "Microsoft Defender for Endpoint Onboarding".</span><span class="sxs-lookup"><span data-stu-id="9ca4c-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="9ca4c-266">Создание папки групповой политики с именем "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="9ca4c-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="папки":::

    <span data-ttu-id="9ca4c-268">**Это добавит новую папку на каждом сервере, на который применяется GPO под названием MMA, и будет храниться в c:\windows. Это будет содержать файлы установки для ммА, необходимые условия и установить скрипт.**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="9ca4c-269">Создайте предпочтение групповым файлам политик для каждого из файлов, хранимого в логотипе Net.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="изображение групповой политики1":::

<span data-ttu-id="9ca4c-271">Он копирует файлы из DOMAIN\NETLOGON\MMA\filename в C:\windows\MMA\filename , поэтому файлы установки локализованы **на сервере:**</span><span class="sxs-lookup"><span data-stu-id="9ca4c-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="развертывание мма cmd":::

<span data-ttu-id="9ca4c-273">Для двух ЦБ (один для Windows Server 2008R2/Windows 7 и другой для Windows Server 2012 R2) повторите процесс, но создайте таргетинг уровня элементов на вкладке COMMON, поэтому файл копируется только в соответствующую версию платформы и операционной системы в области:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="целевой редактор":::

- <span data-ttu-id="9ca4c-275">Для Windows Server 2008 R2 вам понадобится (и он будет только копировать) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="9ca4c-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="9ca4c-276">Для Windows Server 2012 R2 вам потребуется (и он будет только копировать вниз) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="9ca4c-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="9ca4c-277">После этого необходимо создать политику скриптов для запуска:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="свойства запуска":::

<span data-ttu-id="9ca4c-279">Имя файла, который будет работать здесь, — c:\windows\MMA\DeployMMA.cmd.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="9ca4c-280">После перезапуска сервера в процессе запуска он установит обновление для работы с клиентами и диагностическую телеметрию КБ, а затем установит агента MMA, задав при этом ID рабочего пространства и ключ, и сервер будет на борту.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="9ca4c-281">Вы также можете  использовать немедленную задачу для запуска deployMMA.cmd, если вы не хотите перезагрузки всех серверов.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="9ca4c-282">Это можно сделать в два этапа.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-282">This could be done in two phases.</span></span> <span data-ttu-id="9ca4c-283">Сначала **создайте файлы** и папку в GPO — дайте системе время для обеспечения того, чтобы GPO была применена, и все серверы имеют файлы установки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="9ca4c-284">Затем добавьте немедленную задачу.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-284">Then, add the immediate task.</span></span> <span data-ttu-id="9ca4c-285">Это приведет к такому же результату, не требуя перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="9ca4c-286">Так как сценарий имеет метод выхода и не будет повторно запускаться, если ммА установлен, вы также можете использовать ежедневную запланированную задачу для достижения того же результата.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="9ca4c-287">Как и политика соответствия требованиям диспетчера конфигурации, она будет проверяться ежедневно, чтобы убедиться, что ммА присутствует.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="задача расписания":::

:::image type="content" source="images/newtaskprops.png" alt-text="новые свойства задач":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="развертывание реквизитов для скачивания мма":::

:::image type="content" source="images/tasksch.png" alt-text="планировщик задач":::

<span data-ttu-id="9ca4c-292">Как упоминалось в документации по onboarding для Server, конкретно вокруг Сервера 2008 R2, см. ниже:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="9ca4c-293">Для Windows Server 2008 R2 PS1 убедитесь, что вы выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="9ca4c-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="9ca4c-294">Установка [ежемесячного обновления в феврале 2018 г.](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="9ca4c-295">Установка [либо .NET framework 4.5 (или](https://www.microsoft.com/download/details.aspx?id=30653) более поздней) или [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="9ca4c-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="9ca4c-296">Убедитесь, что KBs присутствуют перед Windows Server 2008 R2 Этот процесс позволяет использовать все серверы, если у вас нет диспетчера конфигурации, управляющих серверами.</span><span class="sxs-lookup"><span data-stu-id="9ca4c-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ca4c-297">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9ca4c-297">Related topics</span></span>

- [<span data-ttu-id="9ca4c-298">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ca4c-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="9ca4c-299">Подключение устройствах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="9ca4c-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="9ca4c-300">Настройка параметров прокси-сервера и соединения с Интернетом</span><span class="sxs-lookup"><span data-stu-id="9ca4c-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="9ca4c-301">Запустите тест обнаружения на недавно висячем устройстве Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="9ca4c-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="9ca4c-302">Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9ca4c-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
