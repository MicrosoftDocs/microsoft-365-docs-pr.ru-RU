---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487700"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1e54f-103">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1e54f-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="1e54f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1e54f-105">В этой статье описывается, как регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="1e54f-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="1e54f-106">Регистрация устройств iOS и Android в тестовой среде состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="1e54f-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="1e54f-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="1e54f-108">Этап 2: регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="1e54f-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="1e54f-109">Этап 3: удаленное управление устройствами iOS и Android</span><span class="sxs-lookup"><span data-stu-id="1e54f-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="1e54f-111">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="1e54f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1e54f-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1e54f-113">Если вы хотите подать заявку на устройства iOS и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1e54f-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1e54f-114">Если вы хотите зарегистрировать устройства с iOS и Android на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1e54f-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e54f-115">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1e54f-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1e54f-116">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное лицензирование и членство в группах, и вы можете поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="1e54f-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="1e54f-117">Этап 2: регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="1e54f-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="1e54f-118">Сначала выполните инструкции в разделе [install и войдите в приложение корпоративного портала](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , чтобы настроить приложение корпоративного портала Microsoft Intune для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1e54f-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="1e54f-119">Затем воспользуйтесь инструкциями в статье [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , чтобы зарегистрировать устройство для iOS.</span><span class="sxs-lookup"><span data-stu-id="1e54f-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="1e54f-120">Затем используйте инструкции, приведенные в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , чтобы зарегистрировать устройство с Android.</span><span class="sxs-lookup"><span data-stu-id="1e54f-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="1e54f-121">Этап 3: удаленное управление устройствами iOS и Android</span><span class="sxs-lookup"><span data-stu-id="1e54f-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="1e54f-122">Microsoft Intune предоставляет возможности удаленной блокировки и сброса секретного кода.</span><span class="sxs-lookup"><span data-stu-id="1e54f-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="1e54f-123">Если кто-то теряет свое устройство, вы можете удаленно заблокировать устройство.</span><span class="sxs-lookup"><span data-stu-id="1e54f-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="1e54f-124">Если кто-то забыл свой секретный код, вы можете удаленно сбросить его.</span><span class="sxs-lookup"><span data-stu-id="1e54f-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="1e54f-125">Чтобы удаленно заблокировать устройство iOS или Android, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e54f-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="1e54f-126">Войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="1e54f-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1e54f-127">На портале Azure введите **Intune** в поле поиска, а затем выберите **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1e54f-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="1e54f-128">Нажмите кнопку **устройства > все устройства**.</span><span class="sxs-lookup"><span data-stu-id="1e54f-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1e54f-129">В списке устройств выберите устройство iOS или Android, а затем выберите действие **Remote Lock** .</span><span class="sxs-lookup"><span data-stu-id="1e54f-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="1e54f-130">Чтобы удаленно сбросить секретный код, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1e54f-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="1e54f-131">При необходимости войдите на портал Azure по адресу, [https://portal.azure.com](https://portal.azure.com) используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="1e54f-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1e54f-132">На портале Azure введите **Intune** в поле поиска, а затем выберите **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1e54f-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="1e54f-133">Выберите **Devices**  >  **All Devices**(устройства).</span><span class="sxs-lookup"><span data-stu-id="1e54f-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="1e54f-134">В списке устройств, которыми вы управляете, выберите устройство для iOS или Android, выберите **... Дополнительно**, а затем выберите Удаленное действие **Удаление кода** для устройства.</span><span class="sxs-lookup"><span data-stu-id="1e54f-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="1e54f-135">Дополнительные эксперименты приведены в разделе [Доступные действия устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="1e54f-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="1e54f-136">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="1e54f-136">Next step</span></span>

<span data-ttu-id="1e54f-137">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="1e54f-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e54f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1e54f-138">See Also</span></span>

[<span data-ttu-id="1e54f-139">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="1e54f-140">Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="1e54f-141">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1e54f-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
