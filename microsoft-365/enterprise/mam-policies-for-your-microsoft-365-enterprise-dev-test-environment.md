---
title: Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования для добавления политик соответствия требованиям к устройствам Intune в тестовую среду Microsoft 365 Enterprise.
ms.openlocfilehash: eb140844eba4bc5cf5eba7fe452345f251ced0ff
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072119"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="12009-103">Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="12009-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="12009-104">С помощью инструкций, описанных в этой статье, вы добавите политику соответствия требованиям для устройств Intune в тестовую среду Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="12009-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="12009-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="12009-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="12009-107">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12009-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="12009-108">Если вы хотите просто настроить политики MAM в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="12009-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="12009-109">Если вы хотите настроить политики MAM на имитации предприятия, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="12009-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="12009-110">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="12009-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="12009-111">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="12009-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="12009-112">Этап 2: Создание политики соответствия требованиям устройств для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="12009-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="12009-113">На этом этапе создается политика соответствия требованиям устройств для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="12009-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="12009-114">Перейдите на портал Office 365 по адресу[https://portal.office.com](https://portal.office.com)() и войдите в свою подписку на тестовую лаборатория Office 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="12009-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="12009-115">На новой вкладке браузера откройте портал Azure по адресу [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="12009-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="12009-116">На вкладке портал Azure в браузере в области навигации щелкните **все службы**, введите **Intune**, а затем щелкните **Intune**.</span><span class="sxs-lookup"><span data-stu-id="12009-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="12009-117">Если вы видите, что в колонке **Microsoft Intune** вы еще **не включили сообщение Управление устройствами** , щелкните его.</span><span class="sxs-lookup"><span data-stu-id="12009-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="12009-118">В колонке **центр управления мобильными устройствами** щелкните **Intune MDM Authority**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="12009-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="12009-119">Обновите вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="12009-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="12009-120">В левой области навигации нажмите **Группы**.</span><span class="sxs-lookup"><span data-stu-id="12009-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="12009-121">В колонке **группы — все группы** выберите пункт **+ Новая группа**.</span><span class="sxs-lookup"><span data-stu-id="12009-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="12009-122">В колонке **Группа** выберите **Office 365** или **Безопасность** для **типа группы?**, введите " **управляемые пользователи устройств Windows 10** " в поле **имя**, выберите **назначено** в **поле Тип участия**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="12009-122">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="12009-123">Закройте вкладку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="12009-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="12009-124">Закройте колонку группы **— все группы** .</span><span class="sxs-lookup"><span data-stu-id="12009-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="12009-125">В колонке **Microsoft Intune** в списке **быстрые задачи** щелкните **создать политику соответствия**.</span><span class="sxs-lookup"><span data-stu-id="12009-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="12009-126">В колонке **Профили политики соответствия** нажмите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="12009-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="12009-127">В колонке **Создание политики** в поле **имя**введите **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="12009-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="12009-128">В разделе **платформа**выберите **Windows 10 и более поздние версии**, нажмите кнопку **ОК** в колонке **политика соответствия требованиям Windows 10** , а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="12009-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="12009-129">Закройте колонку **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="12009-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="12009-130">В колонке **Профили политики соответствия** щелкните имя политики **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="12009-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="12009-131">В колонке **Windows 10** нажмите кнопку **назначения**, а затем выберите пункт **выбрать группы для включения**.</span><span class="sxs-lookup"><span data-stu-id="12009-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="12009-132">В колонке **выберите группы для включения** выберите группу **управляемые пользователи устройств Windows 10** и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="12009-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="12009-133">Нажмите кнопку **сохранить**, а затем закройте колонку **Windows 10** для назначений.</span><span class="sxs-lookup"><span data-stu-id="12009-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="12009-134">Закройте колонку **Профили политики соответствия**.</span><span class="sxs-lookup"><span data-stu-id="12009-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="12009-135">В колонке **Microsoft Intune** щелкните **клиентские приложения** на левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="12009-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="12009-136">В колонке **клиентские приложения** выберите пункт **приложения**и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="12009-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="12009-137">В колонке **Добавление приложения** выберите **Тип приложения**, а затем выберите **Windows 10** в разделе **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="12009-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="12009-138">Щелкните **настроить набор приложений**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12009-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="12009-139">Щелкните **сведения о наборе приложений**, введите **Office Apps для Windows 10** в **поле Имя набора**, **приложения Office для Windows 10** в **пакете описание**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12009-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="12009-140">Щелкните **параметры набора приложений**, выберите **полугодие** в **канале обновления**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12009-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="12009-141">В колонке **Добавление приложения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="12009-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="12009-142">Теперь у вас есть политика соответствия требованиям устройств для тестирования выбранных приложений в политике соответствия требованиям устройств для **Windows 10** и для членов группы **управляемых пользователей устройств Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="12009-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="12009-143">Обратите внимание, что при выборе пункта Office 365 в качестве типа группы будут созданы дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="12009-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="12009-144">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="12009-144">Next step</span></span>

<span data-ttu-id="12009-145">Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="12009-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="12009-146">См. также</span><span class="sxs-lookup"><span data-stu-id="12009-146">See also</span></span>

<span data-ttu-id="12009-147">[Руководства по лаборатории тестирования для Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="12009-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="12009-148">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12009-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="12009-149">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="12009-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="12009-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="12009-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
