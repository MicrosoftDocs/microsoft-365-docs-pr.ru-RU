---
title: Развертывание приложений на устройствах
description: Сведения о добавлении и развертывании приложений на компьютеры, управляемые Майкрософт устройствах.
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, приложения LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922030"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="de5be-104">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="de5be-104">Deploy apps to devices</span></span>
<span data-ttu-id="de5be-105">Часть включенной в компьютеры, управляемые Майкрософт включает добавление и развертывание приложений на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="de5be-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="de5be-106">После использования портала компьютеры, управляемые Майкрософт можно добавить и развернуть приложения.</span><span class="sxs-lookup"><span data-stu-id="de5be-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="de5be-107">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="de5be-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="de5be-108">[Добавление приложений компьютеры, управляемые Майкрософт](#1) портала . Это могут быть существующие приложения для бизнеса или приложения из Microsoft Store для бизнеса, синхронизированные с Intune.</span><span class="sxs-lookup"><span data-stu-id="de5be-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="de5be-109">[Создайте Azure Active Directory (AD) для](#2) назначения приложений . Вы будете использовать эти группы для управления назначением приложений.</span><span class="sxs-lookup"><span data-stu-id="de5be-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="de5be-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="de5be-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="de5be-111">Шаг 1. Добавление приложений на компьютеры, управляемые Майкрософт портал</span><span class="sxs-lookup"><span data-stu-id="de5be-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="de5be-112">Вы можете добавить приложения на основе [Win32](#lob-apps)или Windows [](#msfb-apps) MSI или Microsoft Store для бизнеса приложения для компьютеры, управляемые Майкрософт, а затем развернуть их на компьютеры, управляемые Майкрософт устройствах.</span><span class="sxs-lookup"><span data-stu-id="de5be-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="de5be-113">Win32 или Windows MSI-приложения для компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="de5be-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="de5be-114">Вы можете добавить приложения для бизнеса (LOB) в компьютеры, управляемые Майкрософт портал.</span><span class="sxs-lookup"><span data-stu-id="de5be-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="de5be-115">Сведения о требованиях к приложениям, установленным на компьютеры, управляемые Майкрософт устройствах, см. в компьютеры, управляемые Майкрософт [требования к приложениям.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="de5be-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="de5be-116">В этой процедуре необходимо выбрать, какое приложение нужно добавить, а затем настроить и загрузить источник приложения.</span><span class="sxs-lookup"><span data-stu-id="de5be-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="de5be-117">**Добавление приложения LOB или Windows на компьютеры, управляемые Майкрософт портал**</span><span class="sxs-lookup"><span data-stu-id="de5be-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="de5be-118">Вы можете войти в компьютеры, управляемые Майкрософт портал или войти в Intune, а затем найти компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="de5be-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="de5be-119">Мы покажем вход на компьютеры, управляемые Майкрософт портал.</span><span class="sxs-lookup"><span data-stu-id="de5be-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="de5be-120">Во входе [на компьютеры, управляемые Майкрософт администратора](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="de5be-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="de5be-121">В **рамках инвентаризации** выберите **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="de5be-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="de5be-122">В рабочей нагрузке Приложения выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="de5be-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="de5be-123">В **приложении** Добавить выберите **приложение Line-of-business** или **Windows (Win32).**</span><span class="sxs-lookup"><span data-stu-id="de5be-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="de5be-124">Если вы выбрали приложение **Line-of-business,** см. в [Windows-бизнес-приложение](/intune/lob-apps-windows) для Microsoft Intune инструкций по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="de5be-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="de5be-125">Если вы выбрали **Windows (Win32),** см. в инструкции по добавлению и настройке приложений [win32](/intune/apps-win32-app-management) для управления Windows приложениями.</span><span class="sxs-lookup"><span data-stu-id="de5be-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="de5be-126">Microsoft Store для бизнеса приложения</span><span class="sxs-lookup"><span data-stu-id="de5be-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="de5be-127">Если вы еще не зарегистрировались в Microsoft Store для бизнеса, вы можете зарегистрироваться при покупке приложений.</span><span class="sxs-lookup"><span data-stu-id="de5be-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="de5be-128">После того как у вас есть приложения, вы можете синхронизировать их с компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="de5be-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="de5be-129">**Покупка приложений из Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="de5be-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="de5be-130">Во входе [Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса администратора.</span><span class="sxs-lookup"><span data-stu-id="de5be-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="de5be-131">Выберите **Магазин для моей группы**.</span><span class="sxs-lookup"><span data-stu-id="de5be-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="de5be-132">Используйте поиск, чтобы найти нужное приложение и выбрать приложение.</span><span class="sxs-lookup"><span data-stu-id="de5be-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="de5be-133">Сведения о продукте выберите **Get the App**.</span><span class="sxs-lookup"><span data-stu-id="de5be-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="de5be-134">Microsoft Store добавляет приложение в **продукты вашей** организации.</span><span class="sxs-lookup"><span data-stu-id="de5be-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="de5be-135">**Принудительное синхронизация между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="de5be-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="de5be-136">Во входе [в Microsoft Endpoint Manager центр администрирования.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="de5be-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="de5be-137">Выберите **соединители** администрирования клиента и  >    >  **маркеры Microsoft Store для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="de5be-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="de5be-138">Выберите **синхронизацию,** чтобы получить приложения, которые вы приобрели из Microsoft Store в Intune.</span><span class="sxs-lookup"><span data-stu-id="de5be-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="de5be-139">**Чтобы убедиться, что синхронизация между Intune и Microsoft Store для бизнеса активна**</span><span class="sxs-lookup"><span data-stu-id="de5be-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="de5be-140">Во входе [Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса администратора.</span><span class="sxs-lookup"><span data-stu-id="de5be-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="de5be-141">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="de5be-141">Select **Manage**.</span></span>
3. <span data-ttu-id="de5be-142">Выберите **Параметры** и выберите **Распределить**.</span><span class="sxs-lookup"><span data-stu-id="de5be-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="de5be-143">В **средствах управления** убедитесь, что Intune указан в списке и состояние **Active**.</span><span class="sxs-lookup"><span data-stu-id="de5be-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="de5be-144">Шаг 2. Создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="de5be-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="de5be-145">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="de5be-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="de5be-146">В этой таблице описаны необходимые группы (доступные, необходимые и удалить).</span><span class="sxs-lookup"><span data-stu-id="de5be-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="de5be-147">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="de5be-147">App assignment type</span></span> |    <span data-ttu-id="de5be-148">Групповое использование</span><span class="sxs-lookup"><span data-stu-id="de5be-148">Group use</span></span>    | <span data-ttu-id="de5be-149">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="de5be-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="de5be-150">Available</span><span class="sxs-lookup"><span data-stu-id="de5be-150">Available</span></span> |  <span data-ttu-id="de5be-151">Приложение будет доступно из Корпоративный портал или веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="de5be-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="de5be-152">MMD — *имя приложения* — доступно</span><span class="sxs-lookup"><span data-stu-id="de5be-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="de5be-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="de5be-153">Required</span></span> |  <span data-ttu-id="de5be-154">Приложение устанавливается на устройства в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="de5be-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="de5be-155">MMD — *имя приложения* — обязательное</span><span class="sxs-lookup"><span data-stu-id="de5be-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="de5be-156">Удалить</span><span class="sxs-lookup"><span data-stu-id="de5be-156">Uninstall</span></span> |  <span data-ttu-id="de5be-157">Приложение неустановлено с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="de5be-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="de5be-158">MMD — *имя приложения* — Uninstall</span><span class="sxs-lookup"><span data-stu-id="de5be-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="de5be-159">Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить его с компьютеры, управляемые Майкрософт устройства.</span><span class="sxs-lookup"><span data-stu-id="de5be-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="de5be-160">Шаг 3. Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="de5be-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="de5be-161">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="de5be-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="de5be-162">Во входе [на компьютеры, управляемые Майкрософт администратора](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="de5be-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="de5be-163">В области Управляемый рабочий стол выберите **Приложения.**</span><span class="sxs-lookup"><span data-stu-id="de5be-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="de5be-164">В рабочей нагрузке Приложения выберите приложение, которое необходимо назначить пользователям, и выберите **Группы Назначения пользователей.**</span><span class="sxs-lookup"><span data-stu-id="de5be-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="de5be-165">Для конкретного приложения выберите тип назначения (Доступные, необходимые, удалить) и назначить соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="de5be-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="de5be-166">В области Назначение приложений выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="de5be-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="de5be-167">Шаги для начала работы с компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="de5be-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="de5be-168">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="de5be-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="de5be-169">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="de5be-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="de5be-170">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="de5be-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="de5be-171">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="de5be-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="de5be-172">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="de5be-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="de5be-173">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="de5be-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="de5be-174">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="de5be-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="de5be-175">Развертывание приложений (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="de5be-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->