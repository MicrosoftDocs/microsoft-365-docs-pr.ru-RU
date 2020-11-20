---
title: Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий
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
description: Используйте это руководство по лаборатории тестирования для добавления политик соответствия требованиям к устройствам Intune в тестовую среду Microsoft 365 для предприятий.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367099"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="40022-103">Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="40022-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="40022-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="40022-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="40022-105">В этой статье описывается, как добавить политику соответствия требованиям для устройств Intune для устройств с Windows 10 и приложений Microsoft 365 для предприятий в тестовую среду Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="40022-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="40022-106">Добавление политики соответствия требованиям к устройствам Intune включает в себя два этапа:</span><span class="sxs-lookup"><span data-stu-id="40022-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="40022-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="40022-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="40022-108">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="40022-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="40022-110">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="40022-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="40022-111">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="40022-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="40022-112">Если вы хотите настроить политики MAM только в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="40022-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="40022-113">Если вы хотите настроить политики MAM на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="40022-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="40022-114">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="40022-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="40022-115">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="40022-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="40022-116">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="40022-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="40022-117">На этом этапе создается политика соответствия требованиям устройств для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="40022-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="40022-118">На этом этапе для добавления группы используется Microsoft Intune и [центр администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , а также создается политика соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="40022-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="40022-119">Перейдите в [центр администрирования microsoft 365](https://admin.microsoft.com)и войдите в свою подписку на тестовую лаборатория Microsoft 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="40022-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="40022-120">Выберите центр администрирования **диспетчера конечных точек** .</span><span class="sxs-lookup"><span data-stu-id="40022-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="40022-121">Откроется [центр администрирования диспетчера конечных точек](https://go.microsoft.com/fwlink/?linkid=2109431) .</span><span class="sxs-lookup"><span data-stu-id="40022-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="40022-122">Если сообщение, похожее на " **Управление устройствами" не включено** , отображается сообщение, выберите Intune в качестве администратора MDM.</span><span class="sxs-lookup"><span data-stu-id="40022-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="40022-123">Конкретные действия приведены [в разделе Установка центра управления мобильными устройствами](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="40022-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="40022-124">Центр администрирования диспетчера конечных точек посвящен управлению устройствами и управлению приложениями.</span><span class="sxs-lookup"><span data-stu-id="40022-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="40022-125">Обзор этого центра администрирования приведен [в разделе Tutorial: пошаговое руководство Intune в диспетчере конечных точек Майкрософт](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="40022-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="40022-126">В **группы** добавьте новую группу **Microsoft 365** или группу **безопасности** с именем " **управляемые пользователи устройств Windows 10**" с **назначенным** типом членства.</span><span class="sxs-lookup"><span data-stu-id="40022-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="40022-127">На следующих этапах вы назначите политику соответствия требованиям для этой группы.</span><span class="sxs-lookup"><span data-stu-id="40022-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="40022-128">Конкретные действия и сведения о **Microsoft 365** или группах **безопасности** содержатся в разделе [Добавление групп для организации пользователей и устройств](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="40022-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="40022-129">В окне **устройства** создайте политику соответствия требованиям Windows 10.</span><span class="sxs-lookup"><span data-stu-id="40022-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="40022-130">Назначьте эту политику для созданной **управляемой группы пользователей устройств с Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="40022-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="40022-131">В политике можно заблокировать простые пароли, для них требуется брандмауэр, необходимо запустить службу антивредоносной программы защитника Майкрософт и т. д.</span><span class="sxs-lookup"><span data-stu-id="40022-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="40022-132">Политика соответствия требованиям обычно включает базовые параметры или значение по крайней мере, которое должно иметь каждое устройство.</span><span class="sxs-lookup"><span data-stu-id="40022-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="40022-133">Конкретные действия и сведения о доступных параметрах соответствия, которые можно настроить, приведены в разделе [Использование политик соответствия для установки правил для управляемых устройств](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="40022-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="40022-134">По завершении у вас есть политика соответствия требованиям устройств для тестирования членов в группе **управляемых пользователей устройств Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="40022-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="40022-135">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="40022-135">Next step</span></span>

<span data-ttu-id="40022-136">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="40022-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="40022-137">См. также</span><span class="sxs-lookup"><span data-stu-id="40022-137">See also</span></span>

<span data-ttu-id="40022-138">[Microsoft 365 для корпоративных руководств по лаборатории тестирования](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="40022-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="40022-139">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="40022-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="40022-140">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="40022-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="40022-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="40022-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
