---
title: Уведомления конечных пользователей о нежелательной почте в Office 36
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
description: Когда администратор включает уведомления конечного пользователя о нежелательной почте в политиках защиты от нежелательной почты, получатели сообщения будут получать периодические уведомления о сообщениях, помещенных в карантин.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857154"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="839ec-103">Уведомления конечных пользователей о нежелательной почте в Office 365</span><span class="sxs-lookup"><span data-stu-id="839ec-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="839ec-104">Карантин содержит потенциально опасные или нежелательные сообщения в организациях Office 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange</span><span class="sxs-lookup"><span data-stu-id="839ec-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="839ec-105">Дополнительные сведения см в разделе [Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="839ec-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="839ec-106">По умолчанию уведомления о нежелательной почте для конечных пользователей отключаются в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="839ec-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="839ec-107">Когда администратор [включает уведомления конечных пользователей о нежелательной почте](configure-your-spam-filter-policies.md), получатели сообщений будут получать периодические уведомления о сообщениях, помещенных в карантин, массовой рассылке или (на апрель, 2020).</span><span class="sxs-lookup"><span data-stu-id="839ec-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="839ec-108">В октябре 2019 мы удалили возможность освобождать сообщения, помещенные в карантин, непосредственно из уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="839ec-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="839ec-109">Вместо этого пользователи могут перейти в центр безопасности Office 365 &, чтобы освободить сообщения, помещенные в карантин (либо напрямую, либо нажав кнопку **Просмотр** в уведомлении).</span><span class="sxs-lookup"><span data-stu-id="839ec-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="839ec-110">Дополнительные сведения см. [в статье Поиск и освобождение сообщений, помещенных в карантин, в качестве пользователя в Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="839ec-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="839ec-111">Сообщения, помещенные в карантин как высокодостоверные фишингом, вредоносные программы или правила обработки почты (также называемые правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="839ec-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="839ec-112">Дополнительные сведения см. [в статье Поиск и освобождение сообщений, помещенных в карантин, в качестве администратора в Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="839ec-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="839ec-113">Уведомление о нежелательной почте для конечных пользователей содержит следующие сведения для каждого сообщения в карантине:</span><span class="sxs-lookup"><span data-stu-id="839ec-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="839ec-114">**Отправитель**: имя и адрес электронной почты для отправки сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="839ec-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="839ec-115">**Тема**: текст строки темы сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="839ec-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="839ec-116">**Дата**: Дата и время (в формате UTC), когда сообщение было помещено в карантин.</span><span class="sxs-lookup"><span data-stu-id="839ec-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="839ec-117">**Блокировать отправителя**: щелкните эту ссылку, чтобы добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="839ec-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="839ec-118">**Обзор**: щелкните эту ссылку, чтобы перейти к карантину в центре безопасности & соответствия требованиям, в котором можно выпустить, удалить или сообщить о сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="839ec-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Пример уведомления конечного пользователя о нежелательной почте](../../media/end-user-spam-notification.png)
