---
title: Настройка переадресации электронной почты
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Настройка переадстройки электронной почты в одну или несколько учетных записей электронной почты с помощью Office 365.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926646"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="a6098-103">Настройка переадстройки электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a6098-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a6098-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="a6098-104">The admin center is changing.</span></span> <span data-ttu-id="a6098-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="a6098-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="a6098-106">Администратор организации может предъявлять требования к компании для организации, чтобы настроить переадминант электронной почты для почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="a6098-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="a6098-107">Переадресация позволяет пересылать сообщения, отправленные в почтовый ящик пользователя, в другой почтовый ящик в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="a6098-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6098-108">Политики фильтрации исходящие нежелательной почты можно использовать для управления автоматической переадружаемой почтой внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="a6098-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="a6098-109">Дополнительные сведения см. в поддоме "Управление автоматической переадружаемой внешней электронной [почтой" в Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="a6098-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="a6098-110">Настройка переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="a6098-110">Configure email forwarding</span></span>

<span data-ttu-id="a6098-111">Прежде чем настроить переадстройку электронной почты, обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="a6098-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="a6098-112">После того как вы настроили пересылку электронной почты, будут пересылаться только новые сообщения, отправленные из почтового ящика.  </span><span class="sxs-lookup"><span data-stu-id="a6098-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="a6098-113">Для переададантки электронной почты необходимо, чтобы у  *учетной записи*  была лицензия.</span><span class="sxs-lookup"><span data-stu-id="a6098-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="a6098-114">При настройке переададации электронной почты из-за того, что пользователь покинул организацию, можно преобразовать почтовый ящик в общий [почтовый ящик.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="a6098-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="a6098-115">Таким образом несколько человек смогут получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="a6098-115">This way several people can access it.</span></span> <span data-ttu-id="a6098-116">Однако общий почтовый ящик не может превышать 50 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a6098-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="a6098-117">Для этого необходимо быть администратором Exchange или глобальным администратором в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6098-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="a6098-118">Дополнительные сведения см. в разделе ["Роли администраторов".](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a6098-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a6098-119">В Центре администрирования перейдите на страницу **"Активные** \> **[пользователи".](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="a6098-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="a6098-120">Выберите имя пользователя, сообщения электронной почты которого вы хотите переадранить, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="a6098-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="a6098-121">На **вкладке "Почта"** выберите **"Управление пересылками электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="a6098-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="a6098-122">На странице пересылания электронной почты выберите "Пересылать все сообщения электронной почты,отправленные в этот почтовый ящик", введите адрес пересылки и выберите, хотите ли вы сохранить копию пересылаемой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a6098-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a6098-123">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="a6098-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a6098-124">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="a6098-124">Select **Save changes**.</span></span>

    <span data-ttu-id="a6098-125">**Чтобы перенаправить на несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook для переададратовки на адреса.</span><span class="sxs-lookup"><span data-stu-id="a6098-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a6098-126">Дополнительные узнать см. в поддоме "Использование правил [для автоматической переададки сообщений".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="a6098-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="a6098-127">Или в Центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте в нее [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадпределение так, чтобы она укачилась на DL, используя инструкции, инструкции из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a6098-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="a6098-128">Не удаляйте учетную запись пользователя, сообщения электронной почты которого вы переададаете, или удаляйте их лицензию!</span><span class="sxs-lookup"><span data-stu-id="a6098-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a6098-129">В этом случае переададка почты будет остановиться.</span><span class="sxs-lookup"><span data-stu-id="a6098-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a6098-130">В Центре администрирования перейдите на страницу **"Активные** \> **[пользователи".](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="a6098-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="a6098-131">Выберите имя пользователя, сообщения электронной почты которого вы хотите переадранить, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="a6098-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="a6098-132">Раз **развернуть параметры почты,** а затем в **разделе** "Пересылание электронной почты" выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a6098-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="a6098-133">On the email forwarding page, set the toggle to **On,** enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span><span class="sxs-lookup"><span data-stu-id="a6098-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a6098-134">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="a6098-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a6098-135">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a6098-135">Select **Save**.</span></span>

   <span data-ttu-id="a6098-136">**Чтобы перенаправить на несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook для переададратовки на адреса.</span><span class="sxs-lookup"><span data-stu-id="a6098-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a6098-137">Дополнительные узнать см. в поддоме "Использование правил [для автоматической переададки сообщений".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="a6098-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="a6098-138">Или в Центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте в нее [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадпределение так, чтобы она укачилась на DL, используя инструкции, инструкции из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a6098-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="a6098-139">Не удаляйте учетную запись пользователя, сообщения электронной почты которого вы переададаете, или удаляйте их лицензию!</span><span class="sxs-lookup"><span data-stu-id="a6098-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a6098-140">В этом случае переададка почты будет остановиться.</span><span class="sxs-lookup"><span data-stu-id="a6098-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a6098-141">В Центре администрирования перейдите на страницу **"Активные** \> **[пользователи".](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="a6098-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="a6098-142">Выберите имя пользователя, сообщения электронной почты которого вы хотите переадранить, чтобы открыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="a6098-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="a6098-143">Раз **развернуть параметры почты,** а затем в **разделе** "Пересылание электронной почты" выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a6098-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="a6098-144">On the email forwarding page, set the toggle to **On,** enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span><span class="sxs-lookup"><span data-stu-id="a6098-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a6098-145">Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="a6098-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a6098-146">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a6098-146">Select **Save**.</span></span>

   <span data-ttu-id="a6098-147">**Чтобы перенаправить на несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook для переададратовки на адреса.</span><span class="sxs-lookup"><span data-stu-id="a6098-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a6098-148">Дополнительные узнать см. в поддоме "Использование правил [для автоматической переададки сообщений".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="a6098-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="a6098-149">Или в Центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте в нее [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадпределение так, чтобы она укачилась на DL, используя инструкции, инструкции из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a6098-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="a6098-150">Не удаляйте учетную запись пользователя, сообщения электронной почты которого вы переададаете, или удаляйте их лицензию!</span><span class="sxs-lookup"><span data-stu-id="a6098-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a6098-151">В этом случае переададка почты будет остановиться.</span><span class="sxs-lookup"><span data-stu-id="a6098-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
