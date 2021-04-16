---
title: Закрытие учетной записи
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Узнайте, как закрыть учетную запись в Корпорации Майкрософт.
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860551"
---
# <a name="close-your-account"></a><span data-ttu-id="e132c-103">Закрытие учетной записи</span><span class="sxs-lookup"><span data-stu-id="e132c-103">Close your account</span></span>

<span data-ttu-id="e132c-104">Когда вы закрываете свою учетную запись в Microsoft, вся информация, связанная с вашей учетной записью, удаляется.</span><span class="sxs-lookup"><span data-stu-id="e132c-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="e132c-105">Эта информация включает в себя подписки, лицензии, способы оплаты, пользователей и пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="e132c-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e132c-106">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="e132c-106">Before you begin</span></span>

<span data-ttu-id="e132c-107">Перед началом этого процесса обязательно сделайте резервную копию любых данных, которые вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="e132c-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="e132c-108">Для выполнения описанных в этой статье действий необходимы права глобального администратора или администратора по выставлению счетов.</span><span class="sxs-lookup"><span data-stu-id="e132c-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="e132c-109">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e132c-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="e132c-110">Шаг 1. Удаление пользователей</span><span class="sxs-lookup"><span data-stu-id="e132c-110">Step 1: Delete users</span></span>

<span data-ttu-id="e132c-111">Удалите всех пользователей, за исключением одного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e132c-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="e132c-112">Глобальный администратор завершает действия по закрытию учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e132c-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="e132c-113">Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e132c-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="e132c-114">Если пользователи синхронизируются из локального, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью портала Azure или cmdlets Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e132c-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="e132c-115">Чтобы удалить пользователей, см. <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">в публикации Администратор управления пользователями. Удалите одного или несколько пользователей.</a></span><span class="sxs-lookup"><span data-stu-id="e132c-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="e132c-116">Вы также можете использовать комдлет <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell для удаления пользователей оптом.</span><span class="sxs-lookup"><span data-stu-id="e132c-116">You can also use the <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="e132c-117">Если в организации используется Active Directory, синхронизируются с Microsoft Azure Active Directory (Azure AD), удалите учетную запись пользователя из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e132c-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="e132c-118">Инструкции см. в <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">публикации Bulk delete users in Azure Active Directory.</a></span><span class="sxs-lookup"><span data-stu-id="e132c-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="e132c-119">Шаг 2. Отмена всех активных подписок</span><span class="sxs-lookup"><span data-stu-id="e132c-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="e132c-120">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="e132c-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e132c-121">На **вкладке Продукты** найдите активную подписку.</span><span class="sxs-lookup"><span data-stu-id="e132c-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="e132c-122">Нажмите **Дополнительные действия** (три точки) и выберите **Отменить подписку**.</span><span class="sxs-lookup"><span data-stu-id="e132c-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="e132c-123">В области **Отмена подписки** выберите причину, по которой вы отменяете подписку.</span><span class="sxs-lookup"><span data-stu-id="e132c-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="e132c-124">Вы можете предоставить отзыв.</span><span class="sxs-lookup"><span data-stu-id="e132c-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="e132c-125">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e132c-125">Select **Save**.</span></span>
5. <span data-ttu-id="e132c-126">Повторите действия с 1 по 4, чтобы отменить все активные подписки.</span><span class="sxs-lookup"><span data-stu-id="e132c-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="e132c-127">Шаг 3. Удаление всех отключенных подписок</span><span class="sxs-lookup"><span data-stu-id="e132c-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="e132c-128">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="e132c-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e132c-129">На **вкладке Продукты** выберите отключенную подписку.</span><span class="sxs-lookup"><span data-stu-id="e132c-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="e132c-130">На странице сведения о подписке в разделе **Параметры** подписки и параметров оплаты выберите **Удалить подписку.**</span><span class="sxs-lookup"><span data-stu-id="e132c-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="e132c-131">В области **Удалить подписку** выберите **Удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="e132c-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="e132c-132">В **диалоговом окне Удалить** подписку выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="e132c-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="e132c-133">Для каждой отключенной подписки повторите действия от 3 до 5 до удаления всех подписок.</span><span class="sxs-lookup"><span data-stu-id="e132c-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="e132c-134">Если вы не можете немедленно удалить отключенную подписку, обратитесь <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">в службу поддержки</a></span><span class="sxs-lookup"><span data-stu-id="e132c-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="e132c-135">Шаг 4. Отключение многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e132c-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="e132c-136">Во входе в центр администрирования с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e132c-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="e132c-137">Чтобы проверить, какие роли у вас есть, см. [в этой информации.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="e132c-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="e132c-138">Перейдите на **страницу Пользователи**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи.</a></span><span class="sxs-lookup"><span data-stu-id="e132c-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="e132c-139">Выберите **многофакторную проверку подлинности.**</span><span class="sxs-lookup"><span data-stu-id="e132c-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="e132c-140">На странице многофакторной проверки подлинности отключать все учетные записи, за исключением глобальной учетной записи администратора, которую вы используете в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="e132c-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="e132c-141">Вы также можете использовать PowerShell для отключения <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">многофакторной</a>проверки подлинности для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="e132c-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="e132c-142">Шаг 5. Удаление каталога в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e132c-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="e132c-143">Во входе в центр администрирования <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e132c-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="e132c-144">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e132c-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="e132c-145">Переключиться на организацию, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e132c-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="e132c-146">Выберите **Удалить клиента**.</span><span class="sxs-lookup"><span data-stu-id="e132c-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="e132c-147">Если в организации не удается пройти одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как проходить проверки.</span><span class="sxs-lookup"><span data-stu-id="e132c-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="e132c-148">После того как вы пройдете все проверки, **выберите Удаление** для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="e132c-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="e132c-149">После завершения этого заключительного шага ваша учетная запись в Microsoft закрывается и удаляется.</span><span class="sxs-lookup"><span data-stu-id="e132c-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>