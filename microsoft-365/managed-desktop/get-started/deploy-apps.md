---
title: Развертывание приложений на устройствах
description: Сведения о добавлении и развертывании приложений на устройствах Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
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
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="10af7-104">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="10af7-104">Deploy apps to devices</span></span>
<span data-ttu-id="10af7-105">Часть включенной в Microsoft Managed Desktop включает добавление и развертывание приложений на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="10af7-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="10af7-106">После использования портала Microsoft Managed Desktop можно добавить и развернуть приложения.</span><span class="sxs-lookup"><span data-stu-id="10af7-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="10af7-107">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="10af7-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="10af7-108">[Добавьте приложения](#1) на портал Microsoft Managed Desktop . Это могут быть существующие приложения для бизнеса или приложения из Microsoft Store для бизнеса, которые вы синхронизировали с Intune.</span><span class="sxs-lookup"><span data-stu-id="10af7-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="10af7-109">[Создайте группы Azure Active Directory (AD)](#2) для назначения приложений . Вы будете использовать эти группы для управления назначением приложений.</span><span class="sxs-lookup"><span data-stu-id="10af7-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="10af7-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="10af7-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="10af7-111">Шаг 1. Добавление приложений на портал Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="10af7-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="10af7-112">Вы можете добавить приложения на основе [Win32 или Windows MSI](#lob-apps)или [приложения Microsoft Store для](#msfb-apps) бизнеса в Microsoft Managed Desktop, а затем развернуть их на устройствах Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="10af7-113">Win32 или приложения на основе Windows MSI в Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="10af7-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="10af7-114">Вы можете добавить приложения для бизнеса (LOB) на портал Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="10af7-115">Сведения о требованиях к приложениям, установленным на устройствах Microsoft Managed Desktop, см. в приложении [Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="10af7-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="10af7-116">В этой процедуре необходимо выбрать, какое приложение нужно добавить, а затем настроить и загрузить источник приложения.</span><span class="sxs-lookup"><span data-stu-id="10af7-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="10af7-117">**Добавление приложения LOB или приложения Windows на портал Microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="10af7-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="10af7-118">Вы можете войти на портал Microsoft Managed Desktop или войти в Intune, а затем найти microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="10af7-119">Мы покажем вход на портал Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="10af7-120">Во входе на [портал Администрирование управляемых настольных компьютеров](https://aka.ms/mmdportal)Майкрософт .</span><span class="sxs-lookup"><span data-stu-id="10af7-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="10af7-121">В **рамках инвентаризации** выберите **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="10af7-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="10af7-122">В рабочей нагрузке Приложения выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="10af7-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="10af7-123">В **добавлении** приложения выберите **приложение Line-of-business или** Приложение Для Windows **(Win32).**</span><span class="sxs-lookup"><span data-stu-id="10af7-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="10af7-124">Если вы выбрали **приложение Line-of-business,** см. в этой строке Добавление [бизнес-приложения Windows в Microsoft Intune](/intune/lob-apps-windows) для инструкции по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="10af7-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="10af7-125">Если вы выбрали **приложение Windows (Win32),** см. в инструкции по добавлению и настройке приложений Windows руководство приложениями [Win32.](/intune/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="10af7-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="10af7-126">Приложения Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="10af7-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="10af7-127">Если вы еще не зарегистрировались в Microsoft Store для бизнеса, вы можете зарегистрироваться при покупке приложений.</span><span class="sxs-lookup"><span data-stu-id="10af7-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="10af7-128">После того как у вас есть приложения, вы можете синхронизировать их с Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="10af7-129">**Покупка приложений в Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="10af7-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="10af7-130">Во входе [в Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью Microsoft Store for Business Admin.</span><span class="sxs-lookup"><span data-stu-id="10af7-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="10af7-131">Выберите **Магазин для моей группы**.</span><span class="sxs-lookup"><span data-stu-id="10af7-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="10af7-132">Используйте поиск, чтобы найти нужное приложение и выбрать приложение.</span><span class="sxs-lookup"><span data-stu-id="10af7-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="10af7-133">Сведения о продукте выберите **Get the App**.</span><span class="sxs-lookup"><span data-stu-id="10af7-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="10af7-134">Microsoft Store добавляет приложение в **ваши продукты** для организации.</span><span class="sxs-lookup"><span data-stu-id="10af7-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="10af7-135">**Принудительное синхронизация между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="10af7-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="10af7-136">Во входе в [центр администрирования microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="10af7-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="10af7-137">Выберите **соединители**  >  **администрирования клиента и**  >  **маркеры Microsoft Store для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="10af7-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="10af7-138">Выберите **синхронизацию,** чтобы получить приложения, приобретенные в Microsoft Store, в Intune.</span><span class="sxs-lookup"><span data-stu-id="10af7-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="10af7-139">**Чтобы убедиться, что синхронизация между Intune и Microsoft Store для бизнеса активна**</span><span class="sxs-lookup"><span data-stu-id="10af7-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="10af7-140">Во входе [в Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью Microsoft Store for Business Admin.</span><span class="sxs-lookup"><span data-stu-id="10af7-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="10af7-141">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="10af7-141">Select **Manage**.</span></span>
3. <span data-ttu-id="10af7-142">Выберите **Параметры,** а затем выберите **Распределить**.</span><span class="sxs-lookup"><span data-stu-id="10af7-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="10af7-143">В **средствах управления** убедитесь, что Intune указан в списке и состояние **Active**.</span><span class="sxs-lookup"><span data-stu-id="10af7-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="10af7-144">Шаг 2. Создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="10af7-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="10af7-145">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="10af7-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="10af7-146">В этой таблице описаны необходимые группы (доступные, необходимые и удалить).</span><span class="sxs-lookup"><span data-stu-id="10af7-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="10af7-147">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="10af7-147">App assignment type</span></span> |    <span data-ttu-id="10af7-148">Групповое использование</span><span class="sxs-lookup"><span data-stu-id="10af7-148">Group use</span></span>    | <span data-ttu-id="10af7-149">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="10af7-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="10af7-150">Available</span><span class="sxs-lookup"><span data-stu-id="10af7-150">Available</span></span> |  <span data-ttu-id="10af7-151">Приложение будет доступно в приложении или веб-сайте портала компании.</span><span class="sxs-lookup"><span data-stu-id="10af7-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="10af7-152">MMD — *имя приложения* — доступно</span><span class="sxs-lookup"><span data-stu-id="10af7-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="10af7-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="10af7-153">Required</span></span> |  <span data-ttu-id="10af7-154">Приложение устанавливается на устройства в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="10af7-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="10af7-155">MMD — *имя приложения* — обязательное</span><span class="sxs-lookup"><span data-stu-id="10af7-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="10af7-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="10af7-156">Uninstall</span></span> |  <span data-ttu-id="10af7-157">Приложение неустановлено с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="10af7-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="10af7-158">MMD — *имя приложения* — Uninstall</span><span class="sxs-lookup"><span data-stu-id="10af7-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="10af7-159">Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить его с устройства Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="10af7-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="10af7-160">Шаг 3. Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="10af7-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="10af7-161">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="10af7-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="10af7-162">Во входе на [портал Администрирование управляемых настольных компьютеров](https://aka.ms/mmdportal)Майкрософт .</span><span class="sxs-lookup"><span data-stu-id="10af7-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="10af7-163">В области Управляемый рабочий стол выберите **Приложения.**</span><span class="sxs-lookup"><span data-stu-id="10af7-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="10af7-164">В рабочей нагрузке Приложения выберите приложение, которое необходимо назначить пользователям, и выберите **Группы Назначения пользователей.**</span><span class="sxs-lookup"><span data-stu-id="10af7-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="10af7-165">Для конкретного приложения выберите тип назначения (Доступные, необходимые, удалить) и назначить соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="10af7-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="10af7-166">В области Назначение приложений выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="10af7-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="10af7-167">Действия по началу работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="10af7-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="10af7-168">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="10af7-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="10af7-169">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="10af7-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="10af7-170">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="10af7-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="10af7-171">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="10af7-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="10af7-172">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="10af7-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="10af7-173">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="10af7-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="10af7-174">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="10af7-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="10af7-175">Развертывание приложений (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="10af7-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->