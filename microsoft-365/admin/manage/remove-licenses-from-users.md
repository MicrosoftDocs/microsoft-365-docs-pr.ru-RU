---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте, как отогнать лицензии из учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915198"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="57d59-103">Отмена назначения лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="57d59-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="57d59-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="57d59-104">The admin center is changing.</span></span> <span data-ttu-id="57d59-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="57d59-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="57d59-106">Лицензии можно отогнать от пользователей на странице **Активные** пользователи или на странице **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="57d59-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="57d59-107">Метод, который вы используете, зависит от того, хотите ли вы отогнать лицензии на продукт от определенных пользователей или отогнать лицензии пользователей от конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="57d59-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="57d59-108">Подготовка</span><span class="sxs-lookup"><span data-stu-id="57d59-108">Before you begin</span></span>

- <span data-ttu-id="57d59-109">Чтобы отогнать лицензии, необходимо быть администратором глобальной лицензии, лицензии и пользователя.</span><span class="sxs-lookup"><span data-stu-id="57d59-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="57d59-110">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="57d59-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="57d59-111">Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="57d59-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="57d59-112">Вы также можете [удалить учетные записи пользователей,](../add-users/delete-a-user.md) которые были назначены лицензии, чтобы сделать их лицензию доступной для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="57d59-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="57d59-113">При удалении учетной записи пользователя их лицензия сразу же доступна для назначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="57d59-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="57d59-114">Использование страницы Лицензии для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="57d59-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="57d59-115">При использовании страницы **Лицензии** для отозвал лицензии, вы отозвал лицензии для определенного продукта для до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="57d59-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="57d59-116">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="57d59-117">Выберите продукт, для которого необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="57d59-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="57d59-118">Выберите пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="57d59-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="57d59-119">Выберите **лицензии unassign**.</span><span class="sxs-lookup"><span data-stu-id="57d59-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="57d59-120">В поле **Unassign licenses** выберите **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="57d59-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="57d59-121">Используйте страницу Активные пользователи для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="57d59-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="57d59-122">Если вы используете **страницу Активные** пользователи для ненамеряния лицензий, вы не передаете лицензии на продукты от пользователей.</span><span class="sxs-lookup"><span data-stu-id="57d59-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="57d59-123">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="57d59-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="57d59-124">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-125">Выберите строку пользователя, для чего необходимо отогнать лицензию.</span><span class="sxs-lookup"><span data-stu-id="57d59-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="57d59-126">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="57d59-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="57d59-127">**Расширите раздел Лицензии,** очистите поля для лицензий, которые необходимо отостановить, а затем выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="57d59-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="57d59-128">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="57d59-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="57d59-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-130">Выберите пользователя, для который необходимо отогнать лицензию.</span><span class="sxs-lookup"><span data-stu-id="57d59-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="57d59-131">Справа в строке **Лицензии продукта** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="57d59-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="57d59-132">В области **лицензий** продуктов переключите переключатель в положение **Off** для лицензии, которая будет отменить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="57d59-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="57d59-133">Например, если отключить лицензию Office 365 Enterprise E3, она отключит лицензию и все службы в соответствии с этой лицензией для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="57d59-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="57d59-134">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="57d59-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="57d59-135">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="57d59-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="57d59-136">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-137">Выберите пользователя, для который необходимо отогнать лицензию.</span><span class="sxs-lookup"><span data-stu-id="57d59-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="57d59-138">Справа в строке **Лицензии продукта** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="57d59-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="57d59-139">В области **лицензий** продуктов переключите переключатель в положение **Off** для лицензии, которая будет отменить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="57d59-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="57d59-140">Например, если отключить лицензию Office 365 Enterprise E3, она отключит лицензию и все службы в соответствии с этой лицензией для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="57d59-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="57d59-141">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="57d59-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="57d59-142">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="57d59-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="57d59-143">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-144">Выберите круги рядом с именами пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="57d59-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="57d59-145">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="57d59-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="57d59-146">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57d59-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="57d59-147">В нижней части области **Заменить** существующие продукты выберите удалить все лицензии на продукты из выбранного окна пользователей, а затем выберите **заменить**  \> **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="57d59-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="57d59-148">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="57d59-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="57d59-149">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-150">Выберите поля рядом с именами пользователей, для которых необходимо отогнать все лицензии.</span><span class="sxs-lookup"><span data-stu-id="57d59-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="57d59-151">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="57d59-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="57d59-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="57d59-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="57d59-153">В нижней части области **Заменяйте**  существующие продукты, выберите удалить все лицензии на продукты из выбранного окна пользователей, а затем выберите **Замените** \> **закрыть** \> .</span><span class="sxs-lookup"><span data-stu-id="57d59-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="57d59-154">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="57d59-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="57d59-155">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="57d59-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="57d59-156">Выберите поля рядом с именами пользователей, для которых необходимо отогнать все лицензии.</span><span class="sxs-lookup"><span data-stu-id="57d59-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="57d59-157">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="57d59-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="57d59-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="57d59-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="57d59-159">В нижней части области **Заменяйте**  существующие продукты, выберите удалить все лицензии на продукты из выбранного окна пользователей, а затем выберите **Замените** \> **закрыть** \> .</span><span class="sxs-lookup"><span data-stu-id="57d59-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="57d59-160">Что происходит с данными пользователя при удале лицензии?</span><span class="sxs-lookup"><span data-stu-id="57d59-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="57d59-161">При удалении лицензии у пользователя данные, связанные с этой учетной записью, удерживаются в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57d59-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="57d59-162">После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="57d59-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="57d59-163">Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удаляется из центра администрирования Microsoft 365 или удаляется с помощью синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57d59-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="57d59-164">Дополнительные сведения см. в [сайте Хранения и удаления OneDrive.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="57d59-164">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="57d59-165">При удалении лицензии почтовый ящик пользователя больше не будет искаться с помощью средства поиска электронных данных, например поиска контента или предварительного поиска электронных данных.</span><span class="sxs-lookup"><span data-stu-id="57d59-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="57d59-166">Дополнительные сведения см. в материалах "Поиск отключенных или от лицензированных почтовых ящиков" в "Поиск контента" [в Microsoft 365.](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="57d59-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="57d59-167">Если у вас есть подписка enterprise, например Office 365 Enterprise E3, Exchange Online позволяет сохранять данные почтовых ящиков удаленных учетных записей пользователей с помощью неактивных почтовых [ящиков.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="57d59-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="57d59-168">Дополнительные сведения см. в рублях Создание и управление неактивными почтовыми [ящиками в Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="57d59-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="57d59-169">Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии, а также как получить доступ к данным после этого, см. в см. в twitter [Remove a former employee.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="57d59-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="57d59-170">Если вы удалите лицензию пользователя и у них все еще установлены приложения Office, они увидят ошибки без лицензии на продукт и активацию в [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) при использовании приложений Office.</span><span class="sxs-lookup"><span data-stu-id="57d59-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57d59-171">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="57d59-171">Next steps</span></span>

<span data-ttu-id="57d59-172">Если вы не собираетесь перенаходить неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за больше лицензий, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="57d59-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="57d59-173">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="57d59-173">Related content</span></span>

<span data-ttu-id="57d59-174">[Удаление лицензий из подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="57d59-174">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="57d59-175">[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="57d59-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="57d59-176">[Понимание подписок и лицензий в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="57d59-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>