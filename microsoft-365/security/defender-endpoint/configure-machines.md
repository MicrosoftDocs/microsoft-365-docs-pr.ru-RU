---
title: Убедитесь, что устройства настроены правильно
description: Правильно настраивайте устройства, чтобы повысить общую устойчивость к угрозам и повысить возможности обнаружения и реагирования на атаки.
keywords: onboard, управление Intune, MDATP, WDATP, Microsoft Defender, Защитник Windows, расширенные средства защиты от угроз, уменьшение поверхности атаки, ASR, базовый уровень безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163367"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="fd882-104">Убедитесь, что устройства настроены правильно</span><span class="sxs-lookup"><span data-stu-id="fd882-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd882-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fd882-105">**Applies to:**</span></span>
- [<span data-ttu-id="fd882-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd882-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fd882-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd882-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fd882-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fd882-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fd882-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fd882-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="fd882-110">С помощью правильно настроенных устройств можно повысить общую устойчивость к угрозам и повысить возможности обнаружения и реагирования на атаки.</span><span class="sxs-lookup"><span data-stu-id="fd882-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="fd882-111">Управление конфигурацией безопасности помогает убедиться, что ваши устройства:</span><span class="sxs-lookup"><span data-stu-id="fd882-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="fd882-112">Onboard to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fd882-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="fd882-113">Встреча или превышение базовой конфигурации безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd882-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="fd882-114">Иметь стратегические меры по смягчению последствий атаки</span><span class="sxs-lookup"><span data-stu-id="fd882-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="fd882-115">Щелкните **управление конфигурацией** из меню навигации, чтобы открыть страницу управления конфигурацией устройства.</span><span class="sxs-lookup"><span data-stu-id="fd882-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="fd882-116">![Страница управления конфигурацией безопасности](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="fd882-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="fd882-117">*Страница управления конфигурацией устройств*</span><span class="sxs-lookup"><span data-stu-id="fd882-117">*Device configuration management page*</span></span>

<span data-ttu-id="fd882-118">Вы можете отслеживать состояние конфигурации на организационном уровне и быстро принимать меры в ответ на плохое покрытие на борту, проблемы с соответствием требованиям и плохо оптимизированные меры по смягчению последствий атак с помощью прямых, глубоких ссылок на страницы управления устройствами в центре безопасности Microsoft Intune и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd882-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="fd882-119">При этом вы можете воспользоваться преимуществами:</span><span class="sxs-lookup"><span data-stu-id="fd882-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="fd882-120">Всеобъемлющая видимость событий на устройствах</span><span class="sxs-lookup"><span data-stu-id="fd882-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="fd882-121">Надежный интеллект угроз и мощные технологии обучения устройств для обработки необработанных событий и определения активности и показателей угрозы нарушения</span><span class="sxs-lookup"><span data-stu-id="fd882-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="fd882-122">Полный набор функций безопасности, настроенных для эффективного остановки установки вредоносных имплантатов, захвата системных файлов и процессов, эксфильтрации данных и других действий с угрозами.</span><span class="sxs-lookup"><span data-stu-id="fd882-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="fd882-123">Оптимизация смягчения последствий атак, максимальное повышение стратегической защиты от активности угроз и сведение к минимуму влияния на производительность</span><span class="sxs-lookup"><span data-stu-id="fd882-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="fd882-124">Регистрация устройств в управление Intune</span><span class="sxs-lookup"><span data-stu-id="fd882-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="fd882-125">Управление конфигурацией устройств тесно сотрудничает с управлением устройствами Intune для создания инвентаризации устройств в организации и базовой конфигурации безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd882-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="fd882-126">Вы сможете отслеживать и управлять вопросами конфигурации на устройствах Windows 10 с управлением Intune.</span><span class="sxs-lookup"><span data-stu-id="fd882-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="fd882-127">Прежде чем обеспечить правильную настройку устройств, зарегистрировать их в управление Intune.</span><span class="sxs-lookup"><span data-stu-id="fd882-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="fd882-128">Регистрация intune является надежной и имеет несколько параметров регистрации для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fd882-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="fd882-129">Дополнительные сведения о параметрах регистрации Intune см. в материале о настройке [регистрации для устройств Windows.](https://docs.microsoft.com/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="fd882-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="fd882-130">Для регистрации устройств Windows в Intune администраторам должны быть назначены лицензии.</span><span class="sxs-lookup"><span data-stu-id="fd882-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="fd882-131">[Узнайте о назначении лицензий для регистрации устройств.](https://docs.microsoft.com/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="fd882-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="fd882-132">Чтобы оптимизировать управление устройствами через Intune, [подключите Intune к Защитнику для конечной точки.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="fd882-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="fd882-133">Получение необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="fd882-133">Obtain required permissions</span></span>
<span data-ttu-id="fd882-134">По умолчанию управлять профилями конфигурации устройств, необходимыми для бортовых устройств и развертывания базовой базы безопасности, могут только пользователи, которым назначена роль глобального администратора или администратора службы Intune в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fd882-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="fd882-135">Если вам назначены другие роли, убедитесь, что у вас есть необходимые разрешения:</span><span class="sxs-lookup"><span data-stu-id="fd882-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="fd882-136">Полные разрешения на конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="fd882-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="fd882-137">Полные разрешения на базовые показатели безопасности</span><span class="sxs-lookup"><span data-stu-id="fd882-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="fd882-138">Чтение разрешений для политик соответствия требованиям к устройствам</span><span class="sxs-lookup"><span data-stu-id="fd882-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="fd882-139">Чтение разрешений в организации</span><span class="sxs-lookup"><span data-stu-id="fd882-139">Read permissions to the organization</span></span>

<span data-ttu-id="fd882-140">![Необходимые разрешения на intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="fd882-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="fd882-141">*Разрешения конфигурации устройств в Intune*</span><span class="sxs-lookup"><span data-stu-id="fd882-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="fd882-142">Дополнительные новости о назначении разрешений в Intune см. в материале [о создании настраиваемой роли.](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="fd882-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fd882-143">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fd882-143">In this section</span></span>
<span data-ttu-id="fd882-144">Статья</span><span class="sxs-lookup"><span data-stu-id="fd882-144">Topic</span></span> | <span data-ttu-id="fd882-145">Описание</span><span class="sxs-lookup"><span data-stu-id="fd882-145">Description</span></span>
:---|:---
[<span data-ttu-id="fd882-146">Получить устройства на борту в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd882-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="fd882-147">Отслеживание состояния onboarding устройств, управляемых intune, и дополнительных устройств на борту через Intune.</span><span class="sxs-lookup"><span data-stu-id="fd882-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="fd882-148">Повышение соответствия базовому стандарту безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd882-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="fd882-149">Отслеживание базового соответствия и несоответствия.</span><span class="sxs-lookup"><span data-stu-id="fd882-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="fd882-150">Развертывание базовой базы безопасности на более управляемых intune устройствах.</span><span class="sxs-lookup"><span data-stu-id="fd882-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="fd882-151">Оптимизация развертывания и обнаружения правил ASR</span><span class="sxs-lookup"><span data-stu-id="fd882-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="fd882-152">Просмотрите развертывание правил и настройка обнаружения с помощью средств анализа воздействия в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd882-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="fd882-153">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fd882-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fd882-154">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fd882-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)