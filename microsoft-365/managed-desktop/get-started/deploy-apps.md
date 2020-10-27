---
title: Развертывание приложений на устройствах
description: Сведения для добавления и развертывания приложений на настольных устройствах, управляемых корпорацией Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
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
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="cc9b1-104">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="cc9b1-104">Deploy apps to devices</span></span>
<span data-ttu-id="cc9b1-105">Часть входящей миграции на Настольный компьютер Майкрософт с управляемым подключением включает добавление и развертывание приложений на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="cc9b1-106">Когда вы используете портал для настольных компьютеров Майкрософт, вы можете добавлять и развертывать свои приложения.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="cc9b1-107">Общий процесс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc9b1-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="cc9b1-108">[Добавление приложений на портал для настольных ПК, управляемых корпорацией Майкрософт](#1) . Это могут быть существующие бизнес-приложения (LOB) или приложения из Microsoft Store для бизнеса, которые вы синхронизированы с Intune.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="cc9b1-109">[Создайте группы Azure Active Directory (AD) для назначения приложения](#2) , вы будете использовать эти группы для управления назначением приложения.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="cc9b1-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="cc9b1-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="cc9b1-111">Шаг 1: Добавление приложений на управляемый портал для настольных ПК Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cc9b1-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="cc9b1-112">Вы можете добавить [приложения Win32 или Windows MSI](#lob-apps)или [Microsoft Store для бизнес-приложений](#msfb-apps) на компьютер с управляемым учетом Microsoft Store, а затем развернуть их на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="cc9b1-113">Приложения Win32 или Windows MSI для настольного компьютера, управляемого Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cc9b1-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="cc9b1-114">Вы можете добавить бизнес-приложения (LOB) на портал для настольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="cc9b1-115">Для получения сведений о требованиях к приложениям, установленным на настольных компьютерах, управляемых Майкрософт, ознакомьтесь с [требованиями к приложениям, управляемым](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="cc9b1-116">В этой процедуре показано, как выбрать тип приложения, которое вы хотите добавить, а затем настроить и отправить источник приложения.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="cc9b1-117">**Добавление бизнес-приложения или приложения Windows в управляемый портал для настольных ПК Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="cc9b1-118">Вы можете войти на портал для настольных компьютеров Майкрософт или войти в Intune, а затем найти компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="cc9b1-119">Мы покажем вход на портал для настольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="cc9b1-120">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="cc9b1-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="cc9b1-121">В разделе **запасы** выберите **приложения** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="cc9b1-122">В рабочей нагрузке приложений нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="cc9b1-123">В окне **Добавление приложения** выберите **бизнес-приложение** или **приложение Windows (Win32)** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="cc9b1-124">Если вы выбрали **бизнес-приложение** , ознакомьтесь со статьей [Добавление бизнес-приложения Windows в Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) для получения инструкций по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="cc9b1-125">Если вы выбрали **Windows App (Win32)** , ознакомьтесь с инструкциями по добавлению и настройке приложений Windows в разделе [Управление приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="cc9b1-126">Приложения Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cc9b1-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="cc9b1-127">Если вы не зарегистрированы в Microsoft Store для бизнеса, вы можете зарегистрироваться при работе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="cc9b1-128">После создания приложений вы можете синхронизировать их с настольными компьютерами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="cc9b1-129">**Приобретение приложений из Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="cc9b1-130">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="cc9b1-131">Выберите **магазин для группы** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="cc9b1-132">Используйте поиск, чтобы найти нужное приложение, и выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="cc9b1-133">В разделе сведения о продукте выберите пункт **Получение приложения** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="cc9b1-134">Microsoft Store добавляет приложение к **вашим продуктам** вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="cc9b1-135">**Принудительная синхронизация между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="cc9b1-136">Войдите в [центр администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="cc9b1-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="cc9b1-137">Выберите соединители **администрирования клиентов**  >  **и маркеры**  >  **Microsoft Store для бизнеса** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="cc9b1-138">Выберите **Sync (синхронизировать** ), чтобы получить приложения, приобретенные вами из Microsoft Store в Intune.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="cc9b1-139">**Проверка активности синхронизации между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="cc9b1-140">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="cc9b1-141">Выберите **Управление** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-141">Select **Manage** .</span></span>
3. <span data-ttu-id="cc9b1-142">Выберите **Параметры** и нажмите кнопку **распределить** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="cc9b1-143">В разделе **средства управления** убедитесь, что в списке присутствует служба Intune и состояние **активна** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="cc9b1-144">Шаг 2: создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc9b1-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="cc9b1-145">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="cc9b1-146">В этой таблице перечислены необходимые группы (доступные, обязательные и удаляемые).</span><span class="sxs-lookup"><span data-stu-id="cc9b1-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="cc9b1-147">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="cc9b1-147">App assignment type</span></span> |    <span data-ttu-id="cc9b1-148">Использование группы</span><span class="sxs-lookup"><span data-stu-id="cc9b1-148">Group use</span></span>    | <span data-ttu-id="cc9b1-149">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc9b1-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="cc9b1-150">Available</span><span class="sxs-lookup"><span data-stu-id="cc9b1-150">Available</span></span> |  <span data-ttu-id="cc9b1-151">Приложение будет доступно из приложения или веб-сайта корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="cc9b1-152">ММД — *имя приложения* — доступно</span><span class="sxs-lookup"><span data-stu-id="cc9b1-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="cc9b1-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9b1-153">Required</span></span> |  <span data-ttu-id="cc9b1-154">Приложение устанавливается на устройствах в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="cc9b1-155">ММД — *имя приложения* — обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9b1-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="cc9b1-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="cc9b1-156">Uninstall</span></span> |  <span data-ttu-id="cc9b1-157">Приложение удалено с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="cc9b1-158">ММД — *имя приложения* — удаление</span><span class="sxs-lookup"><span data-stu-id="cc9b1-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="cc9b1-159">Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить приложение с компьютера, управляемого Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="cc9b1-160">Шаг 3: назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="cc9b1-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="cc9b1-161">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="cc9b1-162">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="cc9b1-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="cc9b1-163">В области управляемый Рабочий стол выберите пункт **приложения** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="cc9b1-164">В рабочей нагрузке приложений выберите приложение, которому вы хотите назначить пользователей, и выберите **назначить группы пользователей** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="cc9b1-165">Для конкретного приложения выберите тип назначения (доступное, необходимое, удалите) и назначьте соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="cc9b1-166">В области назначить приложения нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="cc9b1-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="cc9b1-167">Действия для начала работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cc9b1-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="cc9b1-168">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="cc9b1-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="cc9b1-169">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="cc9b1-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="cc9b1-170">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="cc9b1-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="cc9b1-171">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="cc9b1-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="cc9b1-172">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="cc9b1-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="cc9b1-173">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="cc9b1-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="cc9b1-174">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="cc9b1-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="cc9b1-175">Развертывание приложений (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="cc9b1-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
