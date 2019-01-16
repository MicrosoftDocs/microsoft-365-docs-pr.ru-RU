---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: В этом документе Test Lab Guide используйте для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления.
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870576"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9af8d-103">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9af8d-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9af8d-104">Выполнив инструкции, приведенные в этой статье, вы сможете регистрация и проверка возможности управления базовой мобильного устройства для iOS и Android в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="9af8d-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="9af8d-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="9af8d-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9af8d-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="9af8d-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9af8d-108">Если необходимо зарегистрировать iOS и Android в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9af8d-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9af8d-109">Если необходимо зарегистрировать iOS и Android в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9af8d-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9af8d-p101">Тестирование автоматизирована лицензирования и членства в группе не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="9af8d-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="9af8d-112">Этап 2: Регистрация операций ввода-вывода и Android</span><span class="sxs-lookup"><span data-stu-id="9af8d-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="9af8d-113">Во-первых, используйте инструкции в [установки и войдите в приложение портала компании](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) для настройки приложения портала компании Майкрософт Intune для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="9af8d-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="9af8d-114">Затем используйте инструкции из статьи [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) для подачи заявок на устройстве операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="9af8d-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="9af8d-115">Затем используйте инструкции из статьи [Заявка Android устройство в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) возможность зачисления Android устройства.</span><span class="sxs-lookup"><span data-stu-id="9af8d-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="9af8d-116">Этап 3: IOS и Android удаленного управления</span><span class="sxs-lookup"><span data-stu-id="9af8d-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="9af8d-p102">Microsoft Intune предоставляет удаленного блокировки и код связи для сброса возможности. Если кто-то теряет свои устройства, можно заблокировать устройство удаленно. Если кто-то забудет их код связи, ее можно восстановить удаленно.</span><span class="sxs-lookup"><span data-stu-id="9af8d-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="9af8d-120">Чтобы заблокировать операций ввода-вывода или Android устройство удаленно:</span><span class="sxs-lookup"><span data-stu-id="9af8d-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="9af8d-121">Войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с использованием учетных данных учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9af8d-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9af8d-122">Выберите **все службы**, введите **Intune**и нажмите кнопку **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="9af8d-123">Нажмите кнопку **устройства > все устройства**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="9af8d-124">В списке устройств нажмите кнопку операций ввода-вывода или Android устройства и нажмите кнопку действие **удаленного блокировки** .</span><span class="sxs-lookup"><span data-stu-id="9af8d-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="9af8d-125">Чтобы удаленно сбросить секретный код, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9af8d-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="9af8d-126">При необходимости, войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с использованием учетных данных учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9af8d-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9af8d-127">Выберите **все службы**, введите **Intune**и нажмите кнопку **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="9af8d-128">Нажмите кнопку **устройства > все устройства**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="9af8d-p103">В списке устройств, управление, щелкните операций ввода-вывода или Android устройство и выберите **... Дополнительные**. Выберите действие удаленных устройств **Удалить секретный код** .</span><span class="sxs-lookup"><span data-stu-id="9af8d-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="9af8d-131">Дополнительные экспериментов в разделе [действия из доступных устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="9af8d-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="9af8d-132">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="9af8d-132">Next step</span></span>

<span data-ttu-id="9af8d-133">Изучите дополнительное [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="9af8d-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9af8d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9af8d-134">See Also</span></span>

[<span data-ttu-id="9af8d-135">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9af8d-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="9af8d-136">Политики соответствия устройства для вашего предприятия 365 Microsoft тестовой среды</span><span class="sxs-lookup"><span data-stu-id="9af8d-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="9af8d-137">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9af8d-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9af8d-138">Мобильные решения на предприятиях + безопасности (Командной)</span><span class="sxs-lookup"><span data-stu-id="9af8d-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
