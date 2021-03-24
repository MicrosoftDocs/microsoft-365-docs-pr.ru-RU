---
title: Уведомления о нежелательной почте конечных пользователей в Microsoft 365
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
description: Администраторы могут узнать о уведомлениях о нежелательной почте конечных пользователей для карантинов в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069902"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="bb181-103">Использование уведомлений о нежелательной почте пользователей для выпуска и сообщения с карантином</span><span class="sxs-lookup"><span data-stu-id="bb181-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bb181-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="bb181-104">**Applies to**</span></span>
- [<span data-ttu-id="bb181-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bb181-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bb181-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="bb181-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bb181-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb181-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bb181-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="bb181-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="bb181-109">Дополнительные сведения см. в сообщении о карантине в [EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="bb181-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="bb181-110">По умолчанию уведомления о нежелательной почте конечных пользователей отключены в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="bb181-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="bb181-111">Когда администратор включает уведомления о нежелательной почте конечного [пользователя,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)получатели (включая общие почтовые ящики с включенной автоматической поддержкой) будут получать периодические уведомления о своих сообщениях, которые были карантинными, как спам, массовые сообщения электронной почты или (по апрель 2020 г.) фишинг.</span><span class="sxs-lookup"><span data-stu-id="bb181-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="bb181-112">Для общих почтовых ящиков уведомления о нежелательной почте конечных пользователей поддерживаются только для пользователей, которым предоставлено разрешение FullAccess для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="bb181-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="bb181-113">Дополнительные сведения см. в [разделЕ Использование EAC для редактирования делегирования общих почтовых ящиков.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="bb181-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="bb181-114">Уведомление о нежелательной почте конечных пользователей не поддерживается для групп.</span><span class="sxs-lookup"><span data-stu-id="bb181-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="bb181-115">Сообщения, которые были на карантине в качестве высокой уверенности в фишинге, вредоносных программах или правилах потока почты (также известные как правила транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="bb181-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="bb181-116">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bb181-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="bb181-117">Уведомление о нежелательной почте от конечных пользователей содержит следующие сведения для каждого сообщения, содержаного на карантине:</span><span class="sxs-lookup"><span data-stu-id="bb181-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="bb181-118">**Отправитель.** Имя отправки и адрес электронной почты на карантин.</span><span class="sxs-lookup"><span data-stu-id="bb181-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="bb181-119">**Тема.** Текст строки темы в карантинном сообщении.</span><span class="sxs-lookup"><span data-stu-id="bb181-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="bb181-120">**Дата.** Дата и время (в UTC), когда сообщение было на карантине.</span><span class="sxs-lookup"><span data-stu-id="bb181-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="bb181-121">**Блок отправитель.** Щелкните эту ссылку, чтобы добавить отправитель в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="bb181-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="bb181-122">Дополнительные сведения см. [в сообщении Block a mail sender.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="bb181-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="bb181-123">**Выпуск.** Для сообщений о нежелательной почте (не фишинга) вы можете освободить это сообщение здесь, не заехав на карантин центра & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bb181-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="bb181-124">**Обзор.** Щелкните эту ссылку, чтобы перейти к карантину в Центре соответствия требованиям безопасности &, где можно (в зависимости от причины карантина сообщения) просмотреть, освободить, удалить или сообщить о своих карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="bb181-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="bb181-125">Дополнительные сведения см. в [сообщении Find and release quarantined messages as a user in EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="bb181-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Пример уведомления о нежелательной почте для конечных пользователей](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="bb181-127">Заблокированный отправитель по-прежнему может отправлять вам почту.</span><span class="sxs-lookup"><span data-stu-id="bb181-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="bb181-128">Любые сообщения от этого отправитель, которые будут отправлены в почтовый ящик, будут немедленно перемещены в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bb181-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="bb181-129">Будущие сообщения от этого отправщика будут отправляться в папку нежелательной почты или в карантин для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb181-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="bb181-130">Если вы хотите удалить эти сообщения по прибытии, а не на карантин, используйте правила потока почты [(также](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) известные как правила транспорта), чтобы удалить сообщения по прибытии.</span><span class="sxs-lookup"><span data-stu-id="bb181-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>