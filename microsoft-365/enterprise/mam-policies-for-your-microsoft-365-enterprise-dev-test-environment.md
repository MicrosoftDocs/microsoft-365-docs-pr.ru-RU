---
title: Политики соответствия требованиям к устройствам для Microsoft 365 для корпоративной тестовой среды
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по тестовой лаборатории, чтобы добавить политики соответствия требованиям к устройствам Intune в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367099"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="88497-103">Политики соответствия требованиям к устройствам для Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="88497-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="88497-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="88497-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="88497-105">В этой статье описывается, как добавить политику соответствия требованиям устройств Intune для Windows 10 устройств и Приложения Microsoft 365 для предприятий в Microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="88497-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="88497-106">Добавление политики соответствия требованиям устройств Intune включает два этапа:</span><span class="sxs-lookup"><span data-stu-id="88497-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="88497-107">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="88497-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="88497-108">Этап 2. Создание политики соответствия требованиям устройств для Windows 10 устройств</span><span class="sxs-lookup"><span data-stu-id="88497-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="88497-110">Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="88497-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="88497-111">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="88497-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="88497-112">Если вы хотите настроить политики MAM только легким способом с минимальными требованиями, следуйте инструкциям в [легкой базовой конфигурации.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="88497-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="88497-113">Если вы хотите настроить политики MAM в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="88497-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="88497-114">Для тестирования автоматического лицензирования и членства в группах не требуется смоделированная тестовая среда предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="88497-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="88497-115">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет собой типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="88497-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="88497-116">Этап 2. Создание политики соответствия требованиям устройств для Windows 10 устройств</span><span class="sxs-lookup"><span data-stu-id="88497-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="88497-117">На этом этапе создается политика соответствия требованиям для Windows 10 устройств.</span><span class="sxs-lookup"><span data-stu-id="88497-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="88497-118">На этом этапе Microsoft Intune и [центр администрирования Microsoft Endpoint Manager для](https://go.microsoft.com/fwlink/?linkid=2109431) добавления группы и создания политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="88497-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="88497-119">Перейдите в [центр администрирования Microsoft 365](https://admin.microsoft.com)и войдите в свою Microsoft 365 тестовую лабораторную подписку с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="88497-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="88497-120">Выберите центр **Endpoint Manager** администратора.</span><span class="sxs-lookup"><span data-stu-id="88497-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="88497-121">Открывается [Endpoint Manager центр](https://go.microsoft.com/fwlink/?linkid=2109431) администрирования.</span><span class="sxs-lookup"><span data-stu-id="88497-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="88497-122">Если сообщение, аналогичное **you haven't enabled device management,** еще не отображается, выберите Intune в качестве органа MDM.</span><span class="sxs-lookup"><span data-stu-id="88497-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="88497-123">Для определенных действий [см. в приложении Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="88497-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="88497-124">Центр администрирования Endpoint Manager фокусируется на управлении устройствами и управлении приложениями.</span><span class="sxs-lookup"><span data-stu-id="88497-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="88497-125">Для экскурсии по этому центру администрирования [см. в учебнике: Walkthrough Intune в Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="88497-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="88497-126">В **Группах** добавьте новую группу **Microsoft 365** или группу безопасности с Windows 10 пользователями устройств **с** **присвоенным типом** членства. </span><span class="sxs-lookup"><span data-stu-id="88497-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="88497-127">На следующих действиях вы назначите эту группу политику соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="88497-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="88497-128">Для определенных действий и сведений  о группах **Microsoft 365** или группах безопасности см. в добавлении групп [для организации пользователей и устройств.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="88497-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="88497-129">В **Устройствах** создайте политику Windows 10 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="88497-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="88497-130">Назначьте эту политику группе **пользователей управляемых Windows 10 устройств,** созданной вами.</span><span class="sxs-lookup"><span data-stu-id="88497-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="88497-131">В своей политике можно блокировать простые пароли, требовать брандмауэра, требовать запуска службы microsoft Defender Antimalware и других.</span><span class="sxs-lookup"><span data-stu-id="88497-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="88497-132">Политика соответствия требованиям обычно включает базовые параметры или минимальный минимум, который должен иметь каждое устройство.</span><span class="sxs-lookup"><span data-stu-id="88497-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="88497-133">Для определенных действий и сведений о доступных параметрах соответствия требованиям см. в статью Использование политик соответствия требованиям для установки правил для управляемых [устройств.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="88497-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="88497-134">По завершению у вас есть политика соответствия требованиям для устройств для тестирования участников в группе **Windows 10 пользователей устройств.**</span><span class="sxs-lookup"><span data-stu-id="88497-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="88497-135">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="88497-135">Next step</span></span>

<span data-ttu-id="88497-136">Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#mobile-device-management) и возможностями управления мобильными устройствами в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="88497-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="88497-137">См. также</span><span class="sxs-lookup"><span data-stu-id="88497-137">See also</span></span>

<span data-ttu-id="88497-138">[Microsoft 365 для руководства лаборатории](m365-enterprise-test-lab-guides.md)тестирования предприятия .</span><span class="sxs-lookup"><span data-stu-id="88497-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="88497-139">Регистрация устройств iOS и Android в Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="88497-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="88497-140">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="88497-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="88497-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="88497-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
