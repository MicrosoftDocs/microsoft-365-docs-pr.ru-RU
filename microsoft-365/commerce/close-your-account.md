---
title: Закрытие учетной записи
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Узнайте, как закрыть учетную запись в Корпорации Майкрософт.
ms.date: 04/02/2021
ms.openlocfilehash: 767a82088500bc24c0d4755a2dafd40742fc796c
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331770"
---
# <a name="close-your-account"></a><span data-ttu-id="d2537-103">Закрытие учетной записи</span><span class="sxs-lookup"><span data-stu-id="d2537-103">Close your account</span></span>

<span data-ttu-id="d2537-104">Когда вы закрываете свою учетную запись в Microsoft, вся информация, связанная с вашей учетной записью, удаляется.</span><span class="sxs-lookup"><span data-stu-id="d2537-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="d2537-105">Эта информация включает в себя подписки, лицензии, способы оплаты, пользователей и пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="d2537-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d2537-106">Подготовка</span><span class="sxs-lookup"><span data-stu-id="d2537-106">Before you begin</span></span>

<span data-ttu-id="d2537-107">Перед началом этого процесса обязательно сделайте резервную копию любых данных, которые вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="d2537-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="d2537-108">Для выполнения описанных в этой статье действий необходимы права глобального администратора или администратора по выставлению счетов.</span><span class="sxs-lookup"><span data-stu-id="d2537-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="d2537-109">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d2537-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="d2537-110">Шаг 1. Удаление пользователей</span><span class="sxs-lookup"><span data-stu-id="d2537-110">Step 1: Delete users</span></span>

<span data-ttu-id="d2537-111">Удалите всех пользователей, за исключением одного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d2537-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="d2537-112">Глобальный администратор завершает действия по закрытию учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d2537-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="d2537-113">Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2537-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="d2537-114">Если пользователи синхронизируются из локального, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью портала Azure или Azure PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d2537-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="d2537-115">Чтобы удалить пользователей, см. [в публикации Администратор управления пользователями. Удалите одного или несколько пользователей.](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)</span><span class="sxs-lookup"><span data-stu-id="d2537-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="d2537-116">Вы также можете использовать комдлет [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell для удаления пользователей оптом.</span><span class="sxs-lookup"><span data-stu-id="d2537-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="d2537-117">Если в организации используется Active Directory, синхронизируются с Microsoft Azure Active Directory (Azure AD), удалите учетную запись пользователя из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2537-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="d2537-118">Инструкции см. в [публикации Bulk delete users in Azure Active Directory.](/azure/active-directory/users-groups-roles/users-bulk-delete)</span><span class="sxs-lookup"><span data-stu-id="d2537-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="d2537-119">Шаг 2. Отмена всех активных подписок</span><span class="sxs-lookup"><span data-stu-id="d2537-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="d2537-120">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="d2537-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d2537-121">На **вкладке Продукты** найдите активную подписку.</span><span class="sxs-lookup"><span data-stu-id="d2537-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="d2537-122">Нажмите **Дополнительные действия** (три точки) и выберите **Отменить подписку**.</span><span class="sxs-lookup"><span data-stu-id="d2537-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="d2537-123">В области **Отмена подписки** выберите причину, по которой вы отменяете подписку.</span><span class="sxs-lookup"><span data-stu-id="d2537-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="d2537-124">Вы можете предоставить отзыв.</span><span class="sxs-lookup"><span data-stu-id="d2537-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="d2537-125">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d2537-125">Select **Save**.</span></span>
5. <span data-ttu-id="d2537-126">Повторите действия с 1 по 4, чтобы отменить все активные подписки.</span><span class="sxs-lookup"><span data-stu-id="d2537-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="d2537-127">Шаг 3. Удаление всех отключенных подписок</span><span class="sxs-lookup"><span data-stu-id="d2537-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="d2537-128">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="d2537-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d2537-129">На **вкладке Продукты** выберите отключенную подписку.</span><span class="sxs-lookup"><span data-stu-id="d2537-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="d2537-130">На странице сведения о подписке в разделе **Параметры** подписки и параметров оплаты выберите **Удалить подписку.**</span><span class="sxs-lookup"><span data-stu-id="d2537-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="d2537-131">В области **Удалить подписку** выберите **Удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="d2537-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="d2537-132">В **диалоговом окне Удалить** подписку выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="d2537-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="d2537-133">Для каждой отключенной подписки повторите действия от 3 до 5 до удаления всех подписок.</span><span class="sxs-lookup"><span data-stu-id="d2537-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="d2537-134">Если вы не можете немедленно удалить отключенную подписку, обратитесь [в службу поддержки.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="d2537-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="d2537-135">Шаг 4. Отключение многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d2537-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="d2537-136">Во входе в центр администрирования с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d2537-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="d2537-137">Чтобы проверить, какие роли у вас есть, см. [в этой информации.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="d2537-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="d2537-138">Перейдите на **страницу Пользователи**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи.</a></span><span class="sxs-lookup"><span data-stu-id="d2537-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="d2537-139">Выберите **многофакторную проверку подлинности.**</span><span class="sxs-lookup"><span data-stu-id="d2537-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="d2537-140">На странице многофакторной проверки подлинности отключать все учетные записи, за исключением глобальной учетной записи администратора, которую вы используете в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="d2537-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="d2537-141">Вы также можете использовать PowerShell для отключения [многофакторной](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)проверки подлинности для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2537-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="d2537-142">Шаг 5. Удаление каталога в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d2537-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="d2537-143">Во входе в центр администрирования <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d2537-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="d2537-144">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d2537-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d2537-145">Переключиться на организацию, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="d2537-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="d2537-146">Выберите **Удалить клиента**.</span><span class="sxs-lookup"><span data-stu-id="d2537-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="d2537-147">Если в организации не удается пройти одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как проходить проверки.</span><span class="sxs-lookup"><span data-stu-id="d2537-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="d2537-148">После того как вы пройдете все проверки, **выберите Удаление** для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="d2537-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="d2537-149">После завершения этого заключительного шага ваша учетная запись в Microsoft закрывается и удаляется.</span><span class="sxs-lookup"><span data-stu-id="d2537-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
