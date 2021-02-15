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
description: Узнайте, как отоименовать лицензии из учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114481"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="810e5-103">Отмена назначения лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="810e5-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="810e5-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="810e5-104">The admin center is changing.</span></span> <span data-ttu-id="810e5-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="810e5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="810e5-106">Вы можете отоименовать лицензии у пользователей на странице **"Активные** пользователи" или на странице **"Лицензии".**</span><span class="sxs-lookup"><span data-stu-id="810e5-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="810e5-107">Способ, который вы используете, зависит от того, хотите ли вы оторовать лицензии на продукт у определенных пользователей или отоименовть лицензии пользователей для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="810e5-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="810e5-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="810e5-108">Before you begin</span></span>

- <span data-ttu-id="810e5-109">Для отзыва лицензий необходимо быть глобальным администратором, администратором лицензий, администратором пользователей.</span><span class="sxs-lookup"><span data-stu-id="810e5-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="810e5-110">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="810e5-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="810e5-111">Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="810e5-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="810e5-112">Вы также можете [удалить учетные](../add-users/delete-a-user.md) записи пользователей, которые были назначены лицензией, чтобы сделать их лицензии доступными для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="810e5-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="810e5-113">При удалении учетной записи пользователя его лицензия сразу же доступна для назначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="810e5-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="810e5-114">Использование страницы "Лицензии" для отзыва лицензий</span><span class="sxs-lookup"><span data-stu-id="810e5-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="810e5-115">При использовании страницы **"Лицензии"** для отзыва лицензий вы отзываете лицензии на определенный продукт для 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="810e5-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="810e5-116">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="810e5-117">Выберите продукт, для которого нужно отоименовать лицензии.</span><span class="sxs-lookup"><span data-stu-id="810e5-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="810e5-118">Выберите пользователей, для которых нужно отоименовать лицензии.</span><span class="sxs-lookup"><span data-stu-id="810e5-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="810e5-119">Выберите **"Отоименуть лицензии".**</span><span class="sxs-lookup"><span data-stu-id="810e5-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="810e5-120">В поле **"Отоименуем лицензии"** выберите **"Отоименование".**</span><span class="sxs-lookup"><span data-stu-id="810e5-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="810e5-121">Использование страницы "Активные пользователи" для отзыва лицензий</span><span class="sxs-lookup"><span data-stu-id="810e5-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="810e5-122">При использовании страницы **"Активные пользователи"** для отзыва лицензий лицензии на продукты от пользователей будут отозшены.</span><span class="sxs-lookup"><span data-stu-id="810e5-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="810e5-123">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="810e5-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="810e5-124">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-125">Выберите строку пользователя, для который нужно отоименовать лицензию.</span><span class="sxs-lookup"><span data-stu-id="810e5-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="810e5-126">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="810e5-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="810e5-127">**Разоберите раздел** "Лицензии", уберите флажки для лицензий, которые нужно отоименовать, а затем выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="810e5-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="810e5-128">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="810e5-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="810e5-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-130">Выберите пользователя, для который вы хотите отоименовать лицензию.</span><span class="sxs-lookup"><span data-stu-id="810e5-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="810e5-131">Справа в строке **"Лицензии на** продукты" выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="810e5-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="810e5-132">В области **"Лицензии** на продукты" переключите переключатель в положение "Выкл." для лицензии, которая будет отознана пользователю. </span><span class="sxs-lookup"><span data-stu-id="810e5-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="810e5-133">Например, если вы отключите лицензию Office 365 корпоративный E3, она отключит эту лицензию и все службы по этой лицензии для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="810e5-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="810e5-134">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="810e5-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="810e5-135">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="810e5-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="810e5-136">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-137">Выберите пользователя, для который вы хотите отоименовать лицензию.</span><span class="sxs-lookup"><span data-stu-id="810e5-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="810e5-138">Справа в строке **"Лицензии на** продукты" выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="810e5-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="810e5-139">В области **"Лицензии** на продукты" переключите переключатель в положение "Выкл." для лицензии, которая будет отознана пользователю. </span><span class="sxs-lookup"><span data-stu-id="810e5-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="810e5-140">Например, если вы отключите лицензию Office 365 корпоративный E3, она отключит эту лицензию и все службы по этой лицензии для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="810e5-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="810e5-141">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="810e5-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="810e5-142">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="810e5-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="810e5-143">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-144">Выберите круги рядом с именами пользователей, для которых нужно отоименовать лицензии.</span><span class="sxs-lookup"><span data-stu-id="810e5-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="810e5-145">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="810e5-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="810e5-146">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="810e5-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="810e5-147">At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="810e5-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="810e5-148">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="810e5-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="810e5-149">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-150">Выберите поля рядом с именами пользователей, для которых нужно отоименовать все лицензии.</span><span class="sxs-lookup"><span data-stu-id="810e5-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="810e5-151">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="810e5-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="810e5-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="810e5-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="810e5-153">At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="810e5-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="810e5-154">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="810e5-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="810e5-155">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="810e5-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="810e5-156">Выберите поля рядом с именами пользователей, для которых нужно отоименовать все лицензии.</span><span class="sxs-lookup"><span data-stu-id="810e5-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="810e5-157">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="810e5-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="810e5-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="810e5-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="810e5-159">At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="810e5-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="810e5-160">Что происходит с данными пользователя при удалите его лицензию?</span><span class="sxs-lookup"><span data-stu-id="810e5-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="810e5-161">При удалении лицензии у пользователя данные, связанные с этой учетной записью, удерживаются в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="810e5-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="810e5-162">После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="810e5-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="810e5-163">Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удален из Центра администрирования Microsoft 365 или не удален с помощью синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="810e5-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="810e5-164">Дополнительные сведения [см. в сведениях о хранении и удалении OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="810e5-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="810e5-165">При удалении лицензии поиск в почтовом ящике пользователя перестает быть поиском с помощью средства eDiscovery, такого как "Поиск контента" или "Advanced eDiscovery".</span><span class="sxs-lookup"><span data-stu-id="810e5-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="810e5-166">Дополнительные сведения см. в подключении "Поиск в отключенных или отключенных почтовых ящиках" в поиске контента [в Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="810e5-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="810e5-167">Если у вас есть корпоративная подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранять данные почтового ящика удаленной учетной записи пользователя с помощью неактивных почтовых [ящиков.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="810e5-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="810e5-168">Дополнительные сведения см. в [теме "Создание неактивных](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)почтовых ящиков в Exchange Online" и управление ими.</span><span class="sxs-lookup"><span data-stu-id="810e5-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="810e5-169">Сведения о блокировке доступа пользователя к данным Microsoft 365 после удаления лицензии, а также о том, как получить доступ к этим данным после удаления, см. в записи "Удаление бывшего [сотрудника".](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="810e5-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="810e5-170">Если вы удалите лицензию пользователя и у него по-прежнему будут установлены приложения Office, то при использовании приложений Office в [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) будут отсут уже нелицензироваться продукты и ошибки активации.</span><span class="sxs-lookup"><span data-stu-id="810e5-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="810e5-171">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="810e5-171">Next steps</span></span>

<span data-ttu-id="810e5-172">Если вы не собираетесь переначивать неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за дополнительные лицензии, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="810e5-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="810e5-173">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="810e5-173">Related content</span></span>

<span data-ttu-id="810e5-174">[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="810e5-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="810e5-175">[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="810e5-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="810e5-176">[Подписки и лицензии в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="810e5-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>