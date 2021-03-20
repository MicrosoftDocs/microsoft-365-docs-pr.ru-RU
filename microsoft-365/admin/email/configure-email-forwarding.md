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
description: Настройка отправки электронной почты на одну или несколько учетных записей электронной почты с помощью Office365.
ms.openlocfilehash: 593a4d1ca906bdee44ec00e260949ff75b582340
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915894"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="cffa0-103">Настройка отправки электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cffa0-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cffa0-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="cffa0-104">The admin center is changing.</span></span> <span data-ttu-id="cffa0-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cffa0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cffa0-106">В качестве администратора организации у вас могут быть требования к компании, чтобы настроить пересылку электронной почты для почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="cffa0-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="cffa0-107">Переадресация позволяет пересылать сообщения, отправленные в почтовый ящик пользователя, в другой почтовый ящик в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="cffa0-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cffa0-108">Вы можете использовать политики исходящие фильтры нежелательной почты для управления автоматической переадружаемой к внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="cffa0-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="cffa0-109">Дополнительные сведения см. в [веб-сайте Control automatic external email forwarding in Microsoft 365.](../../security/office-365-security/external-email-forwarding.md?preserve-view=true&view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="cffa0-109">For more information, see [Control automatic external email forwarding in Microsoft 365](../../security/office-365-security/external-email-forwarding.md?preserve-view=true&view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="cffa0-110">Настройка переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="cffa0-110">Configure email forwarding</span></span>

<span data-ttu-id="cffa0-111">Прежде чем настроить отправку электронной почты, обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="cffa0-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="cffa0-112">После того как вы настроили пересылание электронной почты, будут пересылаться только новые сообщения, отправленные в почтовый ящик.  </span><span class="sxs-lookup"><span data-stu-id="cffa0-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="cffa0-113">Для переададки электронной почты требуется,  *чтобы у учетной*  записи была лицензия.</span><span class="sxs-lookup"><span data-stu-id="cffa0-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="cffa0-114">При настройке пересылания электронной почты из-за того, что пользователь покинул организацию, другим вариантом является преобразование своего почтового ящика [в общий почтовый ящик.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="cffa0-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="cffa0-115">Таким образом, несколько человек могут получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="cffa0-115">This way several people can access it.</span></span> <span data-ttu-id="cffa0-116">Однако общий почтовый ящик не может превышать 50 ГБ.</span><span class="sxs-lookup"><span data-stu-id="cffa0-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="cffa0-117">Для этого необходимо быть администратором Exchange или глобальным администратором в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cffa0-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="cffa0-118">Дополнительные сведения см. в разделе [О ролях администратора.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cffa0-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cffa0-119">В центре администрирования перейдите на страницу **Пользователи** \> **[Активные пользователи.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="cffa0-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="cffa0-120">Выберите имя пользователя, адрес электронной почты которого необходимо отправить для открытия страницы свойств.</span><span class="sxs-lookup"><span data-stu-id="cffa0-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="cffa0-121">На **вкладке Почта** выберите **Управление пересылками электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="cffa0-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="cffa0-122">На странице пересылания электронной почты выберите forward all emails sent **to this mailbox,** enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span><span class="sxs-lookup"><span data-stu-id="cffa0-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cffa0-123">Если вы не видите этот параметр, убедитесь, что лицензия назначена учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cffa0-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cffa0-124">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="cffa0-124">Select **Save changes**.</span></span>

    <span data-ttu-id="cffa0-125">**Чтобы перенаправить несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook, чтобы переад.</span><span class="sxs-lookup"><span data-stu-id="cffa0-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cffa0-126">Дополнительные новости см. в [тексте Правила использования для автоматической переададки сообщений.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="cffa0-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="cffa0-127">Или в центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте к ней [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадстройку, чтобы указать на DL с помощью инструкций в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cffa0-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="cffa0-128">Не удаляйте учетную запись пользователя, переададрующего электронную почту, или удаляйте лицензию!</span><span class="sxs-lookup"><span data-stu-id="cffa0-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cffa0-129">Если вы это сделаете, переададка электронной почты остановится.</span><span class="sxs-lookup"><span data-stu-id="cffa0-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cffa0-130">В центре администрирования перейдите на страницу **Пользователи** \> **[Активные пользователи.](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="cffa0-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="cffa0-131">Выберите имя пользователя, адрес электронной почты которого необходимо отправить для открытия страницы свойств.</span><span class="sxs-lookup"><span data-stu-id="cffa0-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="cffa0-132">Расширение **параметров почты,** а затем в разделе **Пересылание** электронной почты выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cffa0-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="cffa0-133">На странице переададка электронной почты задай окантовку **On,** введите адрес переададки и выберите, хотите ли вы сохранить копию отправленных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cffa0-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cffa0-134">Если вы не видите этот параметр, убедитесь, что лицензия назначена учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cffa0-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cffa0-135">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cffa0-135">Select **Save**.</span></span>

   <span data-ttu-id="cffa0-136">**Чтобы перенаправить несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook, чтобы переад.</span><span class="sxs-lookup"><span data-stu-id="cffa0-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cffa0-137">Дополнительные новости см. в [тексте Правила использования для автоматической переададки сообщений.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="cffa0-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="cffa0-138">Или в центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте к ней [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадстройку, чтобы указать на DL с помощью инструкций в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cffa0-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="cffa0-139">Не удаляйте учетную запись пользователя, переададрующего электронную почту, или удаляйте лицензию!</span><span class="sxs-lookup"><span data-stu-id="cffa0-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cffa0-140">Если вы это сделаете, переададка электронной почты остановится.</span><span class="sxs-lookup"><span data-stu-id="cffa0-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cffa0-141">В центре администрирования перейдите на страницу **Пользователи** \> **[Активные пользователи.](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="cffa0-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="cffa0-142">Выберите имя пользователя, адрес электронной почты которого необходимо отправить для открытия страницы свойств.</span><span class="sxs-lookup"><span data-stu-id="cffa0-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="cffa0-143">Расширение **параметров почты,** а затем в разделе **Пересылание** электронной почты выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cffa0-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="cffa0-144">На странице переададка электронной почты задай окантовку **On,** введите адрес переададки и выберите, хотите ли вы сохранить копию отправленных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cffa0-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cffa0-145">Если вы не видите этот параметр, убедитесь, что лицензия назначена учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cffa0-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cffa0-146">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cffa0-146">Select **Save**.</span></span>

   <span data-ttu-id="cffa0-147">**Чтобы перенаправить несколько адресов** электронной почты, можно попросить пользователя настроить правило в Outlook, чтобы переад.</span><span class="sxs-lookup"><span data-stu-id="cffa0-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cffa0-148">Дополнительные новости см. в [тексте Правила использования для автоматической переададки сообщений.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="cffa0-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="cffa0-149">Или в центре администрирования создайте группу [рассылки,](../setup/create-distribution-lists.md)добавьте к ней [адреса,](add-user-or-contact-to-distribution-list.md)а затем настройте переадстройку, чтобы указать на DL с помощью инструкций в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cffa0-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="cffa0-150">Не удаляйте учетную запись пользователя, переададрующего электронную почту, или удаляйте лицензию!</span><span class="sxs-lookup"><span data-stu-id="cffa0-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cffa0-151">Если вы это сделаете, переададка электронной почты остановится.</span><span class="sxs-lookup"><span data-stu-id="cffa0-151">If you do, email forwarding will stop.</span></span>

::: moniker-end