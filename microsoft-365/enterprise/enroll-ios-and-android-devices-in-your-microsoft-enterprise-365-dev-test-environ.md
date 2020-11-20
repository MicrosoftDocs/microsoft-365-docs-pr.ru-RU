---
title: Регистрация устройств iOS/Ипадос и Android в тестовой среде Microsoft 365 для предприятий
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
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367087"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="386cf-103">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="386cf-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="386cf-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="386cf-105">В этой статье описывается, как регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств iOS/Ипадос и Android в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="386cf-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="386cf-106">Регистрация устройств iOS/Ипадос и Android в тестовой среде состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="386cf-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="386cf-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="386cf-108">Этап 2: регистрация устройств iOS/Ипадос и Android</span><span class="sxs-lookup"><span data-stu-id="386cf-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="386cf-109">Этап 3: удаленное управление устройствами iOS и Ипадос и Android</span><span class="sxs-lookup"><span data-stu-id="386cf-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="386cf-111">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="386cf-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="386cf-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="386cf-113">Если вы хотите подать заявку на устройства iOS/Ипадос и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="386cf-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="386cf-114">Если вы хотите зарегистрировать устройства iOS/Ипадос и Android на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="386cf-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="386cf-115">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="386cf-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="386cf-116">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное лицензирование и членство в группах, и вы можете поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="386cf-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="386cf-117">Этап 2: регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="386cf-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="386cf-118">Если вы просматриваете решение по управлению мобильными устройствами (MDM) для управления устройствами, вы можете использовать Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="386cf-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="386cf-119">При работе с каким бы то ни было поставщиком MDM, включая Intune, устройства "зарегистрированы".</span><span class="sxs-lookup"><span data-stu-id="386cf-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="386cf-120">При регистрации они получают функции и параметры, которые вы настроили.</span><span class="sxs-lookup"><span data-stu-id="386cf-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="386cf-121">В Intune существует несколько способов регистрации устройств iOS/Ипадос и Android.</span><span class="sxs-lookup"><span data-stu-id="386cf-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="386cf-122">Вы можете выбрать вариант регистрации, который лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="386cf-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="386cf-123">Дополнительные сведения и рекомендации представлены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="386cf-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="386cf-124">Руководство по развертыванию: регистрация устройств с iOS и Ипадос в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="386cf-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="386cf-125">Руководство по развертыванию: регистрация устройств с Android в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="386cf-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="386cf-126">Если вы готовы использовать Intune для управления устройствами и хотите получить некоторые рекомендации, то следующие сведения могут помочь:</span><span class="sxs-lookup"><span data-stu-id="386cf-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="386cf-127">Общие сведения об управлении устройствами</span><span class="sxs-lookup"><span data-stu-id="386cf-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="386cf-128">Руководство: пошаговое руководство Intune в диспетчере конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="386cf-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="386cf-129">Руководство по развертыванию: Настройка или переход в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="386cf-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="386cf-130">Этап 3: удаленное управление устройствами iOS и Android</span><span class="sxs-lookup"><span data-stu-id="386cf-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="386cf-131">Microsoft Intune обеспечивает функцию удаленной блокировки и сброса секретного кода.</span><span class="sxs-lookup"><span data-stu-id="386cf-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="386cf-132">Если кто-то теряет свое устройство, вы можете удаленно заблокировать устройство.</span><span class="sxs-lookup"><span data-stu-id="386cf-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="386cf-133">Если кто-то забыл свой секретный код, вы можете удаленно сбросить его.</span><span class="sxs-lookup"><span data-stu-id="386cf-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="386cf-134">Чтобы удаленно заблокировать устройство iOS/Ипадос или Android, ознакомьтесь [со статьей Удаленная блокировка устройств с помощью Intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="386cf-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="386cf-135">Чтобы удаленно сбросить секретный код, ознакомьтесь со статьей [Сброс или Удаление секретного кода устройства в Intune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="386cf-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="386cf-136">Дополнительные задачи, которые можно запускать удаленно, приведены в разделе [Доступные действия устройств](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="386cf-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="386cf-137">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="386cf-137">Next step</span></span>

<span data-ttu-id="386cf-138">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="386cf-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="386cf-139">См. также</span><span class="sxs-lookup"><span data-stu-id="386cf-139">See Also</span></span>

[<span data-ttu-id="386cf-140">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="386cf-141">Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="386cf-142">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="386cf-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
