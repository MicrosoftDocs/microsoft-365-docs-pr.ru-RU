---
title: Этап 3. Условия, при выполнении которых можно считать инфраструктуру Windows 10 Корпоративная настроенной
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 06/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Убедитесь, что используемая вами конфигурация соответствует критериям Microsoft 365 корпоративный для Windows 10 Корпоративная.
ms.openlocfilehash: 7ac79fec93e4b4aae0b075891917e2f88432b80f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870828"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="2fc65-103">Этап 3. Условия, при выполнении которых можно считать инфраструктуру Windows 10 Корпоративная настроенной</span><span class="sxs-lookup"><span data-stu-id="2fc65-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="2fc65-104">Если ваша инфраструктура Windows 10 Корпоративная соответствует указанным ниже требованиям, вы готовы переходить к этапу 4.</span><span class="sxs-lookup"><span data-stu-id="2fc65-104">If your Windows 10 Enterprise infrastructure meets the following conditions, you’re ready to move to Phase 4.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="2fc65-105">Обязательно: домены Microsoft 365 добавлены и проверены</span><span class="sxs-lookup"><span data-stu-id="2fc65-105">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="2fc65-106">Клиент Azure AD для подписок на Office 365 и Intune настраивается с доменными именами Интернета (например, contoso.com), а не только доменным именем, включающим строку "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="2fc65-106">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="2fc65-p101">В противном случае выбор способов проверки подлинности, которые вы можете настроить, будет ограничен. Например, для сквозной и федеративной аутентификации невозможно использовать доменное имя onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fc65-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="2fc65-109">Чтобы выполнить это требование, см. [этап 1](windows10-prepare-your-org.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-109">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="2fc65-110">Необязательно: пользователи добавлены и лицензированы</span><span class="sxs-lookup"><span data-stu-id="2fc65-110">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="2fc65-111">Учетные записи, соответствующие вашим пользователям, добавлены либо непосредственно в клиент Azure AD для ваших подписок на Office 365 и Intune, либо путем синхронизации службы каталогов из локальной службы Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="2fc65-111">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Windows Server AD.</span></span>

