---
title: Уведомления конечных пользователей о нежелательной почте в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут изучить уведомления о нежелательной почте для конечных пользователей в сообщениях, помещенных в карантин, в Exchange Online Protection (EOP).
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600301"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="e15a6-103">Использование уведомлений о нежелательной почте для освобождения и отправки отчетов о сообщениях, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="e15a6-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e15a6-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e15a6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e15a6-105">Дополнительные сведения см в разделе [сообщения, помещенные в карантин, в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e15a6-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e15a6-106">По умолчанию уведомления о нежелательной почте для конечных пользователей отключаются в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e15a6-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="e15a6-107">Когда администратор [включает уведомления конечных пользователей о нежелательной почте](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), получатели (включая общие почтовые ящики с включенной функцией автосопоставления) будут получать периодические уведомления об их сообщениях, которые были помещены в карантин как спам, Массовая Электронная почта или фишинг (на апрель 2020).</span><span class="sxs-lookup"><span data-stu-id="e15a6-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="e15a6-108">Для общих почтовых ящиков уведомления конечных пользователей поддерживаются только для пользователей, которым предоставлено разрешение FullAccess на доступ к общему почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="e15a6-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="e15a6-109">Дополнительные сведения см. в разделе Использование центра администрирования [Exchange для изменения делегирования общих почтовых ящиков](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="e15a6-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="e15a6-110">Уведомления о нежелательной почте для пользователей не поддерживаются для групп.</span><span class="sxs-lookup"><span data-stu-id="e15a6-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="e15a6-111">Сообщения, помещенные в карантин как высокодостоверные фишингом, вредоносные программы или правила обработки почты (также называемые правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="e15a6-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e15a6-112">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e15a6-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="e15a6-113">Уведомление о нежелательной почте для конечных пользователей содержит следующие сведения для каждого сообщения в карантине:</span><span class="sxs-lookup"><span data-stu-id="e15a6-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="e15a6-114">**Отправитель**: имя и адрес электронной почты для отправки сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="e15a6-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="e15a6-115">**Тема**: текст строки темы сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="e15a6-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="e15a6-116">**Дата**: Дата и время (в формате UTC), когда сообщение было помещено в карантин.</span><span class="sxs-lookup"><span data-stu-id="e15a6-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="e15a6-117">**Блокировать отправителя**: щелкните эту ссылку, чтобы добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="e15a6-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="e15a6-118">Дополнительные сведения [см.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="e15a6-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="e15a6-119">**Выпуск**: сообщения о нежелательной почте (нефишинге) вы можете освободить это сообщение, не открывая центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e15a6-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="e15a6-120">**Обзор**: щелкните эту ссылку, чтобы перейти к карантину в центре безопасности & соответствия требованиям, где вы можете (в зависимости от того, почему сообщение было помещено в карантин) просмотреть, освободить, удалить или сообщить о сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="e15a6-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="e15a6-121">Дополнительные сведения см. [в статье Find and Release messages, помещенных в карантин, в качестве пользователя в EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="e15a6-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Пример уведомления конечного пользователя о нежелательной почте](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="e15a6-123">Заблокированный отправитель по-прежнему может отправлять вам сообщения.</span><span class="sxs-lookup"><span data-stu-id="e15a6-123">A blocked sender can still send you mail.</span></span> <span data-ttu-id="e15a6-124">Все сообщения от этого отправителя, которые делают его в вашем почтовом ящике, будут немедленно перемещены в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="e15a6-124">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="e15a6-125">Последующие сообщения от этого отправителя будут передаваться в папку "Нежелательная почта" или в карантин конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e15a6-125">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="e15a6-126">Если вы хотите удалить эти сообщения по прибытии, а не по их карантину, используйте [правила для обработки почтового процесса](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также называемые правилами транспорта), чтобы удалить сообщения по прибытии.</span><span class="sxs-lookup"><span data-stu-id="e15a6-126">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
