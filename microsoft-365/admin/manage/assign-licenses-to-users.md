---
title: Назначение лицензий пользователям
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Назначение лицензий зависит от того, нужно ли назначить лицензии продуктов определенным пользователям или назначить пользователям лицензии на определенный продукт.
ms.date: 04/26/2021
ms.openlocfilehash: c8e5c6a648f08aaba97fe05e19a5cfa0cada2174
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007013"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="42774-103">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="42774-103">Assign licenses to users</span></span>

<span data-ttu-id="42774-104">Вы можете назначать лицензии пользователям на странице **Активные пользователи** или **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="42774-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="42774-105">Выбор метода зависит от того, нужно ли назначить лицензии продуктов определенным пользователям или назначить пользователям лицензии на определенный продукт.</span><span class="sxs-lookup"><span data-stu-id="42774-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="42774-106">В качестве администратора вы не можете назначить лицензии или отменить их назначение для подписок, самостоятельно приобретенных пользователем в организации.</span><span class="sxs-lookup"><span data-stu-id="42774-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="42774-107">Вы можете [получить контроль над самостоятельно приобретенной подпиской](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), а затем назначить лицензии или отменить их назначение.</span><span class="sxs-lookup"><span data-stu-id="42774-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="42774-108">[Узнайте, как одновременно добавить пользователя и назначить лицензию](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="42774-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="42774-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="42774-109">Before you begin</span></span>

- <span data-ttu-id="42774-110">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="42774-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="42774-111">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="42774-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="42774-112">Вы можете [назначать лицензии Microsoft 365 учетным записям пользователей с помощью Windows PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="42774-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="42774-113">Сведения об использовании группового лицензирования см. в статье [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="42774-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="42774-114">Некоторые службы, такие как Sway, назначаются пользователям автоматически и не требуют отдельного назначения.</span><span class="sxs-lookup"><span data-stu-id="42774-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="42774-115">Назначение лицензий пользователям на странице "Лицензии"</span><span class="sxs-lookup"><span data-stu-id="42774-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="42774-116">С помощью страницы **Лицензии** вы можете назначать лицензии на определенный продукт для 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="42774-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="42774-117">На странице **Лицензии** отображается список всех продуктов, на которые у вас есть подписки.</span><span class="sxs-lookup"><span data-stu-id="42774-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="42774-118">Также отображается общее количество лицензий для каждого продукта, количество назначенных и доступных лицензий.</span><span class="sxs-lookup"><span data-stu-id="42774-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="42774-119">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="42774-120">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="42774-121">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="42774-122">Выберите продукт.</span><span class="sxs-lookup"><span data-stu-id="42774-122">Select a product.</span></span>
3. <span data-ttu-id="42774-123">На странице сведений о продукте выберите **Назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="42774-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="42774-124">В области **Назначение лицензий пользователям** начните вводить имя и выберите его в результатах, чтобы добавить в список.</span><span class="sxs-lookup"><span data-stu-id="42774-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="42774-125">Вы можете добавить до 20 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="42774-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="42774-126">Выберите **Включение и отключение приложений и служб**, чтобы назначить или удалить доступ к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="42774-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="42774-127">После завершения нажмите **Назначить**, затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="42774-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="42774-128">При наличии конфликта отобразится сообщение о возникшей проблеме и способе ее устранения.</span><span class="sxs-lookup"><span data-stu-id="42774-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="42774-129">Например, если вы выбрали лицензии, включающие конфликтующие службы, сообщение об ошибке предложит проверить службы, входящие в состав каждой лицензии, и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="42774-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="42774-130">Изменение приложений и служб, к которым у пользователя есть доступ</span><span class="sxs-lookup"><span data-stu-id="42774-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="42774-131">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="42774-132">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="42774-133">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="42774-134">На странице **Лицензии** выберите строку для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="42774-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="42774-135">В области справа выберите приложения и службы, к которым нужно предоставить доступ. Или отмените выбор, чтобы удалить соответствующий доступ.</span><span class="sxs-lookup"><span data-stu-id="42774-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="42774-136">После завершения нажмите **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="42774-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="42774-137">Назначение лицензий на странице "Активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="42774-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="42774-138">С помощью страницы **Активные пользователи** вы можете назначать лицензии пользователей продуктам.</span><span class="sxs-lookup"><span data-stu-id="42774-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="42774-139">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="42774-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="42774-140">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="42774-141">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="42774-142">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="42774-143">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="42774-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="42774-144">Нажмите вверху **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="42774-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="42774-145">В области **Управление лицензиями на продукты** выберите **Назначить больше: сохранить существующие лицензии и назначить больше** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42774-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="42774-146">В разделе **Лицензии** установите флажки для лицензий, которые должны быть у выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="42774-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="42774-147">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="42774-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="42774-148">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="42774-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="42774-149">Снимите флажки для служб, которых не должно быть у пользователей.</span><span class="sxs-lookup"><span data-stu-id="42774-149">Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="42774-150">Внизу области выберите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="42774-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="42774-151">Если у вас недостаточно лицензий для всех пользователей, может потребоваться приобрести дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="42774-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="42774-152">Если нужно назначить лицензии большому количеству пользователей, используйте [Назначение лицензий пользователям по членству в группах в Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="42774-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="42774-153">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="42774-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="42774-154">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="42774-155">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="42774-156">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="42774-157">Выберите строку пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="42774-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="42774-158">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="42774-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="42774-159">Разверните раздел **Лицензии**, установите флажки для лицензий, которые нужно назначить, и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="42774-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="42774-160">Назначение лицензию гостевому пользователю</span><span class="sxs-lookup"><span data-stu-id="42774-160">Assign a license to a guest user</span></span>

<span data-ttu-id="42774-161">Вы можете приглашать гостевых пользователей для совместной работы с вашей организацией в Центре администрирования Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42774-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="42774-162">Сведения о гостевых пользователях см. в статье [Что такое гостевой доступ к Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="42774-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="42774-163">Если у вас нет гостевых пользователей, см. статью [Краткое руководство. Добавление гостевых пользователей в каталог на портале Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="42774-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42774-164">Эти действия может выполнять только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="42774-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="42774-165">Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Центр администрирования Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="42774-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="42774-166">В области навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="42774-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="42774-167">На странице **Пользователи | Все пользователи (предварительная версия)** выберите **Добавить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="42774-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="42774-168">В меню **Выберите поле** щелкните **Тип пользователя** и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="42774-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="42774-169">В следующем меню выберите **Гость**.</span><span class="sxs-lookup"><span data-stu-id="42774-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="42774-170">В списке результатов выберите пользователя, которому нужна лицензия.</span><span class="sxs-lookup"><span data-stu-id="42774-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="42774-171">В разделе **Управление** выберите **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="42774-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="42774-172">Выберите **Назначения**.</span><span class="sxs-lookup"><span data-stu-id="42774-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="42774-173">На странице **Изменение назначений лицензий** выберите продукт, для которого нужно назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="42774-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="42774-174">Справа снимите флажки для всех служб, к которым у гостевого пользователя не должно быть доступа.</span><span class="sxs-lookup"><span data-stu-id="42774-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="42774-175">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="42774-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42774-176">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="42774-176">Next steps</span></span>

<span data-ttu-id="42774-177">Если ваши пользователи не установили приложения Office, поделитесь с ними [Кратким руководством сотрудника](../../business-video/employee-quick-setup.md) для настройки таких элементов, как [Скачивание и установка Microsoft 365 или Office 2019 на ПК или Мак](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) и [Настройка приложений Office и электронной почты на мобильном устройстве](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="42774-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="42774-178">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="42774-178">Related content</span></span>

<span data-ttu-id="42774-179">[Общие сведения о подписках и лицензиях](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="42774-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="42774-180">[Отмена назначения лицензий пользователям](remove-licenses-from-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="42774-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="42774-181">[Покупка или удаление лицензий для подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="42774-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
