---
title: Развертывание приложений для наСтольных устройств, управляемых Майкрософт
description: Сведения для добавления и развертывания приложений на наСтольных устройствах, управляемых корпорацией Майкрософт.
keywords: НаСтольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282525"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="72420-104">Развертывание приложений на наСтольных устройствах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="72420-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="72420-105">Часть входящей миграции на Настольный компьютер Майкрософт с управляемым подключением включает добавление и развертывание приложений на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="72420-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="72420-106">Когда вы используете портал для наСтольных компьютеров Майкрософт, вы можете добавлять и развертывать свои приложения.</span><span class="sxs-lookup"><span data-stu-id="72420-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="72420-107">Общий процесс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72420-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="72420-108">[Добавление приложений на портал для НастольНых ПК, управляемых корпорациЕй Майкрософт](#1) . Это могут быть существующие бизнес-приложения (LOB) или приложения из Microsoft Store для бизнеса, которые вы синхронизированы с Intune.</span><span class="sxs-lookup"><span data-stu-id="72420-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="72420-109">[Создайте группы Azure Active Directory (AD) для назначения приложения](#2) , вы будете использовать эти группы для управления назначением приложения.</span><span class="sxs-lookup"><span data-stu-id="72420-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="72420-110">Назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="72420-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="72420-111">Шаг 1: Добавление приложений на управляемый портал для наСтольных ПК Майкрософт</span><span class="sxs-lookup"><span data-stu-id="72420-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="72420-112">Вы можете добавить [приложения Win32 или Windows MSI](#lob-apps)или [Microsoft Store для бизнес-приложений](#msfb-apps) на компьютер с управляемым учетом Microsoft Store, а затем развернуть их на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="72420-113">Приложения Win32 или Windows MSI для наСтольного компьютера, управляемого Майкрософт</span><span class="sxs-lookup"><span data-stu-id="72420-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="72420-114">Вы можете добавить бизнес-приложения (LOB) на портал для наСтольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="72420-115">Для получения сведений о требованиях к приложениям, установленным на наСтольных компьютерах, управляемых Майкрософт, ознакомьтесь с [требованиями к](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)приложениям, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="72420-116">В этой процедуре показано, как выбрать тип приложения, которое вы хотите добавить, а затем настроить и отправить источник приложения.</span><span class="sxs-lookup"><span data-stu-id="72420-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="72420-117">**Добавление бизнес-приложения или приложения Windows в управляемый портал для наСтольных ПК Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="72420-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="72420-118">Вы можете войти на портал для наСтольных компьютеров Майкрософт или войти в Intune, а затем найти компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="72420-119">Мы покажем вход на портал для наСтольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="72420-120">Войдите на [портал администрирования рабочих столов](http://aka.ms/mmdportal)с управляемЫми правами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="72420-121">В разделе **запасы**выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="72420-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="72420-122">В рабочей нагрузке приложений нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="72420-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="72420-123">В окне **Добавление приложения**выберите **бизнес-приложение** или **приложение Windows (Win32) — Предварительная версия**.</span><span class="sxs-lookup"><span data-stu-id="72420-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="72420-124">Если вы выбрали **бизнес-приложение**, ознакомьтесь со статьей [Добавление бизнес-приложения Windows в Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) для получения инструкций по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="72420-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="72420-125">Если вы выбрали **Windows App (Win32) — Предварительная версия**, ознакомьтесь со статьей [Управление приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) для добавления и настройки приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="72420-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="72420-126">Приложения Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="72420-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="72420-127">Если вы не зарегистрированы в Microsoft Store для бизнеса, вы можете зарегистрироваться при работе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="72420-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="72420-128">После создания приложений вы можете синхронизировать их с наСтольными компьютерами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="72420-129">**Приобретение приложений из Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="72420-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="72420-130">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="72420-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="72420-131">Выберите **магазин для группы**.</span><span class="sxs-lookup"><span data-stu-id="72420-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="72420-132">Используйте поиск, чтобы найти нужное приложение, и выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="72420-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="72420-133">В разделе сведения о продукте выберите пункт **Получение приложения**.</span><span class="sxs-lookup"><span data-stu-id="72420-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="72420-134">Microsoft Store добавляет приложение в **продукты _амп_ Services** для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="72420-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="72420-135">**Принудительная синхронизация между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="72420-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="72420-136">Войдите на [портал Azure](https://portal.azure.com/) как администратор Intune или глобальный администратор для вашего клиента</span><span class="sxs-lookup"><span data-stu-id="72420-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="72420-137">Выберите **все службы _Гт_ Intune**.</span><span class="sxs-lookup"><span data-stu-id="72420-137">Select **All services > Intune**.</span></span> <span data-ttu-id="72420-138">Intune находится в разделе Мониторинг и управление.</span><span class="sxs-lookup"><span data-stu-id="72420-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="72420-139">В области Intune выберите клиентские **приложения**, а затем выберите **Microsoft Store для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="72420-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="72420-140">Выберите **включить** , чтобы синхронизировать приложения Microsoft Store для бизнеса с Intune.</span><span class="sxs-lookup"><span data-stu-id="72420-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="72420-141">Если вы еще не сделали это, выполните вход и связывание учетной записи Microsoft Store для бизнеса с Intune</span><span class="sxs-lookup"><span data-stu-id="72420-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="72420-142">Выберите язык, на котором будут отображаться приложения из Microsoft Store для бизнеса в консоли Intune</span><span class="sxs-lookup"><span data-stu-id="72420-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="72420-143">Выберите **синхронизировать** для синхронизации приложений Microsoft Store для бизнеса с Intune.</span><span class="sxs-lookup"><span data-stu-id="72420-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="72420-144">Убедитесь, что синхронизация между Microsoft Store для бизнеса и Intune активна (следующий шаг).</span><span class="sxs-lookup"><span data-stu-id="72420-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="72420-145">**Проверка активности синхронизации между Intune и Microsoft Store для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="72420-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="72420-146">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="72420-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="72420-147">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="72420-147">Select **Manage**.</span></span>
3. <span data-ttu-id="72420-148">Выберите **Параметры** и нажмите кнопку **распределить**.</span><span class="sxs-lookup"><span data-stu-id="72420-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="72420-149">В разделе **средства управления**убедитесь, что в списке присутствует служба Intune и состояние **активна**.</span><span class="sxs-lookup"><span data-stu-id="72420-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="72420-150">Шаг 2: создание групп Azure AD</span><span class="sxs-lookup"><span data-stu-id="72420-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="72420-151">Создайте три группы Azure AD для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="72420-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="72420-152">В этой таблице перечислены необходимые группы (доступные, обязательные и удаляемые).</span><span class="sxs-lookup"><span data-stu-id="72420-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="72420-153">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="72420-153">App assignment type</span></span> |   <span data-ttu-id="72420-154">Использование группы</span><span class="sxs-lookup"><span data-stu-id="72420-154">Group use</span></span>   | <span data-ttu-id="72420-155">Пример имени Azure AD</span><span class="sxs-lookup"><span data-stu-id="72420-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="72420-156">Available</span><span class="sxs-lookup"><span data-stu-id="72420-156">Available</span></span> |  <span data-ttu-id="72420-157">Приложение будет доступно из приложения или веб-сайта корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="72420-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="72420-158">ММД — *имя приложения* — доступно</span><span class="sxs-lookup"><span data-stu-id="72420-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="72420-159">Обязательный</span><span class="sxs-lookup"><span data-stu-id="72420-159">Required</span></span> |  <span data-ttu-id="72420-160">Приложение устанавливается на устройствах в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="72420-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="72420-161">ММД — *имя приложения* — обязательный</span><span class="sxs-lookup"><span data-stu-id="72420-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="72420-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="72420-162">Uninstall</span></span> |  <span data-ttu-id="72420-163">Приложение пароль удаляется с устройств в выбранных группах.</span><span class="sxs-lookup"><span data-stu-id="72420-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="72420-164">ММД — *имя приложения* — удаление</span><span class="sxs-lookup"><span data-stu-id="72420-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="72420-165">Добавьте пользователей в эти группы, чтобы сделать приложение доступ, установить приложение или удалить приложение с компьютера, управляемого Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="72420-166">Шаг 3: назначение приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="72420-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="72420-167">**Назначение приложения пользователям**</span><span class="sxs-lookup"><span data-stu-id="72420-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="72420-168">Войдите на [портал администрирования рабочих столов](http://aka.ms/mmdportal)с управляемЫми правами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72420-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="72420-169">В области управляемый Рабочий стол выберите пункт **приложения**.</span><span class="sxs-lookup"><span data-stu-id="72420-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="72420-170">В рабочей нагрузке приложений выберите приложение, которому вы хотите назначить пользователей, и выберите **назначить группы пользователей**.</span><span class="sxs-lookup"><span data-stu-id="72420-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="72420-171">Для конкретного приложения выберите тип назначения (доступное, необходимое, удалите) и назначьте соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="72420-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="72420-172">В области назначить приложения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72420-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->