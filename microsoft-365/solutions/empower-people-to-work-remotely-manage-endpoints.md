---
title: Этап 4. Развертывание управления конечными точками для устройств, компьютеров и других конечных точек
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Используйте Microsoft Endpoint Manager для управления устройствами, компьютерами и другими конечными точками.
ms.openlocfilehash: 72aa26c50f5d3c20409382f19d8beabb5d290023
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681484"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="8bd2c-104">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-104">Step 4.</span></span> <span data-ttu-id="8bd2c-105">Развертывание управления конечными точками для устройств, компьютеров и других конечных точек</span><span class="sxs-lookup"><span data-stu-id="8bd2c-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="8bd2c-106">При наличии удаленных сотрудников вам потребуется поддерживать растущее количество личных устройств.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="8bd2c-107">Управление конечными точками — это основанный на политике подход к безопасности, требующий соответствия устройств определенным условиям, прежде чем им будет предоставлен доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="8bd2c-108">Microsoft Endpoint Manager обеспечивает современные возможности управления для защиты ваших данных в облачной и локальной среде.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="8bd2c-109">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) предоставляет службы и инструменты для управления мобильными устройствами, компьютерами, виртуальными машинами, встроенными устройствами и серверами путем сочетания следующих служб, которые вам могут быть уже знакомы.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-109">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Компоненты управления конечными точками для Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="8bd2c-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8bd2c-111">Microsoft Intune</span></span>

<span data-ttu-id="8bd2c-112">Microsoft Intune — это облачная служба, которая включена в Microsoft 365 и предназначена для управления мобильными устройствами (MDM) и мобильными приложениями (MAM).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="8bd2c-113">**MDM:** вы можете полностью контролировать устройства, принадлежащие организации, в том числе их параметры, компоненты и безопасность.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="8bd2c-114">Устройства регистрируются в Intune, где они получают политики Intune с правилами и параметрами.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="8bd2c-115">Например, вы можете задать требования к паролю и ПИН-коду, создать VPN-подключение, настроить защиту от угроз и многое другое.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="8bd2c-116">**MAM:** возможно, удаленные сотрудники не захотят, чтобы вы полностью контролировали их личные устройства, также известные как устройства BYOD ("принеси свое устройство").</span><span class="sxs-lookup"><span data-stu-id="8bd2c-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="8bd2c-117">Вы можете предоставить удаленным сотрудникам выбор и при этом защитить организацию.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="8bd2c-118">Они могут зарегистрировать свои устройства, если хотят получить полный доступ к ресурсам организации.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="8bd2c-119">Если же этим пользователям нужен доступ только к электронной почте или Microsoft Teams, используйте политики защиты приложений, требующие многофакторной проверки подлинности (MFA) для использования этих приложений.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="8bd2c-120">Дополнительные сведения см. в [обзоре Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="8bd2c-121">Диспетчер конфигураций</span><span class="sxs-lookup"><span data-stu-id="8bd2c-121">Configuration Manager</span></span>

