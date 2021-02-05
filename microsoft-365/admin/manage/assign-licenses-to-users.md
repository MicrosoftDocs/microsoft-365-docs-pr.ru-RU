---
title: Назначение лицензий пользователям
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.date: 08/14/2020
ms.openlocfilehash: b5179006da896dbadab10d43a43b094acedcb806
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113989"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="3dcb5-103">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="3dcb5-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3dcb5-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-104">The admin center is changing.</span></span> <span data-ttu-id="3dcb5-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="3dcb5-106">Вы можете назначать лицензии пользователям на странице **Активные пользователи** или **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="3dcb5-107">Выбор метода зависит от того, нужно ли назначить лицензии продуктов определенным пользователям или назначить пользователям лицензии на определенный продукт.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="3dcb5-108">[Узнайте, как одновременно добавить пользователя и назначить лицензию](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3dcb5-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="3dcb5-109">Before you begin</span></span>

- <span data-ttu-id="3dcb5-110">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="3dcb5-111">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="3dcb5-112">Вы можете [назначать лицензии учетным записям пользователей с помощью Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="3dcb5-113">Сведения об использовании группового лицензирования см. в статье [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="3dcb5-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="3dcb5-114">Некоторые службы, такие как Sway, назначаются пользователям автоматически и не требуют отдельного назначения.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="3dcb5-115">Назначение лицензий пользователям на странице "Лицензии"</span><span class="sxs-lookup"><span data-stu-id="3dcb5-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="3dcb5-116">С помощью страницы **Лицензии** вы можете назначать лицензии на определенный продукт для 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="3dcb5-117">На странице **Лицензии** отображается список всех продуктов, на которые у вас есть подписки.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="3dcb5-118">Также отображается общее количество лицензий для каждого продукта, количество назначенных и доступных лицензий.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="3dcb5-119">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3dcb5-120">Выберите продукт.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-120">Select a product.</span></span>
3. <span data-ttu-id="3dcb5-121">На странице сведений о продукте выберите **Назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="3dcb5-122">В области **Назначение лицензий пользователям** начните вводить имя и выберите его в результатах, чтобы добавить в список.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="3dcb5-123">Вы можете добавить до 20 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="3dcb5-124">Выберите **Включение и отключение приложений и служб**, чтобы назначить или удалить доступ к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="3dcb5-125">После завершения нажмите **Назначить**, затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="3dcb5-126">При наличии конфликта отобразится сообщение о возникшей проблеме и способе ее устранения.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="3dcb5-127">Например, если вы выбрали лицензии, включающие конфликтующие службы, сообщение об ошибке предложит проверить службы, входящие в состав каждой лицензии, и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="3dcb5-128">Изменение приложений и служб, к которым у пользователя есть доступ</span><span class="sxs-lookup"><span data-stu-id="3dcb5-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="3dcb5-129">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3dcb5-130">На странице **Лицензии** выберите строку для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="3dcb5-131">В области справа выберите приложения и службы, к которым нужно предоставить доступ. Или отмените выбор, чтобы удалить соответствующий доступ.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="3dcb5-132">После завершения нажмите **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="3dcb5-133">Назначение лицензий на странице "Активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="3dcb5-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="3dcb5-134">С помощью страницы **Активные пользователи** вы можете назначать лицензии пользователей продуктам.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3dcb5-135">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="3dcb5-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3dcb5-136">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-137">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3dcb5-138">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="3dcb5-139">В области **Управление лицензиями на продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3dcb5-140">В области **Добавить к имеющимся продуктам** установите переключатель для лицензии, которую вы хотите назначить выбранным пользователям, в положение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.\</span></span>
    <span data-ttu-id="3dcb5-141">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3dcb5-142">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="3dcb5-143">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3dcb5-144">Внизу области выберите **Добавить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3dcb5-145">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="3dcb5-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3dcb5-146">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-147">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3dcb5-148">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3dcb5-149">В области **Назначить продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3dcb5-150">Установите переключатель для лицензий, которые вы хотите назначить выбранным пользователям, в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.\</span></span>
    <span data-ttu-id="3dcb5-151">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3dcb5-152">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="3dcb5-153">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3dcb5-154">В нижней части области **Добавить к имеющимся продуктам** выберите **Добавить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="3dcb5-155">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="3dcb5-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="3dcb5-156">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-157">Установите флажки рядом с именами пользователей, которым вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="3dcb5-158">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="3dcb5-159">В области **Назначить продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="3dcb5-160">Установите переключатель для лицензий, которые вы хотите назначить выбранным пользователям, в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.\</span></span>
    <span data-ttu-id="3dcb5-161">По умолчанию пользователям автоматически назначаются все службы, связанные с этими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="3dcb5-162">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="3dcb5-163">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="3dcb5-164">В нижней части области **Добавить к имеющимся продуктам** выберите **Добавить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3dcb5-165">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="3dcb5-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="3dcb5-166">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-167">Выберите строку пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3dcb5-168">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="3dcb5-169">Разверните раздел **Лицензии**, установите флажки для лицензий, которые нужно назначить, и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3dcb5-170">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="3dcb5-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="3dcb5-171">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-172">Установите флажок рядом с именем пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3dcb5-173">В области справа в строке **Лицензии на продукты** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3dcb5-174">В области **Лицензии на продукты** установите выключатель для лицензии, которую вы хотите назначить, в положение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="3dcb5-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="3dcb5-175">По умолчанию пользователю автоматически назначаются все службы, связанные с этой лицензией.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="3dcb5-176">Вы можете ограничить доступные для пользователя службы.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="3dcb5-177">Для служб, которых не должно быть у пользователя, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="3dcb5-178">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="3dcb5-179">Назначение лицензий одному пользователю</span><span class="sxs-lookup"><span data-stu-id="3dcb5-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="3dcb5-180">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3dcb5-181">Установите флажок рядом с именем пользователя, которому хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="3dcb5-182">В области справа в строке **Лицензии на продукты** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="3dcb5-183">В области **Лицензии на продукты** установите выключатель для лицензии, которую вы хотите назначить, в положение **Вкл.**</span><span class="sxs-lookup"><span data-stu-id="3dcb5-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.\</span></span>
    <span data-ttu-id="3dcb5-184">По умолчанию пользователю автоматически назначаются все службы, связанные с этой лицензией.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="3dcb5-185">Вы можете ограничить доступные для пользователя службы.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="3dcb5-186">Для служб, которых не должно быть у пользователя, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="3dcb5-187">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="3dcb5-188">Назначение лицензию гостевому пользователю</span><span class="sxs-lookup"><span data-stu-id="3dcb5-188">Assign a license to a guest user</span></span>

<span data-ttu-id="3dcb5-189">Вы можете приглашать гостевых пользователей для совместной работы с вашей организацией в Центре администрирования Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-189">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="3dcb5-190">Сведения о гостевых пользователях см. в статье [Что такое гостевой доступ к Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="3dcb5-190">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="3dcb5-191">Если у вас нет гостевых пользователей, см. статью [Краткое руководство. Добавление гостевых пользователей в каталог на портале Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dcb5-192">Эти действия может выполнять только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="3dcb5-193">Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Центр администрирования Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="3dcb5-194">В области навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="3dcb5-195">На странице **Пользователи | Все пользователи (предварительная версия)** выберите **Добавить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="3dcb5-196">В меню **Выберите поле** щелкните **Тип пользователя** и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="3dcb5-197">В следующем меню выберите **Гость**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="3dcb5-198">В списке результатов выберите пользователя, которому нужна лицензия.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="3dcb5-199">В разделе **Управление** выберите **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="3dcb5-200">Выберите **Назначения**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="3dcb5-201">На странице **Изменение назначений лицензий** выберите продукт, для которого нужно назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="3dcb5-202">Справа снимите флажки для всех служб, к которым у гостевого пользователя не должно быть доступа.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="3dcb5-203">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3dcb5-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dcb5-204">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3dcb5-204">Next steps</span></span>

<span data-ttu-id="3dcb5-205">Если ваши пользователи не установили приложения Office, поделитесь с ними [Кратким руководством сотрудника](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) для настройки таких элементов, как [Скачивание и установка Microsoft 365 или Office 2019 на ПК или Мак](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) и [Настройка приложений Office и электронной почты на мобильном устройстве](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="3dcb5-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="3dcb5-206">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="3dcb5-206">Related content</span></span>

<span data-ttu-id="3dcb5-207">[Общие сведения о подписках и лицензиях](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="3dcb5-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="3dcb5-208">[Отмена назначения лицензий пользователям](remove-licenses-from-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="3dcb5-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="3dcb5-209">[Покупка или удаление лицензий для подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="3dcb5-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
