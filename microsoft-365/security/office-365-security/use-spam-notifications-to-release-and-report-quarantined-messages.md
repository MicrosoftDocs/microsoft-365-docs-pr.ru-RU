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
description: Администраторы могут узнать о уведомлениях пользователей о нежелательной почте для сообщений в карантине в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287549"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="c3819-103">Использование уведомлений пользователей о нежелательной почте для освобождения сообщений в карантине и их отчетов</span><span class="sxs-lookup"><span data-stu-id="c3819-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3819-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c3819-104">**Applies to**</span></span>
- [<span data-ttu-id="c3819-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3819-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3819-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c3819-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c3819-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3819-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c3819-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="c3819-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="c3819-109">Дополнительные сведения см. в сообщении на [карантине в EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c3819-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="c3819-110">По умолчанию уведомления пользователей о нежелательной почте отключены в политиках борьбы с нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="c3819-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="c3819-111">Когда администратор включает уведомления конечных пользователей о нежелательной [почте,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)получатели (включая общие почтовые ящики с включенной поддержкой автомагистрали) будут периодически получать уведомления о своих сообщениях, которые были отправлены на карантин как спам, массовая рассылка или (в апреле 2020 г.) фишинг.</span><span class="sxs-lookup"><span data-stu-id="c3819-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="c3819-112">Для общих почтовых ящиков уведомления конечных пользователей о нежелательной почте поддерживаются только для пользователей, которым предоставлено разрешение fullAccess для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c3819-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="c3819-113">Дополнительные сведения см. в сообщении Об использовании [EAC для изменения делегирования общих почтовых ящиков.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="c3819-113">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="c3819-114">Уведомления пользователей о нежелательной почте не поддерживаются для групп.</span><span class="sxs-lookup"><span data-stu-id="c3819-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="c3819-115">Сообщения, которые были отправлены на карантин как фишинг с высокой достоверности, вредоносные программы или правила потока почты (также известные как правила транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="c3819-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="c3819-116">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c3819-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="c3819-117">Уведомление пользователя о нежелательной почте содержит следующие сведения для каждого сообщения в карантине:</span><span class="sxs-lookup"><span data-stu-id="c3819-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="c3819-118">**Отправитель:** имя отправки и адрес электронной почты сообщения, отправленного в карантин.</span><span class="sxs-lookup"><span data-stu-id="c3819-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="c3819-119">**Тема:** текст строки темы сообщения в карантине.</span><span class="sxs-lookup"><span data-stu-id="c3819-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="c3819-120">**Date**: The date and time (in UTC) that the message was quarantined.</span><span class="sxs-lookup"><span data-stu-id="c3819-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="c3819-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span><span class="sxs-lookup"><span data-stu-id="c3819-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="c3819-122">Дополнительные сведения см. в сообщении [Block a mail sender.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="c3819-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="c3819-123">**Release**: для нежелательных (не фишинговых) сообщений вы можете освободить это сообщение здесь, не переходить на карантин Центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c3819-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="c3819-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span><span class="sxs-lookup"><span data-stu-id="c3819-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="c3819-125">Дополнительные сведения см. в записи поиска и освобождения сообщений на карантине от пользователя [в EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="c3819-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Пример уведомления пользователя о нежелательной почте](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="c3819-127">Заблокированный отправитель по-прежнему может отправлять вам почту.</span><span class="sxs-lookup"><span data-stu-id="c3819-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="c3819-128">Все сообщения от этого отправитель, которые будут отправлены в ваш почтовый ящик, будут немедленно перемещены в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c3819-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="c3819-129">Последующие сообщения от этого отправитель будут перенаправлены в папку нежелательной почты или в карантин пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3819-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="c3819-130">Если вы хотите удалить эти сообщения при поступлении, а не на карантин, используйте правила потока почты [(также](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) известные как правила транспорта) для удаления сообщений при их поступлении.</span><span class="sxs-lookup"><span data-stu-id="c3819-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
