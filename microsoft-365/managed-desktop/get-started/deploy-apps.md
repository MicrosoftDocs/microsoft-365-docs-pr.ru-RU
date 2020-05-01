---
title: Развертывание приложений на устройствах
description: Сведения для добавления и развертывания приложений на настольных устройствах, управляемых корпорацией Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a064a41fc7ab69e31d49553f600dfd6bb91ef7b0
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302916"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="3e6d7-104">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="3e6d7-104">Deploy apps to devices</span></span>
<span data-ttu-id="3e6d7-105">Часть входящей миграции на Настольный компьютер Майкрософт с управляемым подключением включает добавление и развертывание приложений на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="3e6d7-106">Когда вы используете портал для настольных компьютеров Майкрософт, вы можете добавлять и развертывать свои приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="3e6d7-107">Общий процесс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3e6d7-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="3e6d7-108">[Добавление приложений на портал для настольных ПК, управляемых корпорацией Майкрософт](#1) . Это могут быть существующие бизнес-приложения (LOB) или приложения из Microsoft Store для бизнеса, которые вы синхронизированы с Intune.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="3e6d7-109">[Создайте группы Azure Active Directory (AD) для назначения приложения](#2) , вы будете использовать эти группы для управления назначением приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="3e6d7-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="3e6d7-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="3e6d7-111">Шаг 1: Добавление приложений на управляемый портал для настольных ПК Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3e6d7-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="3e6d7-112">Вы можете добавить [приложения Win32 или Windows MSI](#lob-apps)или [Microsoft Store для бизнес-приложений](#msfb-apps) на компьютер с управляемым учетом Microsoft Store, а затем развернуть их на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="3e6d7-113">Приложения Win32 или Windows MSI для настольного компьютера, управляемого Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3e6d7-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="3e6d7-114">Вы можете добавить бизнес-приложения (LOB) на портал для настольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="3e6d7-115">Для получения сведений о требованиях к приложениям, установленным на настольных компьютерах, управляемых Майкрософт, ознакомьтесь с [требованиями к приложениям, управляемым](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="3e6d7-116">В этой процедуре показано, как выбрать тип приложения, которое вы хотите добавить, а затем настроить и отправить источник приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="3e6d7-117">**Добавление бизнес-приложения или приложения Windows в управляемый портал для настольных ПК Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="3e6d7-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="3e6d7-118">Вы можете войти на портал для настольных компьютеров Майкрософт или войти в Intune, а затем найти компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="3e6d7-119">Мы покажем вход на портал для настольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="3e6d7-120">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="3e6d7-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="3e6d7-121">В разделе **запасы**выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="3e6d7-122">В рабочей нагрузке приложений нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="3e6d7-123">В окне **Добавление приложения**выберите **бизнес-приложение** или **приложение Windows (Win32)**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="3e6d7-124">Если вы выбрали **бизнес-приложение**, ознакомьтесь со статьей [Добавление бизнес-приложения Windows в Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) для получения инструкций по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="3e6d7-125">Если вы выбрали **Windows App (Win32)**, ознакомьтесь с инструкциями по добавлению и настройке приложений Windows в разделе [Управление приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) .</span><span class="sxs-lookup"><span data-stu-id="3e6d7-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="3e6d7-126">Приложения Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3e6d7-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="3e6d7-127">Если вы не зарегистрированы в Microsoft Store для бизнеса, вы можете зарегистрироваться при работе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="3e6d7-128">После создания приложений вы можете синхронизировать их с настольными компьютерами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="3e6d7-129">**Приобретение приложений из Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="3e6d7-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="3e6d7-130">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="3e6d7-131">Выберите **магазин для группы**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="3e6d7-132">Используйте поиск, чтобы найти нужное приложение, и выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="3e6d7-133">В разделе сведения о продукте выберите пункт **Получение приложения**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="3e6d7-134">Microsoft Store добавляет приложение в **продукты & услуг** для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="3e6d7-135">**Принудительная синхронизация между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="3e6d7-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="3e6d7-136">Войдите на [портал Azure](https://portal.azure.com/) как администратор Intune или глобальный администратор для вашего клиента</span><span class="sxs-lookup"><span data-stu-id="3e6d7-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="3e6d7-137">Выберите **все службы > Intune**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-137">Select **All services > Intune**.</span></span> <span data-ttu-id="3e6d7-138">Intune находится в разделе Мониторинг и управление.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="3e6d7-139">В области Intune выберите **клиентские приложения**, а затем выберите **Microsoft Store для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="3e6d7-140">Выберите **включить** , чтобы синхронизировать приложения Microsoft Store для бизнеса с Intune.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="3e6d7-141">Если вы еще не сделали это, выполните вход и связывание учетной записи Microsoft Store для бизнеса с Intune</span><span class="sxs-lookup"><span data-stu-id="3e6d7-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="3e6d7-142">Выберите язык, на котором будут отображаться приложения из Microsoft Store для бизнеса в консоли Intune</span><span class="sxs-lookup"><span data-stu-id="3e6d7-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="3e6d7-143">Выберите **синхронизировать** для синхронизации приложений Microsoft Store для бизнеса с Intune.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="3e6d7-144">Убедитесь, что синхронизация между Microsoft Store для бизнеса и Intune активна (следующий шаг).</span><span class="sxs-lookup"><span data-stu-id="3e6d7-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="3e6d7-145">**Проверка активности синхронизации между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="3e6d7-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="3e6d7-146">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="3e6d7-147">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-147">Select **Manage**.</span></span>
3. <span data-ttu-id="3e6d7-148">Выберите **Параметры** и нажмите кнопку **распределить**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="3e6d7-149">В разделе **средства управления**убедитесь, что в списке присутствует служба Intune и состояние **активна**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="3e6d7-150">Шаг 2: создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e6d7-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="3e6d7-151">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="3e6d7-152">В этой таблице перечислены необходимые группы (доступные, обязательные и удаляемые).</span><span class="sxs-lookup"><span data-stu-id="3e6d7-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="3e6d7-153">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="3e6d7-153">App assignment type</span></span> |   <span data-ttu-id="3e6d7-154">Использование группы</span><span class="sxs-lookup"><span data-stu-id="3e6d7-154">Group use</span></span>   | <span data-ttu-id="3e6d7-155">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e6d7-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="3e6d7-156">Available</span><span class="sxs-lookup"><span data-stu-id="3e6d7-156">Available</span></span> |  <span data-ttu-id="3e6d7-157">Приложение будет доступно из приложения или веб-сайта корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="3e6d7-158">ММД — *имя приложения* — доступно</span><span class="sxs-lookup"><span data-stu-id="3e6d7-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="3e6d7-159">Обязательна</span><span class="sxs-lookup"><span data-stu-id="3e6d7-159">Required</span></span> |  <span data-ttu-id="3e6d7-160">Приложение устанавливается на устройствах в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="3e6d7-161">ММД — *имя приложения* — обязательный</span><span class="sxs-lookup"><span data-stu-id="3e6d7-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="3e6d7-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="3e6d7-162">Uninstall</span></span> |  <span data-ttu-id="3e6d7-163">Приложение удалено с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="3e6d7-164">ММД — *имя приложения* — удаление</span><span class="sxs-lookup"><span data-stu-id="3e6d7-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="3e6d7-165">Добавьте пользователей в эти группы, чтобы сделать приложение доступ, установить приложение или удалить приложение с компьютера, управляемого Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="3e6d7-166">Шаг 3: назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="3e6d7-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="3e6d7-167">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="3e6d7-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="3e6d7-168">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="3e6d7-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="3e6d7-169">В области управляемый Рабочий стол выберите пункт **приложения**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="3e6d7-170">В рабочей нагрузке приложений выберите приложение, которому вы хотите назначить пользователей, и выберите **назначить группы пользователей**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="3e6d7-171">Для конкретного приложения выберите тип назначения (доступное, необходимое, удалите) и назначьте соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="3e6d7-172">В области назначить приложения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e6d7-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="3e6d7-173">Действия для начала работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3e6d7-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="3e6d7-174">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="3e6d7-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="3e6d7-175">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="3e6d7-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="3e6d7-176">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="3e6d7-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="3e6d7-177">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="3e6d7-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="3e6d7-178">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="3e6d7-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="3e6d7-179">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="3e6d7-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="3e6d7-180">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="3e6d7-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="3e6d7-181">Развертывание приложений (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="3e6d7-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
