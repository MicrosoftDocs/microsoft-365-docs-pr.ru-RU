---
title: Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования для добавления политик соответствия требованиям к устройствам Intune в тестовую среду Microsoft 365 для предприятий.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487416"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e3730-103">Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3730-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e3730-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="e3730-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e3730-105">В этой статье описывается, как добавить политику соответствия требованиям для устройств Intune для устройств с Windows 10 и приложений Microsoft 365 для предприятий в тестовую среду Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="e3730-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e3730-106">Добавление политики соответствия требованиям к устройствам Intune включает в себя два этапа:</span><span class="sxs-lookup"><span data-stu-id="e3730-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="e3730-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3730-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e3730-108">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3730-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e3730-110">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e3730-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e3730-111">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3730-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e3730-112">Если вы хотите настроить политики MAM только в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e3730-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e3730-113">Если вы хотите настроить политики MAM на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e3730-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3730-114">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e3730-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e3730-115">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="e3730-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="e3730-116">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3730-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="e3730-117">На этом этапе создайте политику соответствия требованиям устройств для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e3730-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="e3730-118">Перейдите в [центр администрирования microsoft 365](https://admin.microsoft.com) и войдите в свою подписку на тестовую лаборатория Microsoft 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e3730-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="e3730-119">На новой вкладке браузера откройте портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="e3730-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="e3730-120">В поле поиска на портале Azure введите **Intune**, а затем выберите **Intune**.</span><span class="sxs-lookup"><span data-stu-id="e3730-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="e3730-121">Если вы видите, что в области **Microsoft Intune** вы еще **не включили сообщение Управление устройствами** , выберите его.</span><span class="sxs-lookup"><span data-stu-id="e3730-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="e3730-122">В области **центр управления мобильными устройствами** выберите пункт **Intune MDM Authority**, а затем нажмите **кнопку Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="e3730-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="e3730-123">Обновите вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="e3730-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="e3730-124">В области навигации слева выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="e3730-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="e3730-125">В области **группы — все группы** выберите пункт **+ Новая группа**.</span><span class="sxs-lookup"><span data-stu-id="e3730-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="e3730-126">В области **Группа** выберите **Microsoft 365** или **Безопасность** для **типа группы?**, введите " **управляемые пользователи устройств Windows 10** " в поле **имя**, выберите **назначено** в **поле Тип участия**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="e3730-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="e3730-127">Выберите **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="e3730-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="e3730-128">В области **Microsoft Intune** в списке **быстрые задачи** выберите **создать политику соответствия**.</span><span class="sxs-lookup"><span data-stu-id="e3730-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="e3730-129">В области **Профили политики соответствия** выберите **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="e3730-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="e3730-130">В области **Создание политики** в поле **имя**введите **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="e3730-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="e3730-131">На **платформе**выберите **Windows 10 и более поздних версий**, нажмите **кнопку ОК** в области **политика соответствия требованиям Windows 10** , а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="e3730-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="e3730-132">Выберите **Профили политики соответствия**, а затем выберите имя политики **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="e3730-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="e3730-133">В области **Windows 10** выберите пункт **назначения**, а затем выберите **пункт Выбрать группы для включения**.</span><span class="sxs-lookup"><span data-stu-id="e3730-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="e3730-134">В области **Выбор групп для включения** выберите группу **управляемые пользователи устройств Windows 10** и нажмите **кнопку Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="e3730-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="e3730-135">Нажмите кнопку **сохранить**, выберите **Microsoft Intune — обзор**, а затем выберите **клиентские приложения** на панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="e3730-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="e3730-136">В области **клиентские приложения** выберите **приложения**и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="e3730-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="e3730-137">В области **Добавление приложения** выберите **Тип приложения**, а затем выберите **Windows 10** в разделе **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="e3730-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="e3730-138">В области **Добавление приложения** выберите **сведения о наборе приложений**.</span><span class="sxs-lookup"><span data-stu-id="e3730-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="e3730-139">В области **сведений о пакете приложений** введите **Microsoft 365 Apps для предприятий** в разделе **имя набора** и **Описание набора**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3730-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="e3730-140">В области **Добавление приложения** выберите пункт **Настройка набора приложений**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3730-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="e3730-141">В области **Добавление приложения** выберите **параметры набора приложений**.</span><span class="sxs-lookup"><span data-stu-id="e3730-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="e3730-142">В качестве **канала обновления**выберите **полугодовой корпоративный выпуск**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3730-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="e3730-143">В области **Добавление приложения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e3730-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="e3730-144">Теперь у вас есть политика соответствия требованиям устройств для тестирования выбранных приложений в политике соответствия требованиям устройств для **Windows 10** и для членов группы **управляемых пользователей устройств Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="e3730-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="e3730-145">Обратите внимание, что при выборе параметра **Microsoft 365** в качестве типа группы создаются дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="e3730-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e3730-146">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e3730-146">Next step</span></span>

<span data-ttu-id="e3730-147">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="e3730-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3730-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e3730-148">See also</span></span>

<span data-ttu-id="e3730-149">[Microsoft 365 для корпоративных руководств по лаборатории тестирования](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="e3730-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="e3730-150">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3730-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="e3730-151">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3730-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e3730-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="e3730-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
