---
title: Onboard devices to the Microsoft Defender ATP service
description: На борту устройств Windows 10, серверов, устройств без Windows и узнайте, как выполнить тест обнаружения.
keywords: onboarding, microsoft defender for endpoint onboarding, windows atp onboarding, sccm, group policy, mdm, local script, detection test
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b7a225e29b4b79b2e6caf95332cb91da3dade7f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186957"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="ee24c-104">Onboard devices to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="ee24c-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee24c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ee24c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee24c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ee24c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee24c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee24c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="ee24c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ee24c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ee24c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ee24c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="ee24c-110">Вам потребуется перейти в раздел onboarding портала Defender для конечной точки на борт любого из поддерживаемых устройств.</span><span class="sxs-lookup"><span data-stu-id="ee24c-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="ee24c-111">В зависимости от устройства вы будете руководствоваться соответствующими действиями и предоставлять параметры средств управления и развертывания, подходящие для устройства.</span><span class="sxs-lookup"><span data-stu-id="ee24c-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="ee24c-112">В общем, для бортовых устройств в службу:</span><span class="sxs-lookup"><span data-stu-id="ee24c-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="ee24c-113">Убедитесь, что устройство выполняет [минимальные требования](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ee24c-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="ee24c-114">В зависимости от устройства выполните этапы настройки, предусмотренные в разделе onboarding портала Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee24c-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="ee24c-115">Использование соответствующего средства управления и метода развертывания для устройств</span><span class="sxs-lookup"><span data-stu-id="ee24c-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="ee24c-116">Запустите тест обнаружения, чтобы убедиться, что устройства правильно на борту и отчеты службе</span><span class="sxs-lookup"><span data-stu-id="ee24c-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="ee24c-117">Параметры onboarding tool</span><span class="sxs-lookup"><span data-stu-id="ee24c-117">Onboarding tool options</span></span>
<span data-ttu-id="ee24c-118">В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.</span><span class="sxs-lookup"><span data-stu-id="ee24c-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="ee24c-119">Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee24c-119">Endpoint</span></span>     | <span data-ttu-id="ee24c-120">Параметры инструмента</span><span class="sxs-lookup"><span data-stu-id="ee24c-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="ee24c-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ee24c-121">**Windows**</span></span>  |  [<span data-ttu-id="ee24c-122">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="ee24c-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="ee24c-123">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="ee24c-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="ee24c-124">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="ee24c-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="ee24c-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee24c-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="ee24c-126">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="ee24c-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="ee24c-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="ee24c-127">**macOS**</span></span>    | [<span data-ttu-id="ee24c-128">Локальные сценарии</span><span class="sxs-lookup"><span data-stu-id="ee24c-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="ee24c-129">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ee24c-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="ee24c-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="ee24c-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="ee24c-131">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="ee24c-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="ee24c-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="ee24c-132">**Linux Server**</span></span> | [<span data-ttu-id="ee24c-133">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="ee24c-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="ee24c-134">Puppet</span><span class="sxs-lookup"><span data-stu-id="ee24c-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="ee24c-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="ee24c-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="ee24c-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="ee24c-136">**iOS**</span></span>      | [<span data-ttu-id="ee24c-137">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="ee24c-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="ee24c-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="ee24c-138">**Android**</span></span>  | [<span data-ttu-id="ee24c-139">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ee24c-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="ee24c-140">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ee24c-140">In this section</span></span>
<span data-ttu-id="ee24c-141">Статья</span><span class="sxs-lookup"><span data-stu-id="ee24c-141">Topic</span></span> | <span data-ttu-id="ee24c-142">Описание</span><span class="sxs-lookup"><span data-stu-id="ee24c-142">Description</span></span>
:---|:---
[<span data-ttu-id="ee24c-143">На борту предыдущих версий Windows</span><span class="sxs-lookup"><span data-stu-id="ee24c-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="ee24c-144">На борту устройств Windows 7 и Windows 8.1 в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ee24c-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="ee24c-145">На борту устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee24c-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="ee24c-146">Чтобы сообщить об этом службе Defender для конечной точки, необходимо иметь бортовые устройства.</span><span class="sxs-lookup"><span data-stu-id="ee24c-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="ee24c-147">Узнайте о средствах и методах, которые можно использовать для настройки устройств в вашем предприятии.</span><span class="sxs-lookup"><span data-stu-id="ee24c-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="ee24c-148">Серверы на борту</span><span class="sxs-lookup"><span data-stu-id="ee24c-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="ee24c-149">На борту Windows Server 2008 R2 sp1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) версии 1803 и более поздней версии Windows Server 2019 и более поздней версии, а также основного выпуска Windows Server 2019 в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee24c-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="ee24c-150">Onboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="ee24c-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="ee24c-151">Defender for Endpoint предоставляет централизованные операции безопасности как для Windows, так и для неконтроционных платформ.</span><span class="sxs-lookup"><span data-stu-id="ee24c-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="ee24c-152">Вы сможете видеть оповещения из различных поддерживаемых операционных систем (ОС) в Центре безопасности Microsoft Defender и лучше защищать сеть организации.</span><span class="sxs-lookup"><span data-stu-id="ee24c-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="ee24c-153">Этот опыт использует данные датчиков сторонних продуктов безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee24c-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="ee24c-154">Запустите тест обнаружения на новом устройстве</span><span class="sxs-lookup"><span data-stu-id="ee24c-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="ee24c-155">Запустите скрипт на новом устройстве, чтобы убедиться, что он должным образом сообщается службе Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ee24c-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="ee24c-156">Настройка параметров прокси и Интернета</span><span class="sxs-lookup"><span data-stu-id="ee24c-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="ee24c-157">Включить связь с облачной службой Defender для конечной точки путем настройки параметров прокси-сервера и подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ee24c-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="ee24c-158">Устранение неполадок с бортовой проблемой</span><span class="sxs-lookup"><span data-stu-id="ee24c-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="ee24c-159">Узнайте об устранении проблем, которые могут возникнуть во время бортовой платы.</span><span class="sxs-lookup"><span data-stu-id="ee24c-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="ee24c-160">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ee24c-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ee24c-161">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ee24c-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)