<span data-ttu-id="8bd2c-122">Диспетчер конфигураций — это локальное решение для управления компьютерами, серверами и ноутбуками в вашей сети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="8bd2c-123">Используйте диспетчер конфигураций для развертывания приложений, обновлений программного обеспечения и операционных систем.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="8bd2c-124">Кроме того, вы можете отслеживать соответствие требованиям, запросы, применять действия в клиентах в режиме реального времени и т. д.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="8bd2c-125">Вы можете включить в нем поддержку облака для интеграции с Intune, Azure AD, ATP в Microsoft Defender и другими облачными службами.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="8bd2c-126">Дополнительные сведения см. в [обзоре диспетчера конфигураций](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="8bd2c-127">Совместное управление</span><span class="sxs-lookup"><span data-stu-id="8bd2c-127">Co-management</span></span>

<span data-ttu-id="8bd2c-128">Совместное управление объединяет существующие вложения в локальный диспетчер конфигураций с облаком посредством Intune и других облачных служб Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="8bd2c-129">Вы можете выбрать диспетчер конфигураций или Intune в качестве центра управления для различных рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="8bd2c-130">Для совместного управления используются облачные функции на основе Intune, в том числе условный доступ и обеспечение соблюдения требований к устройствам.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="8bd2c-131">Некоторые задачи остаются локальными, а другие выполняются в облаке.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="8bd2c-132">Дополнительные сведения см. в [обзоре совместного управления](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="8bd2c-133">Аналитика компьютеров</span><span class="sxs-lookup"><span data-stu-id="8bd2c-133">Desktop Analytics</span></span>

<span data-ttu-id="8bd2c-134">Аналитика компьютеров — это облачная служба, интегрирующаяся с диспетчером конфигураций и предоставляющая аналитику, чтобы вы могли принимать взвешенные решения о клиентах Windows.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="8bd2c-135">В ней данные из вашей организации объединяются с данными, собранными из миллионов других устройств, подключенных к облачным службам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-135">It combines data from your organization with data aggregated from millions of other devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="8bd2c-136">С помощью Аналитики компьютеров можно:</span><span class="sxs-lookup"><span data-stu-id="8bd2c-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="8bd2c-137">Создать опись приложений, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="8bd2c-138">Оценить совместимость приложений с последними обновлениями компонентов Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="8bd2c-139">Обнаружить проблемы совместимости и получить рекомендации по их устранению на основе облачной аналитики данных.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-139">Identify compatibility issues and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="8bd2c-140">Создать пилотные группы, отражающие состояние приложений и драйверов на минимальном наборе устройств.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="8bd2c-141">Развернуть Windows 10 на пилотных и рабочих устройствах.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="8bd2c-142">Дополнительные сведения см. в [обзоре Аналитики компьютеров](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="8bd2c-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="8bd2c-143">Windows Autopilot</span></span>

<span data-ttu-id="8bd2c-144">В Windows Autopilot реализована автоматическая платформа для самостоятельного развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="8bd2c-145">Она включает набор технологий, используемых вами для настройки и предварительной конфигурации новых устройств, а также подготовки их к работе.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-145">It includes a collection of technologies you use to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="8bd2c-146">Также можно использовать Windows Autopilot для сброса, перепрофилирования и восстановления устройств.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="8bd2c-147">Windows Autopilot позволяет ИТ-отделам предварительно настроить устройства с минимальной инфраструктурой для управления или без нее, используя простой и удобный процесс.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="8bd2c-148">С точки зрения пользователя для подготовки устройства к работе достаточно нескольких простых действий.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="8bd2c-149">С точки зрения ИТ-специалиста пользователь должен лишь подключиться к сети и подтвердить свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="8bd2c-150">Дополнительные сведения см. в [обзоре Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="8bd2c-151">Технические ресурсы администраторов для управления конечными точками</span><span class="sxs-lookup"><span data-stu-id="8bd2c-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="8bd2c-152">Стратегия управления устройством в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8bd2c-152">Device management roadmap for Microsoft 365</span></span>](../enterprise/device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="8bd2c-153">Способы регистрации различных типов устройств для управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="8bd2c-153">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="8bd2c-154">Инструкции по использованию Microsoft Intune для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="8bd2c-154">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="8bd2c-155">Результаты этапа 3</span><span class="sxs-lookup"><span data-stu-id="8bd2c-155">Results of Step 3</span></span>

<span data-ttu-id="8bd2c-156">Вы используете набор функций и возможностей Endpoint Manager для управления мобильными устройствами, компьютерами, виртуальными машинами, встроенными устройствами и серверами.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-156">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="8bd2c-157">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="8bd2c-157">Next step</span></span>

<span data-ttu-id="8bd2c-158">[![Этап 5. Развертывание служб и приложений для повышения производительности удаленных сотрудников](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span><span class="sxs-lookup"><span data-stu-id="8bd2c-158">[![Step 5: Deploy remote worker productivity apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span></span>

<span data-ttu-id="8bd2c-159">Перейдите к [этапу 5](empower-people-to-work-remotely-teams-productivity-apps.md), чтобы дать удаленным сотрудникам возможность использовать приложения Microsoft 365 для повышения производительности, такие как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-159">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
