---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: Узнайте, как отогнать лицензии из учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 550136c2cfa8d81a31e52a4313dc9c967a55d56e
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398197"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="5480c-103">Отмена назначения лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="5480c-103">Unassign licenses from users</span></span>

<span data-ttu-id="5480c-104">Лицензии можно отогнать от пользователей на странице **Активные** пользователи или на странице **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="5480c-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="5480c-105">Метод, который вы используете, зависит от того, хотите ли вы отогнать лицензии на продукт от определенных пользователей или отогнать лицензии пользователей от конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="5480c-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="5480c-106">Как администратор вы не можете назначить или отозначить лицензии для подписки на покупку самостоятельной службы, купленной пользователем в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5480c-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="5480c-107">Вы можете [взять на себя подписку на](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)покупку самообслужива, а затем назначить или отозначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="5480c-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5480c-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5480c-108">Before you begin</span></span>

- <span data-ttu-id="5480c-109">Чтобы отогнать лицензии, необходимо быть администратором глобальной лицензии, лицензии и пользователя.</span><span class="sxs-lookup"><span data-stu-id="5480c-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="5480c-110">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5480c-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="5480c-111">Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5480c-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="5480c-112">Вы также можете [удалить учетные записи пользователей,](../add-users/delete-a-user.md) которые были назначены лицензии, чтобы сделать их лицензию доступной для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="5480c-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="5480c-113">При удалении учетной записи пользователя их лицензия сразу же доступна для назначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="5480c-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="5480c-114">Использование страницы Лицензии для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="5480c-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="5480c-115">При использовании страницы **Лицензии** для отозвал лицензии, вы отозвал лицензии для определенного продукта для до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="5480c-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5480c-116">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="5480c-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5480c-117">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу **Биллинг** > **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="5480c-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5480c-118">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу **Биллинг** > **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="5480c-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5480c-119">Выберите продукт, для которого необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5480c-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="5480c-120">Выберите пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5480c-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="5480c-121">Выберите **лицензии unassign**.</span><span class="sxs-lookup"><span data-stu-id="5480c-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="5480c-122">В поле **Unassign licenses** выберите **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="5480c-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="5480c-123">Используйте страницу Активные пользователи для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="5480c-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="5480c-124">Если вы используете **страницу Активные** пользователи для ненамеряния лицензий, вы не передаете лицензии на продукты от пользователей.</span><span class="sxs-lookup"><span data-stu-id="5480c-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="5480c-125">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="5480c-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="5480c-126">В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5480c-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5480c-127">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу Активные пользователи **Биллинга.** > </span><span class="sxs-lookup"><span data-stu-id="5480c-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5480c-128">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу Активные пользователи **Биллинга.** > </span><span class="sxs-lookup"><span data-stu-id="5480c-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5480c-129">Выберите строку пользователя, для чего необходимо отогнать лицензию.</span><span class="sxs-lookup"><span data-stu-id="5480c-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="5480c-130">В области справа выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="5480c-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="5480c-131">**Расширите раздел Лицензии,** очистите поля для лицензий, которые необходимо отостановить, а затем выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="5480c-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="5480c-132">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="5480c-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5480c-133">В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5480c-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5480c-134">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования</a>перейдите на страницу Активные пользователи **Биллинга.** > </span><span class="sxs-lookup"><span data-stu-id="5480c-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5480c-135">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования</a>перейдите на страницу Активные пользователи **Биллинга.** > </span><span class="sxs-lookup"><span data-stu-id="5480c-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5480c-136">Выберите круги рядом с именами пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5480c-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="5480c-137">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="5480c-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="5480c-138">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5480c-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="5480c-139">В нижней части области **Заменить** существующие продукты выберите удалить все лицензии на продукты из выбранного окна пользователей, а затем выберите **заменить**  \> **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5480c-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="5480c-140">Что происходит с данными пользователя при удале лицензии?</span><span class="sxs-lookup"><span data-stu-id="5480c-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="5480c-141">При удалении лицензии у пользователя данные, связанные с этой учетной записью, удерживаются в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5480c-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="5480c-142">После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="5480c-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="5480c-143">Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удаляется из центра администрирования Microsoft 365 или удаляется с помощью синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5480c-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="5480c-144">Дополнительные сведения см. в [сайте Хранения и удаления OneDrive.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="5480c-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="5480c-145">При удалении лицензии почтовый ящик пользователя больше не будет искаться с помощью средства поиска электронных данных, например поиска контента или предварительного поиска электронных данных.</span><span class="sxs-lookup"><span data-stu-id="5480c-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="5480c-146">Дополнительные сведения см. в материалах "Поиск отключенных или от лицензированных почтовых ящиков" в "Поиск контента" [в Microsoft 365.](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="5480c-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="5480c-147">Если у вас есть подписка enterprise, например Office 365 Enterprise E3, Exchange Online позволяет сохранять данные почтовых ящиков удаленных учетных записей пользователей с помощью неактивных почтовых [ящиков.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5480c-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="5480c-148">Дополнительные сведения см. в рублях Создание и управление неактивными почтовыми [ящиками в Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="5480c-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="5480c-149">Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии, а также как получить доступ к данным после этого, см. в см. в twitter [Remove a former employee.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="5480c-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="5480c-150">Если вы удалите лицензию пользователя и у них все еще установлены приложения Office, они увидят ошибки без лицензии на продукт и активацию в [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) при использовании приложений Office.</span><span class="sxs-lookup"><span data-stu-id="5480c-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5480c-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5480c-151">Next steps</span></span>

<span data-ttu-id="5480c-152">Если вы не собираетесь перенаходить неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за больше лицензий, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="5480c-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="5480c-153">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="5480c-153">Related content</span></span>

<span data-ttu-id="5480c-154">[Удаление лицензий из подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5480c-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="5480c-155">[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5480c-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="5480c-156">[Понимание подписок и лицензий в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5480c-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>