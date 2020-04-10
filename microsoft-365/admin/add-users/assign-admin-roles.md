---
title: Назначение ролей администратора центра администрирования Microsoft 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Сведения о том, как назначать роли администратора пользователю или нескольким пользователям в вашей организации, чтобы они могли выполнять определенные задачи в центре администрирования.
ms.openlocfilehash: 3f22ef22571dd04dd3364a95ed860f53b8ff207b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211923"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="d5bf9-103">Назначение ролей администратора</span><span class="sxs-lookup"><span data-stu-id="d5bf9-103">Assign admin roles</span></span>

<span data-ttu-id="d5bf9-104">Если вы являетесь лицом, которое приобрели вашу подписку на Microsoft Business, вы являетесь глобальным администратором. Это означает, что у вас есть неограниченный контроль над продуктами в подписках и вы можете получить доступ к большинству данных.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="d5bf9-105">Более подробную информацию можно узнать в статье [сведения о ролях администратора](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d5bf9-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="d5bf9-106">При добавлении новых пользователей, если им не назначена роль администратора, они находятся в *роли пользователя* и не имеют прав администратора для всех центров администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="d5bf9-107">Но если вам нужна помощь по выполнению своих задач, вы можете назначить роль администратора пользователю.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="d5bf9-108">Например, если вам требуется кто-то помочь вам сбросить пароли, вам не следует назначать им роль глобального администратора, назначьте им роль администратора паролей.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="d5bf9-109">Наличие слишком большого числа глобальных администраторов с неограниченным доступом к данным и интерактивному бизнесу является угрозой безопасности.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

<span data-ttu-id="d5bf9-110">Посмотрите короткое видео о добавлении администратора.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-110">Watch a short video about adding an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="d5bf9-111">Если вам был полезен этот видеоролик, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="d5bf9-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="d5bf9-112">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

## <a name="assign-admin-roles"></a><span data-ttu-id="d5bf9-113">Назначение ролей администратора</span><span class="sxs-lookup"><span data-stu-id="d5bf9-113">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="d5bf9-114">Назначить пользователей для роли можно двумя различными способами:</span><span class="sxs-lookup"><span data-stu-id="d5bf9-114">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="d5bf9-115">Вы можете перейти к сведениям о пользователе и **управлять ролями** , чтобы назначить роль пользователю.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-115">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="d5bf9-116">Кроме того, можно перейти к **роли** и выбрать роль, а затем добавить в нее нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-116">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="d5bf9-117">Назначение ролей администратора пользователям с помощью ролей</span><span class="sxs-lookup"><span data-stu-id="d5bf9-117">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="d5bf9-118">В центре администрирования **перейдите к** > **роли** ролей, чтобы просмотреть все роли администратора, доступные в Организации.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-118">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="d5bf9-119">Выберите роль администратора, которой нужно назначить пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="d5bf9-120">Выберите **назначенные администраторы** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="d5bf9-121">Введите **Отображаемое имя** **пользователя или имя пользователя,** а затем выберите пользователя в списке предложений.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="d5bf9-122">Добавьте нескольких пользователей, пока не закончите работу.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="d5bf9-123">Нажмите кнопку **сохранить**, а затем пользователь будет добавлен в список назначенных администраторов.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="d5bf9-124">Назначение пользователю роли администратора из активных пользователей</span><span class="sxs-lookup"><span data-stu-id="d5bf9-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="d5bf9-125">В центре администрирования перейдите на страницу **Пользователи** > [Активные пользователи](https://go.microsoft.com/fwlink/p/?linkid=834822) .</span><span class="sxs-lookup"><span data-stu-id="d5bf9-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="d5bf9-126">На странице **Активные пользователи** выберите пользователя, роль администратора которого требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="d5bf9-127">В раскрывающейся области рядом с пунктом **роли**выберите **Управление ролями**.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-127">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="d5bf9-128">Выберите роль администратора, которую необходимо назначить пользователю.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="d5bf9-129">Если вам не удается найти нужную роль, выберите **Показать все** в нижней части списка.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d5bf9-130">В центре администрирования перейдите в раздел \*\*Пользователи \*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d5bf9-131">На странице **Активные пользователи** выберите пользователя, роль администратора которого требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="d5bf9-132">В раскрывающейся области рядом с пунктом **роли**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="d5bf9-133">Если вы не видите параметр **изменить** , у вас нет разрешения на изменение и назначение ролей администратора другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="d5bf9-134">Запросите глобального администратора вашей организации, чтобы назначить им роли.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="d5bf9-135">В небольших организациях бизнес-владелец (пользователь, который приобрел подписку) является глобальным администратором. В крупных организациях основные сотрудники ИТ-отдела являются глобальными администраторами.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="d5bf9-136">Выберите **Настраиваемый администратор** , чтобы просмотреть список ролей, которые мы настроили.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="d5bf9-137">Описание каждой роли можно узнать в статье [сведения о ролях администратора.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d5bf9-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d5bf9-138">В центре администрирования перейдите в раздел \*\*Пользователи \*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d5bf9-139">На странице **Активные пользователи** выберите пользователя, роль администратора которого требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="d5bf9-140">В раскрывающейся области рядом с пунктом **роли**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="d5bf9-141">Если вы не видите параметр **изменить** , у вас нет разрешения на изменение и назначение ролей администратора другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="d5bf9-142">Запросите глобального администратора вашей организации, чтобы назначить им роли.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="d5bf9-143">В небольших организациях бизнес-владелец (пользователь, который приобрел подписку) является глобальным администратором. В крупных организациях основные сотрудники ИТ-отдела являются глобальными администраторами.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="d5bf9-144">Выберите **Настраиваемый администратор** , чтобы просмотреть список ролей, которые мы настроили.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="d5bf9-145">Описание каждой роли можно узнать в статье [сведения о ролях администратора.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d5bf9-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="d5bf9-146">Назначение ролей администраторов нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="d5bf9-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="d5bf9-147">Если вы знаете PowerShell, ознакомьтесь [со статьей назначение ролей учетным записям пользователей с помощью PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span><span class="sxs-lookup"><span data-stu-id="d5bf9-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span></span> <span data-ttu-id="d5bf9-148">Он идеально подходит для назначения ролей сотням пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="d5bf9-149">Для назначения ролей десяткам пользователей воспользуйтесь приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a><span data-ttu-id="d5bf9-150">Не помогло?</span><span class="sxs-lookup"><span data-stu-id="d5bf9-150">Didn't work for you?</span></span>

<span data-ttu-id="d5bf9-151">Возможно, у вас нет соответствующих разрешений и у вас нет доступа к назначению ролей администратора другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-151">You might not have the correct permissions and so you don't have access to assign admin roles to other users.</span></span> <span data-ttu-id="d5bf9-152">Попросите другого администратора назначить роли за вас.</span><span class="sxs-lookup"><span data-stu-id="d5bf9-152">Ask another admin to assign roles for you.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="d5bf9-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d5bf9-153">Related articles</span></span>

[<span data-ttu-id="d5bf9-154">Назначение ролей учетным записям пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5bf9-154">Assign roles to user accounts with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[<span data-ttu-id="d5bf9-155">Авторизация и удаление отношений партнеров</span><span class="sxs-lookup"><span data-stu-id="d5bf9-155">Authorize or remove partner relationships</span></span>](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[<span data-ttu-id="d5bf9-156">Добавление альтернативного адреса электронной почты с помощью центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="d5bf9-156">Add an alternative email address using the Exchange admin center</span></span>](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

