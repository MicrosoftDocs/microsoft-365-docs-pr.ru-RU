---
title: Уведомления конечных пользователей о нежелательной почте в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208553"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="94926-103">Использование уведомлений о нежелательной почте для освобождения и отправки отчетов о сообщениях, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="94926-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="94926-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, на карантине могут быть потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="94926-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="94926-105">Дополнительные сведения см в разделе [сообщения, помещенные в карантин, в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94926-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="94926-106">По умолчанию уведомления о нежелательной почте для конечных пользователей отключаются в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="94926-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="94926-107">Когда администратор [включает уведомления конечных пользователей о нежелательной почте](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), получатели будут получать периодические уведомления об их сообщениях, которые были помещены в карантин как спам, Массовая Электронная почта или фишинг (на апрель 2020).</span><span class="sxs-lookup"><span data-stu-id="94926-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="94926-108">Сообщения, помещенные в карантин как высокодостоверные фишингом, вредоносные программы или правила обработки почты (также называемые правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="94926-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="94926-109">Дополнительные сведения см. [в статье Manage a карантинных сообщений и файлов в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="94926-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="94926-110">Уведомление о нежелательной почте для конечных пользователей содержит следующие сведения для каждого сообщения в карантине:</span><span class="sxs-lookup"><span data-stu-id="94926-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="94926-111">**Отправитель**: имя и адрес электронной почты для отправки сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="94926-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="94926-112">**Тема**: текст строки темы сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="94926-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="94926-113">**Дата**: Дата и время (в формате UTC), когда сообщение было помещено в карантин.</span><span class="sxs-lookup"><span data-stu-id="94926-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="94926-114">**Блокировать отправителя**: щелкните эту ссылку, чтобы добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="94926-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="94926-115">Дополнительную информацию можно узнать [в статье блокировка отправителя почты в Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="94926-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="94926-116">**Выпуск**: сообщения о нежелательной почте (нефишинге) вы можете освободить это сообщение, не открывая центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="94926-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="94926-117">**Рецензирование**: щелкните эту ссылку, чтобы перейти к карантину в центре безопасности & соответствия требованиям, в котором можно выпустить, удалить или сообщить о сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="94926-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="94926-118">Дополнительные сведения см. [в статье Find and Release messages, помещенных в карантин, в качестве пользователя в EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="94926-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Пример уведомления конечного пользователя о нежелательной почте](../../media/end-user-spam-notification.png)
