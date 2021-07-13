---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: Метод, который используется для ненамеряния лицензий на продукты, зависит от того, вы отозвале лицензии у определенных пользователей или от конкретного продукта.
ms.date: 06/07/2021
ms.openlocfilehash: 8a67d7e690ff07631f696a97d6ed59925bc871df
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392495"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="5b3c1-103">Отмена назначения лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="5b3c1-103">Unassign licenses from users</span></span>

<span data-ttu-id="5b3c1-104">Лицензии можно отогнать от пользователей на странице **Активные** пользователи или на странице **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="5b3c1-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="5b3c1-105">Метод, который вы используете, зависит от того, хотите ли вы отогнать лицензии на продукт от определенных пользователей или отогнать лицензии пользователей от конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="5b3c1-106">В качестве администратора вы не можете назначить лицензии или отменить их назначение для подписок, самостоятельно приобретенных пользователем в организации.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="5b3c1-107">Вы можете [получить контроль над самостоятельно приобретенной подпиской](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), а затем назначить лицензии или отменить их назначение.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5b3c1-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5b3c1-108">Before you begin</span></span>

- <span data-ttu-id="5b3c1-109">Чтобы отогнать лицензии, необходимо быть администратором глобальной лицензии, лицензии и пользователя.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="5b3c1-110">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5b3c1-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="5b3c1-111">Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5b3c1-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="5b3c1-112">Вы также можете [удалить учетные записи пользователей,](../add-users/delete-a-user.md) которые были назначены лицензии, чтобы сделать их лицензию доступной для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="5b3c1-113">При удалении учетной записи пользователя их лицензия сразу же доступна для назначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="5b3c1-114">Использование страницы Лицензии для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="5b3c1-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="5b3c1-115">При использовании страницы **Лицензии** для отозвал лицензии, вы отозвал лицензии для определенного продукта для до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5b3c1-116">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5b3c1-117">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5b3c1-118">В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="5b3c1-119">Выберите продукт, для которого необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="5b3c1-120">Выберите пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="5b3c1-121">Выберите **лицензии unassign**.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="5b3c1-122">В поле **Unassign licenses** выберите **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="5b3c1-123">Используйте страницу Активные пользователи для ненамеряния лицензий</span><span class="sxs-lookup"><span data-stu-id="5b3c1-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="5b3c1-124">Если вы используете **страницу Активные** пользователи для ненамеряния лицензий, вы не передаете лицензии на продукты от пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="5b3c1-125">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="5b3c1-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5b3c1-126">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5b3c1-127">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5b3c1-128">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="5b3c1-129">Выберите строку пользователя, для чего необходимо отогнать лицензию.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="5b3c1-130">На правой панели выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="5b3c1-131">**Расширите раздел Лицензии,** очистите поля для лицензий, которые необходимо отостановить, а затем выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="5b3c1-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="5b3c1-132">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="5b3c1-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5b3c1-133">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5b3c1-134">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5b3c1-135">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="5b3c1-136">Выберите круги рядом с именами пользователей, для которых необходимо отогнать лицензии.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-136">Select the circles next to the names of the users who you want to unassign licenses for.</span></span>
3. <span data-ttu-id="5b3c1-137">Нажмите вверху **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-137">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="5b3c1-138">В области **Управление лицензиями продуктов** выберите **Unassign все изменения**  >  **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="5b3c1-138">In the **Manage product licenses** pane, select **Unassign all** > **Save changes**.</span></span>
5. <span data-ttu-id="5b3c1-139">В нижней части области выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-139">At the bottom of the pane, select **Done**.</span></span>  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="5b3c1-140">Что происходит с данными пользователя при удале лицензии?</span><span class="sxs-lookup"><span data-stu-id="5b3c1-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="5b3c1-141">При удалении лицензии у пользователя Exchange данные, связанные с этой учетной записью, в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="5b3c1-142">После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="5b3c1-143">Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удаляется из Центр администрирования Microsoft 365 или удаляется с помощью синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="5b3c1-144">Дополнительные сведения см. [в OneDrive хранения и удаления.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="5b3c1-145">При удалении лицензии почтовый ящик пользователя больше не будет искаться с помощью средства поиска электронных данных, например поиска контента или Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="5b3c1-146">Дополнительные сведения см. в материалах "Поиск отключенных или от лицензированных почтовых ящиков" в области поиска контента [в Microsoft 365.](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="5b3c1-147">Если у Enterprise подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранять данные почтовых ящиков удаленных учетных записей пользователей с помощью неактивных почтовых [ящиков.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="5b3c1-148">Дополнительные сведения см. в [сообщении Create and manage inactive mailboxes in Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="5b3c1-149">Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии, а также как получить доступ к данным после этого, см. в этой записи [Remove a former employee.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="5b3c1-150">Если вы удалите лицензию пользователя и Office установлены приложения, [](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) они увидят ошибки без лицензии на продукт и активацию Office при использовании Office приложений.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b3c1-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5b3c1-151">Next steps</span></span>

<span data-ttu-id="5b3c1-152">Если вы не собираетесь перенаходить неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за больше лицензий, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="5b3c1-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="5b3c1-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b3c1-153">Related content</span></span>

<span data-ttu-id="5b3c1-154">[Удаление лицензий из подписки](../../commerce/licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="5b3c1-155">[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="5b3c1-156">[Понимание подписок и лицензий в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5b3c1-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
