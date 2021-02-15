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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376321"
---
# <a name="close-your-account"></a><span data-ttu-id="2891f-103">Закрытие учетной записи</span><span class="sxs-lookup"><span data-stu-id="2891f-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2891f-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="2891f-104">The admin center is changing.</span></span> <span data-ttu-id="2891f-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="2891f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="2891f-106">Когда вы закрываете свою учетную запись в Microsoft, вся информация, связанная с вашей учетной записью, удаляется.</span><span class="sxs-lookup"><span data-stu-id="2891f-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="2891f-107">Эта информация включает в себя подписки, лицензии, способы оплаты, пользователей и пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="2891f-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2891f-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="2891f-108">Before you begin</span></span>

<span data-ttu-id="2891f-109">Перед началом этого процесса обязательно сделайте резервную копию любых данных, которые вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="2891f-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="2891f-110">Для выполнения задач в этой статье необходимо быть глобальным администратором или администратором вы выставления счета.</span><span class="sxs-lookup"><span data-stu-id="2891f-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="2891f-111">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2891f-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="2891f-112">Шаг 1. Удаление пользователей</span><span class="sxs-lookup"><span data-stu-id="2891f-112">Step 1: Delete users</span></span>

<span data-ttu-id="2891f-113">Удалите всех пользователей, кроме одного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="2891f-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="2891f-114">Глобальный администратор завершает действия по закрытию учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2891f-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="2891f-115">Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2891f-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="2891f-116">Если пользователи синхронизируются из локальной сети, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью портала Azure или с помощью cmdlets Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2891f-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="2891f-117">Чтобы удалить пользователей, см. <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">"Администратор управления пользователями: удаление одного или более пользователей"</a></span><span class="sxs-lookup"><span data-stu-id="2891f-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="2891f-118">Для массового удаления пользователей можно также использовать <a href="https://go.microsoft.com/fwlink/?linkid=842230">msolUser</a> PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2891f-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="2891f-119">Если ваша организация использует Active Directory, синхронизируются с Microsoft Azure Active Directory (Azure AD), удалите учетную запись пользователя из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2891f-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="2891f-120">Инструкции см. в <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">подсети "Массовое удаление пользователей в Azure Active Directory".</a></span><span class="sxs-lookup"><span data-stu-id="2891f-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="2891f-121">Шаг 2. Отмена всех активных подписок</span><span class="sxs-lookup"><span data-stu-id="2891f-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="2891f-122">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="2891f-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2891f-123">На **вкладке** "Продукты" найдите активную подписку.</span><span class="sxs-lookup"><span data-stu-id="2891f-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="2891f-124">Нажмите **Дополнительные действия** (три точки) и выберите **Отменить подписку**.</span><span class="sxs-lookup"><span data-stu-id="2891f-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="2891f-125">В области **Отмена подписки** выберите причину, по которой вы отменяете подписку.</span><span class="sxs-lookup"><span data-stu-id="2891f-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="2891f-126">Вы можете предоставить отзыв.</span><span class="sxs-lookup"><span data-stu-id="2891f-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="2891f-127">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2891f-127">Select **Save**.</span></span>
5. <span data-ttu-id="2891f-128">Повторите шаги 1-4, чтобы отменить все активные подписки.</span><span class="sxs-lookup"><span data-stu-id="2891f-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="2891f-129">Шаг 3. Удаление всех отключенных подписок</span><span class="sxs-lookup"><span data-stu-id="2891f-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="2891f-130">В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="2891f-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2891f-131">На **вкладке** "Продукты" выберите отключенную подписку.</span><span class="sxs-lookup"><span data-stu-id="2891f-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="2891f-132">На странице сведений о подписке в **разделе** "Параметры подписки и оплаты" выберите **"Удалить подписку".**</span><span class="sxs-lookup"><span data-stu-id="2891f-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="2891f-133">В области **"Удаление подписки"** выберите **"Удалить подписку".**</span><span class="sxs-lookup"><span data-stu-id="2891f-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="2891f-134">В **диалоговом окне** "Удаление подписки" выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="2891f-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="2891f-135">Для каждой отключенной подписки повторите шаги 3–5, пока не будут удалены все подписки.</span><span class="sxs-lookup"><span data-stu-id="2891f-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="2891f-136">Если вы не можете сразу удалить отключенную подписку, обратитесь <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">в службу поддержки</a></span><span class="sxs-lookup"><span data-stu-id="2891f-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="2891f-137">Шаг 4. Отключение многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="2891f-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="2891f-138">Во sign in to the admin center with a Global administrator account.</span><span class="sxs-lookup"><span data-stu-id="2891f-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="2891f-139">Чтобы проверить, какие роли у вас есть, см. "Проверка ролей [администратора" в организации.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="2891f-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="2891f-140">Перейдите на **страницу**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">"Активные пользователи".</a></span><span class="sxs-lookup"><span data-stu-id="2891f-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="2891f-141">Выберите **многофакторную проверку подлинности.**</span><span class="sxs-lookup"><span data-stu-id="2891f-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="2891f-142">На странице многофакторной проверки подлинности отключать все учетные записи, кроме используемой учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="2891f-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="2891f-143">Вы также <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">можете использовать PowerShell, чтобы</a>отключить многофакторную проверку подлинности для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="2891f-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="2891f-144">Шаг 5. Удаление каталога в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2891f-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="2891f-145">Во sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span><span class="sxs-lookup"><span data-stu-id="2891f-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="2891f-146">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2891f-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="2891f-147">Переключиться на организацию, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="2891f-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="2891f-148">Выберите **"Удалить клиент"**.</span><span class="sxs-lookup"><span data-stu-id="2891f-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="2891f-149">Если в организации не удается пройти одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как их пройти.</span><span class="sxs-lookup"><span data-stu-id="2891f-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="2891f-150">После выполнения всех проверок выберите **"Удалить",** чтобы завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="2891f-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="2891f-151">После завершения этого заключительного шага ваша учетная запись в Майкрософт будет закрыта и удалена.</span><span class="sxs-lookup"><span data-stu-id="2891f-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>