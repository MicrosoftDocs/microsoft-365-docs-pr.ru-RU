---
title: Развертывание приложений на устройствах
description: Сведения о добавлении и развертывании приложений на настольных устройствах, управляемых Майкрософт.
keywords: Microsoft Managed Desktop, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769110"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="b0ed8-104">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="b0ed8-104">Deploy apps to devices</span></span>
<span data-ttu-id="b0ed8-105">Частью подключения к компьютеру, управляемому Майкрософт, является добавление и развертывание приложений на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="b0ed8-106">После использования портала microsoft Managed Desktop можно добавлять и развертывать приложения.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="b0ed8-107">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="b0ed8-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="b0ed8-108">[Добавьте приложения](#1) на портал управляемых Майкрософт компьютеров. Это могут быть бизнес-приложения или приложения из Microsoft Store для бизнеса, которые вы синхронизировали с Intune.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="b0ed8-109">[Создайте группы Azure Active Directory (AD)](#2) для назначения приложений. Вы будете использовать эти группы для управления назначением приложения.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="b0ed8-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="b0ed8-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="b0ed8-111">Шаг 1. Добавление приложений на портал microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b0ed8-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="b0ed8-112">Вы можете добавить [win32,](#lob-apps)приложения на основе Windows MSI или приложения [Microsoft Store](#msfb-apps) для бизнеса на компьютеры, управляемые Майкрософт, а затем развернуть их на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="b0ed8-113">Приложения на основе Win32 или Windows MSI для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0ed8-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="b0ed8-114">Вы можете добавить бизнес-приложения на портал microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="b0ed8-115">Сведения о требованиях к приложениям, установленным на управляемых Майкрософт настольных устройствах, см. в сведениях о требованиях к приложениям для управляемых компьютеров [Майкрософт.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="b0ed8-116">В этой процедуре вы выберете, какое приложение вы хотите добавить, а затем настроите и загрузите источник приложения.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="b0ed8-117">**Добавление приложения для LOB или Windows на портал microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="b0ed8-118">Вы можете войти на портал microsoft Managed Desktop portal или войти в Intune, а затем найти компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="b0ed8-119">Мы покажем вход на портал microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="b0ed8-120">Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="b0ed8-121">Under **Inventory**, select **Apps**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="b0ed8-122">В рабочей нагрузке приложений выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="b0ed8-123">В **приложении "Добавить"** **выберите бизнес-приложение** или **приложение для Windows (Win32).**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="b0ed8-124">Если вы выбрали **бизнес-приложение,** см. инструкции по добавлению и настройке бизнес-приложений в [Microsoft Intune.](https://docs.microsoft.com/intune/lob-apps-windows)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="b0ed8-125">Если вы выбрали приложение **для Windows (Win32),** инструкции по добавлению и настройке приложений для Windows см. в руководстве по управлению приложениями [Win32.](https://docs.microsoft.com/intune/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="b0ed8-126">Приложения Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b0ed8-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="b0ed8-127">Если вы еще не зарегистрировались в Microsoft Store для бизнеса, вы можете зарегистрироваться при покупке приложений.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="b0ed8-128">После того как у вас есть приложения, вы можете синхронизировать их с компьютерами, управляемыми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="b0ed8-129">**Покупка приложений из Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="b0ed8-130">Во sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b0ed8-131">Выберите **"Магазин" для моей группы.**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="b0ed8-132">Используйте поиск, чтобы найти нужное приложение, и выберите его.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="b0ed8-133">В сведениях о продукте выберите **"Получить приложение".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="b0ed8-134">Microsoft Store добавляет приложение в **ваши продукты** для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="b0ed8-135">**Принудительное синхронизация Между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="b0ed8-136">Во входе в [Центр администрирования Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="b0ed8-137">Выберите **соединители**  >  **администрирования клиентов и маркеры**  >  **Microsoft Store для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="b0ed8-138">Выберите **"Синхронизация",** чтобы получить приложения, приобретенные в Microsoft Store, в Intune.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="b0ed8-139">**Проверка активности синхронизации Между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="b0ed8-140">Во sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b0ed8-141">Выберите **"Управление".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-141">Select **Manage**.</span></span>
3. <span data-ttu-id="b0ed8-142">Выберите **"Параметры",** а затем выберите **"Распространить".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="b0ed8-143">В **средстве управления** убедитесь, что Intune указан в списке и находится в **активном состоянии.**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="b0ed8-144">Шаг 2. Создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="b0ed8-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="b0ed8-145">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="b0ed8-146">В этой таблице описаны необходимые вам группы (доступные, необходимые и удалить).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="b0ed8-147">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="b0ed8-147">App assignment type</span></span> |    <span data-ttu-id="b0ed8-148">Использование групп</span><span class="sxs-lookup"><span data-stu-id="b0ed8-148">Group use</span></span>    | <span data-ttu-id="b0ed8-149">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="b0ed8-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="b0ed8-150">Available</span><span class="sxs-lookup"><span data-stu-id="b0ed8-150">Available</span></span> |  <span data-ttu-id="b0ed8-151">Приложение будет доступно из приложения или веб-сайта портала компании.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="b0ed8-152">MMD — *имя приложения —* доступно</span><span class="sxs-lookup"><span data-stu-id="b0ed8-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="b0ed8-153">Обязательна</span><span class="sxs-lookup"><span data-stu-id="b0ed8-153">Required</span></span> |  <span data-ttu-id="b0ed8-154">Приложение устанавливается на устройства в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="b0ed8-155">MMD — *имя приложения* — обязательно</span><span class="sxs-lookup"><span data-stu-id="b0ed8-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="b0ed8-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="b0ed8-156">Uninstall</span></span> |  <span data-ttu-id="b0ed8-157">Приложение будет выгрузлено с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="b0ed8-158">MMD *— имя приложения* — удалить</span><span class="sxs-lookup"><span data-stu-id="b0ed8-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="b0ed8-159">Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить его с компьютера, управляемого Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="b0ed8-160">Шаг 3. Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="b0ed8-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="b0ed8-161">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="b0ed8-162">Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b0ed8-163">В области "Управляемый рабочий стол" выберите **"Приложения".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="b0ed8-164">В рабочей нагрузке "Приложения" выберите приложение, для которое нужно назначить пользователей, и выберите **"Назначить группы пользователей".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="b0ed8-165">Для конкретного приложения выберите тип назначения (доступен, требуется, удалить) и назначьте соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="b0ed8-166">В области "Назначить приложения" выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="b0ed8-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="b0ed8-167">Действия по началу работы с компьютером, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0ed8-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="b0ed8-168">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="b0ed8-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="b0ed8-169">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="b0ed8-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="b0ed8-170">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="b0ed8-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="b0ed8-171">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="b0ed8-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="b0ed8-172">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="b0ed8-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="b0ed8-173">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="b0ed8-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="b0ed8-174">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="b0ed8-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="b0ed8-175">Развертывание приложений (в этом разделе)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
