---
title: Назначение лицензий пользователям
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте, как назначать лицензии пользователям.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015951"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="c3001-103">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="c3001-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c3001-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="c3001-104">The admin center is changing.</span></span> <span data-ttu-id="c3001-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c3001-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="c3001-106">Вы можете назначать лицензии пользователям на странице **Активные пользователи** или **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="c3001-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="c3001-107">Выбор метода зависит от того, нужно ли назначить лицензии продуктов определенным пользователям или назначить пользователям лицензии на определенный продукт.</span><span class="sxs-lookup"><span data-stu-id="c3001-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="c3001-108">[Узнайте, как одновременно добавить пользователя и назначить лицензию](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="c3001-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c3001-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c3001-109">Before you begin</span></span>

- <span data-ttu-id="c3001-110">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3001-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="c3001-111">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c3001-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="c3001-112">Вы можете [назначать лицензии учетным записям пользователей с помощью Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="c3001-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="c3001-113">Сведения об использовании группового лицензирования см. в статье [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="c3001-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="c3001-114">Некоторые службы, такие как Sway, назначаются пользователям автоматически и не требуют отдельного назначения.</span><span class="sxs-lookup"><span data-stu-id="c3001-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="c3001-115">Назначение лицензий пользователям на странице "Лицензии"</span><span class="sxs-lookup"><span data-stu-id="c3001-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="c3001-116">С помощью страницы **Лицензии** вы можете назначать лицензии на определенный продукт для 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3001-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="c3001-117">На странице **Лицензии** отображается список всех продуктов, на которые у вас есть подписки.</span><span class="sxs-lookup"><span data-stu-id="c3001-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="c3001-118">Также отображается общее количество лицензий для каждого продукта, количество назначенных и доступных лицензий.</span><span class="sxs-lookup"><span data-stu-id="c3001-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="c3001-119">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c3001-120">Выберите продукт.</span><span class="sxs-lookup"><span data-stu-id="c3001-120">Select a product.</span></span>
3. <span data-ttu-id="c3001-121">На странице сведений о продукте выберите **Назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="c3001-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="c3001-122">В области **Назначение лицензий пользователям** начните вводить имя и выберите его в результатах, чтобы добавить в список.</span><span class="sxs-lookup"><span data-stu-id="c3001-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="c3001-123">Вы можете добавить до 20 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="c3001-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="c3001-124">Выберите **Включение и отключение приложений и служб**, чтобы назначить или удалить доступ к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="c3001-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="c3001-125">После завершения нажмите **Назначить**, затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="c3001-126">При наличии конфликта отобразится сообщение о возникшей проблеме и способе ее устранения.</span><span class="sxs-lookup"><span data-stu-id="c3001-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="c3001-127">Например, если вы выбрали лицензии, включающие конфликтующие службы, сообщение об ошибке предложит проверить службы, входящие в состав каждой лицензии, и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="c3001-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="c3001-128">Изменение приложений и служб, к которым у пользователя есть доступ</span><span class="sxs-lookup"><span data-stu-id="c3001-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="c3001-129">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c3001-130">На странице **Лицензии** выберите строку для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3001-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="c3001-131">В области справа выберите приложения и службы, к которым нужно предоставить доступ. Или отмените выбор, чтобы удалить соответствующий доступ.</span><span class="sxs-lookup"><span data-stu-id="c3001-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="c3001-132">После завершения нажмите **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="c3001-133">Назначение лицензий на странице "Активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="c3001-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="c3001-134">С помощью страницы **Активные пользователи** вы можете назначать лицензии пользователей продуктам.</span><span class="sxs-lookup"><span data-stu-id="c3001-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="c3001-135">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c3001-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="c3001-136">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-137">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="c3001-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="c3001-138">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="c3001-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="c3001-139">В области **Управление лицензиями на продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c3001-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c3001-140">В области **Добавить к имеющимся продуктам** установите переключатель для лицензии, которую вы хотите назначить выбранным пользователям, в положение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="c3001-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.\</span></span>
    <span data-ttu-id="c3001-141">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="c3001-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="c3001-142">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="c3001-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="c3001-143">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="c3001-144">Внизу области выберите **Добавить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="c3001-145">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c3001-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="c3001-146">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-147">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="c3001-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="c3001-148">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="c3001-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c3001-149">В области **Назначить продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c3001-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c3001-150">Установите переключатель для лицензий, которые вы хотите назначить выбранным пользователям, в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.\</span></span>
    <span data-ttu-id="c3001-151">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="c3001-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="c3001-152">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="c3001-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="c3001-153">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="c3001-154">В нижней части области **Добавить к имеющимся продуктам** выберите **Добавить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="c3001-155">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c3001-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="c3001-156">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-157">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="c3001-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="c3001-158">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="c3001-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c3001-159">В области **Назначить продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c3001-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c3001-160">Установите переключатель для лицензий, которые вы хотите назначить выбранным пользователям, в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.\</span></span>
    <span data-ttu-id="c3001-161">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="c3001-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="c3001-162">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="c3001-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="c3001-163">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="c3001-164">В нижней части области **Добавить к имеющимся продуктам** выберите **Добавить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="c3001-165">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="c3001-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="c3001-166">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-167">Выберите строку пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="c3001-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="c3001-168">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="c3001-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="c3001-169">Разверните раздел **Лицензии**, установите флажки для лицензий, которые нужно назначить, и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c3001-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="c3001-170">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="c3001-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="c3001-171">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-172">Установите флажок рядом с именем пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="c3001-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="c3001-173">В области справа в строке **Лицензии на продукты** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c3001-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c3001-174">В области **Лицензии на продукты** установите выключатель для лицензии, которую вы хотите назначить, в положение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="c3001-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="c3001-175">По умолчанию пользователю автоматически назначаются все службы, связанные с этой лицензией.</span><span class="sxs-lookup"><span data-stu-id="c3001-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="c3001-176">Вы можете ограничить доступные для пользователя службы.</span><span class="sxs-lookup"><span data-stu-id="c3001-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="c3001-177">Для служб, которых не должно быть у пользователя, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="c3001-178">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="c3001-179">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="c3001-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="c3001-180">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="c3001-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c3001-181">Установите флажок рядом с именем пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="c3001-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="c3001-182">В области справа в строке **Лицензии на продукты** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c3001-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c3001-183">В области **Лицензии на продукты** установите выключатель для лицензии, которую вы хотите назначить, в положение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="c3001-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="c3001-184">По умолчанию пользователю автоматически назначаются все службы, связанные с этой лицензией.</span><span class="sxs-lookup"><span data-stu-id="c3001-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="c3001-185">Вы можете ограничить доступные для пользователя службы.</span><span class="sxs-lookup"><span data-stu-id="c3001-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="c3001-186">Для служб, которых не должно быть у пользователя, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="c3001-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="c3001-187">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c3001-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="c3001-188">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c3001-188">Next steps</span></span>

<span data-ttu-id="c3001-189">Если ваши пользователи не установили приложения Office, поделитесь с ними [Кратким руководством сотрудника](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) для настройки таких элементов, как [Скачивание и установка Microsoft 365 или Office 2019 на ПК или Мак](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) и [Настройка приложений Office и электронной почты на мобильном устройстве](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="c3001-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="c3001-190">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="c3001-190">Related content</span></span>

<span data-ttu-id="c3001-191">[Общие сведения о подписках и лицензиях](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c3001-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="c3001-192">[Отмена назначения лицензий пользователям](remove-licenses-from-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c3001-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="c3001-193">[Покупка или удаление лицензий для подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c3001-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>