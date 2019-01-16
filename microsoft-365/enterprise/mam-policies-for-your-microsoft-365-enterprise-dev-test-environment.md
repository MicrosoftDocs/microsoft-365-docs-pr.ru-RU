---
title: Политики соответствия устройства для вашего предприятия 365 Microsoft тестовой среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: В этом документе Test Lab Guide служит для добавления политики соответствия Intune устройства на предприятии 365 Microsoft тестовой среды.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871068"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="904b1-103">Политики соответствия устройства для вашего предприятия 365 Microsoft тестовой среды</span><span class="sxs-lookup"><span data-stu-id="904b1-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="904b1-104">Согласно инструкциям в этой статье добавьте политики соответствия требованиям к Intune устройства для тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="904b1-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="904b1-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="904b1-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="904b1-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="904b1-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="904b1-108">Если необходимо настроить политики MAM образом lightweight с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="904b1-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="904b1-109">Если вы хотите настроить политики MAM имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="904b1-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="904b1-p101">Тестирование автоматизирована лицензирования и членства в группе не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="904b1-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="904b1-112">Этап 2: Создание политики соответствия устройств для устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="904b1-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="904b1-113">На этом этапе создается политики соответствия устройств для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="904b1-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="904b1-114">Перейдите на портале Office по ([https://office.com](https://office.com)) и войти в систему с учетной записью глобального администратора пробной подписки Office 365.</span><span class="sxs-lookup"><span data-stu-id="904b1-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="904b1-115">На новой вкладке браузере откройте Azure портал по [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="904b1-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="904b1-116">На вкладке Azure портала в браузере, в области навигации щелкните **все службы**, введите **Intune**и нажмите кнопку **Intune**.</span><span class="sxs-lookup"><span data-stu-id="904b1-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="904b1-p102">Если сообщение **еще не включено управление устройствами еще не** отображаются на blade **Microsoft Intune** , щелкните его. На blade **центра управления мобильных устройств** нажмите кнопку **Intune MDM сертификации**и нажмите кнопку **выбрать**. Обновление вкладки вашего браузера.</span><span class="sxs-lookup"><span data-stu-id="904b1-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="904b1-120">В области навигации слева выберите раздел **Группы**.</span><span class="sxs-lookup"><span data-stu-id="904b1-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="904b1-121">На blade **групп все группы** нажмите кнопку **+ Новая группа**.</span><span class="sxs-lookup"><span data-stu-id="904b1-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="904b1-122">На blade **группы** , выберите **Office 365** для **группу, тип?**, введите в поле **имя** **управляемых Windows 10 пользователей устройств** выберите **назначено** в **типа участия**и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="904b1-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="904b1-123">Закройте вкладку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="904b1-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="904b1-124">Закройте blade **групп все группы** .</span><span class="sxs-lookup"><span data-stu-id="904b1-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="904b1-125">На blade **Intune Майкрософт** , в списке **быстрого задач** нажмите кнопку **Создать политики соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="904b1-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="904b1-126">В колонке **Профили политики соответствия** нажмите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="904b1-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="904b1-p103">На blade **Создать политику** в поле **имя**введите **Windows 10**. В **платформы**выберите **10 и более поздних версий Windows**, нажмите **кнопку ОК** на blade **политики соответствия Windows 10** и нажмите кнопку **Создать**. Закройте blade **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="904b1-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="904b1-130">На blade **Профилей политики соответствия требованиям** щелкните имя политики **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="904b1-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="904b1-131">На blade **Windows 10** нажмите кнопку **назначения**и нажмите кнопку **Выбрать группы для включения**.</span><span class="sxs-lookup"><span data-stu-id="904b1-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="904b1-132">На blade **Выберите группы для включения** выберите группу **пользователей устройств управляемых 10 Windows** и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="904b1-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="904b1-133">Нажмите кнопку **Сохранить**, а затем закройте blade **Windows 10 - назначений** .</span><span class="sxs-lookup"><span data-stu-id="904b1-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="904b1-134">Закройте колонку **Профили политики соответствия**.</span><span class="sxs-lookup"><span data-stu-id="904b1-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="904b1-135">На blade **Microsoft Intune** выберите **клиентского приложения** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="904b1-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="904b1-136">На blade **Клиентских приложений** выберите **приложения**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="904b1-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="904b1-137">В blade **Добавить приложение** выберите **Тип приложения**и выберите **Windows 10** в разделе **Набор Office 365**.</span><span class="sxs-lookup"><span data-stu-id="904b1-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="904b1-138">Нажмите кнопку **Настройка пакета приложения**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="904b1-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="904b1-139">Нажмите кнопку **Информации о приложении Suite**, введите в поле **Имя набора** **приложений Office для Windows 10** в поле **Описание набора** **приложений Office для Windows 10** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="904b1-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="904b1-140">Нажмите кнопку **Параметры набора приложений**, выберите **точками годовая** в **канале обновления**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="904b1-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="904b1-141">На blade **Добавить приложение** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="904b1-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="904b1-142">Теперь у вас есть политики соответствия устройств для тестирования выбранных приложений в соответствие требованиям политики устройств **Windows 10** и для членов группы **пользователей устройств управляемых Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="904b1-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="904b1-143">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="904b1-143">Next step</span></span>

<span data-ttu-id="904b1-144">Изучите дополнительное [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="904b1-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="904b1-145">См. также</span><span class="sxs-lookup"><span data-stu-id="904b1-145">See also</span></span>

<span data-ttu-id="904b1-146">[365 Enterprise руководствах](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="904b1-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="904b1-147">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="904b1-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="904b1-148">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="904b1-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="904b1-149">Мобильные решения на предприятиях + безопасности (Командной)</span><span class="sxs-lookup"><span data-stu-id="904b1-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
