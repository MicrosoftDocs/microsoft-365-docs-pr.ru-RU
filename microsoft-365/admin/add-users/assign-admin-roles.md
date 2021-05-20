---
title: Назначение ролей администратора Microsoft 365 администратора
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
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Узнайте, как назначить роли администратора пользователю или нескольким пользователям в вашем бизнесе, чтобы они могли выполнять определенные задачи в центре администратора.
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571869"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="03558-103">Назначение ролей администратора</span><span class="sxs-lookup"><span data-stu-id="03558-103">Assign admin roles</span></span>

<span data-ttu-id="03558-104">Если вы приобрели бизнес-подписку Майкрософт, вы являетсяе глобальным администратором. Это означает, что у вас есть неограниченный контроль над продуктами в подписках, и вы можете получить доступ к большинству данных.</span><span class="sxs-lookup"><span data-stu-id="03558-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="03558-105">Дополнительные сведения см. в статье [О ролях администраторов](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="03558-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="03558-106">При добавления новых пользователей, если вы не назначите им роль администратора, то они *находятся в роли пользователя* и не имеют привилегий администратора ни в одном из центров администратора Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="03558-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="03558-107">Но если вам нужна помощь в получении результатов, вы можете назначить роль администратора пользователю.</span><span class="sxs-lookup"><span data-stu-id="03558-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="03558-108">Например, если вам нужен кто-то, кто поможет сбросить пароли, не следует присваивать им глобальную роль администратора, следует назначить им роль администратора паролей.</span><span class="sxs-lookup"><span data-stu-id="03558-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="03558-109">Чрезмерное количество глобальных администраторов с неограниченным доступом к вашим данным и деловым операциям в сети представляет угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="03558-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="03558-110">Смотреть: Добавить администратора.</span><span class="sxs-lookup"><span data-stu-id="03558-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="03558-111">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="03558-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="03558-112">Назначение ролей администратора</span><span class="sxs-lookup"><span data-stu-id="03558-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="03558-113">Вы можете назначить пользователей на роль 2 различными способами:</span><span class="sxs-lookup"><span data-stu-id="03558-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="03558-114">Вы можете перейти к деталям пользователя и **управлять ролями,** чтобы назначить роль пользователю.</span><span class="sxs-lookup"><span data-stu-id="03558-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="03558-115">Или вы можете перейти к **ролям** и выбрать роль, а затем добавить несколько пользователей к нему.</span><span class="sxs-lookup"><span data-stu-id="03558-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="03558-116">Назначение ролей администратора пользователям, использующим роли</span><span class="sxs-lookup"><span data-stu-id="03558-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="03558-117">В админ-центре перейдите на **роли**.</span><span class="sxs-lookup"><span data-stu-id="03558-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="03558-118">Выберите **вкладки Azure AD** или **Intune** для просмотра ролей администратора, доступных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03558-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="03558-119">Выберите роль администратора, которую вы хотите назначить пользователю.</span><span class="sxs-lookup"><span data-stu-id="03558-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="03558-120">Выберите **назначенных** > **администраторов Добавить**.</span><span class="sxs-lookup"><span data-stu-id="03558-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="03558-121">Ввемите **имя или** **имя пользователя,** а затем выберите пользователя из списка предложений.</span><span class="sxs-lookup"><span data-stu-id="03558-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="03558-122">Добавьте несколько пользователей, пока не будете готовы.</span><span class="sxs-lookup"><span data-stu-id="03558-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="03558-123">Выберите **Сохранить**, а затем пользователь будет добавлен в список назначенных администраторов.</span><span class="sxs-lookup"><span data-stu-id="03558-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="03558-124">Назначение пользователю роли администратора в разделе “Активные пользователи”</span><span class="sxs-lookup"><span data-stu-id="03558-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="03558-125">В центре администратора перейдите на страницу  > [пользователей Active.](https://go.microsoft.com/fwlink/p/?linkid=834822)</span><span class="sxs-lookup"><span data-stu-id="03558-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="03558-126">На странице **Активных пользователей** выберите пользователя, роль администратора которого вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="03558-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="03558-127">В панели вылета, под **ролями,** выберите **роли Управления.**</span><span class="sxs-lookup"><span data-stu-id="03558-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="03558-128">Выберите роль администратора, которую вы хотите назначить пользователю.</span><span class="sxs-lookup"><span data-stu-id="03558-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="03558-129">Если вы не видите роль, которую вы ищете, **выберите Показать все** в нижней части списка.</span><span class="sxs-lookup"><span data-stu-id="03558-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="03558-130">В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="03558-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="03558-131">На странице **Активных пользователей** выберите пользователя, роль администратора которого вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="03558-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="03558-132">В вылете панели, рядом с **ролями**, выберите **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="03558-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="03558-133">Если вы не видите **опцию редактирования,** то у вас нет разрешения на редактирование и вы не можете назначить роли администратора другим людям.</span><span class="sxs-lookup"><span data-stu-id="03558-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="03558-134">Попросите глобального администратора в вашем бизнесе назначить роли для вас.</span><span class="sxs-lookup"><span data-stu-id="03558-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="03558-135">В малом бизнесе владелец бизнеса (лицо, купивший подписку) является глобальным администратором. В крупном бизнесе ключевыми людьми в ИТ-отделе являются глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="03558-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="03558-136">Выберите **индивидуального администратора,** чтобы увидеть список ролей, которые мы настроили для вас.</span><span class="sxs-lookup"><span data-stu-id="03558-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="03558-137">Для описания каждой роли [](about-admin-roles.md) см.</span><span class="sxs-lookup"><span data-stu-id="03558-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="03558-138">В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="03558-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="03558-139">На странице **Активных пользователей** выберите пользователя, роль администратора которого вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="03558-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="03558-140">В вылете панели, рядом с **ролями**, выберите **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="03558-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="03558-141">Если вы не видите **опцию редактирования,** то у вас нет разрешения на редактирование и вы не можете назначить роли администратора другим людям.</span><span class="sxs-lookup"><span data-stu-id="03558-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="03558-142">Попросите глобального администратора в вашем бизнесе назначить роли для вас.</span><span class="sxs-lookup"><span data-stu-id="03558-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="03558-143">В малом бизнесе владелец бизнеса (лицо, купивший подписку) является глобальным администратором. В крупном бизнесе ключевыми людьми в ИТ-отделе являются глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="03558-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="03558-144">Выберите **индивидуального администратора,** чтобы увидеть список ролей, которые мы настроили для вас.</span><span class="sxs-lookup"><span data-stu-id="03558-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="03558-145">Для описания каждой роли [](about-admin-roles.md) см.</span><span class="sxs-lookup"><span data-stu-id="03558-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="03558-146">Назначение ролей администраторов нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="03558-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="03558-147">Если вы знаете PowerShell, [см.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="03558-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="03558-148">Идеально подходит для назначения ролей сотням пользователей.</span><span class="sxs-lookup"><span data-stu-id="03558-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="03558-149">Для назначения ролей десяткам пользователей воспользуйтесь приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="03558-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="03558-150">Проверка ролей администратора в организации</span><span class="sxs-lookup"><span data-stu-id="03558-150">Check admin roles in your organization</span></span>

<span data-ttu-id="03558-151">Возможно, у вас нет правильных разрешений на назначение ролей администратора другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="03558-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="03558-152">Проверьте, есть ли у вас правильные разрешения, или попросите другого администратора назначить вам роли.</span><span class="sxs-lookup"><span data-stu-id="03558-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="03558-153">Вы можете проверить разрешения на роль администратора 2 различными способами:</span><span class="sxs-lookup"><span data-stu-id="03558-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="03558-154">Вы можете перейти к данным пользователя и заглянуть под роли **на** странице **учетной** записи.</span><span class="sxs-lookup"><span data-stu-id="03558-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="03558-155">Или вы можете перейти к **ролям и** выбрать роль администратора, а также выбрать назначенных администраторов, чтобы увидеть, какие пользователи назначены.</span><span class="sxs-lookup"><span data-stu-id="03558-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="03558-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="03558-156">Related content</span></span>

<span data-ttu-id="03558-157">[О Microsoft 365 администратора (статья)](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="03558-157">[About Microsoft 365 admin roles](about-admin-roles.md) (article)</span></span>

<span data-ttu-id="03558-158">[Разрешения на роль администратора в Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (статья)</span><span class="sxs-lookup"><span data-stu-id="03558-158">[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (article)</span></span>

<span data-ttu-id="03558-159">[Назначение ролей учетным записям пользователей с помощью PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="03558-159">[Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (article)</span></span>

<span data-ttu-id="03558-160">[Разрешить или удалить партнерские отношения](../misc/add-partner.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="03558-160">[Authorize or remove partner relationships](../misc/add-partner.md) (article)</span></span>