<span data-ttu-id="2fc65-112">Добавив пользователей, вы можете назначить им лицензии на Microsoft 365 корпоративный либо непосредственно как администратор пользователей или глобальный администратор, либо автоматически через членство в группах.</span><span class="sxs-lookup"><span data-stu-id="2fc65-112">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="2fc65-113">В этом вам поможет описание [этапа 1](windows10-prepare-your-org.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-113">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="2fc65-114">Необязательно: диагностика включена</span><span class="sxs-lookup"><span data-stu-id="2fc65-114">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="2fc65-115">Вы включили параметры диагностики данных с помощью групповой политики, Microsoft Intune, редактора реестра или в командной строке.</span><span class="sxs-lookup"><span data-stu-id="2fc65-115">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="2fc65-116">В этом вам поможет описание [этапа 1](windows10-prepare-your-org.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-116">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="2fc65-117">Обязательно для обновления на месте: создана последовательность задач диспетчера конфигураций для развертывания операционной системы</span><span class="sxs-lookup"><span data-stu-id="2fc65-117">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="2fc65-118">Чтобы запустить последовательность задач диспетчера конфигураций для обновления на месте на устройстве с Windows 7 или Windows 8.1, необходимо:</span><span class="sxs-lookup"><span data-stu-id="2fc65-118">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="2fc65-119">задать подходящий уровень диагностических данных Windows;</span><span class="sxs-lookup"><span data-stu-id="2fc65-119">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="2fc65-120">проверить готовность к обновлению Windows;</span><span class="sxs-lookup"><span data-stu-id="2fc65-120">Verify the readiness to upgrade Windows</span></span>
- <span data-ttu-id="2fc65-121">создать последовательность задач диспетчера конфигураций, которая включает коллекцию устройств и развертывание операционной системы с использованием образа ОС Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2fc65-121">Create a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="2fc65-p102">Когда это будет сделано, вы можете выполнить обновление на месте для тех устройств, которые готовы к обновлению Windows. Чтобы получить максимум пользы от Microsoft 365 корпоративный, обновите как можно больше устройств с Windows 7 и Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="2fc65-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="2fc65-p103">Каждое устройство с Windows 10 Корпоративная может использовать преимущества интегрированного решения Microsoft 365 корпоративный. Остальные устройства с Windows 7 или Windows 8.1 не могут использовать облачные технологии и расширенные функции безопасности, доступные в Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="2fc65-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="2fc65-126">Чтобы выполнить это требование, см. [этап 2](windows10-deploy-inplaceupgrade.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-126">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="2fc65-127">Обязательно для новых устройств: настроено решение Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="2fc65-127">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="2fc65-128">Чтобы использовать Windows Autopilot для развертывания и настройки Windows 10 Корпоративная на новом устройстве, необходимо:</span><span class="sxs-lookup"><span data-stu-id="2fc65-128">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="2fc65-129">задать подходящий уровень диагностических данных Windows;</span><span class="sxs-lookup"><span data-stu-id="2fc65-129">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="2fc65-130">выполнить необходимые условия для Windows Autopilot, в том числе:</span><span class="sxs-lookup"><span data-stu-id="2fc65-130">Completed the prerequisites for Windows Autopilot, which include:</span></span>
- <span data-ttu-id="2fc65-131">регистрацию устройств и настройку запуска при первом включении компьютера;</span><span class="sxs-lookup"><span data-stu-id="2fc65-131">Device registration and OOBE customization</span></span>
- <span data-ttu-id="2fc65-132">фирменную символику для запуска при первом включении компьютера;</span><span class="sxs-lookup"><span data-stu-id="2fc65-132">Company branding for OOBE</span></span>
- <span data-ttu-id="2fc65-133">автоматическую регистрацию MDM в Microsoft Intune;</span><span class="sxs-lookup"><span data-stu-id="2fc65-133">MDM auto-enrollment in Microsoft Intune</span></span>
- <span data-ttu-id="2fc65-134">сетевое подключение к облачным службам, которые использует Windows Autopilot;</span><span class="sxs-lookup"><span data-stu-id="2fc65-134">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="2fc65-135">предварительную установку Windows 10 версии 1703 или выше на устройствах;</span><span class="sxs-lookup"><span data-stu-id="2fc65-135">Devices must be pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="2fc65-136">выбрать программу Windows Autopilot Deployment для своей организации.</span><span class="sxs-lookup"><span data-stu-id="2fc65-136">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="2fc65-137">Когда конфигурация Windows Autopilot будет готова, с ее помощью вы можете настроить в Windows 10 Корпоративная запуск при первом включении (OOBE) для:</span><span class="sxs-lookup"><span data-stu-id="2fc65-137">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="2fc65-138">новых устройств;</span><span class="sxs-lookup"><span data-stu-id="2fc65-138">New devices</span></span>
- <span data-ttu-id="2fc65-139">устройств, которые уже прошли настройку первого включения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2fc65-139">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="2fc65-140">Windows Autopilot настраивает устройство и подключает его к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2fc65-140">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="2fc65-141">Без Windows Autopilot потребуется настраивать новые устройства (в том числе выполнять подключение к Azure AD) вручную.</span><span class="sxs-lookup"><span data-stu-id="2fc65-141">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="2fc65-142">Чтобы выполнить это требование, см. [этап 3](windows10-deploy-autopilot.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-142">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="2fc65-143">Необязательно: служба работоспособности устройств Windows Analytics используется для наблюдения за устройствами с Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="2fc65-143">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="2fc65-p104">Вы использовали данные мониторинга в службе работоспособности устройств, чтобы обнаруживать и устранять проблемы, влияющие на работу пользователей. Быстрое реагирование может снизить затраты на поддержку и показать пользователям ваше серьезное отношение к ОС Windows 10 Корпоративная, что поспособствует ее принятию в организации.</span><span class="sxs-lookup"><span data-stu-id="2fc65-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="2fc65-146">Чтобы выполнить это требование, см. [этап 4](windows10-enable-windows-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-146">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="2fc65-147">Обязательно: вы используете антивирусную программу "Защитник Windows" или собственное антивредоносное решение</span><span class="sxs-lookup"><span data-stu-id="2fc65-147">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="2fc65-p105">Вы развернули антивирусную программу "Защитник Windows" или собственное антивирусное решение для защиты устройств с Windows 10 Корпоративная от вредоносных программ. Если развернута антивирусная программа "Защитник Windows", то должен быть реализован способ создания отчетов, например System Center Configuration Manager или Microsoft Intune, для отслеживания событий и действий антивируса.</span><span class="sxs-lookup"><span data-stu-id="2fc65-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="2fc65-150">Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-av).</span><span class="sxs-lookup"><span data-stu-id="2fc65-150">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="2fc65-151">Обязательно: используется Exploit Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="2fc65-151">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="2fc65-152">Вы развернули Exploit Guard в Защитнике Windows для защиты устройств с Windows 10 Корпоративная от вторжений и реализовали способ создания отчетов, например System Center Configuration Manager или Microsoft Intune, для отслеживания событий и действий, связанных с вторжениями.</span><span class="sxs-lookup"><span data-stu-id="2fc65-152">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="2fc65-153">Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-eg).</span><span class="sxs-lookup"><span data-stu-id="2fc65-153">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="2fc65-154">Обязательно: вы используете Advanced Threat Protection в Защитнике Windows (только в Microsoft 365 корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="2fc65-154">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="2fc65-155">Вы развернули Advanced Threat Protection (ATP) в Защитнике Windows, чтобы обнаруживать и расследовать особо опасные угрозы для сети и устройств с Windows 10 Корпоративная, а также реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="2fc65-155">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="2fc65-156">При необходимости вы интегрировали службу ATP в Защитнике Windows с другими средствами, чтобы расширить ее возможности.</span><span class="sxs-lookup"><span data-stu-id="2fc65-156">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="2fc65-157">Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-atp).</span><span class="sxs-lookup"><span data-stu-id="2fc65-157">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>


## <a name="next-phase"></a><span data-ttu-id="2fc65-158">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="2fc65-158">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="2fc65-159">Следующий компонент полного развертывания Microsoft 365 корпоративный — [Office 365 профессиональный плюс](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="2fc65-159">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
