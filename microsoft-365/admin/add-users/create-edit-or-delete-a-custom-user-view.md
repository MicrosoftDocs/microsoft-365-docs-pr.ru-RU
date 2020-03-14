---
title: Создание, изменение и удаление настраиваемых представлений пользователей в Office 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Узнайте, как использовать фильтры для создания, изменения или удаления настраиваемого представления пользователя в Office 365.
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "42632957"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="46d15-103">Создание, изменение и удаление настраиваемых представлений пользователей в Office 365</span><span class="sxs-lookup"><span data-stu-id="46d15-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="46d15-p101">Если вы глобальный администратор или администратор управления пользователями Office 365, вы можете создавать настраиваемые представления пользователей для просмотра их подмножества. Эти представления дополняют стандартный набор представлений, входящих в Office 365. Настраиваемые представления пользователей можно создавать, изменять и удалять, а доступны они всем администраторам.</span><span class="sxs-lookup"><span data-stu-id="46d15-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="46d15-107">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="46d15-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="46d15-108">Настраиваемые представления пользователей в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="46d15-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="46d15-109">При создании, изменении или удалении настраиваемого представления пользователя изменения будут отображаться в списке **фильтров** , которые будут видеть все администраторы вашей компании при переходе на страницу **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="46d15-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="46d15-110">Можно создать до 50 настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="46d15-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="46d15-111">При создании, изменении или удалении настраиваемого представления пользователя изменения будут отображаться в списке **представлений** , который будут видеть все администраторы вашей компании при переходе на страницу **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="46d15-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="46d15-112">Можно создать до 50 настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="46d15-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="46d15-113">При создании, изменении или удалении настраиваемого представления пользователя изменения будут отображаться в списке **представлений** , который будут видеть все администраторы вашей компании при переходе на страницу **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="46d15-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="46d15-114">Можно создать до 50 настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="46d15-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="46d15-115">Стандартные представления пользователей отображаются по умолчанию в раскрывающемся списке **фильтров** .</span><span class="sxs-lookup"><span data-stu-id="46d15-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="46d15-116">К стандартным фильтрам относятся **все пользователи**, **лицензированные**пользователи, **гостевые пользователи**, **разрешен вход**, запрещен **Вход**, **нелицензированные пользователи**, **Пользователи с ошибками**, **Администраторы выставления счетов**, **Глобальные администраторы**, **Администраторы служб поддержки**, **Администраторы служб**и **Администраторы управления пользователями**.</span><span class="sxs-lookup"><span data-stu-id="46d15-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="46d15-117">Изменить или удалить стандартные представления нельзя.</span><span class="sxs-lookup"><span data-stu-id="46d15-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="46d15-118">Ниже приведены другие замечания о стандартных представлениях.</span><span class="sxs-lookup"><span data-stu-id="46d15-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="46d15-p106">В некоторых стандартных представлениях сортировка списков, содержащих более 2000 пользователей, не выполняется. Чтобы найти конкретного пользователя в таком списке, используйте поле поиска.</span><span class="sxs-lookup"><span data-stu-id="46d15-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="46d15-p107">Если вы приобрели службы Office 365 не у Майкрософт, и **администраторы выставления счетов** не будут отображаться в списке стандартных представлений. Дополнительные сведения см. в разделе [Назначение ролей администратора](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="46d15-p107">If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list. For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="46d15-123">Выбор фильтров для настраиваемого представления пользователей</span><span class="sxs-lookup"><span data-stu-id="46d15-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="46d15-124">Вы можете создавать и редактировать настраиваемые представления в **настраиваемой области фильтра** .</span><span class="sxs-lookup"><span data-stu-id="46d15-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="46d15-125">Если выбрать несколько вариантов фильтрации, в результаты будут включены пользователи, соответствующие всем условиям.</span><span class="sxs-lookup"><span data-stu-id="46d15-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="46d15-126">В следующем примере показано, как создать настраиваемое представление "Пользователи из Канады", в котором показаны все пользователи определенного домена, находящиеся в Канаде.</span><span class="sxs-lookup"><span data-stu-id="46d15-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="46d15-127">**A – Domain** Если в Организации имеется несколько доменов, можно выбрать из раскрывающегося списка доступных доменов.</span><span class="sxs-lookup"><span data-stu-id="46d15-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="46d15-128">**Состояние B — для входа** Выберите разрешенных или заблокированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="46d15-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="46d15-129">**C — расположение** Выберите расположение из раскрывающегося списка стран.</span><span class="sxs-lookup"><span data-stu-id="46d15-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="46d15-130">**Лицензия D — назначенная продукция** Выберите из раскрывающегося списка лицензий, доступных в Организации.</span><span class="sxs-lookup"><span data-stu-id="46d15-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="46d15-131">При выборе этого фильтра отображаются пользователи, которым назначена выбранная лицензия.</span><span class="sxs-lookup"><span data-stu-id="46d15-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="46d15-132">Отображаемые пользователи могут также иметь и другие лицензии.</span><span class="sxs-lookup"><span data-stu-id="46d15-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="46d15-133">Вы также можете отфильтровать пользователей по дополнительным сведениям профиля, используемым в вашей организации, таким как отдел, город, область или край, должность, страна или регион.</span><span class="sxs-lookup"><span data-stu-id="46d15-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="46d15-134">**Другие условия**:</span><span class="sxs-lookup"><span data-stu-id="46d15-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="46d15-135">**Только синхронизированные пользователи**: при выборе этого параметра отображаются все пользователи, синхронизированные с локальной службой Active Directory независимо от того, были ли они активированы.</span><span class="sxs-lookup"><span data-stu-id="46d15-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="46d15-136">**Пользователи с ошибками**: при выборе этого параметра отображаются пользователи, при подготовке которых возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="46d15-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="46d15-p110">**Пользователи без лицензий**: при выборе этого параметра отображаются все пользователи, которым не назначены лицензии. В результаты этого представления также могут включаться пользователи, которым предоставлен почтовый ящик Exchange, но не назначена лицензия. Чтобы отслеживать таких пользователей отдельно, используйте фильтр **Пользователи без лицензий с почтовыми ящиками или архивами Exchange**. В результаты этого представления также могут включаться пользователи, у которых есть архив Exchange, но нет лицензии.</span><span class="sxs-lookup"><span data-stu-id="46d15-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="46d15-p111">**Пользователи без лицензий с почтовыми ящиками или архивами Exchange**: установите этот флажок, если нужно отобразить учетные записи пользователей, созданные в Exchange Online и связанные с почтовыми ящиками Exchange, но не имеющие лицензии на Office 365. Результаты применения этого фильтра включают пользователей, имеющих архив Exchange.</span><span class="sxs-lookup"><span data-stu-id="46d15-p111">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license. The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 
    
