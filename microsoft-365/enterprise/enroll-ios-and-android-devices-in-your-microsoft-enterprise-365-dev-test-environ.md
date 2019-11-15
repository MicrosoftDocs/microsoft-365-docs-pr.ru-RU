---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: 0d7e03d1dcc6e8f401258587c1dbc083b1237d49
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640381"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cb631-103">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb631-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cb631-104">Следуя инструкциям, приведенным в этой статье, вы сможете регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb631-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="cb631-106">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="cb631-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cb631-107">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cb631-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cb631-108">Если вы хотите, чтобы вы просто зарегистрировали устройства iOS и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cb631-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cb631-109">Если вы хотите зарегистрировать устройства с iOS и Android на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cb631-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb631-110">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="cb631-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cb631-111">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="cb631-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="cb631-112">Этап 2: регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="cb631-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="cb631-113">Сначала выполните инструкции в разделе [install и войдите в приложение корпоративного портала](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , чтобы настроить приложение корпоративного портала Microsoft Intune для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="cb631-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="cb631-114">Затем воспользуйтесь инструкциями в статье [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , чтобы зарегистрировать устройство для iOS.</span><span class="sxs-lookup"><span data-stu-id="cb631-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="cb631-115">Затем используйте инструкции, приведенные в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , чтобы зарегистрировать устройство с Android.</span><span class="sxs-lookup"><span data-stu-id="cb631-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="cb631-116">Этап 3: удаленное управление устройствами iOS и Android</span><span class="sxs-lookup"><span data-stu-id="cb631-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="cb631-117">Microsoft Intune предоставляет возможности удаленной блокировки и сброса секретного кода.</span><span class="sxs-lookup"><span data-stu-id="cb631-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="cb631-118">Если пользователь потеряет свое устройство, вы можете заблокировать это устройство удаленно.</span><span class="sxs-lookup"><span data-stu-id="cb631-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="cb631-119">Если кто-то забыл свой секретный код, его можно сбросить в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="cb631-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="cb631-120">Чтобы удаленно заблокировать устройство iOS или Android:</span><span class="sxs-lookup"><span data-stu-id="cb631-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="cb631-121">Войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cb631-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="cb631-122">Выберите **все службы**, введите **Intune**, а затем щелкните **Intune**.</span><span class="sxs-lookup"><span data-stu-id="cb631-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="cb631-123">Нажмите кнопку **устройства > все устройства**.</span><span class="sxs-lookup"><span data-stu-id="cb631-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="cb631-124">В списке устройств выберите устройство iOS или Android, а затем щелкните действие **Remote Lock** .</span><span class="sxs-lookup"><span data-stu-id="cb631-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="cb631-125">Чтобы удаленно сбросить секретный код, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cb631-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="cb631-126">При необходимости войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cb631-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="cb631-127">Выберите **все службы**, введите **Intune**, а затем щелкните **Intune**.</span><span class="sxs-lookup"><span data-stu-id="cb631-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="cb631-128">Нажмите кнопку **устройства > все устройства**.</span><span class="sxs-lookup"><span data-stu-id="cb631-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="cb631-129">В списке управляемых устройств щелкните устройство iOS или Android и выберите **... Дополнительные сведения**.</span><span class="sxs-lookup"><span data-stu-id="cb631-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="cb631-130">Затем выберите Удаленное действие **удалить секретный код** устройства.</span><span class="sxs-lookup"><span data-stu-id="cb631-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="cb631-131">Дополнительные эксперименты приведены в разделе [Доступные действия устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="cb631-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="cb631-132">Дальнейшее действие</span><span class="sxs-lookup"><span data-stu-id="cb631-132">Next step</span></span>

<span data-ttu-id="cb631-133">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="cb631-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb631-134">См. также</span><span class="sxs-lookup"><span data-stu-id="cb631-134">See Also</span></span>

[<span data-ttu-id="cb631-135">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cb631-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="cb631-136">Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cb631-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="cb631-137">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cb631-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

