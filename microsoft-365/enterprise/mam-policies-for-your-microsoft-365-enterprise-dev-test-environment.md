---
title: Политики MAM для вашей тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: В этом документе Test Lab Guide служит для добавления политики управления (MAM) Intune мобильных приложений на предприятии 365 Microsoft тестовой среды.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871068"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="360a9-103">Политики MAM для вашей тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="360a9-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="360a9-104">С помощью инструкции в этом разделе добавьте политик управления (MAM) Intune мобильных приложений на предприятии 365 Microsoft тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="360a9-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="360a9-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="360a9-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="360a9-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="360a9-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="360a9-108">Если необходимо настроить политики MAM образом lightweight с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="360a9-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="360a9-109">Если вы хотите настроить политики MAM имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="360a9-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="360a9-p101">Тестирование автоматизирована лицензирования и членства в группе не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="360a9-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="360a9-112">Этап 2. Создание и развертывание политики MAM для устройств с ОС iOS и Android</span><span class="sxs-lookup"><span data-stu-id="360a9-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="360a9-113">На этом этапе можно создать и развернуть две разные политики MAM отдельно для устройств с iOS и устройств Android.</span><span class="sxs-lookup"><span data-stu-id="360a9-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="360a9-114">Последовательно выберите пункты портала Office 365 в ([https://portal.office.com](https://portal.office.com)) и войти в систему с учетной записью глобального администратора пробной подписки Office 365.</span><span class="sxs-lookup"><span data-stu-id="360a9-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="360a9-115">На новой вкладке браузере откройте Azure портал по [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="360a9-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="360a9-116">Вкладки Azure портала в Internet Explorer, в области навигации щелкните **все службы**, введите **Intune**и нажмите кнопку **Intune**.</span><span class="sxs-lookup"><span data-stu-id="360a9-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="360a9-p102">Если сообщение **еще не включено управление устройствами еще не** отображаются на blade **Microsoft Intune** , щелкните его. На blade **центра управления мобильных устройств** нажмите кнопку **Intune MDM сертификации**и нажмите кнопку **выбрать**. Обновление вкладки вашего браузера.</span><span class="sxs-lookup"><span data-stu-id="360a9-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="360a9-120">В области навигации слева выберите раздел **Группы**.</span><span class="sxs-lookup"><span data-stu-id="360a9-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="360a9-121">На blade **групп все группы** нажмите кнопку **+ Новая группа**.</span><span class="sxs-lookup"><span data-stu-id="360a9-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="360a9-122">На blade **группы** , выберите **Office 365** для **группу, тип?** введите **управляемых пользователей устройств операций ввода-вывода** в поле **имя**выберите **назначено** в **типа участия**и затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="360a9-123">Закройте вкладку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="360a9-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="360a9-124">На blade **групп все группы** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="360a9-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="360a9-125">На blade **группы** , выберите **Office 365** для **группу, тип?**, введите **управляемых Android устройство пользователя** в поле **имя**выберите **назначено** в **типа участия**и затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="360a9-126">Закройте blade **групп все группы** .</span><span class="sxs-lookup"><span data-stu-id="360a9-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="360a9-127">В колонке **Intune**, в списке **Быстрые задачи**, выберите **Создайте политику соответствия**.</span><span class="sxs-lookup"><span data-stu-id="360a9-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="360a9-128">В колонке **Профили политики соответствия** нажмите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="360a9-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="360a9-p103">В колонке **Создание политики**, в строке **Имя**, введите **iOS**. В разделе **Платформа** выберите **iOS**, нажмите **ОК** в колонке **Политика соответствия для iOS**, а затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="360a9-131">В колонке **Профили политики соответствия** нажмите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="360a9-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="360a9-p104">В колонке **Создание политики**, в строке **Имя**, введите **Android**. В разделе **Платформа** выберите **Android**, нажмите **ОК** в колонке **Политика соответствия для Android**, а затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="360a9-134">В колонке **Профили политики соответствия** щелкните имя политики **Android**.</span><span class="sxs-lookup"><span data-stu-id="360a9-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="360a9-135">В колонке **Android — Свойства**, в левой области навигации, нажмите **Назначения** > **Выбрать группы**.</span><span class="sxs-lookup"><span data-stu-id="360a9-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="360a9-136">В колонке **Выбор групп** выберите группу **Управляемые пользователи устройств Android** и нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="360a9-137">Нажмите кнопку **Сохранить**, а затем закройте blade **Android - назначений** .</span><span class="sxs-lookup"><span data-stu-id="360a9-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="360a9-138">В колонке **Профили политики соответствия** щелкните имя политики **iOS**.</span><span class="sxs-lookup"><span data-stu-id="360a9-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="360a9-139">В колонке **iOS — Свойства**, в левой области навигации, нажмите **Назначения** > **Выбрать группы**.</span><span class="sxs-lookup"><span data-stu-id="360a9-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="360a9-140">В колонке **Выбор групп** выберите группу **Управляемые пользователи устройств iOS** и нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="360a9-141">Нажмите кнопку **Сохранить**, а затем закройте blade **iOS - назначений** .</span><span class="sxs-lookup"><span data-stu-id="360a9-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="360a9-142">Закройте колонку **Профили политики соответствия**.</span><span class="sxs-lookup"><span data-stu-id="360a9-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="360a9-143">В колонке **Intune** нажмите **Управление приложениями** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="360a9-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="360a9-144">В колонке **Мобильные приложения** нажмите **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="360a9-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="360a9-145">В списке приложений выберите **PowerPoint**. </span><span class="sxs-lookup"><span data-stu-id="360a9-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="360a9-p105">В колонке **PowerPoint — Обзор** нажмите **Назначения > Выбрать группы > Управляемые устройства iOS > Выбрать**. В разделе **Тип** выберите **Доступные** и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="360a9-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="360a9-148">Повторите шаг 29 для следующих приложений:</span><span class="sxs-lookup"><span data-stu-id="360a9-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="360a9-149">Outlook для Android</span><span class="sxs-lookup"><span data-stu-id="360a9-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="360a9-150">Word для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-150">Word for iOS</span></span>
    
    - <span data-ttu-id="360a9-151">Excel для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="360a9-152">Outlook для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="360a9-153">Microsoft Dynamics CRM на iPad для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="360a9-154">Microsoft Dynamics CRM на iPhone для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="360a9-155">Dynamics CRM для телефонов для Android</span><span class="sxs-lookup"><span data-stu-id="360a9-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="360a9-156">Dynamics CRM для планшетов для Android</span><span class="sxs-lookup"><span data-stu-id="360a9-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="360a9-157">Excel для Android</span><span class="sxs-lookup"><span data-stu-id="360a9-157">Excel for Android</span></span>
    
    - <span data-ttu-id="360a9-158">Word для Android</span><span class="sxs-lookup"><span data-stu-id="360a9-158">Word for Android</span></span>
    
    - <span data-ttu-id="360a9-159">OneNote для iOS</span><span class="sxs-lookup"><span data-stu-id="360a9-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="360a9-160">Закройте вкладку **Мобильные приложения — Приложения**.</span><span class="sxs-lookup"><span data-stu-id="360a9-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="360a9-161">В колонке **Мобильные приложения** нажмите **Политики защиты приложений**.</span><span class="sxs-lookup"><span data-stu-id="360a9-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="360a9-162">В колонке **Политики защиты приложений** нажмите **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="360a9-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="360a9-163">В колонке **Добавление политики** введите **iOS** и нажмите **Выбрать необходимые приложения**.</span><span class="sxs-lookup"><span data-stu-id="360a9-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="360a9-164">В колонке **Приложения** выберите **PowerPoint**, **Microsoft Dynamics CRM на iPhone**, **Excel**, **Microsoft Dynamics CRM на iPhone**, **Word**, **OneNote** и **Outlook** и нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="360a9-165">В колонке **Добавление политики** нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="360a9-166">В колонке **Политики защиты приложений** нажмите **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="360a9-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="360a9-167">В колонке **Добавление политики** введите **Android**, выберите **Android** в разделе **Платформа** и нажмите **Выбрать необходимые приложения**.</span><span class="sxs-lookup"><span data-stu-id="360a9-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="360a9-168">В колонке **Приложения** выберите **PowerPoint**, **Dynamics CRM для планшетов**, **Excel**, **Word**, **Outlook** и **Dynamics CRM для телефонов** и нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="360a9-169">В колонке **Добавление политики** нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="360a9-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="360a9-170">Вы создали две отдельные политики MAM для устройств с ОС iOS и устройств с ОС Android и теперь можете поэкспериментировать с тестированием параметров для выбранных приложений.</span><span class="sxs-lookup"><span data-stu-id="360a9-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="360a9-171">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="360a9-171">Next step</span></span>

<span data-ttu-id="360a9-172">Изучите дополнительное [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="360a9-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="360a9-173">См. также</span><span class="sxs-lookup"><span data-stu-id="360a9-173">See also</span></span>

<span data-ttu-id="360a9-174">[365 Enterprise руководствах](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="360a9-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="360a9-175">Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="360a9-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="360a9-176">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="360a9-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="360a9-177">Мобильные решения на предприятиях + безопасности (Командной)</span><span class="sxs-lookup"><span data-stu-id="360a9-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
