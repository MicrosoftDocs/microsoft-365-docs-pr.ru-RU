---
title: Развертывание приложений для Microsoft Desktop управляемых устройств
description: Сведения по добавлению и развертывание приложений Microsoft Desktop управляемых устройств.
keywords: Microsoft Desktop управляемых, 365 Майкрософт, службы, документации, приложения, бизнес-приложений, бизнес-приложений
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341618"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="b3e9b-104">Развертывание приложений для Microsoft Desktop управляемых устройств</span><span class="sxs-lookup"><span data-stu-id="b3e9b-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="b3e9b-p101">Часть адаптация новых сотрудников к рабочему столу управляемых Microsoft включает добавление и развертывание приложений для устройства конечных пользователей. Если вы используете портал Microsoft Desktop управляемых, можно добавить и развертывание приложений.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="b3e9b-107">Весь процесс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="b3e9b-108">[Установка приложений на портале Microsoft Desktop управляемых](#1) - это может существующих приложений бизнес (LOB) или приложений из хранилища Майкрософт для бизнеса, синхронизирован с Intune.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="b3e9b-109">[Создание Azure Active Directory (AD) группы для назначения приложения](#2) — эти группы будет использовать для управления назначения приложения.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="b3e9b-110">Назначение приложений для пользователей</span><span class="sxs-lookup"><span data-stu-id="b3e9b-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="b3e9b-111">Шаг 1: Добавление приложений Microsoft Desktop управляемых портала</span><span class="sxs-lookup"><span data-stu-id="b3e9b-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="b3e9b-112">Добавление [Win32, приложений на основе Windows MSI](#lob-apps)или [Microsoft хранилища для бизнес-приложений](#msfb-apps) Microsoft Desktop управляемых и разверните их Microsoft Desktop управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="b3e9b-113">Win32 или Windows приложений на основе MSI, в корпорацию Майкрософт управляемого рабочего стола</span><span class="sxs-lookup"><span data-stu-id="b3e9b-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="b3e9b-p102">Портал Microsoft Desktop управляемых можно добавить ваших приложений бизнес (LOB). Сведения о требованиях для установки на устройствах Microsoft Desktop управляемых приложений в разделе [requirements приложения Microsoft Desktop управляемых](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="b3e9b-116">В этой процедуре будет предложено выбрать тип приложения, необходимо добавить и настройка и отправка исходного приложения.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="b3e9b-117">**Чтобы добавить БИЗНЕС-приложение или приложение Windows на портале Microsoft Desktop управляемых**</span><span class="sxs-lookup"><span data-stu-id="b3e9b-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="b3e9b-p103">Можно вход на портал Microsoft Desktop управляемых или вход на портал Intune и затем найдите рабочий стол управляемых Microsoft. Вы увидите вход в портал Microsoft управляемых Desktop.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="b3e9b-120">Войдите в [портал Microsoft управляемого рабочего стола администратора](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b3e9b-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="b3e9b-121">В разделе **запасов**выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="b3e9b-122">В рабочую нагрузку приложения затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="b3e9b-123">В **приложении добавить**выберите **бизнес - приложение** или **приложение Windows (Win32) - предварительного просмотра**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="b3e9b-124">Если вы выбрали **бизнес - приложения**, в разделе [Add бизнес - приложения Windows Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) инструкции по добавлению и настройке бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="b3e9b-125">Если выбран **Предварительный просмотр приложения Windows (Win32) -** видеть [управления приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) инструкции по добавлению и настройке приложения для Windows.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="b3e9b-126">Хранилище Microsoft для бизнес-приложений</span><span class="sxs-lookup"><span data-stu-id="b3e9b-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="b3e9b-p104">Если вы еще не зарегистрированы хранилища Майкрософт для бизнеса, вы можете воспользоваться при покупке приложений. После того как ваших приложений можно синхронизировать их на рабочий стол управляемых Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="b3e9b-129">**Покупки приложения из магазина корпорации Майкрософт для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b3e9b-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="b3e9b-130">Войдите в [Microsoft хранилища для бизнеса](https://businessstore.microsoft.com) с хранилищем Microsoft для учетной записи администратора предприятия.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b3e9b-131">Выберите **Поиск моей группы**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="b3e9b-132">Поиск, приложения, который будет и выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="b3e9b-p105">На сведения о продукте выберите **получить приложение**. Хранилище Microsoft добавляет приложение **службы & продуктов** для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="b3e9b-135">**Для принудительной синхронизации между Intune и хранилища Майкрософт для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b3e9b-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="b3e9b-136">Войдите в [Портал Azure](https://portal.azure.com/) как глобальный администратор или администратор Intune для клиента</span><span class="sxs-lookup"><span data-stu-id="b3e9b-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="b3e9b-p106">Выберите **все службы > Intune**. Intune возможности мониторинга + управления раздела.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="b3e9b-139">В области Intune выберите **Клиентских приложений**и выберите **Microsoft хранилища для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="b3e9b-140">Установите флажок **Включить** синхронизацию хранилища Майкрософт для бизнес-приложений с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="b3e9b-141">Если это еще не сделано, sign up и свяжите Microsoft хранения для учетной записи бизнеса с Intune</span><span class="sxs-lookup"><span data-stu-id="b3e9b-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="b3e9b-142">Выберите язык отображения приложений в магазине Майкрософт для бизнеса в консоль Intune</span><span class="sxs-lookup"><span data-stu-id="b3e9b-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="b3e9b-143">Выберите **синхронизации** для синхронизации хранилища Майкрософт для бизнес-приложений с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="b3e9b-144">Убедитесь, что синхронизация между хранилища Майкрософт для бизнеса и Intune является активной (Далее).</span><span class="sxs-lookup"><span data-stu-id="b3e9b-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="b3e9b-145">**Проверка синхронизации между Intune и хранилища Майкрософт для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b3e9b-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="b3e9b-146">Войдите в [Microsoft хранилища для бизнеса](https://businessstore.microsoft.com) с хранилищем Microsoft для учетной записи администратора предприятия.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b3e9b-147">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-147">Select **Manage**.</span></span>
3. <span data-ttu-id="b3e9b-148">Выберите **Параметры** , а затем выберите **распределить**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="b3e9b-149">В разделе **средства управления**убедитесь, что указано Intune и что состояние является **активным**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="b3e9b-150">Шаг 2: Создание группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="b3e9b-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="b3e9b-p107">Создайте три группы Azure AD для каждого приложения. В этой таблице перечислены группы, вам потребуются (доступен, необходимо и удалить).</span><span class="sxs-lookup"><span data-stu-id="b3e9b-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="b3e9b-153">Тип назначения приложения</span><span class="sxs-lookup"><span data-stu-id="b3e9b-153">App assignment type</span></span> |   <span data-ttu-id="b3e9b-154">Использование группы</span><span class="sxs-lookup"><span data-stu-id="b3e9b-154">Group use</span></span>   | <span data-ttu-id="b3e9b-155">Имя примера Azure AD</span><span class="sxs-lookup"><span data-stu-id="b3e9b-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="b3e9b-156">Доступно</span><span class="sxs-lookup"><span data-stu-id="b3e9b-156">Available</span></span> |  <span data-ttu-id="b3e9b-157">Приложение будет доступно из приложения портала компании или веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="b3e9b-158">MMD — *имя приложения* — доступен</span><span class="sxs-lookup"><span data-stu-id="b3e9b-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="b3e9b-159">Обязательный</span><span class="sxs-lookup"><span data-stu-id="b3e9b-159">Required</span></span> |  <span data-ttu-id="b3e9b-160">Приложение устанавливается на устройствах в выбранных групп.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="b3e9b-161">MMD — *имя приложения* — требуется</span><span class="sxs-lookup"><span data-stu-id="b3e9b-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="b3e9b-162">"Удалить",</span><span class="sxs-lookup"><span data-stu-id="b3e9b-162">Uninstall</span></span> |  <span data-ttu-id="b3e9b-163">Установлено приложение удаляется из устройств в выбранных групп.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="b3e9b-164">MMD — *имя приложения* — удаление</span><span class="sxs-lookup"><span data-stu-id="b3e9b-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="b3e9b-165">Добавьте пользователей в эти группы сделать доступных приложений, установка приложения или удалить приложения из свои устройства Microsoft управляемых Desktop.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="b3e9b-166">Шаг 3: Назначение приложений для пользователей</span><span class="sxs-lookup"><span data-stu-id="b3e9b-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="b3e9b-167">**Чтобы назначить приложение для пользователей**</span><span class="sxs-lookup"><span data-stu-id="b3e9b-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="b3e9b-168">Войдите в [портал Microsoft управляемого рабочего стола администратора](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="b3e9b-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b3e9b-169">В области управляемого рабочего стола выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="b3e9b-170">В рабочую нагрузку приложения выберите приложения, которые необходимо назначить пользователям и выберите пункт **назначить группы пользователей**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="b3e9b-171">Для конкретного приложения выберите тип назначения (доступен, необходимости удаления) и назначьте соответствующие группы.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="b3e9b-172">В области Назначение приложения нажмите **кнопку OK**.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-172">In the Assign Apps pane, select **OK**.</span></span>

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