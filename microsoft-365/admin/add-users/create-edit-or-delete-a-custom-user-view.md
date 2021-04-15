---
title: Создание, изменение и удаление настраиваемых представлений пользователей
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Узнайте, как использовать фильтры для создания, редактирования или удаления пользовательского представления пользователя в Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755576"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="33567-103">Создание, изменение и удаление настраиваемых представлений пользователей</span><span class="sxs-lookup"><span data-stu-id="33567-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="33567-104">Если вы администратор глобального или пользовательского управления microsoft 365 для подписки на бизнес, вы можете создать настраиваемые представления пользователей для просмотра определенного подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="33567-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="33567-105">Эти представления в дополнение к стандартному набору представлений.</span><span class="sxs-lookup"><span data-stu-id="33567-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="33567-106">Настраиваемые представления пользователей можно создавать, изменять и удалять, а доступны они всем администраторам.</span><span class="sxs-lookup"><span data-stu-id="33567-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="33567-107">Пользовательские представления пользователей в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="33567-107">Custom user views in the admin center</span></span>

<span data-ttu-id="33567-108">При создании, редактировании или удалении пользовательского представления изменения будут показаны в списке **Filter,** который видят все администраторы в вашей компании, когда они перейдут на страницу **Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="33567-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="33567-109">Можно создать до 50 настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="33567-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="33567-110">Стандартные представления пользователей отображаются по умолчанию в выпадаемом списке **Фильтры.**</span><span class="sxs-lookup"><span data-stu-id="33567-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="33567-111">Стандартные фильтры включают всех пользователей **,** лицензированных пользователей **,** гостевых пользователей **,** Вход **разрешено** **,** Вход заблокирован **,** Нелицензированная пользователей **,** Пользователи с ошибками **,** Биллинг администраторы **,** Глобальные администраторы , **Helpdesk** администраторы , **администраторы** службы и администраторы управления пользователями **.**</span><span class="sxs-lookup"><span data-stu-id="33567-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="33567-112">Изменить или удалить стандартные представления нельзя.</span><span class="sxs-lookup"><span data-stu-id="33567-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="33567-113">Ниже приведены другие замечания о стандартных представлениях.</span><span class="sxs-lookup"><span data-stu-id="33567-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="33567-p104">В некоторых стандартных представлениях сортировка списков, содержащих более 2000 пользователей, не выполняется. Чтобы найти конкретного пользователя в таком списке, используйте поле поиска.</span><span class="sxs-lookup"><span data-stu-id="33567-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="33567-116">Если вы не приобретли Microsoft 365 у **Microsoft,** администраторы биллинга не отображаются в списке стандартных представлений.</span><span class="sxs-lookup"><span data-stu-id="33567-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="33567-117">Дополнительные сведения см. в [дополнительных сведениях о назначении ролей администратора.](assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="33567-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="33567-118">Выбор фильтров для настраиваемого представления пользователей</span><span class="sxs-lookup"><span data-stu-id="33567-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="33567-119">Вы можете создавать и редактировать настраиваемые представления в области **настраиваемой фильтрации.**</span><span class="sxs-lookup"><span data-stu-id="33567-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="33567-120">Если выбрать несколько вариантов фильтрации, в результаты будут включены пользователи, соответствующие всем условиям.</span><span class="sxs-lookup"><span data-stu-id="33567-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="33567-121">В следующем примере показано, как создать настраиваемое представление "Пользователи из Канады", в котором показаны все пользователи определенного домена, находящиеся в Канаде.</span><span class="sxs-lookup"><span data-stu-id="33567-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="33567-122">**A — домен** Если у вас несколько доменов для организации, вы можете выбрать из выпадаемого списка доступных доменов.</span><span class="sxs-lookup"><span data-stu-id="33567-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="33567-123">**B . Состояние входной группы** Выберите пользователей, которые разрешены или заблокированы.</span><span class="sxs-lookup"><span data-stu-id="33567-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="33567-124">**C — расположение** Выберите расположение из выпадаемого списка стран.</span><span class="sxs-lookup"><span data-stu-id="33567-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="33567-125">**D — назначенная лицензия на продукт** Выберите из выпадаемого списка лицензий, доступных в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="33567-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="33567-126">При выборе этого фильтра отображаются пользователи, которым назначена выбранная лицензия.</span><span class="sxs-lookup"><span data-stu-id="33567-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="33567-127">Отображаемые пользователи могут также иметь и другие лицензии.</span><span class="sxs-lookup"><span data-stu-id="33567-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="33567-128">Вы также можете отфильтровать пользователей по дополнительным сведениям профиля, используемым в вашей организации, таким как отдел, город, область или край, должность, страна или регион.</span><span class="sxs-lookup"><span data-stu-id="33567-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="33567-129">**Другие условия**:</span><span class="sxs-lookup"><span data-stu-id="33567-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="33567-130">**Только синхронизированные пользователи**: при выборе этого параметра отображаются все пользователи, синхронизированные с локальной службой Active Directory независимо от того, были ли они активированы.</span><span class="sxs-lookup"><span data-stu-id="33567-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="33567-131">**Пользователи с ошибками**: при выборе этого параметра отображаются пользователи, при подготовке которых возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="33567-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="33567-p108">**Пользователи без лицензий**: при выборе этого параметра отображаются все пользователи, которым не назначены лицензии. В результаты этого представления также могут включаться пользователи, которым предоставлен почтовый ящик Exchange, но не назначена лицензия. Чтобы отслеживать таких пользователей отдельно, используйте фильтр **Пользователи без лицензий с почтовыми ящиками или архивами Exchange**. В результаты этого представления также могут включаться пользователи, у которых есть архив Exchange, но нет лицензии.</span><span class="sxs-lookup"><span data-stu-id="33567-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="33567-136">**Нелицензионные пользователи с почтовыми ящиками и архивами Exchange** Выберите этот поле, чтобы показать учетные записи пользователей, созданные в Exchange Online и в которых есть почтовый ящик Exchange, но им не была назначена лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33567-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="33567-137">Результаты применения этого фильтра включают пользователей, имеющих архив Exchange.</span><span class="sxs-lookup"><span data-stu-id="33567-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="33567-138">**Нелицензионные пользователи с фильтром почтовых ящиков Exchange** работают, когда:</span><span class="sxs-lookup"><span data-stu-id="33567-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="33567-139">Почтовый ящик недавно был преобразован  из общего в **пользовательский** и не имеет лицензии.</span><span class="sxs-lookup"><span data-stu-id="33567-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="33567-140">Почтовый ящик недавно был перенесен в Microsoft 365, но лицензия не назначена.</span><span class="sxs-lookup"><span data-stu-id="33567-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="33567-141">Почтовый ящик создан с помощью PowerShell, лицензия не назначена.</span><span class="sxs-lookup"><span data-stu-id="33567-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="33567-142">Для пользователя создается новый почтовый ящикNew-RemoteMailbox созданный локально.</span><span class="sxs-lookup"><span data-stu-id="33567-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="33567-143">В настраиваемых представлениях, возвращающих более 2 000 пользователей, сортировка списка результатов не выполняется.</span><span class="sxs-lookup"><span data-stu-id="33567-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="33567-144">В этом случае используйте поле поиска для поиска пользователей или изменения пользовательского представления для уточнения поиска.</span><span class="sxs-lookup"><span data-stu-id="33567-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="33567-145">Создание настраиваемой пользовательской точки зрения</span><span class="sxs-lookup"><span data-stu-id="33567-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="33567-146">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="33567-147">На странице **Активные пользователи** выберите **фильтры** и выберите **Новый фильтр.**</span><span class="sxs-lookup"><span data-stu-id="33567-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="33567-148">На странице **Настраиваемый фильтр** введите имя фильтра, выберите условия для настраиваемой фильтра, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="33567-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="33567-149">Теперь настраиваемый вид включен в список фильтров.</span><span class="sxs-lookup"><span data-stu-id="33567-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="33567-150">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="33567-151">На странице **Активные пользователи** выберите **Представления** и выберите **Добавить настраиваемую точку зрения.**</span><span class="sxs-lookup"><span data-stu-id="33567-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="33567-152">На странице **Настраиваемые представления** введите имя фильтра, выберите условия для настраиваемой фильтра, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="33567-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="33567-153">Теперь настраиваемый вид включен в список фильтров.</span><span class="sxs-lookup"><span data-stu-id="33567-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="33567-154">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="33567-155">На странице **Активные пользователи** выберите **Представления** и выберите **Добавить настраиваемую точку зрения.**</span><span class="sxs-lookup"><span data-stu-id="33567-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="33567-156">На странице **Настраиваемые представления** введите имя фильтра, выберите условия для настраиваемой фильтра, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="33567-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="33567-157">Теперь настраиваемый вид включен в список фильтров.</span><span class="sxs-lookup"><span data-stu-id="33567-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="33567-158">Изменение или удаление пользовательского представления</span><span class="sxs-lookup"><span data-stu-id="33567-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="33567-159">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="33567-160">На странице **Активные пользователи** выберите **фильтр,** выберите фильтр, который необходимо изменить, а затем выберите **фильтр Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33567-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="33567-161">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="33567-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="33567-162">На странице **Настраиваемый фильтр** отредактировать сведения по мере необходимости, а затем выбрать **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="33567-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="33567-163">Или, чтобы удалить фильтр, в нижней части страницы выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="33567-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="33567-164">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="33567-165">На странице **Активные пользователи** выберите **Представления,** выберите фильтр, который необходимо изменить, а затем **измените это представление.**</span><span class="sxs-lookup"><span data-stu-id="33567-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="33567-166">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="33567-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="33567-167">На странице **Настраиваемые представления** отредактируете сведения по мере необходимости, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="33567-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="33567-168">Или, чтобы удалить фильтр, в нижней части страницы выберите **Удаление настраиваемого представления**.</span><span class="sxs-lookup"><span data-stu-id="33567-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="33567-169">В центре администрирования перейдите к **пользователям** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active.</a></span><span class="sxs-lookup"><span data-stu-id="33567-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="33567-170">На странице **Активные пользователи** выберите **Представления,** выберите фильтр, который необходимо изменить, а затем **измените это представление.**</span><span class="sxs-lookup"><span data-stu-id="33567-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="33567-171">Вы можете изменять только настраиваемые представления.</span><span class="sxs-lookup"><span data-stu-id="33567-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="33567-172">На странице **Настраиваемые представления** отредактируете сведения по мере необходимости, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="33567-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="33567-173">Или, чтобы удалить фильтр, в нижней части страницы выберите **Удаление настраиваемого представления**.</span><span class="sxs-lookup"><span data-stu-id="33567-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     