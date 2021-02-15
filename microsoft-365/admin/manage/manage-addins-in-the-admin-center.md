---
title: Управление надстройками в Центре администрирования
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте об использовании централизованных надстройок для развертывания надстройки для пользователей и групп в организации.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114205"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="95656-103">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="95656-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="95656-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="95656-104">The admin center is changing.</span></span> <span data-ttu-id="95656-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="95656-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="95656-106">Надстройки Office помогают персонализировать документы и упрощают доступ к информации в Интернете (см. "Пуск с помощью надстройки [Office").](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="95656-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="95656-107">После того как администратор развернет надстройки для пользователей в организации, администратор может отключить или включить надстройки, редактировать, удалять и управлять доступом к надстройки.</span><span class="sxs-lookup"><span data-stu-id="95656-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="95656-108">Дополнительные сведения об установке надстройки из Центра администрирования см. в подстройки "Развертывание" в [Центре администрирования.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="95656-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="95656-109">Состояния надстроек</span><span class="sxs-lookup"><span data-stu-id="95656-109">Add-in states</span></span>

<span data-ttu-id="95656-110">Надстройка может быть в состоянии **"Включаем"** или **"Выключите".**</span><span class="sxs-lookup"><span data-stu-id="95656-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="95656-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="95656-111">**State**</span></span>|<span data-ttu-id="95656-112">**Механизм перехода**</span><span class="sxs-lookup"><span data-stu-id="95656-112">**How the state occurs**</span></span>|<span data-ttu-id="95656-113">**Влияние**</span><span class="sxs-lookup"><span data-stu-id="95656-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95656-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="95656-114">**Active**</span></span>  <br/> |<span data-ttu-id="95656-115">Администратор загрузил надстройки и настроил ее пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="95656-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="95656-116">Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.</span><span class="sxs-lookup"><span data-stu-id="95656-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="95656-117">**Отключена**</span><span class="sxs-lookup"><span data-stu-id="95656-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="95656-118">Администратор отключил надстройку.</span><span class="sxs-lookup"><span data-stu-id="95656-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="95656-119">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="95656-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="95656-120">Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="95656-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="95656-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="95656-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="95656-122">Администратор удалил надстройку.</span><span class="sxs-lookup"><span data-stu-id="95656-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="95656-123">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="95656-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="95656-124">Рассмотрите возможность удаления надстройки, если она больше не используется.</span><span class="sxs-lookup"><span data-stu-id="95656-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="95656-125">Например, отключение надстройки имеет смысл, если она используется только в определенные периоды года.</span><span class="sxs-lookup"><span data-stu-id="95656-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="95656-126">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="95656-126">Delete an add-in</span></span>

<span data-ttu-id="95656-127">Вы также можете удалить развернутую надстройки.</span><span class="sxs-lookup"><span data-stu-id="95656-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="95656-128">В Центре администрирования перейдите на страницу **"Службы**  >  **& надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="95656-129">Центр администрирования обновляется до интерфейса развертывания с помощью интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="95656-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="95656-130">Если вы не видите вышеперечисленные действия, перейдите в раздел "Централизованное развертывание", перейдите в раздел "Интегрированные приложения  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="95656-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="95656-131">В верхней части страницы **"Интегрированные приложения"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="95656-132">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="95656-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="95656-133">Щелкните **"Удалить надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="95656-134">Удалите кнопку надстройки в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="95656-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="95656-135">Проверьте выбор и выберите **"Удалить надстройку".**</span><span class="sxs-lookup"><span data-stu-id="95656-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="95656-136">Изменение доступа к надстройки</span><span class="sxs-lookup"><span data-stu-id="95656-136">Edit add-in access</span></span>

<span data-ttu-id="95656-137">После развертывания администраторы также могут управлять доступом пользователей к надстройки.</span><span class="sxs-lookup"><span data-stu-id="95656-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="95656-138">В Центре администрирования перейдите на страницу **"Службы**  >  **& надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="95656-139">Центр администрирования обновляется до интерфейса развертывания с помощью интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="95656-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="95656-140">Если вы не видите вышеперечисленные действия, перейдите в раздел "Централизованное развертывание", перейдите в раздел "Интегрированные приложения  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="95656-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="95656-141">В верхней части страницы **"Интегрированные приложения"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="95656-142">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="95656-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="95656-143">Нажмите **кнопку "Изменить"** в **области "Кто имеет доступ".**</span><span class="sxs-lookup"><span data-stu-id="95656-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="95656-144">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="95656-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="95656-145">Запретить загрузку надстройки, отключив Магазин Office для всех клиентов (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="95656-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="95656-146">Установка надстройки Outlook управляется другим [процессом.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95656-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="95656-147">Как организация вы можете запретить скачивание новых надстройок Office из Магазина Office.</span><span class="sxs-lookup"><span data-stu-id="95656-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="95656-148">Это можно использовать в сочетании с централизованным развертыванием, чтобы обеспечить развертывание только утвержденных организацией надстройок для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="95656-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="95656-149">**Отключение приобретения надстройки**</span><span class="sxs-lookup"><span data-stu-id="95656-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="95656-150">В центре администрирования перейдите в раздел **Параметры** \> [Услуги&amp;](https://go.microsoft.com/fwlink/p/?linkid=2053743) надстроек.</span><span class="sxs-lookup"><span data-stu-id="95656-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="95656-151">Центр администрирования обновляется до интерфейса развертывания с помощью интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="95656-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="95656-152">Если вы не видите вышеперечисленные действия, перейдите в раздел "Централизованное развертывание", перейдите в раздел "Интегрированные приложения  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="95656-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="95656-153">В верхней части страницы **"Интегрированные приложения"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="95656-154">Выберите **приложения и службы, которые принадлежат пользователю.**</span><span class="sxs-lookup"><span data-stu-id="95656-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="95656-155">Отпустим параметр, разрешив пользователям доступ к магазину Office.</span><span class="sxs-lookup"><span data-stu-id="95656-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="95656-156">Это не позволит всем пользователям получить следующие надстройки в Магазине.</span><span class="sxs-lookup"><span data-stu-id="95656-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="95656-157">Надстройки для Word, Excel и PowerPoint 2016:</span><span class="sxs-lookup"><span data-stu-id="95656-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="95656-158">Windows</span><span class="sxs-lookup"><span data-stu-id="95656-158">Windows</span></span>
    
  - <span data-ttu-id="95656-159">Mac</span><span class="sxs-lookup"><span data-stu-id="95656-159">Mac</span></span>
    
  - <span data-ttu-id="95656-160">Office</span><span class="sxs-lookup"><span data-stu-id="95656-160">Office</span></span>
    
    
- <span data-ttu-id="95656-161">Приобретения, начиная с **AppSource**</span><span class="sxs-lookup"><span data-stu-id="95656-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="95656-162">Надстройки в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95656-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="95656-163">Пользователь, который пытается получить доступ к Магазину, увидит следующее сообщение: "К **сожалению, Microsoft 365** настроен для предотвращения индивидуального приобретения надстройки Магазина Office".</span><span class="sxs-lookup"><span data-stu-id="95656-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="95656-164">Поддержка отключения Магазина Office доступна в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="95656-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="95656-165">Windows: 16.0.9001 — в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="95656-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="95656-166">Mac: 16.10.18011401 — в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="95656-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="95656-167">iOS: 2.9.18010804 — в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="95656-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="95656-168">Интернет — в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="95656-168">The web - Currently available.</span></span>
    
<span data-ttu-id="95656-169">Это не помешает администратору использовать централизованное развертывание для назначения надстройки из Магазина Office.</span><span class="sxs-lookup"><span data-stu-id="95656-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="95656-170">Чтобы запретить пользователю вход с помощью учетной записи Майкрософт, можно ограничить вход только учетной записью организации.</span><span class="sxs-lookup"><span data-stu-id="95656-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="95656-171">Дополнительные сведения [см. в документах "Удостоверение", "Проверка подлинности" и "Авторизация" в Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95656-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="95656-172">Запретить пользователям доступ к магазину Office также предотвратит загрузку нео [side-ins office для тестирования.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="95656-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="95656-173">Дополнительные данные о пользовательском интерфейсе с надстройки</span><span class="sxs-lookup"><span data-stu-id="95656-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="95656-174">После развертывания надстройки конечные пользователи смогут приступить к ее использованию в своих приложениях Office (см. статью "Запуск с помощью [надстройки Office").](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="95656-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="95656-175">Надстройка отображается на всех платформах, которые поддерживает надстройка.</span><span class="sxs-lookup"><span data-stu-id="95656-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="95656-p110">Если надстройка поддерживает команды, они будут отображаться на ленте Office. В приведенном ниже примере для надстройки **Цитаты** отображается команда **Найти цитату**.</span><span class="sxs-lookup"><span data-stu-id="95656-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Лента Office с ссылками поиска](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="95656-179">Если развернутая надстройка не поддерживает команды надстройки или вы хотите просмотреть все развернутые надстройки, их можно просмотреть с помощью my **Add-ins.**</span><span class="sxs-lookup"><span data-stu-id="95656-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="95656-180">В Word 2016, Excel 2016 или PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="95656-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="95656-181">Выберите **\> "Вставить мои надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="95656-182">Откройте вкладку **Управляются администратором** в окне "Надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="95656-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="95656-183">Дважды щелкните надстройку, которую вы развернули ранее (в данном примере  **Цитаты** ).</span><span class="sxs-lookup"><span data-stu-id="95656-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="95656-184">![Вкладка "Управляемые администратором" на странице надстройки Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="95656-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="95656-185">В Outlook</span><span class="sxs-lookup"><span data-stu-id="95656-185">In Outlook</span></span>

1. <span data-ttu-id="95656-186">На **ленте "Главная"** выберите **"Получить надстройки".**</span><span class="sxs-lookup"><span data-stu-id="95656-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="95656-187">![Кнопка "Хранилище" в Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="95656-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="95656-188">Выберите **"Управляемый администратором"** в левой области.</span><span class="sxs-lookup"><span data-stu-id="95656-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="95656-189">Подробнее</span><span class="sxs-lookup"><span data-stu-id="95656-189">Learn more</span></span>

[<span data-ttu-id="95656-190">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="95656-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="95656-191">Получите дополнительные сведения о создании [надстроек Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="95656-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="95656-192">Для управления надстройки используйте централизованные развертывания [PowerShell.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="95656-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="95656-193">Устранение неполадок: пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="95656-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="95656-194">Несовершеннолетних и приобретение надстройки в Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="95656-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
