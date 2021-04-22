---
title: Повышение соответствия базовому стандарту безопасности Microsoft Defender для конечной точки
description: Базовый уровень безопасности Microsoft Defender для конечной точки задает элементы управления безопасностью, чтобы обеспечить оптимальную защиту.
keywords: Управление intune, Microsoft Defender for Endpoint, Microsoft Defender, Microsoft Defender for Endpoint ASR, базовый уровень безопасности
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933605"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="36a3c-104">Повышение соответствия базовому стандарту безопасности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="36a3c-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="36a3c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="36a3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="36a3c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="36a3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="36a3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36a3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="36a3c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="36a3c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="36a3c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="36a3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="36a3c-110">Базовые уровни безопасности обеспечивают настройку функций безопасности в соответствии с рекомендациями экспертов по безопасности и администраторов системы Windows.</span><span class="sxs-lookup"><span data-stu-id="36a3c-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="36a3c-111">При развертывании базовый уровень безопасности Defender для конечной точки задает элементы управления безопасностью Defender for Endpoint для обеспечения оптимальной защиты.</span><span class="sxs-lookup"><span data-stu-id="36a3c-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="36a3c-112">Чтобы понять базовые показатели безопасности и их присвоение в Intune с помощью профилей конфигурации, ознакомьтесь [с этим часто задаваемым вопросам.](https://docs.microsoft.com/intune/security-baselines#q--a)</span><span class="sxs-lookup"><span data-stu-id="36a3c-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="36a3c-113">Перед развертыванием и отслеживанием соответствия базовым требованиям безопасности:</span><span class="sxs-lookup"><span data-stu-id="36a3c-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="36a3c-114">Регистрация устройств в управление Intune</span><span class="sxs-lookup"><span data-stu-id="36a3c-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="36a3c-115">Убедитесь, что у вас есть необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="36a3c-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="36a3c-116">Сравните базовые показатели безопасности Microsoft Defender для конечной точки и Windows Intune</span><span class="sxs-lookup"><span data-stu-id="36a3c-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="36a3c-117">Базовый уровень безопасности Windows Intune предоставляет полный набор рекомендуемых параметров, необходимых для безопасной настройки устройств под управлением Windows, включая параметры браузера, параметры PowerShell, а также параметры некоторых функций безопасности, таких как антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="36a3c-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="36a3c-118">В отличие от этого, в базовой версии Defender для конечной точки предусмотрены параметры, оптимизируют все элементы управления безопасностью в стеке Defender для конечной точки, включая параметры обнаружения конечных точек и ответа (EDR), а также параметры, также найденные в базовой версии безопасности Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="36a3c-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="36a3c-119">Дополнительные сведения о каждом базовом сценарии см. в.</span><span class="sxs-lookup"><span data-stu-id="36a3c-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="36a3c-120">Базовые параметры безопасности Windows для Intune</span><span class="sxs-lookup"><span data-stu-id="36a3c-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="36a3c-121">Базовые параметры Microsoft Defender для конечной точки для Intune</span><span class="sxs-lookup"><span data-stu-id="36a3c-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="36a3c-122">В идеале устройства, на борту с защитником для конечной точки, развернуты оба базовых плана: базовый уровень безопасности Windows Intune для первоначальной безопасности Windows, а затем базовый уровень безопасности Defender для конечной точки на уровне сверху, чтобы оптимально настроить элементы управления безопасностью Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="36a3c-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="36a3c-123">Чтобы воспользоваться последними данными о рисках и угрозах и свести к минимуму конфликты по мере развития базовых показателей, всегда применяйте новейшие версии базовых показателей во всех продуктах, как только они будут выпущены.</span><span class="sxs-lookup"><span data-stu-id="36a3c-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="36a3c-124">Базовый уровень безопасности Defender для конечной точки оптимизирован для физических устройств и в настоящее время не рекомендуется использовать для виртуальных машин (виртуальных машин) или конечных точек VDI.</span><span class="sxs-lookup"><span data-stu-id="36a3c-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="36a3c-125">Некоторые базовые параметры могут повлиять на удаленные интерактивные сеансы в виртуализированных средах.</span><span class="sxs-lookup"><span data-stu-id="36a3c-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="36a3c-126">Мониторинг соответствия базовому стандарту безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="36a3c-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="36a3c-127">**Базовая** карточка безопасности для управления конфигурацией устройств предоставляет обзор соответствия требованиям для устройств Windows 10, которые были назначены базовой базой безопасности Defender для конечной точки. [](configure-machines.md)</span><span class="sxs-lookup"><span data-stu-id="36a3c-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="36a3c-128">![Базовая карта безопасности](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="36a3c-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="36a3c-129">*Карта, показывающая соответствие базовому стандарту безопасности Defender для конечной точки*</span><span class="sxs-lookup"><span data-stu-id="36a3c-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="36a3c-130">Каждому устройству предоставляется один из следующих типов состояния:</span><span class="sxs-lookup"><span data-stu-id="36a3c-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="36a3c-131">**Соответствует базовому параметру**— параметры устройства соответствуют всем настройкам в базовой</span><span class="sxs-lookup"><span data-stu-id="36a3c-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="36a3c-132">**Не соответствует базовой линии**— по крайней мере один параметр устройства не соответствует базовому</span><span class="sxs-lookup"><span data-stu-id="36a3c-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="36a3c-133">**Неправильно настроенный**— по крайней мере один базовый параметр неправильно настроен на устройстве и находится в состоянии конфликта, ошибки или ожидания</span><span class="sxs-lookup"><span data-stu-id="36a3c-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="36a3c-134">**Не применимо**. По крайней мере один базовый параметр не применим на устройстве</span><span class="sxs-lookup"><span data-stu-id="36a3c-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="36a3c-135">Чтобы просмотреть конкретные устройства, выберите **Настройка базового уровня** безопасности на карте.</span><span class="sxs-lookup"><span data-stu-id="36a3c-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="36a3c-136">Это позволяет вам получить управление устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="36a3c-136">This takes you to Intune device management.</span></span> <span data-ttu-id="36a3c-137">Затем выберите **состояние устройства** для имен и статусов устройств.</span><span class="sxs-lookup"><span data-stu-id="36a3c-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="36a3c-138">Могут возникнуть расхождения в агрегированных данных, отображаемой на странице управления конфигурацией устройств, и данных, отображаемой на экранах обзоров в Intune.</span><span class="sxs-lookup"><span data-stu-id="36a3c-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="36a3c-139">Обзор и назначение базовой базы безопасности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="36a3c-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="36a3c-140">Управление конфигурацией устройств отслеживает базовое соответствие только устройствам Windows 10, которые были специально назначены базовой базой безопасности Microsoft Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="36a3c-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="36a3c-141">Вы можете удобно просмотреть базовый уровень и назначить его устройствам в управлении устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="36a3c-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="36a3c-142">Выберите **Настройка базовой базы безопасности** на базовой карте **безопасности,** чтобы перейти к управлению устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="36a3c-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="36a3c-143">Отображается аналогичный обзор базового соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="36a3c-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="36a3c-144">Кроме того, вы можете перейти к базовой линии безопасности Defender для конечной точки на портале Microsoft Azure из всех служб **> Intune >** безопасности устройств > базовых > базовых показателей ATP Защитника Microsoft .</span><span class="sxs-lookup"><span data-stu-id="36a3c-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="36a3c-145">Создайте новый профиль.</span><span class="sxs-lookup"><span data-stu-id="36a3c-145">Create a new profile.</span></span>

   <span data-ttu-id="36a3c-146">![Обзор базового обзора базовой безопасности Для Защитника Майкрософт для конечной точки в Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="36a3c-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="36a3c-147">*Обзор базового обзора базовой безопасности Для Защитника Майкрософт для конечной точки в Intune*</span><span class="sxs-lookup"><span data-stu-id="36a3c-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="36a3c-148">Во время создания профиля можно просмотреть и настроить определенные параметры в базовом варианте.</span><span class="sxs-lookup"><span data-stu-id="36a3c-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="36a3c-149">![Параметры базовой безопасности при создании профиля в Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="36a3c-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="36a3c-150">*Параметры базовой безопасности при создании профиля в Intune*</span><span class="sxs-lookup"><span data-stu-id="36a3c-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="36a3c-151">Назначьте профиль соответствующей группе устройств.</span><span class="sxs-lookup"><span data-stu-id="36a3c-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="36a3c-152">![Базовые профили безопасности в Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="36a3c-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="36a3c-153">*Назначение базового профиля безопасности в Intune*</span><span class="sxs-lookup"><span data-stu-id="36a3c-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="36a3c-154">Создайте профиль, чтобы сохранить его и развернуть его в назначенной группе устройств.</span><span class="sxs-lookup"><span data-stu-id="36a3c-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="36a3c-155">![Назначение базового уровня безопасности в Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="36a3c-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="36a3c-156">*Создание базового профиля безопасности в Intune*</span><span class="sxs-lookup"><span data-stu-id="36a3c-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="36a3c-157">Базовые показатели безопасности в Intune предоставляют удобный способ комплексной защиты и защиты устройств.</span><span class="sxs-lookup"><span data-stu-id="36a3c-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="36a3c-158">[Дополнительные данные о базовых уровнях безопасности в Intune.](https://docs.microsoft.com/intune/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="36a3c-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="36a3c-159">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="36a3c-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="36a3c-160">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="36a3c-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="36a3c-161">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="36a3c-161">Related topics</span></span>
- [<span data-ttu-id="36a3c-162">Убедитесь, что ваши устройства настроены правильно</span><span class="sxs-lookup"><span data-stu-id="36a3c-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="36a3c-163">Запись устройств в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="36a3c-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="36a3c-164">Оптимизация развертывания и обнаружений правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="36a3c-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
