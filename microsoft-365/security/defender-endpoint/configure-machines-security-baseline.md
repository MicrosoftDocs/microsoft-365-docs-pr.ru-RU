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
ms.openlocfilehash: a5f3d2de452a8a1ab201f558b93d45dfa6ded3e6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841550"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="17dda-104">Повышение соответствия базовому стандарту безопасности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="17dda-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17dda-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="17dda-105">**Applies to:**</span></span>
- [<span data-ttu-id="17dda-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="17dda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="17dda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17dda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="17dda-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="17dda-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17dda-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="17dda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="17dda-110">Базовые уровни безопасности обеспечивают настройку функций безопасности в соответствии с рекомендациями экспертов по безопасности и Windows системных администраторов.</span><span class="sxs-lookup"><span data-stu-id="17dda-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="17dda-111">При развертывании базовый уровень безопасности Defender для конечной точки задает элементы управления безопасностью Defender for Endpoint для обеспечения оптимальной защиты.</span><span class="sxs-lookup"><span data-stu-id="17dda-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="17dda-112">Чтобы понять базовые показатели безопасности и их присвоение в Intune с помощью профилей конфигурации, ознакомьтесь [с этим часто задаваемым вопросам.](/intune/security-baselines#q--a)</span><span class="sxs-lookup"><span data-stu-id="17dda-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="17dda-113">Перед развертыванием и отслеживанием соответствия базовым требованиям безопасности:</span><span class="sxs-lookup"><span data-stu-id="17dda-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="17dda-114">Регистрация устройств в управление Intune</span><span class="sxs-lookup"><span data-stu-id="17dda-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="17dda-115">Убедитесь, что у вас есть необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="17dda-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="17dda-116">Сравнение базовых показателей безопасности Microsoft Defender для конечной точки и Windows Intune</span><span class="sxs-lookup"><span data-stu-id="17dda-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="17dda-117">Базовая линия безопасности Windows Intune содержит полный набор рекомендуемых параметров, необходимых для безопасной настройки устройств, работающих Windows, включая параметры браузера, параметры PowerShell, а также параметры некоторых функций безопасности, таких как антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="17dda-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="17dda-118">В отличие от этого базовый параметр Defender for Endpoint предоставляет параметры, оптимизируют все элементы управления безопасностью в стеке Defender для конечной точки, включая параметры для обнаружение и нейтрализация атак на конечные точки (EDR), а также параметры, также найденные в базовой линии безопасности Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="17dda-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="17dda-119">Дополнительные сведения о каждом базовом сценарии см. в.</span><span class="sxs-lookup"><span data-stu-id="17dda-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="17dda-120">Windows базовые параметры безопасности для Intune</span><span class="sxs-lookup"><span data-stu-id="17dda-120">Windows security baseline settings for Intune</span></span>](/intune/security-baseline-settings-windows)
- [<span data-ttu-id="17dda-121">Базовые параметры Microsoft Defender для конечной точки для Intune</span><span class="sxs-lookup"><span data-stu-id="17dda-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="17dda-122">В идеале для устройств, на борту в Defender для конечной точки, развернуты оба базовых плана: базовый уровень безопасности Windows Intune для первоначальной безопасности Windows, а затем базовый уровень безопасности Defender для конечной точки на уровне сверху, чтобы оптимально настроить элементы управления безопасностью Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="17dda-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="17dda-123">Чтобы воспользоваться последними данными о рисках и угрозах и свести к минимуму конфликты по мере развития базовых показателей, всегда применяйте новейшие версии базовых показателей во всех продуктах, как только они будут выпущены.</span><span class="sxs-lookup"><span data-stu-id="17dda-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="17dda-124">Базовый уровень безопасности Defender для конечной точки оптимизирован для физических устройств и в настоящее время не рекомендуется использовать для виртуальных машин (виртуальных машин) или конечных точек VDI.</span><span class="sxs-lookup"><span data-stu-id="17dda-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="17dda-125">Некоторые базовые параметры могут повлиять на удаленные интерактивные сеансы в виртуализированных средах.</span><span class="sxs-lookup"><span data-stu-id="17dda-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="17dda-126">Мониторинг соответствия базовому стандарту безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="17dda-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="17dda-127">**Базовая** карточка безопасности в управлении конфигурацией устройств предоставляет обзор соответствия требованиям для Windows 10 устройств, которые были назначены базовой базой безопасности Defender для конечной точки. [](configure-machines.md)</span><span class="sxs-lookup"><span data-stu-id="17dda-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="17dda-128">![Базовая карта безопасности](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="17dda-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="17dda-129">*Карта, показывающая соответствие базовому стандарту безопасности Defender для конечной точки*</span><span class="sxs-lookup"><span data-stu-id="17dda-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="17dda-130">Каждому устройству предоставляется один из следующих типов состояния:</span><span class="sxs-lookup"><span data-stu-id="17dda-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="17dda-131">**Соответствует базовому параметру**— параметры устройства соответствуют всем настройкам в базовой</span><span class="sxs-lookup"><span data-stu-id="17dda-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="17dda-132">**Не соответствует базовой линии**— по крайней мере один параметр устройства не соответствует базовому</span><span class="sxs-lookup"><span data-stu-id="17dda-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="17dda-133">**Неправильно настроенный**— по крайней мере один базовый параметр неправильно настроен на устройстве и находится в состоянии конфликта, ошибки или ожидания</span><span class="sxs-lookup"><span data-stu-id="17dda-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="17dda-134">**Не применимо**. По крайней мере один базовый параметр не применим на устройстве</span><span class="sxs-lookup"><span data-stu-id="17dda-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="17dda-135">Чтобы просмотреть конкретные устройства, выберите **Настройка базового уровня** безопасности на карте.</span><span class="sxs-lookup"><span data-stu-id="17dda-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="17dda-136">Это позволяет вам получить управление устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="17dda-136">This takes you to Intune device management.</span></span> <span data-ttu-id="17dda-137">Затем выберите **состояние устройства** для имен и статусов устройств.</span><span class="sxs-lookup"><span data-stu-id="17dda-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="17dda-138">Могут возникнуть расхождения в агрегированных данных, отображаемой на странице управления конфигурацией устройств, и данных, отображаемой на экранах обзоров в Intune.</span><span class="sxs-lookup"><span data-stu-id="17dda-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="17dda-139">Обзор и назначение базовой базы безопасности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="17dda-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="17dda-140">Управление конфигурацией устройств отслеживает базовое соответствие только Windows 10 устройств, которые были специально назначены базовой базой безопасности Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="17dda-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="17dda-141">Вы можете удобно просмотреть базовый уровень и назначить его устройствам в управлении устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="17dda-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="17dda-142">Выберите **Настройка базовой базы безопасности** на базовой карте **безопасности,** чтобы перейти к управлению устройствами Intune.</span><span class="sxs-lookup"><span data-stu-id="17dda-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="17dda-143">Отображается аналогичный обзор базового соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="17dda-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="17dda-144">Кроме того, вы можете перейти к базовой линии безопасности Defender для конечной точки на портале Microsoft Azure из всех служб **> Intune >** устройства > базовые > ATP в Защитнике Microsoft базовые > ATP в Защитнике Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17dda-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="17dda-145">Создайте новый профиль.</span><span class="sxs-lookup"><span data-stu-id="17dda-145">Create a new profile.</span></span>

   <span data-ttu-id="17dda-146">![Обзор базового обзора базовой безопасности Для Защитника Майкрософт для конечной точки в Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="17dda-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="17dda-147">*Обзор базового обзора базовой безопасности Для Защитника Майкрософт для конечной точки в Intune*</span><span class="sxs-lookup"><span data-stu-id="17dda-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="17dda-148">Во время создания профиля можно просмотреть и настроить определенные параметры в базовом варианте.</span><span class="sxs-lookup"><span data-stu-id="17dda-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="17dda-149">![Параметры базовой безопасности при создании профиля в Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="17dda-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="17dda-150">*Параметры базовой безопасности при создании профиля в Intune*</span><span class="sxs-lookup"><span data-stu-id="17dda-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="17dda-151">Назначьте профиль соответствующей группе устройств.</span><span class="sxs-lookup"><span data-stu-id="17dda-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="17dda-152">![Базовые профили безопасности в Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="17dda-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="17dda-153">*Назначение базового профиля безопасности в Intune*</span><span class="sxs-lookup"><span data-stu-id="17dda-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="17dda-154">Создайте профиль, чтобы сохранить его и развернуть его в назначенной группе устройств.</span><span class="sxs-lookup"><span data-stu-id="17dda-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="17dda-155">![Назначение базового уровня безопасности в Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="17dda-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="17dda-156">*Создание базового профиля безопасности в Intune*</span><span class="sxs-lookup"><span data-stu-id="17dda-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="17dda-157">Базовые показатели безопасности в Intune предоставляют удобный способ комплексной защиты и защиты устройств.</span><span class="sxs-lookup"><span data-stu-id="17dda-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="17dda-158">[Дополнительные данные о базовых уровнях безопасности в Intune.](/intune/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="17dda-158">[Learn more about security baselines on Intune](/intune/security-baselines).</span></span>

><span data-ttu-id="17dda-159">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="17dda-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17dda-160">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="17dda-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="17dda-161">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="17dda-161">Related topics</span></span>
- [<span data-ttu-id="17dda-162">Убедитесь, что ваши устройства настроены правильно</span><span class="sxs-lookup"><span data-stu-id="17dda-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="17dda-163">Запись устройств в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="17dda-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="17dda-164">Оптимизация развертывания и обнаружений правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="17dda-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
