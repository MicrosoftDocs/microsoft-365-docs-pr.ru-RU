---
title: Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный
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
description: Используйте это руководство по лаборатории тестирования для добавления политик соответствия требованиям к устройствам Intune в тестовую среду Microsoft 365 Enterprise.
ms.openlocfilehash: 4324ccca761e504812edc210ee6b6abdc484b670
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631589"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36bd0-103">Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36bd0-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36bd0-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="36bd0-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="36bd0-105">С помощью инструкций, описанных в этой статье, вы добавите политику соответствия требованиям для устройств Intune для устройств Windows 10 и приложений Microsoft 365 для предприятий в тестовую среду Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36bd0-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="36bd0-107">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="36bd0-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36bd0-108">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36bd0-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36bd0-109">Если вы хотите просто настроить политики MAM в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="36bd0-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="36bd0-110">Если вы хотите настроить политики MAM на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="36bd0-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36bd0-111">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="36bd0-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="36bd0-112">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="36bd0-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="36bd0-113">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="36bd0-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="36bd0-114">На этом этапе создается политика соответствия требованиям устройств для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="36bd0-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="36bd0-115">Перейдите на портал Office 365 по адресу[https://portal.office.com](https://portal.office.com)() и войдите в свою подписку на тестовую лаборатория Office 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="36bd0-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="36bd0-116">На новой вкладке браузера откройте портал Azure по адресу [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="36bd0-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="36bd0-117">На вкладке портал Azure в браузере введите **Intune** в поле поиска, а затем щелкните **Intune**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="36bd0-118">Если вы видите **вы еще не включили** в области **Microsoft Intune** сообщение "Управление устройствами еще", щелкните его.</span><span class="sxs-lookup"><span data-stu-id="36bd0-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="36bd0-119">В области **центр управления мобильными устройствами** щелкните **Intune MDM Authority**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="36bd0-120">Обновите вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="36bd0-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="36bd0-121">В левой области навигации нажмите **Группы**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="36bd0-122">В области **группы — все группы** нажмите кнопку **+ создать группу**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="36bd0-123">В области **Группа** выберите **Office 365** или **Безопасность** для **типа группы?**, введите " **управляемые пользователи устройств Windows 10** " в поле **имя**, выберите **назначено** в **поле Тип участия**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="36bd0-124">Выберите **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="36bd0-125">В области **Microsoft Intune** в списке **быстрые задачи** щелкните **создать политику соответствия**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="36bd0-126">В области **Профили политики соответствия** нажмите кнопку **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="36bd0-127">В области **Создание политики** в поле **имя**введите **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="36bd0-128">В разделе **платформа**выберите **Windows 10 и более поздние версии**, нажмите кнопку **ОК** в области **политика соответствия требованиям Windows 10** , а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="36bd0-129">Щелкните **Профили политики соответствия требованиям**, а затем выберите имя политики **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="36bd0-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="36bd0-130">В области **Windows 10** нажмите кнопку **назначения**, а затем выберите пункт **выбрать группы для включения**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="36bd0-131">В области **Выбор групп для включения** выберите группу **управляемые пользователи устройств Windows 10** и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="36bd0-132">Нажмите кнопку **сохранить**, выберите **Microsoft Intune — обзор**, а затем щелкните **клиентские приложения** на панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="36bd0-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="36bd0-133">В области **клиентские приложения** выберите пункт **приложения**и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="36bd0-134">В области **Добавление приложения** выберите **Тип приложения**, а затем выберите **Windows 10** в разделе **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="36bd0-135">В области **Добавление приложения** выберите **сведения о наборе приложений**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="36bd0-136">В области **сведений о пакете приложений** введите **Microsoft 365 Apps для предприятий** в разделе **имя набора** и **Описание набора**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="36bd0-137">Нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="36bd0-137">Click OK.</span></span>

19. <span data-ttu-id="36bd0-138">В области **Добавление приложения** выберите пункт **Настройка набора приложений**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="36bd0-139">В области **Добавление приложения** выберите **параметры набора приложений**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="36bd0-140">В качестве **канала обновления**выберите **полугодие**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="36bd0-141">В области **Добавление приложения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="36bd0-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="36bd0-142">Теперь у вас есть политика соответствия требованиям устройств для тестирования выбранных приложений в политике соответствия требованиям устройств для **Windows 10** и для членов группы **управляемых пользователей устройств Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="36bd0-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="36bd0-143">Обратите внимание, что при выборе пункта Office 365 в качестве типа группы будут созданы дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="36bd0-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="36bd0-144">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="36bd0-144">Next step</span></span>

<span data-ttu-id="36bd0-145">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="36bd0-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="36bd0-146">См. также</span><span class="sxs-lookup"><span data-stu-id="36bd0-146">See also</span></span>

<span data-ttu-id="36bd0-147">[Руководства по лаборатории тестирования для Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="36bd0-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="36bd0-148">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36bd0-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="36bd0-149">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36bd0-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="36bd0-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="36bd0-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
