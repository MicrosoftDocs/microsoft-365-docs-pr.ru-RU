---
title: Закрытие учетной записи
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Сведения о том, как закрыть учетную запись с помощью корпорации Майкрософт.
ms.openlocfilehash: e41d11502b0c0f738cc23405c387bd5fca1cb0fe
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141282"
---
# <a name="close-your-account"></a><span data-ttu-id="92a6b-103">Закрытие учетной записи</span><span class="sxs-lookup"><span data-stu-id="92a6b-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="92a6b-104">Изменяется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="92a6b-104">The admin center is changing.</span></span> <span data-ttu-id="92a6b-105">Если ваш интерфейс не отвечает указанным здесь сведениям, ознакомьтесь [со статьей о новом центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="92a6b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="92a6b-106">Когда вы закрываете свою учетную запись в Microsoft, вся информация, связанная с вашей учетной записью, удаляется.</span><span class="sxs-lookup"><span data-stu-id="92a6b-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="92a6b-107">Эта информация включает в себя подписки, лицензии, способы оплаты, пользователей и пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="92a6b-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="92a6b-108">Прежде чем приступать к этому процессу, обязательно выполните резервное копирование всех данных, которые необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="92a6b-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="92a6b-109">Шаг 1: удаление пользователей</span><span class="sxs-lookup"><span data-stu-id="92a6b-109">Step 1: Delete users</span></span>

<span data-ttu-id="92a6b-110">Удалите всех пользователей за исключением одного глобального администратора, который завершает действия для закрытия учетной записи.</span><span class="sxs-lookup"><span data-stu-id="92a6b-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="92a6b-111">Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="92a6b-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="92a6b-112">Если пользователи синхронизируются из локальной среды, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью командлетов портала Azure или Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92a6b-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="92a6b-113">Чтобы удалить пользователей, обратитесь к <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">администратору управления пользователями: Удаление одного или нескольких пользователей</a>.</span><span class="sxs-lookup"><span data-stu-id="92a6b-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="92a6b-114">Вы также можете использовать командлет <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove – MsolUser</a> PowerShell для массового удаления пользователей.</span><span class="sxs-lookup"><span data-stu-id="92a6b-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="92a6b-115">Если организация использует службу Active Directory, которая синхронизируется с Azure AD, удалите учетную запись пользователя из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92a6b-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="92a6b-116">Инструкции см в разделе <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">массовое удаление пользователей в Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="92a6b-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="92a6b-117">Шаг 2: Отмена всех активных подписок</span><span class="sxs-lookup"><span data-stu-id="92a6b-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="92a6b-118">В центре администрирования перейдите на страницу **выставление счетов** > по<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">продуктам</a> .</span><span class="sxs-lookup"><span data-stu-id="92a6b-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="92a6b-119">Если список подписок находится в представлении **таблицы** , справа выберите **карточки**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="92a6b-120">Найдите активную подписку, а затем в разделе **параметры & действий** выберите **Отменить подписку**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="92a6b-121">Следуйте инструкциям для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="92a6b-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="92a6b-122">Повторите шаги с 1 по 4 для отмены всех активных подписок.</span><span class="sxs-lookup"><span data-stu-id="92a6b-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="92a6b-123">Шаг 3: удаление всех отключенных подписок</span><span class="sxs-lookup"><span data-stu-id="92a6b-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="92a6b-124">В центре администрирования перейдите на страницу **выставление счетов** > по<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">продуктам</a> .</span><span class="sxs-lookup"><span data-stu-id="92a6b-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="92a6b-125">Если список подписок находится в представлении **таблицы** , справа выберите **карточки**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="92a6b-126">Рядом с полем **состояние подписки**выберите **отключено**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="92a6b-127">Найдите отключенную подписку, а затем в разделе **параметры & действий** нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="92a6b-128">В диалоговом окне **Удаление подписки** установите флажок **я понимаю воздействие** , а затем выберите **удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="92a6b-129">Для каждой отключенной подписки Повторяйте шаги 4 и 5 до тех пор, пока не будут удалены все подписки.</span><span class="sxs-lookup"><span data-stu-id="92a6b-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="92a6b-130">Шаг 4: отключение многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="92a6b-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="92a6b-131">В центре администрирования перейдите на страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a> .</span><span class="sxs-lookup"><span data-stu-id="92a6b-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="92a6b-132">Выберите **многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="92a6b-133">На странице многофакторная проверка подлинности отключите все учетные записи, кроме учетной записи глобального администратора, которую вы используете в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="92a6b-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="92a6b-134">Вы также можете <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">Отключить многофакторную проверку подлинности для нескольких пользователей с помощью PowerShell</a>.</span><span class="sxs-lookup"><span data-stu-id="92a6b-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="92a6b-135">Шаг 5: Удаление каталога в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="92a6b-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="92a6b-136">Войдите в <a href="https://aad.portal.azure.com/" target="_blank">центр администрирования Azure AD</a> , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="92a6b-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="92a6b-137">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="92a6b-138">Перейдите к каталогу, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="92a6b-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="92a6b-139">Выберите команду **Удалить каталог**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="92a6b-140">Если в каталоге не удается выполнить одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как прохождение проверок.</span><span class="sxs-lookup"><span data-stu-id="92a6b-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="92a6b-141">После того как вы пройдете все проверки, нажмите кнопку **Удалить** , чтобы завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="92a6b-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="92a6b-142">После выполнения этого последнего действия ваша учетная запись будет закрыта и удалена.</span><span class="sxs-lookup"><span data-stu-id="92a6b-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
