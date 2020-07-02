---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Сведения о том, как отменить назначение лицензий для учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015939"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="cd646-103">Отмена назначения лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="cd646-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cd646-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="cd646-104">The admin center is changing.</span></span> <span data-ttu-id="cd646-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cd646-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="cd646-106">Вы можете отменить назначение лицензий пользователям на странице " **Активные пользователи** " или на странице " **лицензии** ".</span><span class="sxs-lookup"><span data-stu-id="cd646-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="cd646-107">Используемый способ зависит от того, хотите ли вы отменить назначение лицензий на продукты определенным пользователям или отменить назначение пользователей для конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="cd646-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="cd646-108">Подготовка</span><span class="sxs-lookup"><span data-stu-id="cd646-108">Before you begin</span></span>

- <span data-ttu-id="cd646-109">Чтобы отменить назначение лицензий, вы должны быть глобальной, лицензией и администратором пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd646-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="cd646-110">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cd646-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="cd646-111">Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd646-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="cd646-112">Вы также можете [удалить учетные записи пользователей](../add-users/delete-a-user.md) , которым назначена лицензия, чтобы сделать их лицензия доступной другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="cd646-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="cd646-113">При удалении учетной записи пользователя ее лицензия немедленно становится доступной для назначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="cd646-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="cd646-114">Отмена назначения лицензий с помощью страницы "лицензии"</span><span class="sxs-lookup"><span data-stu-id="cd646-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="cd646-115">При отмене назначения лицензий с помощью страницы " **лицензии** " вы отдаете лицензии для определенного продукта не более чем 20 пользователям.</span><span class="sxs-lookup"><span data-stu-id="cd646-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="cd646-116">В центре администрирования перейдите на страницу лицензии **выставления счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="cd646-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="cd646-117">Выберите продукт, для которого требуется отменить назначение лицензий.</span><span class="sxs-lookup"><span data-stu-id="cd646-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="cd646-118">Выберите пользователей, для которых требуется отменить назначение лицензий.</span><span class="sxs-lookup"><span data-stu-id="cd646-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="cd646-119">Выберите отменить **Назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="cd646-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="cd646-120">В поле отменить **Назначение лицензий** выберите отменить **назначение**.</span><span class="sxs-lookup"><span data-stu-id="cd646-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="cd646-121">Отмена назначения лицензий с помощью страницы "активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="cd646-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="cd646-122">При отмене назначения лицензий с помощью страницы " **Активные пользователи** " вы отдаете им лицензии на продукты.</span><span class="sxs-lookup"><span data-stu-id="cd646-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="cd646-123">Отмена назначения лицензий для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="cd646-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="cd646-124">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-125">Выберите строку пользователя, для которого требуется отменить назначение лицензии.</span><span class="sxs-lookup"><span data-stu-id="cd646-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="cd646-126">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="cd646-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="cd646-127">Разверните раздел **лицензии** , снимите флажки для лицензий, которые требуется отменить, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="cd646-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="cd646-128">Отмена назначения лицензий для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="cd646-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="cd646-129">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-130">Выберите пользователя, для которого требуется отменить назначение лицензии.</span><span class="sxs-lookup"><span data-stu-id="cd646-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="cd646-131">В правой части в строке **лицензии на продукты** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="cd646-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="cd646-132">В области **лицензии на продукты** установите переключатель в положение **выключена** для лицензии, которую вы хотите отменить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd646-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="cd646-133">Например, если вы отключили лицензию Office 365 корпоративный E3, она отбудет отнести эту лицензию и все службы в рамках этой лицензии для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd646-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="cd646-134">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cd646-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="cd646-135">Отмена назначения лицензий для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="cd646-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="cd646-136">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-137">Выберите пользователя, для которого требуется отменить назначение лицензии.</span><span class="sxs-lookup"><span data-stu-id="cd646-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="cd646-138">В правой части в строке **лицензии на продукты** выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="cd646-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="cd646-139">В области **лицензии на продукты** установите переключатель в положение **выключена** для лицензии, которую вы хотите отменить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd646-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="cd646-140">Например, если вы отключили лицензию Office 365 корпоративный E3, она отбудет отнести эту лицензию и все службы в рамках этой лицензии для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd646-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="cd646-141">В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cd646-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="cd646-142">Отмена назначения лицензий для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="cd646-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="cd646-143">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-144">Выберите кружки рядом с именами пользователей, для которых требуется отменить назначение лицензий.</span><span class="sxs-lookup"><span data-stu-id="cd646-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="cd646-145">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="cd646-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="cd646-146">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd646-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cd646-147">В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **закрытие**.</span><span class="sxs-lookup"><span data-stu-id="cd646-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="cd646-148">Отмена назначения лицензий для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="cd646-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="cd646-149">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-150">Установите флажки рядом с именами пользователей, для которых требуется отменить назначение всех лицензий.</span><span class="sxs-lookup"><span data-stu-id="cd646-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="cd646-151">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="cd646-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="cd646-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="cd646-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cd646-153">В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **Закрыть** \> **окно**.</span><span class="sxs-lookup"><span data-stu-id="cd646-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="cd646-154">Отмена назначения лицензий для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="cd646-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="cd646-155">В центре администрирования перейдите в раздел \*\*Пользователи \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="cd646-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd646-156">Установите флажки рядом с именами пользователей, для которых требуется отменить назначение всех лицензий.</span><span class="sxs-lookup"><span data-stu-id="cd646-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="cd646-157">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="cd646-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="cd646-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="cd646-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cd646-159">В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **Закрыть** \> **окно**.</span><span class="sxs-lookup"><span data-stu-id="cd646-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="cd646-160">Что происходит с данными пользователя при удалении лицензии?</span><span class="sxs-lookup"><span data-stu-id="cd646-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="cd646-161">При удалении лицензии у пользователя данные, связанные с этой учетной записью, хранятся в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="cd646-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="cd646-162">По истечении 30-дневного льготного периода данные удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="cd646-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="cd646-163">Файлы, сохраненные в OneDrive для бизнеса, не удаляются, пока пользователь не будет удален из центра администрирования Microsoft 365 или удален с помощью синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd646-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="cd646-164">Дополнительные сведения см. в разделе " [Хранение и удаление OneDrive](https://docs.microsoft.com/onedrive/retention-and-deletion)".</span><span class="sxs-lookup"><span data-stu-id="cd646-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="cd646-165">После удаления лицензии почтовый ящик пользователя больше не может быть доступен для поиска с помощью средства обнаружения электронных данных, такого как поиск контента или Расширенное обнаружение электронных данных.</span><span class="sxs-lookup"><span data-stu-id="cd646-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="cd646-166">Дополнительные сведения см. в разделе "поиск отключенных или отключенных почтовых ящиков" в разделе [Поиск содержимого в Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="cd646-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="cd646-167">Если у вас есть Корпоративная подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранить данные почтового ящика удаленной учетной записи пользователя с помощью [неактивных почтовых ящиков](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="cd646-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="cd646-168">Дополнительные сведения см в статье [Создание неактивных почтовых ящиков и управление ими в Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="cd646-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="cd646-169">Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии и получения доступа к данным, приведенные в статье [Удаление бывшего сотрудника](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="cd646-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="cd646-170">Если удалить лицензию пользователя, но у нее все еще установлены приложения Office, они увидят [нелицензированные продукты и ошибки активации в Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) при использовании приложений Office.</span><span class="sxs-lookup"><span data-stu-id="cd646-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd646-171">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cd646-171">Next steps</span></span>

<span data-ttu-id="cd646-172">Если вы не собираетесь [переназначить неиспользуемые лицензии другим пользователям](../../managed-desktop/get-started/assign-licenses.md), рекомендуем [Удалить лицензии из подписки](../../commerce/licenses/buy-licenses.md) , чтобы вы не оплачиваете больше лицензий, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="cd646-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="cd646-173">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="cd646-173">Related content</span></span>

<span data-ttu-id="cd646-174">[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="cd646-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="cd646-175">[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="cd646-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="cd646-176">[Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="cd646-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>