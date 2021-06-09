---
title: Этап 5. Управление устройствами и приложениями для Microsoft 365 для корпоративных клиентов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Развертывание правильного параметра для управления устройствами и приложениями для Microsoft 365 клиентов.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050998"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="77f5f-104">Этап 5.</span><span class="sxs-lookup"><span data-stu-id="77f5f-104">Step 5.</span></span> <span data-ttu-id="77f5f-105">Управление устройствами и приложениями для Microsoft 365 для корпоративных клиентов</span><span class="sxs-lookup"><span data-stu-id="77f5f-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="77f5f-106">Microsoft 365 для предприятия включает функции, которые помогают управлять устройствами и использовать приложения на этих устройствах в организации с помощью управления мобильными устройствами (MDM) и управления мобильными приложениями (MAM).</span><span class="sxs-lookup"><span data-stu-id="77f5f-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="77f5f-107">Вы можете управлять устройствами iOS, Android, macOS и Windows для защиты доступа к ресурсам организации, включая данные.</span><span class="sxs-lookup"><span data-stu-id="77f5f-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="77f5f-108">Например, можно запретить отправку электронных писем людям за пределами организации или изолировать данные организации от персональных данных на личных устройствах вашего сотрудника.</span><span class="sxs-lookup"><span data-stu-id="77f5f-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="77f5f-109">Вот пример проверки и управления пользователями, их устройствами и их использованием локальных и облачных приложений производительности, таких как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77f5f-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Проверка и управление пользователями, устройствами и приложениями](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="77f5f-111">Чтобы обеспечить безопасность и защиту ресурсов организации, Microsoft 365 для предприятия включают функции, которые помогают управлять устройствами и их доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="77f5f-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="77f5f-112">Существует два варианта управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="77f5f-112">There are two options for device management:</span></span>

- <span data-ttu-id="77f5f-113">Microsoft Intune, которое является комплексным решением для управления устройствами и приложениями для предприятий.</span><span class="sxs-lookup"><span data-stu-id="77f5f-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="77f5f-114">Basic Mobility and Security — это подмножество служб Intune, включающих все Microsoft 365 для управления устройствами в организации.</span><span class="sxs-lookup"><span data-stu-id="77f5f-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="77f5f-115">Дополнительные сведения см. в дополнительных сведениях о возможностях [базовой мобильности и безопасности.](../admin/basic-mobility-security/capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="77f5f-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="77f5f-116">Если у вас Microsoft 365 E3 или E5, следует использовать Intune.</span><span class="sxs-lookup"><span data-stu-id="77f5f-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="77f5f-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77f5f-117">Microsoft Intune</span></span>

<span data-ttu-id="77f5f-118">Вы используете [Microsoft Intune](/mem/intune/fundamentals/planning-guide) для управления доступом к организации с помощью MDM или MAM.</span><span class="sxs-lookup"><span data-stu-id="77f5f-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="77f5f-119">MDM — это когда пользователи "регистрировать" свои устройства в Intune.</span><span class="sxs-lookup"><span data-stu-id="77f5f-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="77f5f-120">После регистрации устройство является управляемым устройством и может получать политики, правила и параметры организации.</span><span class="sxs-lookup"><span data-stu-id="77f5f-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="77f5f-121">Например, можно установить определенные приложения, создать политику паролей, установить VPN-подключение и другие.</span><span class="sxs-lookup"><span data-stu-id="77f5f-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="77f5f-122">Пользователи со своими личными устройствами могут не захоть зарегистрироваться на своих устройствах или управляться политиками Intune и вашей организации.</span><span class="sxs-lookup"><span data-stu-id="77f5f-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="77f5f-123">Но все равно необходимо защитить ресурсы и данные организации.</span><span class="sxs-lookup"><span data-stu-id="77f5f-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="77f5f-124">В этом сценарии вы можете защитить свои приложения с помощью MAM.</span><span class="sxs-lookup"><span data-stu-id="77f5f-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="77f5f-125">Например, можно использовать политику MAM, которая требует от пользователя ввести ПИН-код при SharePoint на устройстве.</span><span class="sxs-lookup"><span data-stu-id="77f5f-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="77f5f-126">Вы также определите, как управлять личными устройствами и устройствами, которые принадлежат организации.</span><span class="sxs-lookup"><span data-stu-id="77f5f-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="77f5f-127">Может потребоваться по-разному относиться к устройствам в зависимости от их использования.</span><span class="sxs-lookup"><span data-stu-id="77f5f-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="77f5f-128">Конфигурации доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="77f5f-128">Identity and device access configurations</span></span>

<span data-ttu-id="77f5f-129">Корпорация Майкрософт предоставляет набор конфигураций для доступа к [удостоверениям](../security/defender-365-security/microsoft-365-policies-configurations.md) и устройствам, чтобы обеспечить безопасную и продуктивную рабочую силу.</span><span class="sxs-lookup"><span data-stu-id="77f5f-129">Microsoft provides a set of configurations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="77f5f-130">В этих конфигурациях используется:</span><span class="sxs-lookup"><span data-stu-id="77f5f-130">These configurations include the use of:</span></span>

- <span data-ttu-id="77f5f-131">Политики условного доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="77f5f-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="77f5f-132">Microsoft Intune соответствия требованиям устройств и политикам защиты приложений</span><span class="sxs-lookup"><span data-stu-id="77f5f-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="77f5f-133">Политики риска для пользователей Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="77f5f-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="77f5f-134">Дополнительные политики облачных приложений</span><span class="sxs-lookup"><span data-stu-id="77f5f-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="77f5f-135">Вот пример применения этих параметров и политик для проверки и ограничения пользователей, их устройств и использования локальных и облачных приложений производительности, таких как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77f5f-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Конфигурации удостоверений и доступа к устройствам для требований и ограничений для пользователей, их устройств и их использования приложений](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="77f5f-137">Для доступа к устройствам и управления приложениями используйте конфигурации в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="77f5f-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="77f5f-138">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="77f5f-138">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="77f5f-139">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="77f5f-139">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="77f5f-140">Результаты этапа 5</span><span class="sxs-lookup"><span data-stu-id="77f5f-140">Results of Step 5</span></span>

<span data-ttu-id="77f5f-141">Для управления устройствами и приложениями для Microsoft 365 клиента вы определили параметры и политики Intune для проверки и ограничения пользователей, их устройств и использования локальных и облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="77f5f-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="77f5f-142">Вот пример клиента с устройством Intune и управлением приложениями с выделением новых элементов.</span><span class="sxs-lookup"><span data-stu-id="77f5f-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Пример клиента с устройством Intune и управлением приложениями](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="77f5f-144">На этой иллюстрации у клиента есть:</span><span class="sxs-lookup"><span data-stu-id="77f5f-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="77f5f-145">Устройства, которые принадлежат организации, зарегистрированные в Intune.</span><span class="sxs-lookup"><span data-stu-id="77f5f-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="77f5f-146">Intune политики устройств и приложений для зарегистрированных и личных устройств.</span><span class="sxs-lookup"><span data-stu-id="77f5f-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="77f5f-147">Текущее обслуживание для управления устройствами и приложениями</span><span class="sxs-lookup"><span data-stu-id="77f5f-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="77f5f-148">На постоянной основе может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="77f5f-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="77f5f-149">Управление регистрацией устройств.</span><span class="sxs-lookup"><span data-stu-id="77f5f-149">Manage device enrollment.</span></span>
- <span data-ttu-id="77f5f-150">Пересмотрите параметры и политики для дополнительных приложений, устройств и требований к безопасности.</span><span class="sxs-lookup"><span data-stu-id="77f5f-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>