> [!TIP]
> <span data-ttu-id="46d15-143">В настраиваемых представлениях, возвращающих более 2 000 пользователей, сортировка списка результатов не выполняется.</span><span class="sxs-lookup"><span data-stu-id="46d15-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="46d15-144">В этом случае используйте поле поиска для поиска пользователей или изменения настраиваемого представления для уточнения поиска.</span><span class="sxs-lookup"><span data-stu-id="46d15-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="46d15-145">Создание настраиваемого представления пользователя</span><span class="sxs-lookup"><span data-stu-id="46d15-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="46d15-146">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="46d15-147">На странице **Активные пользователи** выберите **фильтры** и нажмите кнопку **создать фильтр**.</span><span class="sxs-lookup"><span data-stu-id="46d15-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="46d15-148">На странице **Настраиваемый фильтр** введите имя фильтра, выберите условия для настраиваемого фильтра, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="46d15-149">Ваше настраиваемое представление теперь включено в раскрывающийся список фильтров.</span><span class="sxs-lookup"><span data-stu-id="46d15-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="46d15-150">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="46d15-151">На странице **Активные пользователи** выберите **представления** и нажмите кнопку **Добавить настраиваемое представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="46d15-152">На странице **настраиваемое представление** введите имя фильтра, выберите условия для настраиваемого фильтра, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="46d15-153">Ваше настраиваемое представление теперь включено в раскрывающийся список фильтров.</span><span class="sxs-lookup"><span data-stu-id="46d15-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="46d15-154">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="46d15-155">На странице **Активные пользователи** выберите **представления** и нажмите кнопку **Добавить настраиваемое представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="46d15-156">На странице **настраиваемое представление** введите имя фильтра, выберите условия для настраиваемого фильтра, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="46d15-157">Ваше настраиваемое представление теперь включено в раскрывающийся список фильтров.</span><span class="sxs-lookup"><span data-stu-id="46d15-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="46d15-158">Изменение или Удаление настраиваемого представления пользователя</span><span class="sxs-lookup"><span data-stu-id="46d15-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="46d15-159">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="46d15-160">На странице **Активные пользователи** выберите **Фильтр**, выберите фильтр, который необходимо изменить, и нажмите кнопку **изменить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="46d15-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="46d15-161">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="46d15-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="46d15-162">На странице **Настраиваемый фильтр** измените нужные сведения, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="46d15-163">Или, чтобы удалить фильтр, в нижней части страницы выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="46d15-164">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="46d15-165">На странице **Активные пользователи** выберите **представления**, выберите фильтр, который необходимо изменить, и нажмите кнопку **изменить это представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="46d15-166">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="46d15-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="46d15-167">На странице **настраиваемое представление** измените нужные сведения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="46d15-168">Или, чтобы удалить фильтр, в нижней части страницы выберите **удалить настраиваемое представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="46d15-169">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="46d15-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="46d15-170">На странице **Активные пользователи** выберите **представления**, выберите фильтр, который необходимо изменить, и нажмите кнопку **изменить это представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="46d15-171">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="46d15-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="46d15-172">На странице **настраиваемое представление** измените нужные сведения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46d15-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="46d15-173">Или, чтобы удалить фильтр, в нижней части страницы выберите **удалить настраиваемое представление**.</span><span class="sxs-lookup"><span data-stu-id="46d15-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     

