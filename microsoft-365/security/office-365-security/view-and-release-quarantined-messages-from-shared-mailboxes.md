---
title: Просмотр и освобождение карантинов сообщений из общих почтовых ящиков
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Пользователи могут узнать, как просматривать и действовать в карантинных сообщениях, отправленных в общие почтовые ящики, на которые у них есть разрешения.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e3bf4c84e7a762f7f54f42ff61f0fbdb9dc1edd
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215508"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="faebf-103">Просмотр и освобождение карантинов сообщений из общих почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="faebf-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="faebf-104">Функции, описанные в этой статье, в настоящее время находятся в предварительном просмотре, недоступны для всех и могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="faebf-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="faebf-105">Пользователи могут управлять карантинными сообщениями, если они являются одним из получателей, как описано в "Поиске и выпуске карантиных сообщений как пользователя [в EOP".](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="faebf-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="faebf-106">Но как насчет общих почтовых ящиков, в которых у пользователя есть полный доступ и разрешения отправки как или отправки от имени в почтовый ящик, как описано в общих почтовых ящиках [в Exchange Online?](/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="faebf-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="faebf-107">Ранее для пользователей возможность управлять карантинными сообщениями, отправленными в общий почтовый ящик, требовала, чтобы администраторы не включили автомаппирование для общего почтового ящика (он включен по умолчанию, когда администратор предоставляет пользователю доступ к другому почтовому ящику).</span><span class="sxs-lookup"><span data-stu-id="faebf-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="faebf-108">Однако в зависимости от размера и количества почтовых ящиков, к которые имеет доступ  пользователь, производительность может страдать при попытках Outlook открыть все почтовые ящики, к которые имеет доступ пользователь.</span><span class="sxs-lookup"><span data-stu-id="faebf-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="faebf-109">По этой причине многие администраторы предпочитают удалять [автомаппирование для общих почтовых ящиков.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="faebf-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="faebf-110">Теперь автомаппация больше не требуется пользователям для управления карантинными сообщениями, отправленными в общие почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="faebf-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="faebf-111">Это просто работает.</span><span class="sxs-lookup"><span data-stu-id="faebf-111">It just works.</span></span> <span data-ttu-id="faebf-112">Существует два различных метода доступа к карантинным сообщениям, отправленным в общий почтовый ящик:</span><span class="sxs-lookup"><span data-stu-id="faebf-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="faebf-113">Если администратор [](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) включил уведомления о нежелательной почте для конечных пользователей в политиках по борьбе со спамом, любой  пользователь, который имеет доступ к уведомлениям о нежелательной почте конечных пользователей в общем почтовом ящике, может нажать кнопку Обзор в уведомлении, чтобы перейти на карантин в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="faebf-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="faebf-114">Обратите внимание, что этот метод позволяет пользователям управлять карантинными сообщениями, отправленными в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="faebf-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="faebf-115">Пользователи не могут управлять собственными карантинными сообщениями в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="faebf-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="faebf-116">Пользователь может [перейти на карантин в](find-and-release-quarantined-messages-as-a-user.md)Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="faebf-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="faebf-117">По умолчанию показаны только сообщения, отправленные пользователю.</span><span class="sxs-lookup"><span data-stu-id="faebf-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="faebf-118">Однако пользователь может изменить результаты **Сортировки** (кнопку **ID** сообщения по умолчанию) на адрес электронной почты получателя, ввести общий почтовый ящик, а затем щелкнуть **Обновить,** чтобы увидеть карантинные сообщения, отправленные в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="faebf-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Сортировка карантинов сообщений по адресу электронной почты получателя.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="faebf-120">Независимо от метода, пользователи могут избежать путаницы, включив столбец **Получатель** для карантинов сообщений.</span><span class="sxs-lookup"><span data-stu-id="faebf-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="faebf-121">Максимальное число столбцов для отображения — 7, поэтому пользователю потребуется нажать кнопку **Изменить** столбцы, удалить существующий столбец (например, тип политики), выбрать получателя, а затем нажмите кнопку **Сохранить** или Сохранить по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="faebf-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Удалите столбец тип политики и добавьте столбец Получатель в карантин.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="faebf-123">Важная информация</span><span class="sxs-lookup"><span data-stu-id="faebf-123">Things to keep in mind</span></span>

- <span data-ttu-id="faebf-124">Первый пользователь, который будет действовать в карантинном сообщении, решает судьбу сообщения для всех, кто использует общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="faebf-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="faebf-125">Например, если общий почтовый ящик получает доступ к 10 пользователям и пользователь решает удалить карантиное сообщение, сообщение удаляется для всех 10 пользователей.</span><span class="sxs-lookup"><span data-stu-id="faebf-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="faebf-126">Кроме того, если пользователь решает выпустить сообщение, оно выпущено в общий почтовый ящик и доступно всем другим пользователям общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="faebf-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="faebf-127">В настоящее время кнопка **отправитель** блока недоступна в флажке **Details** для карантинов, отправленных в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="faebf-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="faebf-128">Что касается операций карантина для общих почтовых ящиков, то при использовании вложенных групп безопасности для предоставления доступа к общему почтовому ящику рекомендуется не более двух уровней вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="faebf-128">Regarding quarantine operations for shared mailboxes, if you use nested security groups to grant access to a shared mailbox, we recommend no more than two levels of nested groups.</span></span> <span data-ttu-id="faebf-129">Например, группа A входит в группу B, которая входит в группу C. Чтобы назначить разрешения для общего почтового ящика, не добавляйте пользователя в группу А, а затем назначьте группу C в общий почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="faebf-129">For example, Group A is a member of Group B, which is a member of Group C. To assign permissions to a shared mailbox, don't add the user to Group A and then assign Group C to the shared mailbox.</span></span>  

- <span data-ttu-id="faebf-130">Чтобы управлять карантинными сообщениями для общего почтового ящика [в Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell)конечному пользователю потребуется использовать для идентификации сообщений комлет [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) с общим почтовым адресом для значения параметра _RecipientAddress._</span><span class="sxs-lookup"><span data-stu-id="faebf-130">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="faebf-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="faebf-131">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="faebf-132">Затем конечный пользователь может выбрать карантинное сообщение из списка, чтобы просмотреть или принять меры.</span><span class="sxs-lookup"><span data-stu-id="faebf-132">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="faebf-133">В этом примере показаны все карантинные сообщения, отправленные в общий почтовый ящик, а затем первое сообщение в списке из карантина (первое сообщение в списке — 0, второе — 1 и так далее).</span><span class="sxs-lookup"><span data-stu-id="faebf-133">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="faebf-134">Подробные сведения о синтаксисе и параметрах см. в таких разделах:</span><span class="sxs-lookup"><span data-stu-id="faebf-134">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="faebf-135">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="faebf-135">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="faebf-136">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="faebf-136">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="faebf-137">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="faebf-137">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="faebf-138">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="faebf-138">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
