---
title: Уведомления конечного пользователя о нежелательной почте в Microsoft 365
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
description: Администраторы могут узнать о том, какие уведомления о нежелательной почте в сообщениях, помещенных в карантин, в Exchange Online Protection (EOP) в этом разделе.
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827365"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="8455b-103">Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них</span><span class="sxs-lookup"><span data-stu-id="8455b-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="8455b-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="8455b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="8455b-105">Дополнительные сведения см. в статье "Сообщения в [карантине" в службе EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8455b-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8455b-106">По умолчанию уведомления конечных пользователей о нежелательной почте отключены в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8455b-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="8455b-107">Если администратор включает [уведомления пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)о нежелательной почте, получатели (в том числе общие почтовые ящики с поддержкой AutoMapping) будут периодически получать уведомления о сообщениях, помещенных в карантин как спам, массовая рассылка или фишинг (по состоянию на апрель 2020 г.).</span><span class="sxs-lookup"><span data-stu-id="8455b-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="8455b-108">Для общих почтовых ящиков уведомления конечного пользователя о спаме поддерживаются только для пользователей, которым предоставлено разрешение на полный доступ к этому почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="8455b-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="8455b-109">Дополнительные сведения см. в статье ["Изменение делегирования для общего почтового ящика" в Центре администрирования Exchange.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="8455b-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="8455b-110">Уведомление о нежелательной почте для групп не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8455b-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="8455b-111">Сообщения, которые были помещены в карантин в карантин в виде фишинга с высоким уровнем вероятности, вредоносных программ или правил потока обработки почты (также называемых правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="8455b-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="8455b-112">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="8455b-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="8455b-113">Уведомление конечного пользователя о нежелательной почте содержит следующие сведения о каждом сообщении, помещенном на карантин:</span><span class="sxs-lookup"><span data-stu-id="8455b-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="8455b-114">**Отправитель**— имя отправки и адрес электронной почты помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="8455b-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="8455b-115">**Subject**— текст в строке темы помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="8455b-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="8455b-116">**Дата:** дата и время (в формате UTC) помещения сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="8455b-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="8455b-117">**Заблокировать отправителя:** щелкните эту ссылку, чтобы добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="8455b-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="8455b-118">Дополнительные сведения см. в статье, [посвященной блокированию отправителя почтовой почты.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="8455b-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="8455b-119">**Выпуск:** для нежелательных (не фишинговых) сообщений можно освободить его, не переходя в Центр безопасности & требованиям.</span><span class="sxs-lookup"><span data-stu-id="8455b-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="8455b-120">**Просмотр:** щелкните эту ссылку, чтобы перейти к пункту "Карантин" в Центре соответствия требованиям безопасности &, где можно (в зависимости от того, почему сообщение было помещено в карантин), освобождать или сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="8455b-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="8455b-121">Дополнительные сведения см. в статье "Поиск [и освобождение сообщений на карантине для пользователя в EOP".](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="8455b-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Примеры уведомлений пользователя о нежелательной почте](../../media/end-user-spam-notification.png)
